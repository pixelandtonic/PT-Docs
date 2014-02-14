Changelog
=========

Assets 2.2.3
---------------
Released on February 14, 2013

* Added support for uploading multiple files at once from a file input in a Channel/Safecracker form.
* Added namespaces to the third party libraries to avoid conflicts with other add-ons.
* The ‘assets_ignore_folder_patterns’ and ‘assets_ignore_file_patterns’ config settings no longer require slashes in the array values.
* Fixed a bug that allowed users to rename folders to a disallowed folder name.
* Fixed a bug that prevented some Assets field tags from getting parsed when used within Grid fields.
* Fixed a bug where EE upload directorty filesize restrictions were not enforced for simple front-end uploads.
* Fixed a bug that could cause Assets to crash when attempting to upgrade itself from 1.1.5 or earlier.
* Fixed a compatibility issue when using Assets within Grid within Low Variables.
* Fixed the table view for Assets fields within Grid fields.
* Fixed an issue where date/times could be saved incorrectly when editing an asset’s metadata.
* Fixed a MySQL error that could occur when MySQL was operating in strict mode.

Assets 2.2.2
---------------
Released on October 29, 2013

* Added ‘assets_ignore_folders_patterns’ and ‘assets_ignore_files_patterns’ config settings.
* Reduced the number of queries needed when rendering templates with Assets tags.
* Fixed some compatibility issues with Matrix.
* Fixed some compatibility issues with Better Workflow + Content Elements (requires Content Elements 1.6.3).
* Fixed some compatibility issues with Channel Forms/Safecracker.

Assets 2.2.1
----------------------
Released on October 9, 2013

* Fixed a MySQL error that could occur when saving entries.

Assets 2.2
----------------------
Released on October 9, 2013

* Added Content Elements compatibility
* Added Grid compatibility.
* Added a new Recent Uploads smart source that displays all of the files that were recently uploaded.
* Added ``{folder_id}``, ``{source_id}`` and ``{source_subfolder}`` tags to ``{exp:assets:files}`` and Assets field tags.
* View states are now remembered on a per-source basis, across multiple fields.
* It is no longer necessary to add a trailing slash to the “Subfolder” setting on external sources.
* Added a new ‘assets_recent_upload_hours’ config setting, which determines how far back the Recent Uploads smart source should look for new files (defaults to 24).
* Added a new ‘assets_source_settings’ config setting, making it possible to override your asset source settings from config.php.
* Added a new ‘assets_file_meta_save’ hook that gets called before new file metadata is saved to the database.
* Fixed a bug where the ``{assets_field:filename}`` shortcut tag would include the extension in its response, unlike ``{filename}``.
* Fixed a bug where Assets could output incorrect file URLs on external sources when the “Subfolder” setting was left blank.
* Fixed some PHP errors when working with EE upload directories taht didn’t have a trailish slash in the Server Path setting.
* Fixed a bug where it was not possible to index two upload directories with same names across two MSM sites.
* Fixed a bug where unexpected Ajax responses could crash the Publish page.
* Fixed a bug where indexing might not work on Windows machines.

Assets 2.1.4
----------------------
Released on July 12, 2013

* Added a ``fixed_order`` param to ``{exp:assets:files}`` as an alternative to the ``file_id`` param, where the order of the file IDs determines the order of the output files.
* Added support for ``$config['assets_cache_remote_images'] = 'no';``. If set, Assets will not cache images stored on remote sources.
* Assets’ fields and file manager now show the full filenames on hover when in Thumb View.
* Fixed a bug where Assets columns within Matrix fields would not display thumbnails when set to List View.
* Fixed a bug where disallowed upload directories would still be displayed in Assets’ file manager.
* Fixed a bug where a trailing slash was mandatory for the Subfolder setting on external sources.
* Fixed a bug that would prevent updating from Assets 1.x to 2.1 in one go.
* Fixed a bug with Assets and MSM, if Assets fields had the same name across multiple sites.
* Fixed a possible error when deleting folders on servers with open_basedir enabled.
* Fixed a bug where uploading a file would break on some versions of MySQL.
* FIxed some IE8 compatibility issues.
* Fixed an error that would occur when Assets received an unexpected response from Rackspace on PHP versions prior to 5.3.
* Fixed a compatibility issue between Assets and Better Workflow.
* Fixed a bug where Assets fields would not return any data when accessed via a Relationship field.
* The ``{filename}`` tag now correctly returns the filename sans-extension, as stated by the documentation.
* Fixed a bug where Assets would not respect the Maximum File Size setting.

