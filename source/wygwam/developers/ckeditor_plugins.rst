Adding CKEditor Plugins
=======================

Wygwam makes it possible for other `extensions <http://ellislab.com/expressionengine/user-guide/development/extensions.html>`_ to add new `CKEditor plugins <http://ckeditor.com/addons/plugins/all>`_ without needing to hack Wygwam’s code or place the plugin files inside Wygwam’s own folders.

The Setup
---------

First, create a new folder in themes/third_party/ with the name of your plugin. Place whatever front-end files your plugin will be needing in there.

Then create a new folder in system/expressionengine/third_party/ with the name of your plugin, and place an ext.your_plugin_name.php file inside it.

Give that file some basic EE extension boilerplate code, with the :doc:`wygwam_config <wygwam_config>` hook:

.. code-block:: php

    <?php if (! defined('BASEPATH')) exit('No direct script access allowed');

    class My_awesome_ext
    {
        var $name           = 'My Awesome Extension';
        var $version        = '1.0';
        var $description    = '';
        var $docs_url       = 'http://example.com/';
        var $settings_exist = 'n';

        private $_hooks = array(
            'wygwam_config',
        );

        public function activate_extension()
        {
            foreach ($this->_hooks as $hook)
            {
                ee()->db->insert('extensions', array(
                    'class'    => get_class($this),
                    'method'   => $hook,
                    'hook'     => $hook,
                    'settings' => '',
                    'priority' => 10,
                    'version'  => $this->version,
                    'enabled'  => 'y'
                ));
            }
        }

        public function update_extension($current = NULL)
        {
            return FALSE;
        }

        public function disable_extension()
        {
            ee()->db->where('class', get_class($this))->delete('extensions');
        }

        public function wygwam_config($config, $settings)
        {
            if (($last_call = ee()->extensions->last_call) !== FALSE)
            {
                $config = $last_call;
            }

            // Great things happen here

            return $config;
        }
    }


Plugin Registration
-------------------

Next up, you need to tell CKEditor about your plugin. There are two steps to that:

1. Tell CKEditor to load your plugin using the `extraPlugins <http://docs.ckeditor.com/#!/api/CKEDITOR.config-cfg-extraPlugins>`_ config setting
2. Tell CKEditor where to find your plugin using `CKEDITOR.plugins.addExternal() <http://docs.ckeditor.com/#!/api/CKEDITOR.resourceManager-method-addExternal>`_

.. code-block:: php

    <?php if (! defined('BASEPATH')) exit('No direct script access allowed');

    class My_awesome_ext
    {
        private static $_included_resources = FALSE;

        // ...

        public function wygwam_config($config, $settings)
        {
            if (($last_call = ee()->extensions->last_call) !== FALSE)
            {
                $config = $last_call;
            }

            // Add our plugin to CKEditor
            if (!empty($config['extraPlugins']))
            {
                $config['extraPlugins'] .= ',';
            }

            $config['extraPlugins'] .= 'myplugin';

            $this->_include_resources();

            return $config;
        }

        private function _include_resources()
        {
            // Is this the first time we've been called?
            if (!self::$_included_resources)
            {
                // Tell CKEditor where to find our plugin
                $plugin_url = URL_THIRD_THEMES.'my_awesome_extension/myplugin/';
                ee()->cp->add_to_foot('<script type="text/javascript">CKEDITOR.plugins.addExternal("myplugin", "'.$plugin_url.'");</script>');

                // Don't do that again
                self::$_included_resources = TRUE;
            }
        }
    }

That ``_include_resources()`` method is a great place to include any additional CSS or JS files your plugin requires.


Adding a Toolbar Button
-----------------------

If your plugin has its own toolbar button, you can even make it show up in Wygwam’s toolbar configurator, using Wygwam’s ``wygwam_tb_groups`` hook:

.. code-block:: php

    <?php if (! defined('BASEPATH')) exit('No direct script access allowed');

    class My_awesome_ext
    {
        // ...

        private $_hooks = array(
            'wygwam_config',
            'wygwam_tb_groups',
        );

        // ...

        public function wygwam_tb_groups($tb_groups)
        {
            if (($last_call = ee()->extensions->last_call) !== FALSE)
            {
                $tb_groups = $last_call;
            }

            $tb_groups[] = array('MyPlugin');

            // Is this the toolbar editor?
            if (ee()->input->get('M') == 'show_module_cp')
            {
                // Give our toolbar button an icon
                $icon_url = URL_THIRD_THEMES.'my_awesome_extension/myplugin/icons/myplugin.png';
                ee()->cp->add_to_head('<style type="text/css">.cke_button__myplugin_icon { background-image: url('.$icon_url.'); }</style>');
            }

            return $tb_groups;
        }

        // ...
    }

With that in place, it’s probably a good idea to make some adjustments to the ``wygwam_config()`` function so that the plugin only gets registered if it was actually selected in the toolbar.

.. code-block:: php

    <?php if (! defined('BASEPATH')) exit('No direct script access allowed');

    class My_awesome_ext
    {
        // ...

        public function wygwam_config($config, $settings)
        {
            if (($last_call = ee()->extensions->last_call) !== FALSE)
            {
                $config = $last_call;
            }

            // Check if our toolbar button has been added
            $include_btn = FALSE;

            foreach ($config['toolbar'] as $tbgroup)
            {
                if (in_array('MyPlugin', $tbgroup))
                {
                    $include_btn = TRUE;
                    break;
                }
            }

            if ($include_btn)
            {
                // Add our plugin to CKEditor
                if (!empty($config['extraPlugins']))
                {
                    $config['extraPlugins'] .= ',';
                }

                $config['extraPlugins'] .= 'myplugin';

                $this->_include_resources();
            }

            return $config;
        }

        // ...
    }

There are a couple other hooks that are called from system/expressionengine/third_party/wygwam/helper.php that enable further customization:

* ``wygwam_tb_label_overrides`` – Use if you want to customize the ‘title’ attribute on your button within the toolbar editor.
* ``wygwam_tb_combos`` – Use this if your plugin is adding a new combo box to the toolbar, rather than a button.
