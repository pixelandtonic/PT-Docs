Creating a Custom Style Set
===========================

To customize the contents of the “Styles” toolbar menu, you need to create and assign a custom Style Set to your field’s configuration.

First, create a new Javascript file named my_styles.js. This file will hold your custom Style Set:

.. code-block:: js

    CKEDITOR.stylesSet.add( 'my_styles',
    [
        // Block Styles
        { name: 'Blue Title', element: 'h2', styles: { 'color': 'Blue' } },
        { name: 'Red Title' , element: 'h3', styles: { 'color': 'Red' } },

        // Inline Styles
        { name: 'CSS Style', element: 'span', attributes: { 'class': 'my_style' } },
        { name: 'Marker: Yellow', element: 'span', styles: { 'background-color': 'Yellow' } }
    ]);

Each “style” within your Style Set is an Object with the following attributes:

``name``
    The name that will appear within the Styles menu

``element``
    The element your selection will be converted to (or wrapped by, in the case of “span”) if the style is selected

``styles`` (optional)
    CSS styles that will be applied directly to the element

``attributes`` (optional)
    Any other attributes to be added to the element (i.e. “class”)

Upload this file to your server somewhere, such as /themes/third_party/wygwam_assets/.

Now we need to point Wygwam to our new style set. Go to Add-Ons → Modules → Wygwam, and click on the configuration you want to be using these styles. Then click on the “Add an advanced setting…” drop-down, and choose “styleSet”. A text field will appear. Replace its contents with:

.. code-block:: text

    my_styles:/themes/third_party/wygwam_assets/my_styles.js

(If you uploaded your Javascript file to a different location, use the correct URL.)

Save your configuration, and you’re done!
