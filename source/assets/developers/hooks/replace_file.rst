``assets_replace_file`` Hook
=============================

This hook is called right before replacing a file during a naming conflict in Assets.

Hook Parameters
---------------

``$target_file``
    An object extending ``Assets_base_file`` class for the file that is about to be replaced.

``$new_file``
    An object extending ``Assets_base_file`` class for the file that is about to replace the target file.

**Notes**

When a file is being replaced, it will fire the ``assets_replace_file`` and also the ``asets_delete_file`` hook afterwards.