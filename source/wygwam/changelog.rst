Changelog
=========

Wygwam 4.0.1
-------------------
Released on Feb 12, 2016

* Updated CKEditor to 4.5.7.
* Added support for changing Wygwam fields to and from other text-based field types.
* Fixed a bug where extra dropdown menus were being created in advanced configuration settings.
* Fixed an EE3 deprecation warning.

Wygwam 4.0
-------------------
Released on Feb 3, 2016

* EE3 compatibility (requires 3.1 or later)
* Updated CKEditor to 4.5.6
* Dropped EE2 compatibility
* Dropped CKFinder support

Wygwam 3.3.3
-------------------
Released on Dec 8, 2014

* Updated CKEditor to 4.4.6
* Fixed a compatibility issue with ExpressionEngine < 2.5.

Wygwam 3.3.2
-------------------
Released on Jul 15, 2014

* Added a “wygwam_prevent_url_conversion” config setting that prevents URL conversion to Wygwam tags.

Wygwam 3.3.1
-------------------
Released on May 9, 2014

* Updated CKEditor to 4.3.5
* Fixed a caching issue when Wygwam is set to select images from Assets, and an image is replaced within the Assets selection sheet.

Wygwam 3.3
-------------------
Released on Mar 12, 2014

* Added Grid compatibility.
* Updated CKEditor to 4.3.3.
* Added support for the dialog_noConfirmCancel, scayt_autoStartup, scayt_contextCommands, scayt_contextMenuItemsOrder, scayt_maxSuggestions, scayt_moreSuggestions, and scayt_sLang advanced settings in the config editor.
* Fixed a bug where the CKEDITOR.editorConfig() function in themes/third_party/wygwam/lib/ckeditor/config.js wasn’t getting called early enough to make significatnt changes.

Wygwam 3.2.2
-------------------
Released on Nov 13, 2013

* Added new ``wygwam_before_display``, ``wygwam_before_save``, and ``wygwam_before_replace`` extension hooks.

Wygwam 3.2.1
-------------------
Released on Oct 2, 2013

* Fixed PHP < 5.3 compatibility.

Wygwam 3.2
-------------------
Released on Oct 1, 2013

* Made it possible to connect Wygwam to `Assets <http://devot-ee.com/add-ons/assets>`_ sources on Amazon S3, Rackspace Cloud Files, and Google Cloud Storage.
* Added the ``wygwam_tb_groups``, ``wygwam_tb_label_overrides``, and ``wygwam_tb_combos`` extension hooks, making it possible for other extensions to :doc:`add new toolbar buttons <developers/ckeditor_plugins>` to Wygwam’s toolbar configurator.
* Fixed a bug where :doc:`Style Set <using/style_set>` labels could stretch out of view in the Styles menu.

Wygwam 3.1.2
-------------------
Released on Aug 16, 2013

* Brought back the text alignment buttons
* Brought back the text color buttons
* Added support for the ``{element_name}`` variable tag within Content Elements.

Wygwam 3.1.1
-------------------
Released on Aug 6, 2013

* Fixed a bug where the “Create Div Container” button wouldn’t do anything.
* Fixed a bug where dialog text inputs would lose a couple pixels in height when focussed.
* Deleted a bunch of CKEditor files that are not in use.
* Removed the “About” button

Wygwam 3.1
-------------------
Released on Aug 6, 2013

* Added a new “Restrict allowed HTML?” setting which enables you to completely disable CKEditor’s automatic HTML filtering.
* Added a new “Automatically populate the Styles menu with classes in your CSS file?” config setting, which serves as a wrapper for adding the ‘stylesheetparser’ plugin.
* Brought back the Templates toolbar button.

Wygwam 3.0.2
-------------------
Released on Jul 23, 2013

* Brought back the Show Blocks toolbar button.
* Redesigned the Embed Media and Read More toolbar buttons to match CKEditor 4’s new icon style.

Wygwam 3.0.1
-------------------
Released on Jul 22, 2013

* Brought back the Undersine, Subscript, Superscript, and Create Div toolbar buttons.

Wygwam 3.0
-------------------
Released on Jul 22, 2013

* Updated CKEditor to 4.2.
* Added Content Elements compatibility.
* Designed a new skin.
* Added support for new CKEditor advanced config options.
* Fixed the “Edit Configurations” link in the field settings.

Wygwam 2.7.1
-------------------
Released on Apr 23, 2013

