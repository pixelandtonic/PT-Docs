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

.. include:: /templating/_includes/file_params.rst

``offset``
    Skips the first *X* files

``limit``
    Limits the number of files to be returned

``orderby``
    Orders the files by a specified property. Possible values include:

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