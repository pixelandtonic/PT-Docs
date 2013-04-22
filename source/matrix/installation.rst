Installing and Updating
=======================

Requirements
-------------

Make sure your system meets the minimum requirements:

-  `ExpressionEngine <http://ellislab.com/expressionengine/>`_ 2.4 or later


Installing Matrix
-----------------

#. Upload the ee2/third_party/matrix folder to system/expressionengine/third_party/
#. Upload the themes/third_party/matrix folder to themes/third_party/
#. Install the fieldtype in Add-Ons → Fieldtypes
#. While installing, choose to install the extension as well
#. Ensure that Extensions are enabled in Add-Ons → Extensions


Updating Matrix
---------------

Updating from an earlier version of Matrix 2
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

#. Upload the ee2/third_party/matrix folder to system/expressionengine/third_party/, overwriting the old one
#. Upload the themes/third_party/matrix folder to themes/third_party/, overwriting the old one
#. Go to Add-Ons → Fieldtypes → Matrix to trigger Matrix’s update script.
#. Clear your browser’s cache

Upgrading from EE1
~~~~~~~~~~~~~~~~~~

If you are upgrading a site from EE1 to EE2 that has an FF Matrix 1.x or Matrix 2.x field, upgrade EE first, and then simply install Matrix per the `instructions <#installing-matrix>`_. You won’t need to worry about converting your fields or uninstalling the old fieldtype in the CP; Matrix manages all of that for you when you install it.

**Note:** It is highly recommended that you backup your database before upgrading to Matrix 2. But you did that already for the EE upgrade anyway, right?
