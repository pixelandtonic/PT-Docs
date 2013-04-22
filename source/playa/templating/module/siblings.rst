``{exp:playa:siblings}``
========================

You can use the ``{exp:playa:siblings}`` tag pair to loop through entries that share a common parent with other entries.

.. code-block:: html

    <ul class="photo-nav">
        {exp:playa:siblings entry_id="{segment_3}" parent_id="{segment_2}"}
            <li><a href="{path={channel_short_name}/{url_title}}">{title}</a></li>
        {/exp:playa:siblings}
    </ul>


Tag Parameters
--------------

``{exp:playa:siblings}`` supports almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

.. include:: /templating/_includes/shared_sibling_params.rst

``var_prefix``
    Tells Playa to only parse variables that have a certain prefix. This is handy when you’re dealing with variable name conflicts, such as if you’re pulling in an entry with its own Playa tag.

**Note:** By default, siblings will be ordered by the number of common parents they share with the original entry. You can override that with the ``orderby`` param.

**Note:** Playa sets the ``disable`` tag parameter to “``categories|category_fields|member_data|pagination``” by default. So if you want to display categories, member data, or pagination tags in your Playa tag pair, you’ll need to override that parameter.


Variable Tags
-------------

``{exp:playa:siblings}`` supports almost all of ``{exp:channel:entries}``’ `conditional variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#conditional-variables>`_, `single variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#single-variables>`_, and `variable pairs <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#variable-pairs>`_, as well as the following:

``{if no_siblings} … {/if}``
    Outputs the contents only when there are no sibling entries returned.
