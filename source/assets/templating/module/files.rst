``{exp:assets:files}``
======================

You can use the ``{exp:assets:files}`` tag pair to loop through files managed by Assets.

.. code-block:: html

    {exp:assets:folders keywords="drink" recursive="yes"}
        <h3>{folder_name}</h3>
        <ul>
            {exp:assets:files folder_id="{folder_id}"}
                <li><a href="{url:huge}" target="_blank">{if title != ""}{title}{if:else}{filename}{/if}</a></li>
            {/exp:assets:files}
        </ul>
    {/exp:assets:folders}


Tag Parameters
--------------

``{exp:assets:files}`` supports the following parameters:

``folder``
    The path of the folder containing the files you wish to output. Set
    this parameter in the format of either
    “``{filedir_X}optional/subfolder/path``” or
    “``{source_X}optional/subfolder/path``”. You may pass multiple
    IDs, delimited by pipes (‘``|``’). You can also use “any” or “*” to list from all folders.

``folder_id``
    The ID of the folder containing the files you wish to output. You
    may pass multiple IDs, delimited by pipes (‘``|``’).

``keywords``
    Search for files by their metadata values. You may pass multiple values, delimited by pipes (‘``|``’) or double-ampersands (‘``&&``’).

``fixed_order``
    Search for files by their ID in the exp_assets_files table (same as the ``file_id`` param), and output them in the same order as they were entered into the param. You may pass multiple values, delimited by pipes (‘``|``’).

``offset``
    Skips the first *X* files

``limit``
    Limits the number of files to be returned

``orderby``
    Orders the files by a specified property. Possible values include:

    - ``file_id``
    -  ``name``
    -  ``folder``
    -  ``date``
    -  ``size``

``sort``
    Sorts the results. Can be set to “``desc``” or “``random``”.

**Note**: Either the ``folder`` or ``folder_id`` param must be present
for ``{exp:assets:files}`` to output anything.


Variable Tags
-------------

``{exp:assets:files}`` supports the following variable tags:

.. include:: /templating/_includes/file_variables.rst
