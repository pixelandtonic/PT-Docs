``assets_ee_subfolder_upload`` Hook
=====================================

This hook is called after uploading a file to an EE upload directory's subfolder before the thumbnail creation to give other plugins a chance to modify uploaded images. This is fired only for image uploads.

Hook Parameters
---------------

``$file_path``
    The server path of the image uploaded.