Assets 2.1.3
----------------------
Released on May 10, 2013

* Fixed a bug where an upload conflict would be confused with a failed upload.
* Fixed a bug with displaying the modified time for files in List view.
* Fixed a bug where Assets module page titles would be broken for EE < 2.6.
* Fixed a bug where the upload process could break for very small files.
* Fixed a bug where Assets would break with EE < 2.6 and PHP < 5.2.
* Fixed a bug that would sometimes generete notices for EE's upload directory sync.
* Fixed a bug where it was possible to register an existing file with Assets multiple times.
* Fixed a bug where that broke subfolder searching in the File Manager.
* Fixed a bug where images that get resized due to upoad directory preferences would get incorrect width and height values stored in the database.
* Fixed a bug where the ``{exp:assets:files}`` tag would not work if the ``file_id`` parameter was empty.
* Fixed a bug where it was impossible to delete or change a file's title in the File Manager, once it reached the maximum length.
* Fixed a bug where Assets would return an unparsed template rather than an empty string when no files would be found for an entry.

Assets 2.1.2
----------------------
Released on Apr 30, 2013

* Added “Cancel” and “Add files” buttons at the bottom of the file selection sheet.
* The Max Width/Height settings are now enforced when uploading images to EE upload directories.
* Corrected a few bad index entries that could have remained in some installation scenarios.
* Failed uploads now display a proper error message.
* Fixed the date display in the file properties modal for EE 2.6.
* Fixed some IE8 CSS glitches.
* Fixed a bug where uploading an image via Safecracker would not get its thumbnails and manipulations generated.
* Fixed a bug where the Upload button would still appear to work when it was disabled.

Assets 2.1.1
----------------------
Released on Apr 23, 2013

* Added EE 2.6 compatibility.
* Added the ``file_id`` parameter to the ``{exp:assets:files}`` tag.
* Added the ``format`` parameter to the ``:date`` field shortcut tag.
* Fixed a bug where ``{if no_results}`` would output content when it shouldn’t have.
* Fixed a bug that prevented letter case-only file renaming.
* Fixed a bug where the ``{size}`` variable tag would ignore its ``unformatted`` parameter within the primary tag pair.
* Fixed a bug where Upload Folder settings would not be remembered when upgrading to Assets 2.
* Fixed a bug where shortcut tags would not work with files uploaded via SafeCracker.
* Fixed a bug where image borders would show up incorrectly on the Publish page.

Assets 2.1
----------------------
Released on Apr 9, 2013

* Added support for Rackspace Cloud Files and Google Cloud Storage
* External sources can now be set to a subfolder of a bucket/container
* Added ``{exp:assets:total_folders}`` and ``{exp:assets:total_files}``
* Added support for ``sort="random"`` to ``{exp:assets:folders}`` and ``{exp:assets:files}``
* Added the ``{subfolders}`` tag to ``{exp:assets:folders}``
* Added the ``{total_subfolders}`` tag to ``{exp:assets:folders}``
* Added the ``file_id=`` parameter to ``{exp:assets:files}``
* Added a ``{file_id}`` tag to ``{exp:assets:files}``
* Draggables are now semi-transparent, so it’s possible to see the drop target.
* Image manipulation names are now case-insensitive.
* PNG files are now uploaded to Amazon S3 with the proper MIME type.
* File dates are now automatically set to the file’s modified date when uploaded.
* Fixed an issue with Better Workflow and Playa compatibility.
* Fixed an issue that prevented image thumbnails from appearing when Force URL Query Strings is enabled.
* Fixed an issue with indexing on some Windows servers.
* Fixed a bug where Assets would think it should deny access to sources when using SafeCracker.
* Fixed a bug with ``{if no_results}`` conditionals.
* Fixed a bug where context menus would only appear for the latest lazy-loaded batch of files in the file manager.

Assets 2.0.5
----------------------
Released on Feb 4, 2013

