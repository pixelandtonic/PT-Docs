Channel Form
============

You have two options for connecting an Assets field to a `Channel Form <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/>`_.

Showing the full Assets field
-----------------------------

If you want to show the full Assets field (the same thing you see in your Publish page), use Channel Form’s `official syntax <http://ellislab.com/expressionengine/user-guide/modules/channel/channel_form/#other-channel-fields>`_:

.. code-block:: html

   {field:assets_field_name}

Using a file input
------------------

If you’d rather just give your form a simple file input, you can do that instead:

.. code-block:: html

    <input type="file" name="assets_field_name">

You can add ``multiple="multiple"`` to the file input as well, if you want to support multiple file uploads in modern browsers.

Assets also lets you define which upload directory the file will get uploaded to, by creating a hidden input whose name is set to your Assets field name, suffixed with ``_filedir``, and whose value is the upload directory ID:

.. code-block:: html

    <input type="hidden" name="assets_field_name_filedir" value="1">
