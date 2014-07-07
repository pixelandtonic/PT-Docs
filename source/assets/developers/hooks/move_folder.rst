``assets_move_folder`` Hook
=============================

This hook is called right before moving a folder in Assets. 

Hook Parameters
---------------

``$folder_row``
    An StdClass object, representing the folder row that is about to get moved.

``$new_parent_row``
    An StdClass object, representing the folder row that will be the new parent of the moved folder.

**Notes**

If the folder being moved has files in it, the ``assets_move_file`` hook will be called for each file.