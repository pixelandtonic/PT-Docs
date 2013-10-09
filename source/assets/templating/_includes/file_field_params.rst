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