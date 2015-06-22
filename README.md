# table_converter

This is a Drupal utility module to convert MySQL table rows from UTF8 to UTF8MB4.

The module will list of the current tables in the database and will highlight rows that need to be converted in GREEN. 

* Rows that are varchar with length less than 191 will simply be converted to mb4 and their column-length will be unchanged.
* Rows that are varchar with length greater than 191 and are NOT primary keys will be converted and their column-length will be unchanged.
* Rows that are varchar with column-def greater than 191 that are primary keys will be highlighted for conversion in green if there are no column values greater than 191 characters in length. 
* Rows that are varchar with column-def greater than 191 that are primary keys and have values with lengths greater than 191 are highlighted in RED and prevent the "convert all" link from appearing. Resolve those by hand and refresh the page to convert all.
