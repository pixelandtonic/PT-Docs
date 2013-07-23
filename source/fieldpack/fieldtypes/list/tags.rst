Field Tags
==========

The following tags are available for your List fields within ``{exp:channel:entries}`` and Matrix tag pairs.


Primary Tag Pair
----------------

Calling your List field with a tag pair allows you to fully
customize the output:

.. code-block:: html

    <p>I like {my_list_field backspace="2"}{item}, {/my_list_field}.</p>

Variable Tags
~~~~~~~~~~~~~

The following variable is available within your tag pair:

``{item}``
    The current list item.


``:ol`` and ``:ul`` Tags
------------------------

Returns an ordered/unordered list of each of your selected options

.. code-block:: html

    <h3>My favorite things:</h3>
    {my_list_field:ul}
