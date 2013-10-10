``assets_move_file`` Hook
========================

This hook is called before moving the file.

Hook Parameters
---------------

``$file``
    An object extending ``Assets_base_file`` class for the file that is about to be moved.

``$folder_row``
    An StdClass object representing the new parent folder row the file is being move to.

``$file_name``
    The file name that the file will be renamed to.

**Notes**

This hook is fired only if a file of the new name does not exist in the target folder - in other words, it is guaranteed, that the file will be moved. If a conflict exists, the appropriate hook will be fired only after the conflict resolution.