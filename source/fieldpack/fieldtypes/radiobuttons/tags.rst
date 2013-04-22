Field Tags
==========

The following tags are available for your Radio Buttons fields within ``{exp:channel:entries}`` tag pairs.


Primary Tag
-----------

Calling your Radio Buttons field with a single tag returns the selected
option’s value:

.. code-block:: html

    <p>I really like {my_radiobutton_field}.</p>


``:label`` Tag
--------------

Returns the label of the selected option.

.. code-block:: html

    <p>I really like <a href="{my_radiobutton_field}">{my_radiobutton_field:label}</a>.</p>
