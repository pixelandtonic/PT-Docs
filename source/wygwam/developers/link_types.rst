Adding Custom Link Types
========================

Wygwam makes it possible for developers to add custom Link Types to Wygwam’s Link dialog, via the :doc:`wygwam_config <wygwam_config>` extension hook.

To add a custom Link Type, append elements to the ``$config['link_types']`` array. Here’s how you’d do it:

.. code-block:: php

    <?php

    // ...

    function wygwam_config($config, $settings)
    {
        // If another extension shares the same hook,
        // we need to get the latest and greatest config
        if ($this->EE->extensions->last_call !== FALSE)
        {
            $config = $this->EE->extensions->last_call;
        }

        $config['link_types']['Drink Recipes'] = array(
            array('label' => 'Drink Nation',  'url' => 'http://drinknation.com/'),
            array('label' => 'Extra Tasty!',  'url' => 'http://www.extratasty.com/'),
            array('label' => 'The Webtender', 'url' => 'http://www.webtender.com/')
        );

        return $config;
    }

In that example, we created a new Link Type called “Drink Recipes”, and filled it with three websites for the author to choose from.

Each element within your Link Type array can contain the following keys:

``'label'`` (required)
    The label of your link in the Options list.

``'label_depth'``
    The number of indentations your link will have within the Options list.

``'url' (required)``
    The URL that the link will point to.

``'target'``
    The link’s default Target setting value (can be “``_blank``”, “``_top``”, “``_self``”, or “``_parent``”).

``'id'``
    The link’s default Id setting value.

``'dir'``
    The link’s default Language Direction setting value (can be “``ltr``” or “``rtl``”).

``'accesskey'``
    The link’s default Access Key setting value.

``'name'``
    The link’s default Name setting value.

``'lang'``
    The link’s default Language Code setting value.

``'tabindex'``
    The link’s default Tab Index setting value.

``'title'``
    The link’s default Advisory Title setting value.

``'type'``
    The link’s default Advisory Content Type setting value (ex: “text/html”).

``'class'``
    The link’s default Stylesheet Classes setting value.

``'charset'``
    The link’s default Linked Resource Charset setting value.

``'style'``
    The link’s default Style setting value.

``'rel'``
    The link’s default Relationship setting value.
