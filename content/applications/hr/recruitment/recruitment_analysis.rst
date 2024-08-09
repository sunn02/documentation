====================
Recruitment analysis
====================

Reporting is a helpful tool for a recruitment department so they can see which job positions have
the most applicants, which have the most referrals, or how long it takes for applicants to move
through the pipeline.

Knowing how many applicants each specific job position has, along with the numbers for those hired
and refused, can provide valuable insights. This information can assist the recruiting team to pivot
their strategies, to acquire the most desirable candidates.

Recruitment analysis report
===========================

Start by navigating to :menuselection:`Recruitment app --> Reporting --> Recruitment Analysis`.
This presents a line chart of all applicants for the last year.

Three separate color-coded metrics are presented: :guilabel:`In Progress`, :guilabel:`Hired`, and
:guilabel:`Refused`.

Hover the cursor over a month of the chart and a pop-up window appears, and displays the specific
numbers for that month.

.. image:: recruitment_analysis/line-chart.png
   :align: center
   :alt: The default Recruitment Analysis report.

Pivot table view
----------------

For a more detailed view of the information in the :guilabel:`Recruitment Analysis` report, click
the :icon:`oi-view-pivot` :guilabel:`(Pivot)` icon in the top-right corner. This displays all the
information in a pivot table.

In this view, the job positions are displayed in the rows, and the total numbers of applicants in
their various stages, are the columns.

In this example, there are 17 total applicants. Out of that 17, three have been hired, and four
refused. Each job position lists the specific number of applicants, hired, and refused candidates
for that job position. The :guilabel:`Experienced Developer` position has eight total applicants,
two of which were hired, and two were refused.

.. image:: recruitment_analysis/pivot-view.png
   :align: center
   :alt: The detailed pivot table view.

Applicants with referrals
~~~~~~~~~~~~~~~~~~~~~~~~~

To get a better understanding of how effective the company's :doc:`referral program <../referrals>`
is, the :guilabel:`Recruitment Analysis` report can be modified to show how many applicants were
referred by current employees.

From the :icon:`oi-view-pivot` :guilabel:`(Pivot)` view of the :guilabel:`Recruitment Analysis`
report, first click on the :guilabel:`Measures` drop-down button.

Click both :guilabel:`Has Referrer` and :guilabel:`Count`, to activate those two measures. Then,
click :guilabel:`# Applicant`, :guilabel:`# Hired`, and :guilabel:`# Refused` to deactivate those
default measures.

Now the column displays the number of applicants that came from a referral in the :guilabel:`Has
Referral` column, and the total number of applicants in the :guilabel:`Count` column.

.. image:: recruitment_analysis/referral.png
   :align: center
   :alt: The detailed pivot table view displaying the number of referrals and the total applicants.

In this example, the :guilabel:`Experienced Developer` job position has the most applicants from
referrals. Out of the eight applicants, six have applied through a referral from a current employee.
Meanwhile, the :guilabel:`Marketing and Community Manager` job position has the least amount of
referrals out of the total applicants, only one out of six.

Hired through referrals
***********************

It is possible to modify this report even further to see how many referred applicants end up being
hired.

To view this data, click on a :icon:`fa-plus-square` :guilabel:`(Job Position)` row, which reveals a
drop-down menu. Then, click :guilabel:`State` to show the various states that applicants are
currently in.

.. note::
   Only states that have applicants in it are shown for each job position. If a state does **not**
   have any applicants, it does not appear in the list.

To expand the other rows and display the various states, click on the :icon:`fa-plus-square`
:guilabel:`(Job Position)`.

.. image:: recruitment_analysis/state.png
   :align: center
   :alt: The detailed pivot table view displaying the number of referrals and the total applicants,
         along with how many applicants are in each state.

In this example, the :guilabel:`Experienced Developer` job position is the most successful in terms
of referrals. Both of the hired employees came form internal referrals. Meanwhile, there have been
no hired employees for the :guilabel:`Chief Executive Officer`, and the only hired employee for the
:guilabel:`Marketing and Community Manager` was not referred by an employee.

In this scenario, it is possible to determine that the current software developers are providing the
most referrals, with the highest success rate.