* ExpressionEngine 2.6 compatibility.

Wygwam 2.7
-------------------
Released on Jan 22, 2013

* Moved the Editor Configurations page up to the first slot in Wygwam’s module control panel
* If Assets is being used for Wygwam’s file browser, Wygwam will now save the file URLs as ``{assets_X}`` tags, so the URL will be updated when the file is renamed or moved
* Fixed a bug where Wygwam was over-aggressively replacing Page URLs with ``{page_X}`` tags
* Updated CKEditor to 3.6.6
* Updated CKFinder to 2.3.1

Wygwam 2.6.3
-------------------
Released on Aug 29, 2012

* [EE2] Fixed a PHP error in SafeCracker forms when Wygwam is set to use EE’s File Browser

Wygwam 2.6.2
-------------------
Released on Aug 29, 2012

* [EE2] Fixed a Javascript error when using Wygwam within Matrix fields

Wygwam 2.6.1
-------------------
Released on Aug 29, 2012

* [EE2] Fixed a Javascript error in Low Variables when Wygwam was set to use the EE File Browser
* [EE2] Wygwam is now capable of displaying the EE File Browser in Low Variables in EE 2.5.0+, rather than falling back to CKFinder

Wygwam 2.6
-------------------
Released on Aug 28, 2012

* Updated CKEditor to 3.6.4
* Updated CKFinder to 2.3
* Added the ``remove_images="yes"`` parameter
* [EE2] Added “Convert existing rows?” option to Matrix column settings, for converting Text columns to Wygwam
* Leading/trailing whitespace and empty tags are now stripped out from the content when saving
* CKFinder now allows .html files to be uploaded
* Wygwam’s data prep functions are now static methods on the Wygwam_helper class, enabling custom CKEditor instances in Safecracker, without the ``{field:field_name}`` tag
* Wygwam now only uses ``{page_X}`` tags when the full URL matches the page URL (for example, ``href="/about/company"`` will no longer become ``href="{page_X}/company"`` if there is a page with the URI “about”)
* Fixed a Javascript error that occurred if any site pages had non-space whitespace characters in the entry title, such as vertical tabs (common when titles are pasted in from Word)

Wygwam 2.5
-------------------
Released on Apr 18, 2012

* Added a new `Text-Only <http://pixelandtonic.com/wygwam/docs/templates#text_only>`_ tag mode
* The Images-Only tag mode now applies to the ``:excerpt`` and ``:extended`` tags as well as the primary tag
* Updated CKEditor to 3.6.3
* Updated CKFinder to 2.2
* Added ``autoGrow_onStartup`` and ``fillEmptyBlocks`` advanced settings
* Fixed Defer behavior when using Wygwam within Matrix within Low Variables
* Fixed a bug where existing field data wasn't getting properly encoded when using ``{field:field_name}`` tags in SafeCracker
* Fixed a bug where ``{page_X}`` tags wouldn’t parse if accessing an entry from a different MSM site
* Fixed a PHP error that occurred if ``EE->config->item('site_pages')`` returned a string
* Fixed a PHP error that occurred if there are any entries that don’t have an ID (What?)

Wygwam 2.4.0.2
-------------------
Released on Jan 27, 2012

* Fixed CKFinder integration

Wygwam 2.4.0.1
-------------------
Released on Jan 25, 2012

* [EE2] Fixed a bug where toolbars couldn’t be selected in EE 2.4

Wygwam 2.4
-------------------
Released on Jan 24, 2012

