Changelog
=========

Matrix 2.5.5
----------------------
Released on May 2, 2013

* Added compatibility with EE revisions.
* Number cells now allow the use of thousands_sep and dec_point parameters in templates
* Fixed a bug that prevented RTE fields from being used in a Safecracker form.
* Fixed a bug that prevented changing number of rows for RTE cells.
* Fixed a bug that would break Matrix on old PHP installs.

Matrix 2.5.4
----------------------
Released on Apr 23, 2013

* Added EE 2.6 compatibility.
* Fixed Low Search and Solspace Super Search compatibility.
* Fixed some issues with Better Workflow compatibility.

Matrix 2.5.3
----------------------
Released on Jan 22, 2013

* [EE2] Matrix now sets ``is_draft = TRUE`` on celltypes when viewing a Better Workflow draft
* [EE2] Fixed a bug conflict between the “Is col required?” column setting label and the “The [col name] column is required” cell validation error text
* [EE2] Matrix now handles NULL values appropriately when “``IS_EMPTY``” is passed into a ``search:col_name=`` param
* [EE2] Fixed some PHP errors when outputting a file’s size
* The ``beforeSort`` and ``afterSort`` callbacks are now triggered when clicking “Move to top” and “Move to bottom”, fixing a Wygwam bug

Matrix 2.5.2
----------------------
Released on Dec 17, 2012

* [EE2] Fixed a JS error when using a Matrix field with a dash in its name in a Safecracker form
* [EE2] Text columns that had Format set to “Numeric” now get converted to Number columns with Decimals set to “2” rather than “0” when updating from < Matrix 2.5
* [EE2] Changed the behavior of validating Number cells

Matrix 2.5.1
----------------------
Released on Dec 7, 2012

* [EE2] Fixed a bug that prevented tags with parameters from getting parsed when inside a Matrix tag pair
* [EE2] Fixed an MySQL error on EE 2.5.3 when the RTE is not installed
* [EE2] Fixed a PHP notice that affected a few servers when parsing column tag modifiers

Matrix 2.5
----------------------
Released on Dec 5, 2012

* [EE2] Added `Better Workflow <http://betterworkflow.electricputty.co.uk/>`_ support (requires BWF 1.5)
* [EE2] Added a new Rich Text celltype, powered by EE’s new rich text editor (thanks `Rob <https://twitter.com/_rsan>`_!)
* [EE2] Added a new Number celltype, which replaces the numeric Text celltype modes
* [EE2] Added a new Text Direction setting to Text columns
* [EE2] Drastic performance enhancements, especially when the open_basedir restriction is enabled
* Added new “Move to top” and “Move to bottom” options to row contextual menus
* [EE2] Celltypes now get sorted alphabetically by name in the Col Type settings
* [EE2] Matrix now sets ``$field_name``, ``$col_id``, ``$cell_name``, ``$row_id`` (if available) and ``$field_id``/``$var_id`` on celltypes before calling their ``validate_cell()`` methods
* [EE2] Matrix now sets ``$col_id`` on celltypes before calling their ``save_cell_settings()`` methods
* [EE2] Added var prefix support to File manipulation shortcut tags, e.g. ``{var_prefix:file_col:manipulation_name}``
* [EE2] Fixed a bug where Low Variables wouldn’t show the correct language strings
* Fixed some “object is undefined” errors when manually calling ``Matrix.instances[x].initRows()`` from Javascript

Matrix 2.4.3
----------------------
Released on Jul 26, 2012

* [EE2] Fixed ``{switch}`` tags

Matrix 2.4.2
----------------------
Released on Jul 24, 2012

* [EE2] Added the ``var_prefix=`` parameter
* The Maximum Rows field setting no longer hides existing rows in fields with too many rows
* Matrix fields that are hidden by default, or live in a secondary Publish tag, are no longer initialized until they are visible, fixing Text cell display issues, among other things
* Fixed a bug where Matrix would display deleted rows if there was a validation error
* Fixed a bug where the date picker wouldn’t show up for Date cells within Low Variables
* When you duplicate a Matrix-based Low Variable, Matrix will now duplicate the column settings
* Changed what happens to the HTML DOM when rows are deleted (hidden rather than removed) to fix issues with CKEditor instances (like Wygwam fields) that live further down in the page
* [EE1] Fixed some bugs with the LG Data Matrix conversion script

