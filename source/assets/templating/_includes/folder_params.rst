``parent_folder``
    The path of the parent folder whose subfolders you wish to output.
    Set this parameter in the format of either
    “``{filedir_X}optional/subfolder/path``” or
    “``{source_X}optional/subfolder/path``”.

``parent_id``
    The ID of the parent folder whose subfolders you wish to output.
    If this both this parameter and ``parent_folder`` parameter is omitted, 
    Assets will loop through all of your EE upload directories
    and S3 buckets.

``keywords``
    A pipe-delimited list of keywords to filter the folders by.

``recursive``
    If this is set to “``yes``”, all nested folders will be returned
    as well. (Set to “``no``” by default.)
