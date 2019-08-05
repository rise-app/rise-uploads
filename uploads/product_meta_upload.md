# Product Meta CSV file format
A Product Metadata is a schemaless object of information about a product. If RiSE does not have the field you need for your application, then use the Metadata to create it.

The first line of your product CSV has to include the field headers described below with each separated by a comma character `,`. Subsequent lines in the file should contain data for your product using those same fields in that exact same order. Here's a description of each field:

## Handle
The unique handle of the product. In addition, to include metadata to a product variant use the product handle followed by a ":" and the sku. For example, `product-handle:variant-sku`

## Other Fields
All other column headers other than `Handle` will become key value pairs. Eg. Column A2 will have the value from Column B2. The output will be `help_url: 'help.com/url'`  