Matrix 2.4.1
----------------------
Released on May 29, 2012

* Fixed a bug where Matrix didn’t call celltypes’ replace_tag() function on column tags that have parameters

Matrix 2.4
----------------------
Released on May 22, 2012

* Added support for the full breadth of the native File Field’s `template tags and parameters <http://expressionengine.com/user_guide/modules/channel/custom_fields.html#file-field>`_, including Image Manipulation tags, to the File celltype
* Added support for ``replace_tag_catchall()`` within celltypes
* File cells now show an error when displayed in SafeCracker, pointing the user to SafeCracker File
* Fixed a bug where File fields wouldn’t show the File Browser within Low Variables
* Fixed a PHP error when saving an entry via SafeCracker
* Fixed a bug where Date cell using a 24-hour time format would lose their data if there was a validation error

Matrix 2.3
----------------------
Released on Apr 17, 2012

* Added Low Variables compatibility (requires LV 2.2 or later)
* Matrix fields without any rows now display a “No rows exist” dummy row
* Reverted back to the pre-Matrix 2.2 behavior of deleting empty rows when saving
* Cell data is now run through ``form_prep()``, just like normal field data
* Fixed a PHP 5.4 compatibility issue with File cells
* Fixed a bug where text columns would not display plugin-based formatting options when editing an existing Matrix field
* Fixed a bug where unaltered rows’ keywords would go missing after submitting partial Matrix data from a SAEF
* Fixed a bug where ``{field_row_count}`` and ``{field_row_index}`` would cap out at 100 and 99, respectively
* Fixed some CSS conflicts with NSM Override.css
* Fixed a bug where File cells would display a broken image if a thumbnail doesn’t exist
* Renamed the language files back to the lang.xyz.php format
* Added new `` matrix_save_row`` hook
* The ``matrix_data_query`` hook is now called every time ``_data_query()`` is called, and extensions are now passed a 4th argument, ``$select_mode``
* Fixed a PHP error when submitting a SAEF for an entry that has a Matrix field, but without Matrix data in the post

Matrix 2.2.4
----------------------
Released on Jan 24, 2012

* [EE2] Added EE 2.4 compatibility, including support for the new `upload preference config variables <http://expressionengine.com/user_guide/cp/content/files/file_upload_preferences.html#overriding-upload-paths-and-urls-using-configuration-variables>`_
* [EE2] Added support for saving entries via the Channel Entries API
* [EE2] Date cols’ database columns in exp_matrix_data are no longer set to ``UNSIGNED``, allowing for dates prior to 1/1/1970 to be saved (you must re-save your Matrix field before this takes effect)
* [EE2] Entering “0” in a required text cell now passes validation
* [EE2] Fixed a PHP error in the field settings, “Undefined property: Admin_content::$file_upload_preferences_model”

Matrix 2.2.3.2
----------------------
Released on Nov 28, 2011

* *Really* fixed the front end-facing PHP error that Matrix 2.2.3.1 attempted to fix
* Fixed a bug where numeric text cells’ decimal points would get rounded out by default (to achieve the same effect, now you must use ``decimals="0"``)

Matrix 2.2.3.1
----------------------
Released on Nov 21, 2011

* Fixed a front end-facing PHP error on fields that hadn’t been saved since Matrix 2.1.1

Matrix 2.2.3
----------------------
Released on Nov 17, 2011

