``assets_rename_file`` Hook
========================

This hook is called before renaming the file.

Hook Parameters
---------------

``$file``
    An object extending ``Assets_base_file`` class for the file that is about to be replaced.

``$file_name``
    The file name that the file will be renamed to.

**Notes**

This hook is fired only if a file of the new name does not exist in the folder - in other words, it is guaranteed, that the file will be renamed. If a conflict exists, the appropriate hook will be fired only after the conflict resolution.