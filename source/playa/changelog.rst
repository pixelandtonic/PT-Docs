Changelog
=========

Playa 4.4.4
-------------------
Released on July 2, 2013

* Fixed an issue with Playa and Low Variables
* Fixed ordering relationships within a Matrix field
* Fixed a possible bug when updating Playa to Playa 4 and EE to EE 2.6 in one go
* Reduced the generated deprecation notices to one per deprecated tag per template
* Fix several MSM issues
* Fix an issue when filtering entries by category id, using the "not" modifier

Playa 4.4.3
-------------------
Released on May 10, 2013

* Updated the Relationship field conversion script for EE 2.6.
* Fixed an error that could occur when using PHP < 5.2 and EE < 2.6.

Playa 4.4.2
-------------------
Released on Apr 23, 2013

* ExpressionEngine 2.6 compatibility.

Playa 4.4.1
-------------------
Released on Apr 17, 2013

* Playa is now compatible with jQuery 1.9.
* Fixed a bug where using the channel filter would only display entries from the channel with an ID of 1.
* Fixed SQL errors that would occur on clean installs of Playa.

Playa 4.4
-------------------
Released on Apr 16, 2013

* Added Better Workflow compatibility (requires BWF 1.6 or later).
* Added the ability to filter entries by member group.
* Added the ability to only show entries which are editable by the current user.
* Added support for ``CURRENT_USER`` and ``NOT_CURRENT_USER`` constants when filtering Playa relations by author.
* Deprecated the ``{child:property}`` and ``{parent:property}`` tags within Playa tag pairs, in favor of the ``var_prefix`` parameter.
* Drastically decreased Playa’s memory footprint in the templates.
* Prevented several vectors of SQL injection attacks.
* Fixed a parsing bug for nested Playa tags.
* Fixed a bug where Site ID would not be applied as a filter on MSM installations.


Playa 4.3.3
----------------------
Released on Jul 25, 2012

* Fixed a MySQL error that would occur when updating Playa if Matrix isn’t installed
* Fixed a bug that would prevent Playa from parsing any variable tags that begin with ‘e’, ‘x’, or ‘p’

Playa 4.3.2
----------------------
Released on Jul 25, 2012

* Fixed a bug where Playa tags would randomly not parse on the front end

Playa 4.3.1
----------------------
Released on Jul 24, 2012

* Added the ``var_prefix=`` parameter to Playa’s module tag pairs and fieldtype tag pair
* Added "Sites" field setting and "Site" filter to multi-select Playa fields (only visible if MSM is enabled)
* You can now pass entry-specific tags into Playa’s module and fieldtype tag parameters, such as ``{entry_id}`` and ``{my_field_name}``
* Improved template performance
* Changed the relationship keyword format to “``[EntryID] [UrlTitle] [EntryTitle]``”
* Relationship keywords now get saved into exp_matrix_data for Playa columns that are set to Searchable
* Added new ``$data`` argument to the ``playa_fetch_rels_query`` extension hook
* Fixed relationship deletion when Matrix rows are deleted, and added an update script that deletes any orphaned Matrix-based relationships
* Fixed an "Array to string conversion" PHP error in PHP 5.4
* Fixed a PHP error if ``entry_id=`` is set to a non-numeric value
* Fixed a MySQL error when passing multiple entry IDs to ``child_id=`` or ``parent_id=`` params
* Fixed a bug where Playa would only migrate the last selected MH Multi Rel field’s relations

Playa 4.3
----------------------
Released on May 15, 2012

* Added `co-parent relationships <http://pixelandtonic.com/blog/playa-coparents>`_ via three new Playa module tags
* When filtering entries in a Playa field, Playa now passes the ACT value in the post data, so it’s not lost in a .htaccess redirect
* ``field=``, ``field_id=``, ``col=``, ``col_id=``, and ``row_id=`` params now apply to both sides of sibling relationships
* Fixed a bug where clicking on the arrow button in single-select mode would hide the dropdown just as soon as it was shown
* Fixed a PHP error that occurred when updating Playa from an earlier version than 4.0
* Fixed a MySQL error that occurred when using Playa module tags without an ``entry_id=`` param value

Playa 4.2.1
----------------------
Released on Apr 20, 2012

* Improved template tag performance
* Fixed an EE error notice when accessing Low Variables with a Playa field
* Fixed a bug where closing Playa module tags would show up on the front end of the site
* Fixed a PHP error when using ``parent:`` and ``child:`` tags

Playa 4.2
----------------------
Released on Apr 17, 2012