* Added the ``fixed_order=`` param
* [EE2] Added ``decimals=``, ``dec_point=``, and ``thousands_sep=`` params to numeric Text cells
* Celltype tags are now parsed after ``{field_row_index}``, ``{field_row_count}``, ``{row_id}`` and ``{row_index}`` tags
* Fixed a bug where extra previously-saved rows would get displayed after decreasing the Max Rows setting
* Fixed a Text cell bug caused by ampersands not getting encoded properly
* Fixed some IE7 display issues
* [EE2] Fixed “Unable to load requested field type file: ft..php” error when a Matrix tag pair has no column tags
* [EE2] Text cells only call ``$EE->typography->parse_type()`` if the Content Type setting is set to “all”
* [EE1] Fixed a bug where Date cells’ calendar would get hidden by the next row
* [EE2] Fixed a PHP error if the Typography class wasn’t loaded yet
* Decreased an interval’s duration from 1ms to 100ms to prevent CPU spikes in Firefox

Matrix 2.2.2.1
----------------------
Released on Jul 1, 2011

* [EE2] ExpressionEngine 2.2.1 compatibility

Matrix 2.2.2
----------------------
Released on Jun 22, 2011

* [EE2] ExpressionEngine 2.2 compatibility
* [EE2] Added an “Allowed Directory” setting to File columns, which limits file selection to a single upload directory *(requires EE 2.2)*
* [EE2] File columns’ “File Type” setting is now enforced *(requires EE 2.2)*
* [EE2] Added a “Decimal” option to Text columns’ Content setting
* [EE2] Celltypes are now sorted by name in the Col Type drop-down
* [EE2] ``$this->EE->load->view()`` et al. now works from celltypes’ ``display_tag()`` functions

Matrix 2.2.1
----------------------
Released on Apr 27, 2011

* New entries now get zero rows by default (unless the Minimum Rows setting is set)

Matrix 2.2.0.1
----------------------
Released on Apr 12, 2011

* [EE2] Fixed a bug where ``$this->setting['entry_id']`` wasn’t available for celltypes’ ``save_cell()`` method, which affected Playa’s ability to save new cell data

Matrix 2.2
----------------------
Released on Apr 12, 2011

* Added the “Minimum Rows” field setting
* Matrix fields that have no rows actually display no rows now
* Clicking the tab key in the Matrix field configuration settings now favors inputs in the same column
* [EE2] Added the “Is col required?” column setting
* [EE2] Added the ``validate_cell()`` celltype method
* [EE2] Changed the way Matrix columns are associated with their fields (we now use the exp_matrix_cols.field_id column)
* [EE2] Matrix columns are now duplicated alongside field duplication, via MSM
* [EE2] Removed unnecessary ``<input type="file">`` from File cells
* [EE1] Replaced the jQuery UI Datepicker with an EE1-style calendar for Date cells
* Cell tags are now parsed before ``{field_row_index}``, ``{field_row_count}``, ``{row_index}``, ``{row_count}``, and ``{row_id}`` tags
* [EE1] Fixed the “Auto <br>” Text format setting
* [EE2] Fixed a validation bug where the File celltype would think there was a problem selecting a file, even if there wasn’t

Matrix 2.1.4.1
----------------------
Released on Mar 16, 2011

* [EE2] Fixed a PHP error that occurred when parsing Matrix tag pairs that have parameters
* [EE2] Minor template performance enhancement
* [EE1] Matrix now passes the current cell object to celltypes using the legacy ``onDisplayCell`` Javascript callback

Matrix 2.1.4
----------------------
Released on Mar 15, 2011

* Added ``:average``, ``:sum``, ``:lowest``, and ``:highest`` fieldtype tags
* Replaced “Remove column” and “Remove row” language with “Delete column” and “Delete row”
* Moved all field language into the localizable lang file
* Fixed a Javascript error preventing Matrix fields from initializing if the field name contained double quotes
* [EE2] Fixed some cross-browser keystroke detection issues for numeric text fields
* [EE2] Brought back custom Matrix tag parsing for its primary tag pair, while we wait for ExpressionEngine templating bugs to be fixed

Matrix 2.1.3
----------------------
Released on Feb 2, 2011

* Fine-tuned the keystroke detection in text cells
* Added a defense against negative ``offset=`` and ``limit=`` params
* [EE2] Eliminated Matrix’s reliance on its extension

Matrix 2.1.2
----------------------
Released on Jan 4, 2011

