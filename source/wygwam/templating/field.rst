Field Tags
==========

The following tags are available for your Wygwam fields within ``{exp:channel:entries}`` tag pairs.


Primary Tag
-----------

Returns the full contents of your Wygwam field.

.. code-block:: html

    {exp:channel:entries channel="blog"}
        <h1>{title}</h1>
        {my_wygwam_field}
    {/exp:channel:entries}

“Read More” Tags
----------------

The following tags deal with Wygwam fields which use the new “Read More” separators.

``:excerpt`` Tag
~~~~~~~~~~~~~~~~

If your field has a “Read More” separator, this returns your Wygwam field contents up until that point. Otherwise it will return the full contents of your Wygwam field.

``:has_excerpt`` Tag
~~~~~~~~~~~~~~~~~~~~

For use in conditionals. Returns “y” if your Wygwam field has a “Read More” separator within it.

.. code-block:: html

    {my_wygwam_field:excerpt}

    {if my_wygwam_field:has_excerpt}
        <a href="{path='blog/full-posts/{url_title}'}">Read more...</a>
    {/if}

``:extended`` Tag
~~~~~~~~~~~~~~~~~

If your field has a “Read More” separator, this returns the remaining portion of your Wygwam field contents after that point. Otherwise it won’t return anything.

.. code-block:: html

    <h1>{title}</h1>
    {my_wygwam_field:excerpt}

    <div class="extended">
        {my_wygwam_field:extended}
    </div>


Text-Only Mode
--------------

If you pass the parameter ``text_only="yes"`` to Wygwam’s primary, ``:excerpt``, or ``:extended`` tags, Wygwam will remove all the HTML tags from the content, leaving only the text.

.. code-block:: html

    {my_wygwam_field text_only="yes"}

If you just want to remove the images, but leave the rest of the HTML markup in place, you can pass ``remove_images="yes"`` instead.

.. code-block:: html

    {my_wygwam_field remove_images="yes"}


Images-Only Mode
----------------

If you pass the parameter ``images_only="yes"`` to Wygwam’s primary, :excerpt, or :extended tags, Wygwam will remove everything but the images from the content, and separate them with line breaks.

.. code-block:: html

    {my_wygwam_field images_only="yes"}

If you want to have complete control over the HTML output, use a tag pair:

.. code-block:: html

    <ul>
        {my_wygwam_field images_only="yes"}
            <li><img src="{src}" width="{width}" height="{height}" alt="{alt}" /></li>
        {/wygwam_field}
    </ul>

Tag Parameters
~~~~~~~~~~~~~~

The following parameters are available to help customize the images-only output:

``images_only``
    Must be set to “``yes``” to enable images-only mode.

``delimiter``
    Overrides the delimiter used to separate images when using a single tag. (Set to “``<br />``” by default.)

``offset``
    Skips the first *X* images.

``limit``
    Limits the number of images to display.

Variable Tags
~~~~~~~~~~~~~

The following variable tags are available within the tag pair:

``{width}``
    The width of the image, whether it was specified in the ``style`` or ``width`` HTML attributes (if the former, “px” will be removed).

``{height}``
    The height of the image, whether it was specified in the ``style`` or ``height`` HTML attributes (if the former, “px” will be removed).

Attribute tags (``{src}``, ``{alt}``, ``{title}``, etc.)
    The value of the corresponding HTML attribute.

Style tags (``{style:float}``, etc.)
    The value of the corresponding inline CSS style.