* Added Low Variables compatibility
* The ``entry_id=`` param now supports multiple piped entry IDs across all module tags
* ``{exp:playa:children}`` and ``{exp:playa:parents}``’ ``entry_id=`` param now supports multiple entry IDs separated by ``&&``’s to get all of the common children or parents, respectively
* Playa no longer uses the deprecated ``set_gmp()`` function
* Drop panes’ JavaScript now triggers a “change” event when an entry is selected or deselected
* Fixed a bug where the ``{exp:playa:siblings}`` tag would return all Playa children, rather than just the siblings
* Renamed Playa’s language file back to lang.playa.php
* Fixed a bug where the Output Profiler was getting included in keyword search results if there were no matched entries
* Fixed CSS conflicts with NSM Override.css
* Added new ``playa_field_selections_query``, ``playa_save_rels``, and ``playa_fetch_rels_query`` hooks
* Fixed a bug where the single-select’s entries dropdown would disappear if you clicked on its scrollbar
* Fixed the Ctrl-click behavior on Windows
* Fixed a CSS glitch if there are less than two available or selected entries

Playa 4.1.0.3
----------------------
Released on Nov 17, 2011

* Fixed a MySQL error in the Playa 4 updater script if there were Playa relationships existing in both normal Playa fields and Matrix fields

Playa 4.1.0.2
----------------------
Released on Nov 2, 2011

* Fixed a bug where the entry list would intermittently disappear immediately after opening in the single-select UI mode

Playa 4.1.0.1
----------------------
Released on Nov 1, 2011

* Fixed MySQL errors on ``{exp:playa:children}`` and ``{exp:playa:parents}``

Playa 4.1
----------------------
Released on Nov 1, 2011

* Added ``{exp:playa:siblings}``, ``{exp:playa:total_siblings}``, and ``{exp:playa:sibling_ids}`` tags
* Added the ``child_id=`` param to ``{exp:playa:children}``
* Added the ``parent_id=`` to ``{exp:playa:parents}``
* ``:total_children`` and ``:total_parents`` now always return a number
* Playa now uses ``$EE->TMPL->parse_variables_row()`` to parse relative entry tags (``parent:``/``child:``) so things like ``{parent:entry_date format="%F %d %Y"}`` now work``
* Tweaked the single-select UI so that the keyword search is always visible, no matter where the user clicked on the field
* Ensure that there are no duplicate entries pulled in from the same Playa tag
* Fixed bugs for better IE7 compatibility

Playa 4.0.5
----------------------
Released on Apr 27, 2011

* Added field and Matrix cell validation for if the field/cell is set to be required
* Added an MH Multi Relationship field converter
* Fixed a bug where Matrix cell tags would display the parent entry’s data rather than the child’s on some servers

Playa 4.0.4.1
----------------------
Released on Mar 16, 2011

* Removed ``print_r()`` statement

Playa 4.0.4
----------------------
Released on Mar 16, 2011

* Fixed some template parsing errors caused by ``:total_children`` tags which don’t have anything to return
* Fixed a Javascript error in Internet Explorer when using the single-select UI mode
* Fixed the ``orderby=`` param
* Updated the Playa3 folder to Playa 3.1.2 for EE1 users

Playa 4.0.3
----------------------
Released on Feb 23, 2011

* Added “Show expired entries?” and “Show future entries?” field settings
* ``show_future_entries=`` and ``show_expired=`` tag parameters are now set to “no” by default across all Playa tags
* Fixed a security vulnerability with the ``dynamic_parameters=`` tag parameter
* Fixed ``sort="random"`` tag parameter
* Fixed a bug where ``total_children`` and ``total_parents`` tags would return the total number of entries when they should have returned “0”
* Fixed a bug where Playa tags wouldn’t return anything after having already been parsed once in the same HTTP request
* Fixed a bug where Playa’s fieldtype tags would only output once when the parent ``{exp:channel:entries}`` tag had ``cache="yes"`` set
* Fixed a bug where Playa wouldn’t display entries being pulled from a different MSM site *(``site=`` tag parameter required to get it working)*
* Fixed a Javascript error when using a Playa field within a Matrix field which doesn’t have any available entries
* Fixed a bug where Playa fields wouldn’t display the correct entry status colors for statuses whose Highlight setting begins with “``#``”

Playa 4.0.2.1
----------------------
Released on Feb 7, 2011

* Fixed a PHP error when using ``field=`` or ``col=`` params

Playa 4.0.2
----------------------
Released on Feb 7, 2011

* Added ``{if no_children}`` and ``{if no_parents}`` conditionals
* Simplified the field markup a bit to improve Javascript performance
* Fixed a PHP error that occurred when using Playa’s module tags on a template that has no ``{exp:channel:entries}`` tags
* Fixed a CSS conflict with the Corporate theme that occurred when using Playa within a Matrix field

Playa 4.0.1
----------------------
Released on Feb 3, 2011

