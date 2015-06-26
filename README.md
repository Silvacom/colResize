colResize 0.0.10
=========

A DataTables plugin for dynamic resizing of columns

Requires: DataTables 1.10.2 or greater

Installation
------------
To use ColResize, first download DataTables ( http://datatables.net/download ) 
then download dataTables.colResize.js into an `extensions` directory in the DataTables package.

Basic usage
-----------
ColResize is initialised using the `Z` option that it adds to DataTables' `dom` option. For example:

	$(document).ready( function () {
		$('#example').dataTable( {
			"dom": 'Zlfrtip'
		} );
	} );
	
ColResize supports both fixed width tables and variable width tables.
Fixed width table splits the column width difference between itself and its neighbour column.
Variable width tables increase/decreases the width of the table the same amount as the column being resized.
In order for a variable width tables to work, the table needs to be wrapped in a container that allows the table to resize.
One way is to wrap it in a div that has a style of overflow-x: auto.
By default it is fixed width, for variable set tableWidthFixed to false:

	$(document).ready( function () {
		$('#example').dataTable( {
			"dom": 'Zlfrtip',
			"colResize": {
				"tableWidthFixed": false
			}
		} );
	} );
	
ColResize has right to left(rtl) support.
This changes which neighbouring column is resized. Make sure the table
is set to rtl as well otherwise this property will not work.
For right to left set rtl to true:

	$(document).ready( function () {
		$('#example').dataTable( {
			"dom": 'Zlfrtip',
			"colResize": {
				"rtl": true
			}
		} );
	} );
	
To exclude columns from resizing simply add the index to the exclude array.

	$(document).ready( function () {
		$('#example').dataTable( {
			"dom": 'Zlfrtip',
			"colResize": {
				"exclude": [0,1,2]
			}
		} );
	} );

You can set a callback function for when the user is done resizing.

	$(document).ready(function() {
		$('#example').DataTable( {
			"dom": 'Zlfrtip',
			"colResize": {
				"resizeCallback": function(column) {
					alert("Column Resized");
				}
			}
		} );
	} );

You can adjust the width of the resize handle (in px).

	$(document).ready(function() {
		$('#example').DataTable( {
			"dom": 'Zlfrtip',
			"colResize": {
				"handleWidth": 10
			}
		} );
	} );
