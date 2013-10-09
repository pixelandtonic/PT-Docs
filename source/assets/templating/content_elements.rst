Content Elements Tags
=====================

If you want to use an Assets field within `Content Elements <http://www.krea.com/content-elements>`_, use the following template:

.. code-block:: html

   {assets}
       {files}
         <img src="{url}" />
       {/files}
   {/assets}


Tag Parameters
~~~~~~~~~~~~~~

The ``{files}`` tag pair supports the following parameters:

.. include:: /templating/_includes/file_field_params.rst


Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the ``{files}`` tag pair:

.. include:: /templating/_includes/file_variables.rst

