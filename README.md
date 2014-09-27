colResize 0.0.3
=========

A DataTables plugin for dynamic resizing of columns

Requires: DataTables 1.10.2 or greater

Installation
------------
To use ColResize, first download DataTables ( http://datatables.net/download ) 
then download dataTables.colResize.js into an `extensions` directory in the DataTables package.

Basic usage
-----------
ColReorder is initialised using the `Z` option that it adds to DataTables' `dom` option. For example:

	$(document).ready( function () {
		$('#example').dataTable( {
			"dom": 'Zlfrtip'
		} );
	} );