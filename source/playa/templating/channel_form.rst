Channel Form
============

You have two options for connecting a Playa field to a `Channel Form <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/>`_.

Showing the full Playa field
----------------------------

If you want to show the full Playa field (the same thing you see in your Publish page), use Channel Form’s `official syntax <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/#other-channel-fields>`_:

.. code-block:: html

   {field:playa_field_name}

Creating a custom input
-----------------------

If you’d rather give your form a custom input, you can do that instead.

Each entry that should be selected must have an input named with the format ``playa_field_name[selections][]``, and the value must be the entry ID.

.. code-block:: html

    {exp:channel:entries channel="articles"}
        <label><input type="checkbox" name="playa_field_name[selections][]" value="{entry_id}"> {title}</label>
    {/exp:channel:entries}

Note that if you’re editing an existing entry, any existing selections will automatically be removed if they don’t show up in the new post data.