* Added a new “Filter Minimum” setting to the global fieldtype settings
* Fixed several issues with fieldtype tag parsing by converting fieldtype tags to module tags before ``{exp:channel:entries}`` has a chance to parse them
* Fixed a PHP error when using the ``:child_ids`` and ``:parent_ids`` tags
* Fixed a bug where the Drop Panes UI wouldn't display entries in the user-defined order
* Fixed a bug where Playa fields within Matrix fields wouldn't remember their field settings when using the keyword search or applying filters
* Fixed a bug where the Single Select UI would show a large empty drop-down box if there were no keyword search results to display
* Fixed the appearance of Drop Panes when there are less than three available entries
* Fixed a couple CSS conflicts with the Corporate theme
* Prevented the scrollbar from displaying when it's not necessary in Firefox
* ``field=`` parameters in ``{exp:playa}`` tags now respect the primary entry's ``site_id``
* Improved SQL performance in templates
* Updated the code examples in the Nested Relationships docs to use the ``:child_ids`` tag rather than the deprecated ``:entry_ids`` tag.
* Added a note to the Updating Instructions to warn against uninstalling Playa before updating

Playa 4.0
----------------------
Released on Feb 2, 2011

* Dropped EE1 compatibility
* New translucent Drop Panes UI
* New single-select UI with autocomplete
* New ``{exp:playa}`` module tags, enabling much more powerful templating
* Relationships are now stored in ``exp_playa_relationships`` rather than EE’s built-in ``exp_relationships``
* Replaced “UI Mode” field setting with simpler “Allow multiple relationships?” setting
* The filter bar above the Drop Panes UI now automatically becomes visible when 20 or more entries are available to be selected
* Added Playa converters for Relationship fields and Solspace’s Related Entries module

Playa 3.1.2
----------------------
Released on Mar 16, 2011

* Added ``start_on=`` and ``stop_before=`` tag parameters
* Simplified the POST data Playa passes to remember which entries are already selected, preventing a “Disallowed Key Characters” error
* [EE1] Fixed a bug where Playa Drop Panes cells would not know their input names on newly created Matrix rows, resulting in a “Disallowed Key Characters” error
* [EE2] Fixed a PHP error that occurred when deleting a Playa field without any relationships
* [EE2] Prevented a PHP error that occurred when ExpressionEngine called Playa’s ``post_save()`` method without having called its ``save()`` method first

Playa 3.1.1
----------------------
Released on Dec 15, 2010

* [EE2] Relationships created by a Playa field are now deleted from the database when the Playa field is deleted *(requires EE 2.1.2)*
* [EE2] Relationships created by a Playa cell within a Matrix field are now deleted from the database when the Playa column on the entire Matrix field are deleted *(requires Matrix 2.1.1)*
* [EE2] Fixed a couple CSS quirks with EE 2.1.2
* [EE2] Fixed an incompatibility with Solspace Super Search

Playa 3.1
----------------------
Released on Nov 29, 2010

* Added the ability to pre-filter entries by the current author
* Added the ability to pre-filter entries by the current channel
* Playa-based relationships are now properly deleted when their containing Matrix row is removed *(requires Matrix 2.1)*
* Single primary tags (and empty primary tag pairs) will now return nothing, rather than fall back to the ``:ul`` tag
* [EE1] Moved the language folder into the module’s folder
* Added Upgrading Instructions to the Docs

Playa 3.0.10
----------------------
Released on Nov 16, 2010

* [EE2] Fixed template parsing when two fields from different MSM sites have the same name
* [EE2] Fixed Drop Panes UI when used within Matrix and without filters
* [EE2] Fixed a PHP error
* [EE1] Fixed a Javascript error

Playa 3.0.9
----------------------
Released on Aug 30, 2010

* Added ``dynamic_parameters=`` param
* Made all PHP includes use absolute paths
* [EE1] Added `Cloner <http://expressionengine.com/index.php?affiliate=brandonkelly&page=/downloads/details/cloner/>`_ support
* [EE2] Added `MX Cloner <http://devot-ee.com/add-ons/mx-cloner/>`_ support
* [EE2] Added autosave support
* [EE2] Fixed incompatibilities with other add-ons using ``generate_json()``

Playa 3.0.8
----------------------
Released on Jul 27, 2010

* Bundled documentation
* Moved theme files to themes/third_party/playa
* Added ``{rel_id}`` tag
* No longer use Search module for Keyword filter
* Show category filter even if there’s only one category
* Fix Javascript error when jQuery is in noConflict mode
* [EE2] Fixed PHP error on some servers when installing Playa
* [EE2] Fixed PHP errors that would occur when saving an entry that didn’t have a Playa field
* [EE2] Fixed Matrix compatibility in templates

