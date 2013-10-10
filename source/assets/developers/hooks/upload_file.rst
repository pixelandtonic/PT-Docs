``assets_upload_file`` Hook
========================

This hook is called after uploading a file in Assets.

Hook Parameters
---------------

``$file``
    An object extending ``Assets_base_file`` class for the uploaded file.

``$folder_row``
    An StdClass object, representing the parent folder row for the file.

**Notes**

When uploading a file, if the file name is already taken, this hook will still be triggered and the file will be uploaded with ``_X`` suffixed to the end of the file name. If the user then chooses to replace the existing file, this will trigger the ``assets_replace_file`` hook to fire.