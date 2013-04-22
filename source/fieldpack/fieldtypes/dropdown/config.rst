Configuration
=============

Dropdown has one setting, “Dropdown Options”, a textarea in
which you specify your select’s options.

List one option per line:

.. code-block:: html

    Herbie Hancock
    Miles Davis
    The Bad Plus

You can optionally specify input values for each option, and organize
options into ``optgroup``\ s:

.. code-block:: html

    Jazz
        herbie : Herbie Hancock
        miles : Miles Davis
    Rock
        beatles : The Beatles
        bobby : Bob Dylan

You can also create a blank option by adding a blank line at the top. You can also give your blank option a label:

.. code-block:: html

     : Select one...
    Herbie Hancock
    Miles Davis
    The Bad Plus

*(Note there’s a space before the colon.)*
