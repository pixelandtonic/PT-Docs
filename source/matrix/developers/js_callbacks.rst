Binding JS Callbacks
====================

If you wish to add any sort of Javascript-powered functionality to your celltype, you can do it using ``Matrix.bind()``.

.. code-block:: js

	Matrix.bind('fieldtype_class', 'event_name', function(cell){
	  // custom code here
	});

Matrix supports the following callbacks:

``display``
	Called for each cell present on page load, and each cell created afterwards.

``beforeSort``
	Called right before a row begins to be sorted.

``afterSort``
	Called after sorting has stopped.

``remove``
	Called right before a row is removed from the DOM.