* Assets now displays a spinner image when loading the next set of 100 files
* Fixed lazy file loading when in list view
* Assets now uses EE’s config/mimes.php list as a fallback if PHP can’t determine the mime type of a file when uploading to S3
* Fixed some CSS conflicts with NSM Override CSS (thanks Leevi!)
* Minor Javascript performance and bug fixes
* Fixed a bug where ``{size}`` tags would output the raw filesize in bytes rather than formatted when used with a ``var_prefix``
* Fixed a few areas that required PHP 5.2 to work properly

Assets 2.0.4
----------------------
Released on Jan 31, 2013

* Assets’ file manager now only shows 100 files initially, and loads the next 100 when the user scrolls to the bottom of the page, and so on
* Fixed a bug with Better Workflow compatibility
* Fixed the ``{size}`` tag’s ``format=`` parameter
* Fixed a bug that affected file renaming
* Fixed a bug that prevented Assets from realizing that there was a file name conflict
* Fixed a bug where files would not get displayed in Assets fields when the user didn’t have access to their upload directory
* Fixed a bug where selecting a date in the date picker would close the file metadata HUD
* Fixed a bug that prevented a dialog listing stale file records from being displayed after updating Assets’ indexes
* Fixed a bug where just-uploaded files wouldn’t get selected automatically

Assets 2.0.3
----------------------
Released on Jan 22, 2013

* Several keyboard navigation enhancements
* Added the ``var_prefix`` param and ``{if no_results}`` conditionals to ``{exp:assets:files}`` and ``{exp:assets:folders}``
* Resurrected the ``unformatted="yes"`` param fon ``{size}`` variable tags
* Fixed the conflict resolution dialog when renaming a file to the same name as another in the same folder
* Fixed a bug that prevented Assets cells within Matrix within Low Variables from saving (thanks Low!)
* Fixed a bug that prevented you from typing ‘PM’ in the Date metadata text field
* Fixed a bug where newly-created subfolders wouldn’t get placed in alphabetical order
* Fixed a CSS glitch when the File Manager is accessed by non-Super Admins
* Fixed a bug where ``{width:my_manipulation}`` was outputting the height, and ``{height:my_manipulation}`` was outputting the width
* Fixed some wonkiness with File Manager scrolling when the height of the folders was greater than the height of the files
* Fixed horizontal scrolling in the File Manager’s folder list when a folder name is too long to fit in the space it’s given
* Fixed a bug where newly-selected files would get a file name in Assets fields where View was set to “Thumbs” but Show Filenames? was set to “No”
* Fixed a couple PHP errors while upgrading from Assets 1 to 2
* Fixed a couple PHP and MySQL errors when converting a File field to Assets
* Fixed a bug where thumbnails would not display correctly after previewing a Better Workflow entry draft
* Fixed a couple PHP exceptions that were getting thrown when an upload directory or file doesn’t exist anymore
* Fixed field and Matrix cell validation
* Fixed a bug where S3 image thumbnails weren’t getting displayed if the system/expressionengine/cache/assets/s3_sources/ folder was deleted

Assets 2.0.2
----------------------
Released on Jan 17, 2013

* Fixed a PHP error when loading Better Workflow drafts
* Fixed some areas where Assets wasn’t taking EE upload preference $config overrides into account
* Fixed a bug where moving a folder to an S3 bucket wouldn’t move its subfolders too
* Fixed the List View when PHP is not configured to parse short open tags
* Fixed a PHP error when updating to Assets 2 with nonexistent file paths in the exp_assets table
* Replaced a PHP error with a proper error message when saving Assets’ settings and Assets’ fieldtype is not installed

Assets 2.0.1
----------------------
Released on Jan 16, 2013

* Fixed a PHP error when running Assets on an earlier version of PHP than 5.3
* Fixed some installation/upgrade issues
* Fixed support for relative server paths (using ``$config['assets_cp_path']``)
* Fixed a bug where the “Allow multiple selections” field setting wouldn’t stick

Assets 2.0
----------------------
Released on Jan 15, 2013

* Rewritten and redesigned from the ground up
* Amazon S3 support
* Files and folders are now stored in a local DB index
* Added conflict resolution options when attempting to place two files/folders in the same parent folder with the same name
* Added the ability to replace existing files without losing metadata and entry associations
* Added new ``{exp:assets:files}`` and ``{exp:assets:folders}`` module tags
* Added support for simple HTML file field uploads via SafeCracker
* Better Workflow compatibility
* Added some new extension hooks

