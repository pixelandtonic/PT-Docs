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

.. include:: /templating/_includes/file_params.rst

``orderby``
    Order the files by a property or metadata value. Pair with the
    ``sort`` parameter to control the sort order.

``sort``
    Sort the files in ascending or descending order (“``asc``” and
    “``desc``”, respectively), by the property/metadata specified in
    the ``orderby`` parameter.

    If the ``orderby`` parameter was not set, ``sort="desc"`` will
    simply reverse the author-defined order of the files, and
    ``sort="random"`` will randomize the order of the files.

    .. code-block:: html

        {my_assets_field orderby="title|kind|date" sort="asc|asc|desc"}

``offset``
    Skip the first *X* files

    .. code-block:: html

        {my_assets_field offset="{segment_4}" limit="1"}

``limit``
    Limit the number of files to be returned

    .. code-block:: html

        {my_assets_field limit="3"}

``var_prefix``
    This parameter provides a way to avoid tag name conflicts by
    namespacing each of Assets’ variable tags. So for example, if you
    needed to access your current entry’s Title tag from within an Asset
    field’s tag pair, you could do this:

    .. code-block:: html

        {my_assets_field var_prefix="file"}
          <a href="{file:url}">{title} - {file:title}</a>
        {/my_assets_field}

    **Note**: The ``{count}`` tag won’t be affected by this parameter.

``backspace``
    Strip the last *X* characters from the tag output

    .. code-block:: html

        {my_assets_field backspace="2"}{filename}, {/my_assets_field}


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
