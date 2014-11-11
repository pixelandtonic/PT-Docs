Field Tags
==========

The following tags are available for your Checkboxes fields within ``{exp:channel:entries}`` and Matrix tag pairs.


Primary Tag Pair
----------------

Calling your Checkboxes field with a tag pair allows you to fully
customize the output:

.. code-block:: html

    <p>
        I like
        {my_checkboxes_field backspace="2"}{option}, {/my_checkboxes_field}.
    </p>


Tag Parameters
~~~~~~~~~~~~~~

The primary tag pair supports the following parameters:

.. include:: /_includes/shared_multi_primary_params.rst


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the primary tag pair:

.. include:: /_includes/shared_multi_variables.rst


``:ol`` and ``:ul`` Tags
------------------------

Returns an ordered/unordered list of each of your selected options.

.. code-block:: html

    <h3>My favorite things:</h3>
    {my_checkboxes_field:ul sort="asc"}

Tag Parameters
~~~~~~~~~~~~~~

The ``:ol`` and ``:ul`` tags support the following parameters:

.. include:: /_includes/shared_multi_params.rst


``:selected`` Tag
-----------------

For use in conditionals; returns whether or not a particular option is
selected.

.. code-block:: html

    {if {my_checkboxes_field:selected option="kittens"}}
      <p>Kittens!!!</p>
    {/if}


``:total_selections`` Tag
-------------------------

Returns the total number of selected options.

.. code-block:: html

    I have {my_checkboxes_field:total_selections} favorites.
