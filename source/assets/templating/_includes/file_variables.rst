.. rst-class:: collapsible

``{url}``
    The URL to the file.

    ``{url:manipulation_name}`` is also available, for outputting the URL to an image manipulation.

``{server_path}``
    The server path to the file.

    ``{server_path:manipulation_name}`` is also available, for outputting the server path to an image manipulation.

``{subfolder}``
    The subfolder that the file lives in, if any.

``{source_subfolder}``
    The value of the Subfolder setting on the file’s source, if there is one.

``{folder_id}``
    Id of the folder containing the file.

``{source_id}``
    Id of the source containing the file.

``{filename}``
    The name of the file, sans-extension.

``{extension}``
    The file extension.

``{date_modified}``
    The date/time that the file was last modified. Supports the `format <http://ellislab.com/expressionengine/user-guide/templates/date_variable_formatting.html>`_ parameter.

``{kind}``
    The kind of file it is. Possible values are:

    .. include:: /templating/_includes/file_kinds.rst

``{width}``
    The width of the image.

    ``{width:manipulation_name}`` is also available, for outputting the width of an image manipulation.

``{height}``
    The height of the image.

    ``{height:manipulation_name}`` is also available, for outputting the height of an image manipulation.

``{size}``
    The formatted size of the file (e.g. “20 KB”). You can also pass ``unformatted="yes"`` to get the raw file size in bytes.

    ``{size:manipulation_name}`` is also available, for outputting the file size of an image manipulation.

``{file_id}``
    The ID of the file (based on the ``id`` column in the exp_assets_files table).

``{title}``
    The value of the file’s Title metadata field.

``{date}``
    The value of the file’s Date metadata field. Supports the `format <http://ellislab.com/expressionengine/user-guide/templates/date_variable_formatting.html>`_ parameter.

``{alt_text}``
    The value of the file’s Alt Text metadata field.

``{caption}``
    The value of the file’s Caption metadata field.

``{author}``
    The value of the file’s Author/Credit/Producer metadata field.

``{desc}``
    The value of the file’s Description metadata field.

``{location}``
    The value of the file’s Location metadata field.

``{total_files}``
    The total number of files being output.
