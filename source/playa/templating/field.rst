Field Tags
==========

The following tags are available for your Playa fields within ``{exp:channel:entries}`` tag pairs.

Primary Tag Pair
----------------

The Primary Tag Pair will loop through each of your selected entries, outputting whatever data you need from them.

.. code-block:: html

    <h4>Favorite Bands</h4>
    {my_playa_field show_expired="yes" limit="10"}
        <h4><a href="/bands/{url_title}">{title}</a></h4>
        <p>{short_desc}</p>
    {/my_playa_field}

Tag Parameters
~~~~~~~~~~~~~~

The primary tag pair supports almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

``child_id``
    The child entry ID(s) to include. Prefix with “``not``” to define entries to exclude instead.

**Note:** Playa sets the ``disable`` tag parameter to “``categories|category_fields|member_data|pagination``” by default. So if you want to display categories, member data, or pagination tags in your Playa tag pair, you’ll need to override that parameter.

Variable Tags
~~~~~~~~~~~~~

The primary tag pair supports almost all of ``{exp:channel:entries}``’ `conditional variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#conditional-variables>`_, `single variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#single-variables>`_, and `variable pairs <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#variable-pairs>`_, as well as the following:

``{if no_children} ... {/if}``
    Outputs the contents only when there are no child entries returned.


``:ul`` and ``:ol`` Tags
------------------------

Returns an (un)ordered list of the field’s children’s titles.

.. code-block:: html

    <h4>Favorite Bands</h4>
    {my_playa_field:ol show_expired="yes"}

Tag Parameters
~~~~~~~~~~~~~~

The ``:ul`` and ``:ol`` tags support almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

``child_id``
    The child entry ID(s) to include. Prefix with “``not``” to define entries to exclude instead.


``:total_children`` Tag
-----------------------

Returns the total number of the field’s children.

.. code-block:: html

    <p>I have {my_playa_field:total_children show_expired="yes"} favorite bands.</p>

Tag Parameters
~~~~~~~~~~~~~~

The ``:total_children`` tag supports almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

``child_id``
    The child entry ID(s) to include. Prefix with “``not``” to define entries to exclude instead.


``:child_ids`` Tag
------------------

Returns a list of the field’s children’s entry IDs.

.. code-block:: html

    {embed="site/child_entries" child_ids="{my_playa_field:child_ids}"}

Tag Parameters
~~~~~~~~~~~~~~

The ``:child_ids`` tag supports almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

``delimiter``
    The string used to separate the returned entry IDs. (The default is “``|``”.)

``backspace``
    Strips the last *X* characters from the tag output.
