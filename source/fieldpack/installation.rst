Installing and Updating
=======================


Requirements
-------------

Make sure your system meets the minimum requirements:

-  `ExpressionEngine <http://expressionengine.com/>`_ 2.6 or later


Installing Field Pack
---------------------

#. Upload the ee2/third_party/fieldpack folder to system/expressionengine/third_party/
#. Upload the themes/third_party/fieldpack folder to themes/third_party/
#. Go to Add-Ons → Fieldtypes and install whichever fieldtypes you want. Field Pack fieldtypes will be prefixed with “Field Pack”.


Updating Field Pack
-------------------

Updating from an earlier version of Field Pack 2
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. Upload the ee2/third_party/fieldpack folder to
   system/expressionengine/third_party/, overwriting the old one
#. Upload the themes/third_party/fieldpack folder to themes/third_party/,
   overwriting the old one
#. Clear your browser’s cache


Updating from the old Dive Bar fieldtypes
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Field Pack is the successor to seven separate add-ons, availabe from the old P&T Dive Bar:

* P&T Field Pack

  * P&T Checkboxes
  * P&T Dropdown
  * P&T Multiselect
  * P&T Radio Buttons

* P&T List
* P&T Pill
* P&T Switch

If you have any of these installed already, simply install Field Pack 2 per the `instructions <#installing-field-pack>`_, and then delete the old files. You won’t need to worry about converting your fields or uninstalling each of the old fieldtypes in the CP; Field Pack 2 manages all of that for you when you install the new fieldtypes.

Here are all of the folders that are safe to delete once Field Pack 2 is installed:

 * system/expressionengine/third_party/pt_checkboxes
 * system/expressionengine/third_party/pt_dropdown
 * system/expressionengine/third_party/pt_field_pack
 * system/expressionengine/third_party/pt_list
 * system/expressionengine/third_party/pt_multiselect
 * system/expressionengine/third_party/pt_pill
 * system/expressionengine/third_party/pt_radio_buttons
 * system/expressionengine/third_party/pt_switch
 * themes/third_party/pt_list
 * themes/third_party/pt_pill
 * themes/third_party/pt_switch

 If you're using Expression Engine 2.7 or later, you might have to delete these folders before you're able to install the Field Pack 2. Don't worry, though - you will not lose your data!
