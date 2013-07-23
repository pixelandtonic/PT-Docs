Content Elements Tags
=====================

If you want to use a List field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {fieldpack_list}
       {values}
           <li>{item}</li>
       {/values}
   {/fieldpack_list}


Variable Tags
~~~~~~~~~~~~~

The following variable is available within your ``{values}`` tag pair:

``{item}``
    The current list item.
