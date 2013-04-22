Working with ``Assets.Sheet``
=============================

If you have an add-on that includes some sort of file selection
capability, you can implement Assets’ file selection sheet from any page
with very little effort.

Including the Sheet Resources from PHP
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

First you need to make sure that all of the necessary Javascript and CSS
resources have been included on the page. Assets abstracts all of this
behind a simple function:

.. code-block:: js

    // Make sure that Assets is installed
    if (array_key_exists('assets', $this->EE->addons->get_installed()))
    {
        require_once PATH_THIRD.'assets/helper.php';

        $assets_helper = new Assets_helper;
        $assets_helper->include_sheet_resources();
    }

Calling the Sheet from Javascript
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Before getting the sheet to show, you need to initialize a new instance
of ``Assets.Sheet``:

.. code-block:: js

    var mySheet = new Assets.Sheet({

        // optional settings (these are the default values):
        multiSelect: false,
        filedirs:    'all', // or array of filedir IDs
        kinds:       'any', // or array of file kinds ("image", "flash", etc)

        // onSelect callback (required):
        onSelect:    function(files) {
            // files is an array of file IDs and URLs, e.g.:
            // [
            //   { id: 1, url: "/images/uploads/filename1.jpg" },
            //   { id: 2, url: "/images/uploads/filename2.jpg" },
            //   { id: 3, url: "/images/uploads/filename2.jpg" }
            // ]
        }
    });

Once you’ve initialized your sheet, you can get it to actually come into
view by calling:

.. code-block:: js

    mySheet.show();

Your sheet will then slide down from the top of the browser window. If
the user selects any files, the ``onSelect`` callback function will be
called.