Assets 1.2.2
----------------------
Released on Aug 29, 2012

* Added support for ``{assets_field:tag_func:manipulation_name}`` shortcut tags
* Added support for .ppt and .pptx files
* Percent signs are now removed from filenames on upload/move/rename
* Fixed some bugs relating to image manipulation generation

Assets 1.2.1
----------------------
Released on Jul 16, 2012

* Added ``unformatted="yes"`` parameter to ``:size`` shortcut tags and ``{size}`` file property tags, to get the unformatted filesize in bytes
* Added support for ``var_prefix`` with image manipulations
* Added unique class names to the meta rows within file property modals
* Fixed a bug where image manipulations would not run on a subfolder
* Fixed the error message for disallowed mime types

Assets 1.2
----------------------
Released on Jul 10, 2012

* Assets now creates custom image manipulations when images are uploaded
* Assets now checks for “``:manipulation_name``” at the end of its file variable tags (e.g. ``{url:manipulation_name}``), and outputs data accordingly
* Added support for ``{assets_field:manipulation_name}`` shortcut tag for outputting the URL of an image manipulation
* Assets now keeps exp_files up-to-date whenever an image enters or leaves the top level of an upload directory
* Assets now checks config/mimes.php to determine if a file should be allowed to be uploaded
* All subfolders beginning with an underscore are now hidden within Assets
* Fixed Required Field validation
* Fixed a PHP error when viewing a file
* Fixed a couple MySQL errors

Assets 1.1.5
----------------------
Released on Apr 17, 2012

* Added support for Matrix fields within Low Variables
* Limited access to Assets’ settings to Super Admins
* Assets now uses CodeIgniter’s DIR_WRITE_MODE constant when creating new subfolders
* Fixed a bug where Assets fields wouldn’t get properly initialized if hidden by default
* Fixed a bug where single-select fields would show the “Remove File” button before a file was selected
* Fixed a bug where Assets fields would appear on top of other page elements
* Fixed a bug where all uploaded files were automatically selected in the Add File sheet, even if the associated Assets field only allows a single selection
* Fixed the Ctrl-click behavior on Windows
* Fixed a bug when displaying an Assets field with a dash in its field name in the template
* Fixed a bug where Assets would delete all previous selections when an entry is updated via the Channel Entries API, and doesn't include Assets data
* Fixed some CSS conflicts with NSM Override.css

Assets 1.1.4
----------------------
Released on Jan 23, 2012

* [EE2] Added EE 2.4 compatibility, including support for the new `upload preference config variables <http://expressionengine.com/user_guide/cp/content/files/file_upload_preferences.html#overriding-upload-paths-and-urls-using-configuration-variables>`_
* Assets now recognizes .xlsx files as Excel files
* Fixed a bug where Assets fields wouldn’t render correctly when placed on a secondary tab in the Publish page
* Fixed a bug that caused Firefox to spike the CPU when editing metadata
* Fixed some IE7 compatibility issues
* Other minor bugfixes

Assets 1.1.3
----------------------
Released on Sep 26, 2011

* Added `Matrix Multi-Upload <https://github.com/pixelandtonic/matrix_multi_upload>`_ compatibility (requires MMU 1.0)
* Cleaned up the Matrix celltype styling a bit
* Fixed an incompatibility with PHP 5.0.x and 5.1.x

Assets 1.1.2.1
----------------------
Released on Sep 7, 2011

* Went back to manually converting spaces to “%20”s rather than using ``urlencode()`` in file URLs, due to subfolder slashes getting encoded to “%2F”

Assets 1.1.2
----------------------
Released on Sep 6, 2011

* When uploading, moving, or renaming a file, its filename is now cleaned up in the same way that EE does it (converts spaces to underscores, etc.)
* Assets now remembers which files were selected between file view refreshes (i.e. when renaming or moving a file), and will automatically scroll to the first selected file
* Added the ``assets_cp_path`` config setting for sites with both relative Upload Directory server paths and a masked Control Panel
* Added ``orderby=`` and ``sort=`` tag parameters
* File URLs are now run through ``urlencode()``, rather than just getting their spaces swapped for %20’s
* Made all file uploading error language localizable in lang.assets.php
* Fixed the look of selected files in Low Variables when using List View
* Fixed a bug where renaming a folder or file simply to change the text case (“Ex” to “ex”) would append a “1” to the end of the new name
* Fixed a Javascript error due to unescaped curly braces in a regular expression

