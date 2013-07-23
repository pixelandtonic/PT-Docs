Field Tags
==========

The following tags are available for your Dropdown fields within ``{exp:channel:entries}`` and Matrix tag pairs.


Primary Tag
-----------

Calling your Dropdown field with a single tag returns the selected
option’s value:

.. code-block:: html

    <p>I really like {my_dropdown_field}.</p>


``:label`` Tag
--------------

Returns the label of the selected option.

.. code-block:: html

    <p>I really like <a href="{my_dropdown_field}">{my_dropdown_field:label}</a>.</p>
