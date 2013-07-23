Content Elements Tags
=====================

If you want to use a Dropdown field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {fieldpack_dropdown}
       {value}
   {/fieldpack_dropdown}


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the ``{fieldpack_dropdown}`` tag pair:

``{option}``
    The selected option’s value.

``{label}``
    The selected option’s label.
