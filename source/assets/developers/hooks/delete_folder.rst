``assets_delete_folder`` Hook
========================

This hook is called right before deleting a folder in Assets. 

Hook Parameters
---------------

``$folder_row``
    An StdClass object, representing the folder row that is about to get delete.

**Notes**

When deleting a folder, it's files are deleted first (each triggering a call to ``assets_delete_file`` hook) and then it's subfolders are deleted (triggering ``assets_delete_folder`` recursively) and only then is this hook called. That means that, when this hook is called, the folder in question is already empty of any files and subfolders.