Config Settings
===================

Assets checks for several config settings in system/expressionengine/config/config.php, which give you control over various aspects of its behavior.

``assets_allow_indexing``
    If set to ``yes``, ``y`` or ``1``, any user with access to Assets will be able to access source indexing, not only superadmins.

``assets_cache_remote_images``
    Whether Assets should cache the images stored on Amazon S3, Rackspace Cloud Storage, and Google Cloud Files, to speed up the creation of thumbnails. (Default is ``'yes'``.)

``assets_cp_path``
    The path Assets should prepend to your EE upload directory paths in the event that they are relative from the CP but not from index.php.

    This should be a relative path from your index.php file to the direcotry that you access the CP from (e.g. “``./system/``”).

``assets_ignore_file_patterns``
    An array of regular expressions that describe file names that should be excluded from indexing. These are also taken into account when uploading and renaming files.

``assets_ignore_folder_patterns``
    An array of regular expressions that describe folder names that should be excluded from indexing. These are also taken into account when creating or renaming subfolders.

``assets_recent_upload_hours``
    The number of hours back Assets should look for recently uploaded files. (Default is ``24``.)

``assets_show_modified_date``
    If set to ``TRUE``, a Date Modified column will be shown in List view.

``assets_site_url``
    The URL that Assets should route its Ajax requests to. (By default Assets will use the URL defined in the Admin → General Administration → “URL to the root directory of your site” setting.)

    This is useful if your .htaccess file is redirecting Assets’ Ajax requests, thus dropping their POST data and preventing Assets from functioning properly. Setting it to “``/index.php`` is usually a safe way around that.

``assets_source_settings``
    Overrides Amazon S3, Rackspace Cloud Storage, and Gogole Cloud Files source settings.

    The syntax of this setting is the same as EE’s `upload_preferences <http://ellislab.com/expressionengine/user-guide/cp/content/files/file_upload_preferences.html#overriding-upload-paths-and-urls-using-configuration-variables>`_ config setting.

    The available setting keys are:

        * Amazon S3 and Google Cloud Files
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

        * Rackspace Cloud
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

``assets_use_uncompressed_js``
    Whether Assets should serve uncompressed Javascript files. (Default is ``false``).
