Solspace Related Entries
========================

If you had Solspace’ Related Entries module installed before updating to ExpressionEngine 2, don’t worry! We built a Related Entries converter into Playa 4 that’ll help you resurrect those lost relationships.

Due to the fact that Related Entries associated relationships directly with entries, as opposed to Playa which associates them with individual publish fields, we had to get a little creative with this one. So the conversion script will actually create new Playa fields for you – one Playa field per field group that has at least one relationship created by Related Entries.

Here’s how to do it:

#. Go to Add-Ons → Fieldtypes → Playa
#. Choose “Yes” in the “Convert Related Entries?” setting, and click “Submit”
#. Go to Admin → Channel Administration → Custom Fields, and take note of the names of your new Playa fields
#. Updated your templates to use :doc:`Playa’s template tags </templating/index>`
#. If everything looks good, it is safe to delete your exp_related_entries database table

Caveats
-------
* Playa doesn’t have the concept of “main” related entries, so the conversion script just accounts for those by putting any previous “main” entries at the top of the list.
* Playa doesn’t do anything magical for “single entry pages”. {exp:playa} tags must either live within an ``{exp:channel:entries}`` tag pair, or be given an entry_id= parameter.
* Playa doesn’t have a way to display an entry’s parents and children at the same time, a la ``{exp:related_entries:entries direction="both"}``.