Assets 1.1.1
----------------------
Released on Aug 29, 2011

* Fixed a CSS glitch after sorting files in List View
* Fixed a bug where the user would be prompted to increase PHP’s post_max_size and upload_max_filesize settings even if they were set bigger than the file being uploaded
* Fixed a Javascript error in IE

Assets 1.1.0.1
----------------------
Released on Aug 23, 2011

* Fixed a bug where the status bar would display “upload_status” rather than the localized string while uploading files

Assets 1.1
----------------------
Released on Aug 23, 2011

* Added Low Variables compatibility (requires LV 1.3.7 or later)
* Added an upload progress bar
* Assets now enforces the Max Size and Allowed File Types settings when uploading files
* After uploading a file, Assets will now automatically scroll to the file and select it
* Assets now remembers which files were selected when changing view modes
* Added the ability to delete multiple folders or files at once
* Added the ``assets_meta_add_row`` hook, enabling extensions to add custom metadata fields
* Added property and metadata search parameters (``extension=``, ``title=``, etc.)
* Added the ``var_prefix=`` parameter to the primary tag pair
* Added the ``{absolute_total_files}`` variable tag
* Added the ``{date_modified}`` variable tag and ``:date_modified`` shortcut tag
* The ``{url}`` variable tag and ``:url`` shortcut tag now encode any spaces as “``%20``”
* Improved template performance
* Changed the behavior of the “All” checkbox in the Upload Directories field setting so that it deselects all upload directories upon being unchecked
* Added validation to enforce if the Assets field/cell is required
* Assets now deletes unneeded rows in exp_assets_entries when deleting an entry or Matrix row
* Assets now sends its Ajax requests over SSL if you’re accessing the Control Panel via SSL (https://)
* Fixed a bug where Assets would forget which files had been selected if an entry wasn’t saved due to a validation error
* Fixed a bug where Assets fields wouldn’t remember the file order when returning to an existing entry
* Fixed a couple MSM incompatibilities
* Fixed a bug where clicking “Cancel’ after clicking “Rename Folder/File” would rename the folder or file to “ 1”

Assets 1.0.3
----------------------
Released on Jul 19, 2011

* Added ``{server_path}`` and ``{subfolder}`` var tags to the primary tag pair
* Added ``:server_path`` and ``:subfolder`` shortcut tags
* Enabled subfolder creation from the file selection sheet
* Fixed some CSS glitches when using Assets with SafeCracker
* Assets now manually sorts subfolders and file names in thumbnail view, to ensure they are displayed in alphabetical order
* Fixed a SQL syntax error that occurred during installation on some server configurations
* Fixed a PHP error that occurred when using the ``:width`` and ``:height`` tags
* Fixed a bug where the ``{filename}`` var tag and ``:filename`` shortcut tag would include the “{filedir_X}” prefix in the return data

Assets 1.0.2
----------------------
Released on Jul 1, 2011

* Scrollable areas now automatically scroll as needed when clicking the up and down arrows to navigate the list
* Fixed a bug where dragging a subfolder would pull its ancestor folders along with it
* Fixed numerous visual quirks, especially in EE 2.2 or later
* Fixed a bug where templates wouldn’t display files from other MSM sites

Assets 1.0.1
----------------------
Released on Jul 1, 2011

* The File Manager and File Browser sheet now select the first listed Upload Directory by default
* Added primitive keyboard navigation support to folders and files views
* Added a new “Settings” page to the module, with a License Key setting
* Moved all previously hard-coded language strings into the lang.assets.php
* If the EE Output Profiler is enabled, it no longer has its way with the File Manager’s folder list
* Fixed right-clicking files and folders on Firefox/Mac
* Fixed a bug where affected files’ file_path column in exp_assets wouldn’t get updated when moving or renaming a parent folder
* Fixed a bug where right-clicking on a selected file in an Assets field and choosing “View file” would result in a Javascript error
* Fixed a bug that prevented the metadata textareas from auto-growing as you type in EE 2.2
* Fixed a PHP error during file uploading on some servers

Assets 1.0
----------------------
Released on Jun 28, 2011

* Initial release