* Added a new `Images-Only <http://pixelandtonic.com/wygwam/docs/templates#images_only>`_ tag mode, and accompanying tag pair support
* [EE2] Added EE 2.4 compatibility, including support for the new `upload preference config variables <http://expressionengine.com/user_guide/cp/content/files/file_upload_preferences.html#overriding-upload-paths-and-urls-using-configuration-variables>`_
* Updated CKFinder to 2.1.1
* [EE2] Fixed a bug where Read More comments would turn into visible “``<!--read_more-->``” text when submitted via SafeCracker
* Curly brackets are no longer converted into entities (``&#123;`` and ``&#125;``) in the templates
* Wygwam now ensures that all pages actually have URLs (which are not just “/”) before swapping their URLs with ``{page_X}`` tags on save
* The Defer CKEditor Initialization setting’s placeholder Iframe is now dynamically generated
* Enabled extensions using the ``wygwam_config`` hook to set CKEditor’s “``on``” property

Wygwam 2.3.5
-------------------
Released on Nov 1, 2011

* Updated CKEditor to 3.6.2 (adds iOS5 support!)
* Made minor performance improvements in the field and on the front end
* Fixed a couple bugs with Low Variables compatibility
* Fixed a couple PHP and Javascript errors
* Upload directories with a single slash (“/”) for the URL are now ignored when Wygwam is swapping out upload directory URLs for ``{filedir_X}`` tags
* Updated the Style Set documentation to use CKEditor’s new ``CKEDITOR.stylesSet.add()`` syntax

Wygwam 2.3.4.1
-------------------
Released on Jul 1, 2011

* [EE2] ExpressionEngine 2.2.1 compatibility

Wygwam 2.3.4
-------------------
Released on Jul 1, 2011

* [EE2] Fixed a Javascript error that would prevent CKEditor from even showing up if a configuration’s Upload Directory setting wasn’t set
* [EE2] Fixed a bug where images and files selected via the EE File Manager would return the wrong URL in EE 2.2

Wygwam 2.3.3
-------------------
Released on Jun 28, 2011

* [EE2] Added EE File Browser integration
* [EE2] Added `Assets <http://pixelandtonic.com/assets>`_ integration
* [EE2] Added the “File Browser” setting to the module
* Added the ``justifyClasses`` advanced config setting
* Updated CKEditor to 3.6.1
* Updated CKFinder to the latest build of 2.0.2
* [EE2] Fixed a PHP error when using Wygwam with Low Variables, and the Typography class isn’t loaded yet

Wygwam 2.3.2
-------------------
Released on May 26, 2011

* Added support for EE 2.1.5 Beta
* Added support for HTML5 elements ``section``, ``header``, ``footer``, ``nav``, ``article``, ``aside``, ``figure``, ``dialog``, ``hgroup``, ``time``, ``meter``, ``menu``, ``command``, ``keygen``, ``output``, ``progress``, ``audio``, ``video``, ``details``, ``datagrid``, ``datalist`` and ``mark``
* Made the initial field textarea 10 rows high for mobile devices that don’t support rich text editing
* Fixed IE 9 compatibility

Wygwam 2.3.1
-------------------
Released on May 11, 2011

* Updated CKEditor to 3.6
* Compressed the custom CKEditor skin to reduce the number of CSS requests and speed up page load
* Set the ``forcePasteAsPlainText`` CKEditor config setting to “Yes” by default
* Fixed a bug where selected toolbar groups would still show up in the “options” bucket in the toolbar configurator if their first button was disabled
* Fixed a bug where Wygwam variables in Low Variables wouldn’t display images or URLs in templates

Wygwam 2.3
-------------------
Released on Apr 26, 2011

* Updated CKEditor to 3.5.3
* Added new “Read More” plugin, allowing you to define excerpt and extended portions of your contents within the same Wygwam field
* Added the ``:excerpt``, ``:has_excerpt``, and ``:extended`` tags
* Added the Template Tags page to the docs
* Added an “Edit Configurations” link beside the Editor Configuration field setting
* [EE2] Added field and Matrix cell validation for if the field/cell is set to be required
* EE tags are no longer encoded into ``&#123;`` and ``&#125;`` in the tag output
* Added Low Variables support for links which are saved with ``{page_X}`` tags
* Fixed a bug where deferred Wygwam cells within Matrix fields would get unwanted Javascript code in the field contents when sorting rows

Wygwam 2.2.3
-------------------
Released on Mar 15, 2011

* Added support for Windows-style upload directory paths (e.g. “``D:\…``”)
* Added the ability for custom Link Types to pre-populate any of the Link Dialog’s settings
* Fixed a CKEditor bug where pasting text into Wygwam fields would add an empty paragraph above the pasted text
* Links generated by custom Link Types no longer get “``data-custom-link-type``” attributes

Wygwam 2.2.2
-------------------
Released on Feb 22, 2011

* Updated CKEditor to 3.5.2
* Updated CKFinder to 2.0.2
* Added the ability for third parties to add custom Link Types to the Link dialog (`see how <http://pixelandtonic.com/wygwam/docs/link_types>`_)
* Moved Structure integration to a `separate extension <https://github.com/brandonkelly/wygwam_structure_pages>`_
* Fixed a bug where the Link dialog would show all Link Type settings at the same time
* Fixed a bug where Wygwam would override the ``extraPlugins`` advanced setting
* Fixed glitches with the “Defer CKEditor initialization?” field setting
* Fixed a “Wygwam is undefined” Javascript error in IE8
* Added code to prevent EE’s Typography class from attempting to encode email addresses within Wygwam fields, resulting in a Javascript error in IE7

Wygwam 2.2.1
-------------------
Released on Feb 9, 2011

* Reduced the page weight of the Publish Page
* Localized the “Site Page” Link Type option name in the Link dialog
* Fixed an incompatibility with jQuery, which affected Playa’s Drop Panes UI
* Fixed a bug where Structure pages weren’t displayed in the user-defined order

Wygwam 2.2
-------------------
Released on Feb 9, 2011

* Updated CKEditor to 3.5.1
* New CKEditor dialog skin
* Added Pages and Structure module integration to the Link dialog
* Added a “Relationship” field to the Link dialog, for defining ``rel=`` anchor attributes
* Brought back the Embed Media plugin
* Convert double quote entities (``&quot;``) to normal double quotes (``"``) in the templates

Wygwam 2.1.8
-------------------
Released on Jan 24, 2011

* Updated CKEditor to 3.5
* Added ``dialog_buttonsOrder``, ``disableReadonlyStyling``, and ``removeDialogTabs`` advanced settings
* Added a Troubleshooting page to the Docs
* Fixed a CSS issue with the Source view in EE 2.1.2 and later

Wygwam 2.1.7
-------------------
Released on Dec 15, 2010

* Added sample Output Formatting code to themes/third_party/wygwam/lib/ckeditor/config.js
* Remove ``<div>``’s added by recent versions of Firebug
* Convert double quote entities (``&quot;``) to normal double quotes (``"``) on save
* Keep ``$config['upload_dir']`` around until after the ``wygwam_config`` hook has been called
* Fixed a couple PHP errors
* [EE1] Wygwam now respects the “Allow image URLs in channel entries?” and “Automatically turn URLs and email addresses into links?” channel preferences
* [EE2] Fixed a couple CSS quirks with EE 2.1.2

Wygwam 2.1.6
-------------------
Released on Nov 16, 2010

* Fixed Javascript error when using the Defer field setting

Wygwam 2.1.5
-------------------
Released on Nov 16, 2010

* Updated CKEditor to 3.4.2
* Added support for the “Create Div” button
* Added support for the “defaultLanguage” and “disableNativeSpellChecker” config options
* Added Welsh language support
* [EE1] Fixed support for multibyte characters

Wygwam 2.1.4
-------------------
Released on Sep 23, 2010

* Updated CKEditor to 3.4.1
* Fixed a Javascript error when no field height is set
* Fixed some deferred initialization wonkiness in Firefox
* [EE1] Fixed the “``wygwam_convert_label``” localized string

Wygwam 2.1.3
-------------------
Released on Sep 16, 2010

* Added a page describing Style Sets to the documentation
* Made the toolbar configuration instructions more clear
* Made the ``entities_processNumerical`` setting default to default to “Yes”
* Fixed a bug where configurations only allowed you to select one of the current MSM site’s upload directories
* Reduced the Publish page weight when multiple Wygwam fields exist that use the same configuration

Wygwam 2.1.2
-------------------
Released on Aug 30, 2010

* Added the ability to clone editor configurations
* Added a “Remove” button to configurations’ advanced options
* Made the entire height of deferred initialization fields clickable
* Tidied up the field styling for Low Variables
* [EE2] Fixed PHP error when no upload directories exist
* [EE2] Wygwam now respects the “Allow image URLs in channel entries?” and “Automatically turn URLs and email addresses into links?” channel preferences

Wygwam 2.1.1
-------------------
Released on Aug 25, 2010

* Added a field setting that defers CKEditor initialization until after the field has been clicked on (handy on pages being slowed down by dozens of Wygwam fields)
* Added EE emoticon support
* Fixed toolbar wrapping in Safari and Chrome
* Added ``display_var_tag()`` functions so Wygwam fields have the same template processing via Low Variables as they do within ``{exp:channel:entries}``

Wygwam 2.1.0.1
-------------------
Released on Aug 24, 2010

* [EE2] Fixed the Upload Directory setting

Wygwam 2.1
-------------------
Released on Aug 24, 2010

* Updated CKEditor to 3.4
* Updated CKFinder to 2.0.1
* Restructured files into ee1/ and ee2/ folders
* New translucent skin
* New module for managing editor configurations
* Added `Low Variables <http://loweblog.com/software/low-variables/>`_ support (requires Low Variables 1.3)
* File URLs are now saved using {filedir_X} tags
* Beefed up the auto language mapping a bit
* Made all PHP includes use absolute paths
* Removed the MediaEmbed plugin due to incompatibility issues
* [EE1] Keep CKEditor from forgetting HTML entities
* [EE2] Fixed incompatibilities with other add-ons using generate_json()

Wygwam 2.0.4
-------------------
Released on Jul 27, 2010

* Bundled documentation
* Moved theme files into themes/third_party/wygwam
* [EE2] Fixed an issue that caused data loss on auto-save and when submitting an entry with validation errors
* [EE2] Fixed CKEditor language mapping

Wygwam 2.0.3
-------------------
Released on May 19, 2010

* [EE2] Fixed PHP warning on Field Settings page
* [EE2] Fixed `Matrix <http://pixelandtonic.com/matrix>`_ cell setting saving
* Fixed IE 6/7 compatibility

Wygwam 2.0.2
-------------------
Released on May 4, 2010

* `Matrix 2 <http://pixelandtonic.com/matrix>`_ compatibility
* Add a conversion script to preserve Wygwam fields when upgrading from EE1 to EE2
* Allow relative upload directory server paths
* Protect against data loss when saving an entry before CKEditor has fully initialized
* Prevent fields from containing nothing but a line break
* Remove ``<div>``’s added by recent versions of Firebug

Wygwam 2.0.1
-------------------
Released on Mar 2, 2010

* Updated CKEditor to 3.1.1, which fixed a Copy/Paste bug
* `NSM Addon Updater <http://github.com/newism/nsm.addon_updater.ee_addon>`_ support in EE2
* Added a ```wygwam_config`` <http://pixelandtonic.com/wygwam/docs/wygwam_config>`_ extension hook
* Fixed the ``format_tags`` field setting
* Fixed layout issues in the global settings when using the Corporate theme for EE2
* Roll with Theme folder URLs without a trailing end slash in EE2
* Protect against a PHP error when saving field settings
* Other minor cosmetic fixes

Wygwam 2.0
-------------------
Released on Feb 23, 2010

* EE2 compatibility
* Brand new look
* *XHTML* and *Auto <br>* field conversion
* UI for almost every `CKEditor config setting <http://docs.cksource.com/ckeditor_api/symbols/CKEDITOR.config.html>`_

Wygwam 1.1.5
-------------------
Released on Jan 16, 2010

* Fixed Embed Media bug on some servers

Wygwam 1.1.4
-------------------
Released on Jan 15, 2010

* Updated CKEditor to 3.1
* Updated CKFinder to 1.4.2
* Included fluidByte’s `Embed Media <http://www.fluidbyte.net/index.php?view=embed-youtube-vimeo-etc-into-ckeditor>`_ plugin
* Added new :is_empty and :is_populated tags for conditionals
* fixed Dutch language support
* Uploading files now respects your upload directory’s Maximum File Size setting

Wygwam 1.1.3
-------------------
Released on Oct 29, 2009

* Fixed duplicate editor bug in FF Matrix fields with more than one Wygwam cell
* Fixed a couple file browsing and uploading bugs
* Updated CKEditor to 3.0.1
* Updated CKFinder to 1.4.1.1

Wygwam 1.1.2
-------------------
Released on Oct 7, 2009

* Added a blank option to Upload Directory setting
* Fixed file browsing and uploading for EE installs with relative Fieldtype Folder URLs and/or varying CP subdomains
* Fixed Editor Height setting for some servers
* Minor bug fixes

Wygwam 1.1.1
-------------------
Released on Sep 29, 2009

* Fixed a PHP warning in Wygwam’s settings
* Fixed button toggling for jQuery 1.2

Wygwam 1.1
-------------------
Released on Sep 29, 2009

* File browsing and uploading
* Individual toolbar button toggling
* Field height setting

Wygwam 1.0.3
-------------------
Released on Sep 17, 2009

* Fixed FF Matrix sorting bug (requires `FieldFrame 1.3.4 <http://pixelandtonic.com/fieldframe>`_)

Wygwam 1.0.1
-------------------
Released on Sep 1, 2009

* Site Settings now remembers your license key

Wygwam 1.0
-------------------
Released on Sep 1, 2009

* Initial release