* Added ``{row_index}``, and ``{field_row_count}``, ``{field_row_index}``, ``{field_total_rows}`` single variable tags
* Added ``{prev_row}`` and ``{next_row}`` variable tag pairs
* Prevented some duplicate SQL queries in the templates
* [EE1] Fixed a PHP error that occurred when deleting entries
* [EE2] Fixed a bug where ``settings_modify_matrix_column()`` was passed column settings in an inconsistent format

Matrix 2.1.1.2
----------------------
Released on Dec 22, 2010

* [EE2] Added an error message to the bundled File celltype for when the EE2 File Manager `doesn’t work <http://expressionengine.com/bug_tracker/bug/13240/>`_
* [EE2] Fixed a bug that would cause a SQL error when deleting a Matrix field that had no rows

Matrix 2.1.1.1
----------------------
Released on Dec 15, 2010

* [EE2] Fixed a PHP bug that occurred  while deleting a Matrix field

Matrix 2.1.1
----------------------
Released on Dec 15, 2010

* Added “Auto <br>” and “XHTML” text formatting options to Text cells
* Text cells now respect the “Allow image URLs in channel entries?” and “Automatically turn URLs and email addresses into links?” channel preferences
* Fixed column label previewing for new, unsaved columns in the field settings
* Column instructions can now have line breaks
* Added ``set_row_ids=``, ``set_classes=``, ``set_widths=``, ``border=``, ``width=``, and ``class=`` parameters to the ``:table`` tag
* Fixed a couple PHP errors
* [EE2] Added “Integer” and “Number” text content options to Text cells
* [EE2] Added ``settings_modify_matrix_column()`` celltype method, enabling celltypes to customize their ``exp_matrix_data`` column(s) settings
* [EE2] Celltypes are now filled-up with their field settings before their ``pre-process()`` method is called
* [EE2] Column settings and data associated with a Matrix field are now deleted from the database when the Matrix field is deleted *(requires EE 2.1.2)*
* [EE2] Fixed template parser for celltypes which don’t return anything in their tag functions
* [EE2] Fixed an incompatibility with Solspace Super Search

Matrix 2.1
----------------------
Released on Nov 29, 2010

* Single primary tags (and empty primary tag pairs) will now return nothing, rather than fall back to the ``:table`` tag
* ``{switch}`` tags are now parsed after cell tags
* Added Upgrading Instructions to the Docs
* Added ``post_save_cell()`` celltype callback function
* Added ``delete_rows()`` celltype callback function
* [EE2] Celltypes’ ``pre_process()`` method will now be called if it exists
* [EE2] Calling ``$this->EE->load->view()`` now works as expected from ``display_cell_settings()`` and ``display_cell()``

Matrix 2.0.12
----------------------
Released on Nov 16, 2010

* [EE2] Fixed template parsing when two fields from different MSM sites have the same name
* [EE2] Fixed a PHP error

Matrix 2.0.11
----------------------
Released on Sep 17, 2010

* Fixed a PHP bug that presented the second to last column twice, in place of the should-be last column

Matrix 2.0.10
----------------------
Released on Sep 16, 2010

* Prevent scrollbars on Text cells
* Fixed a bug where Matrix would consider an empty array to be non-null cell data
* [EE1] Respect the “Convert ASCII to Entities” global weblog preference
* [EE1] Fixed PHP errors that occurred when a selected celltype was disabled
* [EE2] Added ``:filename``, ``:extension``, and ``:filesize`` tags to File celltype

Matrix 2.0.9
----------------------
Released on Aug 31, 2010

* Fixed display issue when a dollar sign is present in the column labels or instructions
* [EE2] Added autosave support
* [EE2] Made ``$this->row`` available to celltypes within ``replace_tag()``, etc.

Matrix 2.0.8
----------------------
Released on Aug 16, 2010

