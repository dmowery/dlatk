.. _fwflag_outcome_controls:
==================
--outcome_controls
==================
Switch
======

--outcome_controls <Field1> <Field2> ... 
(alias: --controls)

Description
===========

Generate correlations for --outcomes like the default --correlate while controlling for other variables.

Argument and Default Value
==========================

List fields from the outcome table that should be used as controls in the linear regression.

Details
=======

These values are generated by using least squares linear regression.
For each feature/outcome pair, we normalize all variables, including feature group norms, control variables and outcome variables by subtracting the mean and dividing by the standard deviation, thus creating a data distribution that has a mean of zero and a standard deviation of 1.  We then create a linear model that predicts the outcome value based on the feature group norms, and control variables.
B0 + B1*F + B2*C = predicted O
From this model, the B2 is the value that shows up in the r matrix.

Or in the words of Patrick...

The simplest way (i.e., to get a Pearson correlation between a continuous outcome and some language variable, like normed topic use) is to run a multiple linear regression:


where  is the intercept, and  is the group_norm of the language feature.

When every variable is normalized (which it is here), the regression coefficient b1 is mathematically equivalent to a Pearson r between outcome and the language variable.


Other Switches
==============

Required Switches:
:doc:`fwflag_outcomes` :doc:`fwflag_outcome_table` Optional Switches:
:doc:`fwflag_group_freq_thresh` :doc:`fwflag_outcome_interaction` 
Example Commands
================
.. code:doc:`fwflag_block`:: python


 # Correlates 1grams with age for every user
 ./fwInterface.py :doc:`fwflag_d` twitterGH :doc:`fwflag_t` messages_en :doc:`fwflag_c` cty_id :doc:`fwflag_group_freq_thresh` 100 \ 
 :doc:`fwflag_f` 'feat$cat_moralFoundations$messages_en$cty_id$16to16' :doc:`fwflag_outcome_table` countyVotingSM2 \ 
 :doc:`fwflag_outcomes` Median_Age Rpercent_2008 overall_LS population_density percent_white percent_bachelors \ 
 :doc:`fwflag_outcome_controls` log_mean_income  :doc:`fwflag_output_name` morals2demog_ctrinc :doc:`fwflag_rmatrix` :doc:`fwflag_sort` 