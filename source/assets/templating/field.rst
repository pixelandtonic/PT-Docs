Field Tags
==========

The following tags are available for your Assets fields within ``{exp:channel:entries}`` tag pairs.


Primary Tag Pair
----------------

The Primary Tag Pair will loop through each of your selected files, outputting whatever data you need from them.

.. code-block:: html

	{my_assets_field}
	    <li><a href="{url}" alt="{alt_text}">{filename}</a></li>
	{/my_assets_field}


Tag Parameters
~~~~~~~~~~~~~~

The Primary Tag Pair supports the following parameters:

.. include:: /templating/_includes/file_field_params.rst


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within your primary tag pair:

.. include:: /templating/_includes/file_variables.rst


Shortcut Tags
-------------

If you just want to get data about a single file within your Assets field, you can use a shortcut tag instead of the tag pair. They support the same parameters as the primary tag pair.

.. code-block:: html

    <h1>
      {if '{my_assets_field:title}'}
        {my_assets_field:title}
      {if:else}
        {my_assets_field:filename}
      {/if}
    </h1>

The following shortcut tags are available:

-  ``{my_assets_field:url}``
-  ``{my_assets_field:server_path}``
-  ``{my_assets_field:subfolder}``
-  ``{my_assets_field:filename}``
-  ``{my_assets_field:extension}``
-  ``{my_assets_field:date_modified}``
-  ``{my_assets_field:kind}``
-  ``{my_assets_field:width}``
-  ``{my_assets_field:height}``
-  ``{my_assets_field:size}`` – The formatted file size (e.g. “20 KB”)
-  ``{my_assets_field:size unformatted="yes"}`` – The file size in bytes
-  ``{my_assets_field:file_id}``
-  ``{my_assets_field:title}``
-  ``{my_assets_field:date}``
-  ``{my_assets_field:alt_text}``
-  ``{my_assets_field:caption}``
-  ``{my_assets_field:author}``
-  ``{my_assets_field:desc}``
-  ``{my_assets_field:location}``
-  ``{my_assets_field:total_files}``

Image Manipulation Shortcut Tags
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

You can also access image manipulation properties using the following
shortcut tags:

-  ``{my_assets_field:url:my_manipulation}``
-  ``{my_assets_field:server_path:my_manipulation}``
-  ``{my_assets_field:width:my_manipulation}``
-  ``{my_assets_field:height:my_manipulation}``
-  ``{my_assets_field:size:my_manipulation}``