* Made it easier for other JS scripts to interact with Matrix fields on the Publish page
* Made all PHP includes use absolute paths
* Remember cells with the value of “0”
* [EE1] Fixed “Operation aborted” IE error in SAEFs
* [EE1] Fixed ``dynamic_parameters=`` param
* [EE2] Added `MX Cloner <http://devot-ee.com/add-ons/mx-cloner/>`_ support
* [EE2] Make ``$this->row_id`` available to celltypes in ``display_cell()`` for pre-saved rows
* [EE2] Fixed incompatibilities with other add-ons using ``generate_json()``
* [EE2] Made File cells return nothing in the template when no file is selected

Matrix 2.0.7.1
----------------------
Released on Jul 30, 2010

* Removed ``console.log()`` call from JS

Matrix 2.0.7
----------------------
Released on Jul 27, 2010

* Bundled documentation
* Moved theme files into themes/third_party/matrix
* Fixed JS syntax issues
* [EE1] `Cloner <http://expressionengine.com/downloads/details/cloner/>`_ support
* [EE1] LG Add-on Updater support
* [EE2] Fixed alternate template tags for celltypes (“``{cell:alt_tag}``”)
* [EE2] Fixed PHP errors that would occur when saving an entry that didn’t have a Matrix field
* [EE2] Fixed an issue that prevented Matrix tags from working when being pulled from a different MSM site

Matrix 2.0.6
----------------------
Released on Jun 10, 2010

* [EE2] Fixed a template-facing PHP error

Matrix 2.0.5
----------------------
Released on Jun 10, 2010

* Bring back support for ``<``, ``>``, ``<=``, and ``>=`` prefixes for the ``search:`` parameter
* Fixed PHP warning that occurred when using a celltype that doesn’t have any settings
* [EE1] Auto-serialize and -unserialize array-based cell data, for consistency with FF Matrix 1.x
* [EE1] Fixed PHP warning when updating from FF Matrix
* [EE2] Template performance improvements
* [EE2] Made the ``col_id``, ``col_name``, and ``row_name`` available to celltypes on save
* [EE2] Retain Matrix data when submitting an entry that doesn’t validate
* [EE2] Fixed a MySQL error that occurred when installing the Matrix extension on some Windows servers

Matrix 2.0.4
----------------------
Released on May 19, 2010

* Added ``{row_id}`` `tag variable <http://pixelandtonic.com/matrix/docs/templates>`_
* Added ``row_id=`` `tag parameter <http://pixelandtonic.com/matrix/docs/templates>`_
* Fixed jQuery 1.4 compatibility
* Fixed an IE 6/7 compatibility issue
* Changed the way the row contextual menus get appended to the DOM, fixing a z-index issue with the Corporate theme
* Changed the way Text cells’ Max Length setting gets enforced, fixing an issue with saving cells with multibyte characters
* [EE1] Fixed an issue that prevented Matrix tags from working when being pulled from a different MSM site
* [EE1] Fixed ``{switch}`` tags

Matrix 2.0.3
----------------------
Released on May 10, 2010

* [EE1] Fixed a bug that prevented the menu options from displaying

Matrix 2.0.2
----------------------
Released on May 9, 2010

* Fixed ``orderby`` and ``sort`` params

Matrix 2.0.1
----------------------
Released on May 8, 2010

* Moved all language to the localizable language files
* Fixed text selection quirks
* Fixed ``{if matrix_field}`` conditionals for Matrix fields that don’t have any searchable columns
* [EE1] Fixed SAEF support (requires `FieldFrame <http://pixelandtonic.com/fieldframe>`_ 1.4.2)
* [EE1] Fixed ``search:xyz`` params
* [EE1] Fixed the combination of ``offset`` and ``limit`` params
* [EE2] Switched conditional tag parsing over to EE’s native function

Matrix 2.0
----------------------
Released on May 4, 2010

* EE2 Compatibility
* New UI
* File celltype for EE2
* Column instructions settings
* Column width settings
* Per-column search settings
* Data is now stored in its own database table

Matrix 1.5
----------------------
Released on Feb 23, 2010

* Initial public release
* Added ``dynamic_parameters=`` param
* Added calendar picker to Date celltype
* Allow empty strings in ``offset=`` and ``limit=`` params


