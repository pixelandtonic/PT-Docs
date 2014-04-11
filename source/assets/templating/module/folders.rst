``{exp:assets:folders}``
========================

You can use the ``{exp:assets:folders}`` tag pair to loop through folders managed by Assets.

.. code-block:: html

    <ul>
        {exp:assets:folders}
            <li>
                <a href="{path=assets/view/{folder_id}}">{folder_name}</a>
                {if total_subfolders}
                    <ul>
                        {subfolders}
                    </ul>
                {/if}
            </li>
        {/exp:assets:folders}
    </ul>

Tag Parameters
--------------

``{exp:assets:folders}`` supports the following parameters:

.. include:: /templating/_includes/folder_params.rst

``offset``
    Skips the first *X* folders

``limit``
    Limits the number of folders to be returned

``sort``
    Sorts the results. Can be set to “``desc``” or “``random``”.


Variable Tags
-------------

``{exp:assets:folders}`` supports the following variable tags:

``{folder_id}``
	The ID that Assets has assigned to the current folder.

``{folder_name}``
	The name of the current folder.

``{depth}``
	The depth of the current folder. Top-level sources’ depth are ‘0’,
	first-level subfolders’ depth are ‘1’, their subfolders’ depth are ‘2’,
	and so on.

``{total_subfolders}``
	The total number of subfolders the current folder has.

``{subfolders}``
	If this tag is present, it will get replaced with the entire
	``{exp:assets:folders}`` tag pair’s template code, including the
	``{subfolders}`` tag. This provides a way to recursively output your
	entire folder tree (see example below).

``{parent_id}
    The ID of the current folder's parent folder.
