.. _fwflag_max_tagcloud_words:
====================
--max_tagcloud_words
====================
Switch
======

--max_tagcloud_words

Description
===========

Specify the maximum number of words to appear in a tagcloud.

Argument and Default Value
==========================

Integer value. Default value is 100.

Details
=======Contents [hide]Switch
Description
    Argument and Default Value
    
Other Switches
==============
    
Example Commands
================
.. code:doc:`fwflag_block`:: python
Switch

:doc:`fwflag_max_tagcloud_words` 
Description

Specify the maximum number of words to appear in a tagcloud.   

Argument and Default Value

Integer value. Default value is 100. 


Other Switches
==============

Required Switches:
:doc:`fwflag_tagcloud` 
Example Commands
================
.. code:doc:`fwflag_block`:: python


 # Example command correlating county level outcomes with PA twitter data, using Facebook topics and controlling for region
 ./fwInterface.py :doc:`fwflag_d` paHealth :doc:`fwflag_t` msgsPA_2012 :doc:`fwflag_c` cnty \ 
 :doc:`fwflag_f` 'feat$1gram$msgsPA_2012$cnty$16to16' :doc:`fwflag_outcome_table` outcome_data_with_controls \ 
 :doc:`fwflag_outcomes` diab_perc HIV_rate PAAM_age_adj_mort IM_rate CM_rate food_insec_perc LATHF_perc MV_mort_rate DP_mort_rate \ 
 :doc:`fwflag_tagcloud` :doc:`fwflag_make_wordclouds`  \ 
 :doc:`fwflag_output_name` /localdata/paHealth/d6 :doc:`fwflag_controls` 'new_england' 'midatlantic' 'south' 'midwest' 'southwest' 'west' \ 
 :doc:`fwflag_max_tagcloud_words` 25