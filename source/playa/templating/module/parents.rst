``{exp:playa:parents}``
=======================

You can use the ``{exp:playa:parents}`` tag pair to loop through entries that relate a given entry(s).

.. code-block:: html

    {exp:channel:entries channel="photos"}
        <h3>As Seen in Articles</h3>
        <ul>
        {exp:playa:parents channel="articles"}
            <li><a href="{path={channel_short_name}/{url_title}}">{title}</a></li>
        {/exp:playa:parents}
        </ul>
    {/exp:channel:entries}


Tag Parameters
--------------

``{exp:playa:parents}`` supports almost all of ``{exp:channel:entries}``’ `tag parameters <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#parameters>`_, as well as the following:

.. include:: /templating/_includes/shared_parent_params.rst

``var_prefix``
    Tells Playa to only parse variables that have a certain prefix. This is handy when you’re dealing with variable name conflicts, such as if you’re pulling in an entry with its own Playa tag.

    Note: Playa sets the ``disable`` tag parameter to “``categories|category_fields|member_data|pagination``” by default. So if you want to display categories, member data, or pagination tags in your Playa tag pair, you’ll need to override that parameter.


Variable Tags
-------------

``{exp:playa:parents}`` supports almost all of ``{exp:channel:entries}``’ `conditional variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#conditional-variables>`_, `single variables <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#single-variables>`_, and `variable pairs <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_entries.html#variable-pairs>`_, as well as the following:

``{if no_parents}`` … ``{/if}``
    Outputs the contents only when there are no parent entries returned.
