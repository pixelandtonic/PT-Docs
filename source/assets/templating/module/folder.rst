``{exp:assets:folder}``
========================

You can use the ``{exp:assets:folder}`` tag pair to get information about a folder managed by Assets.

.. code-block:: html

    <ul>
        {exp:assets:folder folder_id="{segment_4}"}
            <li>
                <a href="{path=assets/view/{folder_id}}">{folder_name}</a>
            </li>
        {/exp:assets:folder}
    </ul>

Tag Parameters
--------------

``{exp:assets:folders}`` supports the following parameters:

``folder``
    The path of the folder whose information you wish to output.
    Set this parameter in the format of either
    “``{filedir_X}optional/subfolder/path``” or
    “``{source_X}optional/subfolder/path``”.

``folder_id``
    The ID of the folder whose information you wish to output. 
    The ``folder_id`` parameter takes precedence and at least one of them is required.

Variable Tags
-------------

``{exp:assets:folders}`` supports the following variable tags:

``{folder_id}``
	The ID that Assets has assigned to the current folder.

``{folder_name}``
	The name of the current folder.

``{parent_id}``
    The ID of the current folder's parent folder.
