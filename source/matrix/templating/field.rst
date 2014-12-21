Field Tags
==========

The following tags are available for your Matrix fields within ``{exp:channel:entries}`` tag pairs.


Primary Tag Pair
----------------

To fully customize your Matrix field’s output, use its primary tag pair.

.. code-block:: html

    {my_matrix_field}
        <h2>{speaker_name}</h2>
        <img src="{speaker_photo}" alt="{speaker_name}"/>
        <p>{speaker_description}</p>
    {/my_matrix_field}


Tag Parameters
~~~~~~~~~~~~~~

Matrix’s primary tag pair supports the following tags:

``search``
    Only loop through rows that match a certain criteria. Mimics the parameter for {exp:channel:entries}, and supports comparison operators ``<``, ``>``, ``<=``, and ``>=`` as well.

    .. code-block:: html

        {my_matrix_field search:age=">=16"}

``row_id``
    Only show a specific row by its ID in the exp_matrix_data table.

    .. code-block:: html

        {my_matrix_field row_id="1|2|3"}

    Or prefix with “not” to exclude rows:

    .. code-block:: html

        {my_matrix_field row_id="not 4|5|6"}

``fixed_order``
    Only show specific rows, in a specific order

    .. code-block:: html

        {my_matrix_field fixed_order="3|2|1"}

``orderby``
    Order the rows by their column values.

``sort``
    Specifies how the column values set in ``orderby`` should be sorted. Possible values are “``asc``” and “``desc``”.

    .. code-block:: html

        {my_matrix_field orderby="session_time|session_track" sort="asc|desc"}

    You can also set it to “``random``” to have rows returned in a random order.

``offset``
    Skips the first *X* rows.

``limit``
    Limits the number of rows to be returned.

    .. code-block:: html

        {my_matrix_field offset="5" limit="1"}

``backspace``
    Strips the last *X* characters from the tag output.

    .. code-block:: html

        {my_matrix_field backspace="2"}{speaker_name}, {/my_matrix_field}

``dynamic_parameters``
    Set specific tag parameters “on the fly” using POST data submitted via a form. Mimics the parameter for `{exp:channel:entries} <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#dynamic-parameters>`_.

``var_prefix``
    Tells Matrix to only parse variables that have a certain prefix. This is handy when you’re dealing with variable name conflicts, such as if you’ve got a Matrix field with a Playa column pulling in entries with their own Matrix field:

    .. code-block:: html

        {my_matrix_field var_prefix="spkr"}
            {spkr:favorite_bands} {!-- a Playa column --}
                {albums var_prefix="albm"} {!-- a Matrix field inside the band channel --}
                    {spkr:row_count}.{albm:row_count} - {albm:album_title}
                {/albums}
            {/spkr:favorite_bands}
        {/my_matrix_field}


Variable Tags
~~~~~~~~~~~~~

The following single variables are available within your tag pair:

``{row_id}``
    The current row’s unique ID.

``{row_count}``
    The current row’s count.

``{row_index}``
    The current row’s index. (This is the same as ``{row_count}``, except it starts counting at 0 rather than 1.)

``{total_rows}``
    The total number of rows being returned.

``{field_row_count}``
    The current row’s count within the actual field in the CP, regardless of its position in the current tag output.

``{field_row_index}``
    The current row’s index within the actual field in the CP, regardless of its position in the current tag output. (This is the same as ``{field_row_count}``, except it starts counting at 0 rather than 1.)

``{field_total_rows}``
    The total number of rows in the field in the CP, regardless of how many rows the current tags are outputting.

``{switch}``
    Switch between multiple values based on the current row index.

    .. code-block:: html

        {my_matrix_field}
            <li class="{switch='odd|even'}">
                {row_count} of {total_rows}: {speaker_name}
            </li>
        {/my_matrix_field}

``{prev_row}`` … ``{/prev_row}``
    Access the previous row in the field

    .. code-block:: html

        {gallery row_id="{segment_3}"}
            <h1>{photo_title}</h1>
            <img src="{photo}" alt="{photo_title}" />
            <p>{photo_description}</p>

            {prev_row}<a href="/galleries/{segment_2}/{row_id}">← {photo_title}</a>{/prev_row}
            {if prev_row && next_row} | {/if}
            {next_row}<a href="/galleries/{segment_2}/{row_id}">{photo_title} →</a>{/next_row}
        {/gallery}

``{next_row}`` … ``{/next_row}``
    Access the next row in the field

    .. code-block:: html

        {gallery row_id="{segment_3}"}
            <h1>{photo_title}</h1>
            <img src="{photo}" alt="{photo_title}" />
            <p>{photo_description}</p>

            {prev_row}<a href="/galleries/{segment_2}/{row_id}">← {photo_title}</a>{/prev_row}
            {if prev_row && next_row} | {/if}
            {next_row}<a href="/galleries/{segment_2}/{row_id}">{photo_title} →</a>{/next_row}
        {/gallery}


``:table`` Tag
--------------

Matrix’s ``:table`` tag to quickly create an HTML table filled with your field’s data.

.. code-block:: html

    {my_matrix_field:table cellspacing="0" cellpadding="0"}

Tag Parameters
~~~~~~~~~~~~~~

The ``:table`` tag accepts all of the primary tag pair’s parameters, as well as a couple of its own:

``set_row_ids``
    When set to “``yes``”, ``id`` attributes to all ``<tr>``s within the ``<tbody>``, set to “``row_id_``” followed by the row’s unique ID.

``set_classes``
    When set to “``yes``”, class attributes will be added to all ``<th>`` and ``<td>``’s, set to the column names.

``set_widths``
    When set to “``yes``”, width attributes will be added to all ``<th>`` and ``<td>``’s, set to the column widths.

``cellspacing``
    Sets the table’s ``cellspacing`` attribute.

``cellpadding``
    Sets the table’s ``cellpadding`` attribute.

``border``
    Sets the table’s ``border`` attribute.

``width``
    Sets the table’s ``width`` attribute.

``class``
    Sets the table’s ``class`` attribute.


``:prev_row`` and ``:next_row``
-------------------------------

Access the previous or next row in your field, from a given starting point. The starting point is whatever the first row would be with your declared field parameters.

.. code-block:: html

    {gallery:next_row row_id="{segment_3}"}
        Up next: <a href="/galleries/{segment_2}/{row_id}">{photo_title}</a>
    {/gallery:next_row}

Tag Parameters
~~~~~~~~~~~~~~

The ``:prev_row`` and ``:next_row`` tags accept all of the primary tag pair’s parameters.


``:total_rows``
---------------

The ``:total_rows`` tag returns the total number of rows within your Matrix field.

.. code-block:: html

    {if {my_matrix_field:total_rows} >= 5}
        We’ve got a great lineup of {my_matrix_field:total_rows} speakers!
    {/if}

Tag Parameters
~~~~~~~~~~~~~~

The :total_rows tag accepts all of the primary tag pair’s parameters.


``:average``, ``:lowest``, ``:highest``, and ``:sum``
-----------------------------------------------------

These tags return the average, lowest, highest, or sum value of a given numeric column in your Matrix field.

.. code-block:: html

    The my_matrix_field’ average age is {my_matrix_field:average col="age"}.

Tag Parameters
~~~~~~~~~~~~~~

These tags accept all of the primary tag pair’s parameters, as well as the following:

``col``
    The name of the column you wish to get info about. *(Required)*

``decimals``
    The number of decimal points the number should have. (The default is 0.)

``dec_point``
    The character that will be used for the decimal. (The default is a period.)

``thousands_sep``
    The character that will be used as the thousands separator. (The default is a comma.)
