Installing and Updating
=======================

Requirements
-------------

Make sure your system meets the minimum requirements:

-  `ExpressionEngine <http://ellislab.com/expressionengine/>`_ 2.4 or
   later
-  If you will be using cloud based services with Assets (Amazon S3,
   Rackspace Cloud Files, Google Cloud Storage), you will need the
   `PHP cURL extension <http://us1.php.net/curl>`_ and
   `libcurl <http://curl.haxx.se/libcurl/>`_ installed

Installing Assets
-----------------

#. Upload the ee2/third_party/assets folder to
   system/expressionengine/third_party/
#. Upload the themes/third_party/assets folder to themes/third_party/
#. Install the module in Add-Ons → Modules
#. While installing, choose to install the fieldtype and extension as
   well

Updating Assets
---------------

#. Upload the ee2/third_party/assets folder to
   system/expressionengine/third_party/, overwriting the old one
#. Upload the themes/third_party/assets folder to themes/third_party/,
   overwriting the old one
#. If you’re coming from Assets 1.0.x, go to Add-Ons → Extensions, and
   enable Assets’ extension
#. Go to Add-Ons → Modules and click the “Run Module Updates” button
#. Clear your browser’s cache

**Note**: If you want to update Assets using DevDemon Updater, make sure
that you have Updater 3.1.6 or later.
