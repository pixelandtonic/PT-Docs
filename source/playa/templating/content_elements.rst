Content Elements Tags
=====================

If you want to use a Playa field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {playa}
      <ul>
         {children}
            <li>{title}</li>
         {/children}
      </ul>
   {/playa}


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
