Config Settings
===================

Source settings
-----------------

You can use ``assets_source_settings`` to override any external source settings set in the CP. The following options are available.

Amazon S3 and Google Cloud
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

``access_key_id`` and ``secret_access_key``
    Amazon S3 or Google Cloud key pair to connect to your account.

``bucket``
    The bucket to use.

``location`` 
    The region for the bucket.

``url_prefix``
    URL Prefix to use.

``subfolder``
    Subfolder to use for your source.

Rackspace Cloud
~~~~~~~~~~~~~~~~~~

``username`` and ``api_key``
    Amazon S3 or Google Cloud key pair to connect to your account.

``container``
    The container to use.

``location`` 
    The account location to use.

``url_prefix``
    URL Prefix to use.

``subfolder``
    Subfolder to use for your source.

Recent upload duration
------------------------

``assets_recent_upload_hours``
    This determines the number of hours for Recent Uploads source history.

Javascript compression
--------------
``assets_use_uncompressed_js``
    Settings this to ``true`` will make Assets use the uncompressed version of it's Javascripts, which is useful for debugging issues.

Site URL
--------------

``assets_site_url``
    This setting is used for routing Assets Ajax requests, in case the Site Root URL setting should not be used. For example, if a .htaccess redirect is taking place, depending on server configuration, that might not forward POST data, so you would set ``assets_site_url`` setting to such a value, that it doesn't get redirected.

Control Panel path.
--------------------

``assets_cp_path``
    This setting is used when you are using relative paths in EE Upload Filedir paths. This should point to the folder that contains your admin.php file. This is needed so that Assets can resolve paths for files when it knows only the path of the admin.php file.

Caching remote images
-----------------------

``assets_cache_remote_images``
    By default set to "yes", this makes Assets cache the images from external sources for generating the various sizes used in Assets File manager much faster. Setting this to "no" will cause Assets to download the file every time a new size needs to be created.