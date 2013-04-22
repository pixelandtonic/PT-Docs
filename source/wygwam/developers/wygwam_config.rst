Using the ``wygwam_config`` Hook
================================

Wygwam has an extension hook called “``wygwam_config``”. This hook will enable you to override your Wygwam fields’ `CKEditor config settings <http://docs.cksource.com/ckeditor_api/symbols/CKEDITOR.config.html>`_ right on page load, taking your Wygwam customizations to a whole new level.

If you’ve never written an ExpressionEngine extension before, you can learn how from the `EE Docs <http://ellislab.com/expressionengine/user-guide//development/extensions.html>`_.

We’ve written a few sample extensions to demonstrate what you can do with the hook:

* `Wygwam Upload Tags <https://github.com/pixelandtonic/wygwam_upload_tags>`_ parses your upload directory’s Server Path and URL settings for {screen_name}, {member_id}, and {group_id} tags.
* `Wygwam Super Admin Source <https://github.com/pixelandtonic/wygwam_super_admin_source>`_ enables the Source button for Super Admins, regardless of your Editor Configuration settings.
* `Wygwam Template Links <https://github.com/pixelandtonic/wygwam_template_links>`_ adds a “Templates” link type to the Link dialog, making it easy to link to your site templates.

Hook Parameters
---------------

``$config``
    The array of config settings that are about to be JSON-ified and sent to CKEditor during field initialization.

``$settings``
    The full array of your field’s settings, as they were before being translated into the $config array.

**Return Data?**

Yes – your extension should return the $config array, whether or not you’ve modified it in any way.

**Appearance of Hook in the Code**

.. code-block:: php

    if ($this->EE->extensions->active_hook('wygwam_config'))
    {
        $config = $this->EE->extensions->call('wygwam_config', $config, $all_settings);
    }