Playa 3.0.7
----------------------
Released on May 13, 2010

* Fixed the ``offset`` and ``limit`` params
* [EE2] Fixed the ``backspace`` param

Playa 3.0.6
----------------------
Released on May 10, 2010

* Fixed a Javascript error that occurred when using Select and Multi-select UI modes within `Matrix <http://pixelandtonic.com/matrix>`_
* [EE2] Fixed a PHP error that occurred when saving an entry without any Playa selections

Playa 3.0.5
----------------------
Released on May 4, 2010

* [EE1] Fixed field setting saving

Playa 3.0.4
----------------------
Released on May 4, 2010

* `Matrix 2 <http://pixelandtonic.com/matrix>`_ compatibility
* Check for ``playa_site_index`` config setting as an alternative to the Site URL for running the Drop Pane filters
* Fixed a bug that limited Playa fields to only display 100 entries when set to show all
* Fixed a PHP error that occurred when installing the module separately from the fieldtype and extension
* Keyword search no longer searches in comments associated with the entries

Playa 3.0.3
----------------------
Released on Apr 16, 2010

* [EE2] Fixed a bug that would cause problems while upgrading EE to 2.0.2

Playa 3.0.2
----------------------
Released on Apr 16, 2010

* Fixed some drag-n-drop weirdness
* Fixed ``offset=`` and ``sort="random"`` params
* [EE2] Added ``{count}`` and ``{switch}`` tags (already available in EE1 thanks to FieldFrame)

Playa 3.0.1
----------------------
Released on Apr 12, 2010

* Fixed the Statuses field setting
* Fixed the ``weblog``/``channel`` tag param

Playa 3.0
----------------------
Released on Apr 12, 2010

* EE2 Compatibility
* New, simplified Drop Panes UI
* Lots of new field settings to define your available entries
* Huge performance improvements in the Control Panel

Playa 2.1.4
----------------------
Released on Mar 20, 2010

* Fixed bug which caused Playa Drop Pane fields to freeze up while dragging items

Playa 2.1.3
----------------------
Released on Feb 23, 2010

* Added ```:entry_ids`` <http://pixelandtonic.com/playa/docs/templates#entry_ids>`_ tag
* Removed ``<optgroup>``’s from Weblog filter when the field is only pulling entries from one weblog

Playa 2.1.2
----------------------
Released on Jan 18, 2010

* PHP and Javascript performance improvements
* Show future and expired entries in Keywords search
* Fixed bugs that surface when using Drop Panes within an `FF Matrix <http://pixelandtonic.com/ffmatrix>`_ field
* Properly escape single quotes

Playa 2.1.1
----------------------
Released on Aug 12, 2009

* Fixed a Javascript error *(thanks `Karl! <http://www.karlswedberg.com/>`_)*
* Changed the Keyword Search behavior to only initiate a search after the user has stopped typing

Playa 2.1
----------------------
Released on Aug 3, 2009

* Added ``group_id``, ``category_group``, ``entry_id``, ``url_title``, ``show_expired``, ``show_future_entries``, ``fixed_order``, and ``sort="random"`` `tag params <http://pixelandtonic.com/playa/docs/templates#params>`_
* Added ``:ul`` and ``:ol`` `template tags <http://pixelandtonic.com/playa/docs/templates#ol>`_
* New Multi-select and Select `UI modes <http://pixelandtonic.com/playa/docs/ui-modes>`_
* IE support

Playa 2.0.7
----------------------
Released on May 10, 2009

* Added Multi-select `UI mode <http://pixelandtonic.com/playa/docs/ui-modes>`_ to Playa celltype

Playa 2.0.6
----------------------
Released on Apr 22, 2009

* Added ``category``, ``author``, and ``weblog`` `tag params <http://pixelandtonic.com/playa/docs/templates#params>`_

Playa 2.0.4
----------------------
Released on Apr 19, 2009

* Fixed ``{count}`` and ``{switch}`` tags

Playa 2.0.3
----------------------
Released on Apr 19, 2009

* added ```:total_related_entries`` <http://pixelandtonic.com/playa/docs/templates#total_related_entries>`_ tag

Playa 2.0.2
----------------------
Released on Apr 16, 2009

* Fixed category filtering

Playa 2.0
----------------------
Released on Apr 11, 2009

* Drop Panes `UI mode <http://pixelandtonic.com/playa/docs/ui-modes>`_
* In-field filtering and sorting
* `FF Matrix <http://pixelandtonic.com/ffmatrix>`_ celltype
* New `template tag <http://pixelandtonic.com/playa/docs/templates>`_ with ``status``, ``orderby``, ``sort``, ``limit``, and ``backspace`` params, as well as ``{count}``, ``{total_related_entries}``, and ``{switch}`` tag variables
