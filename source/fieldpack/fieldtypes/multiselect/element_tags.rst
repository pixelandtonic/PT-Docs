Content Elements Tags
=====================

If you want to use a Multiselect field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {fieldpack_multiselect}
       {values}
           <li>{option}</li>
       {/values}
   {/fieldpack_multiselect}


Tag Parameters
~~~~~~~~~~~~~~

The ``{values}`` tag pair supports the following parameters:

.. include:: /_includes/shared_multi_primary_params.rst


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the ``{values}`` tag pair:

.. include:: /_includes/shared_multi_variables.rst
