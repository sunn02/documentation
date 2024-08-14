
.. _odoosh-advanced-frequent_technical_questions:

============================
Frequent Technical Questions
============================

"Scheduled actions do not run at the exact time they were expected"
-------------------------------------------------------------------

On the Odoo.sh platform, we cannot guarantee an exact running time for scheduled actions.

This is due to the fact that there might be multiple customers on the same server, and we must guarantee a fair share of the server for every customer. Scheduled actions are therefore implemented slightly differently than on a regular Odoo server, and are run on a *best effort* policy.

.. warning::
    Do not expect any scheduled action to be run more often than every 5 min.

Are there "best practices" regarding scheduled actions?
-------------------------------------------------------

**Odoo.sh always limits the execution time of scheduled actions (*aka* crons).**
Therefore, you must keep this fact in mind when developing your own crons.

We advise that:

- Your scheduled actions should work on small batches of records.
- Your scheduled actions should commit their work after processing each batch;
  this way, if they get interrupted by the time-limit, there is no need to start over.
- Your scheduled actions should be
  `idempotent <https://stackoverflow.com/a/1077421/3332416>`_: they must not
  cause side-effects if they are started more often than expected.

How can I automate tasks when an IP address change occurs?
----------------------------------------------------------

**Odoo.sh notifies project administrators of IP modifications.**
Additionally, when the IP address of a production instance changes, a `GET` HTTP request is sent to
the path `/_odoo.sh/ip-change` with the new IP address provided as an `ip` query string argument.

This mechanism allows custom actions to be applied in response to the IP address change
(eg: sending an email, contacting a firewall API, configuring database objects, ...)

For security reasons, the `/_odoo.sh/ip-change` route on the production instance is only accessible
by Odoo.sh itself, returning a `403` error if accessed directly. On other instance stages
(development, staging) the route remains accessible for testing purposes.

Here’s a pseudo implementation example:

.. code-block:: python

    class MyController(http.Controller):

        @http.route('/_odoo.sh/ip-change', auth='public')
        def ip_change(self, ip=None, old=None):
            # The ODOO_STAGE variable allows to protects the action from occurring on a staging
            # or development instance while allowing custom testing scenarios if required.
            if os.getenv('ODOO_STAGE') == 'production':
                _logger.info("IP address changed from %s to %s", old, ip)
                # Then perform whatever action required for your use-case:
                # eg: update an ir.config_paramater, send an email, contact another service, ...
            else:
                _logger.info("Simulation of IP address change from %s to %s", old, ip)
                # Then perform whatever action for testing your use-case (if required)
            return 'ok'
