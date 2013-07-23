Content Elements Tags
=====================

If you want to use a Switch field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {fieldpack_switch}
       {value}
   {/fieldpack_switch}


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the ``{fieldpack_switch}`` tag pair:

``{option}``
    The selected option’s value.

``{label}``
    The selected option’s label.
