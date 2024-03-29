# Product CSV file format
A Product is an item attached to a channel(s) that sets the base rules for offers.

The first line of your product CSV has to include the field headers described below with each separated by a comma character `,`. Subsequent lines in the file should contain data for your product using those same fields in that exact same order. Here's a description of each field:

## Handle
Handles are unique names for each product. They can contain letters, dashes and numbers, but no spaces. A handle is used in the URL for each product. For example, the handle for a "Women's Snowboard" should be `womens-snowboard`, and the product's URL would be `https://yourstore.com/product/womens-snowboard`.

Every line in the CSV starting with a different handle is treated as a new product. If you want to add multiple images to a product, or want the product to have variants, you should have multiple lines with the same handle.

## Title
The title of your product. Example: Women's Snowboard

## SEO Title
The SEO Title has a character (letters & numbers) limit of 70.

## Description (Markdown or HTML)
The description of the product in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown.

## SEO Description
The SEO Description has a character (letters & numbers) limit of 160.

## Body (Markdown or HTML)
The content of the product in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown. You can also use RiSE media short codes inside the body, see the Media section of your channel's administrative panel.

## Vendors (min. 2 characters)
A comma seperated list of the the handles of the vendors for your product. For example, `johns-apple-orchard, jims-apple-orchard`.

## Type
The Product type. For example, Snowboard.

## Tags (can be left blank)
Comma-separated list of tags used to tag the product. For example, `tag1, tag2, tag3`.

## Associations (can be left blank)
Comma-separated list of associations used to relate a product with a different product variant. The schema is the "product handle" plus a "colon" and optional a "variant sku". If no variant sku is specified, the default sku will be used. For example, `product-handle1:sku-1, product-handle2, product-handle3:sku-1`.

## Published
States whether or not a product is published on your storefront. Valid values are TRUE if the product is published on your storefront, or FALSE if the product is hidden from your storefront. Leaving the field blank will leave the product unpublished.

## Published Scope (can be left blank)
If published, the scope at which the Product is available to other channels and channel users. Valid Values are:
* global
* local
* private

Defaults to *global*

### Global
A Published Scope of `global` means that the product will be searchable by any system with a RiSE api connection.  This is helpful for when listing products that will be resold in the market place

### Local
A Published Scope of `local` means that the product will be searchable by your channel and your sub-channels.

### Private
A Published Scope of `private` means that the product will be searchable by only your channel


## Option / 1 Name (Default)
If a product has an option that does not alter the SKU, enter its name. For example, Color.

For products with only a single option, this should be set to "Title".

## Option / 1 Value (Default)
If a product has an option, enter its value. For example, Black.

For products with only a single option, this should be set to "Default Title". 

## Option / * Name (Add as Necessary)
The `*` is a place holder for the next iteration number of the option e.g. `Option / 2 name` 

## Option / * Value (Add as Necessary)
The `*` is a place holder for the next iteration number of the option e.g. `Option / 2 value`

### _Note_
Cart Stores all Options in a JSON format allowing for the single model field `options` so it can contain unlimited options. Continue adding option fields as necessary.

### _Note_
If you have an `Option / * Name` column, it must also have an `Option / * Value` column.


## Property Pricing / 1 Name (Default)
If a product has a property that does not alter the SKU but alters the price, enter its name. For example, Topping.
Imagine you are ordering a pizza. The possible variations of pizza are in the millions. So instead of creating a variant of each pizza, create a pricing property.

## Property Pricing / 1 Group (Default)
Grouping for Property Pricing.

## Property Pricing / 1 Value (Default)
If a product has a pricing property, enter its 
price in cents e.g $1.00 written as 100.

## Property Pricing / 1 Image (Default)
If a Pricing Property has an image, list the full link there.

## Property Pricing / * Name (Add as Necessary)
The `*` is a place holder for the next iteration number of the pricing property e.g. `Pricing Property / 2 name` 

## Property Pricing / * Group (Add as Necessary)
The `*` is a place holder for the next iteration number of the pricing property e.g. `Pricing Property / 2 group` 

## Property Pricing / * Value (Add as Necessary)
The `*` is a place holder for the next iteration number of the pricing_property e.g. `Pricing Property / 2 value`

## Property Pricing / * Image (Optional Add as Necessary)
The `*` is a place holder for the next iteration number of the pricing_property e.g. `Pricing Property / 2 image`

### _Note_
Cart Stores all Pricing Properties in a JSON format allowing for the single model field `property_pricing` so it can contain unlimited key value pairs. Continue adding pricing property fields as necessary.

### _Note_
If you have an `Pricing Property / * Name` column, it must also have an `Pricing Property / * Value` column.

## Image Sources
Put the URLs for the product's images separated by a comma character e.g. `,`. Cart will download the images during the import and re-upload them into your data store. 

### _Note_
These images are not variant specific. The variant image column is where you specify variant images.

### _Note_
You won't be able to change your image filename after that image has been uploaded. Don't upload images that have _thumb, _small, or _medium suffixes in their names as these will be created automatically.

## Images Alt Text (can be left blank)
The text that describes the images separated by a pipe character e.g. `|`. Useful if images cannot be displayed or a screenreader passes over an image—the text replaces this element.

## Variant SKU (can be left blank)
The SKU of the product or variant. This is used to track inventory with inventory tracking generics. If no variant sku is provided, RiSE will create a default sku based on the handle of the product

### _Note_
This field can't be left blank if you're using a fulfillment generic.

## Variant Weight
The weight of the product or variant in __grams__. Do not add a unit of measurement, just the number. E.g. `200g` would be `200`. If you are using a different unit of measurement than grams, then supply it in the `Variant Weight Unit` column.

## Variant Weight Unit (can be left blank)
Convert the variant grams field to a different unit of measure by entering kg, g, oz, or lb. If this field is left blank, the weight will be uploaded as grams and then converted to your store's default weight unit.

### _Note_
Cart will always import and export weight in grams, even if you specify a different unit. You must use accurate weights if you intend to offer carrier-calculated shipping or use a fulfillment generics.

## Variant Inventory Tracker (can be left blank)
Include your inventory tracking for this variant or product. Valid values include "shipwire", "amazon_marketplace_web", or blank if inventory is not tracked.

## Variant Inventory Quantity
The number of items you have in stock of this product or variant.

## Variant Inventory Policy
How to handle orders when inventory level for this product or variant has reached zero. Valid values are "deny", or "continue". "deny" will stop selling when inventory reaches 0, and "continue" will allow sales to continue into negative inventory levels.

## Variant Max Quantity
The number of items that a customer can purchase of the product at a time. -1 equals no limit, and a positive integer will enforce no more than this quantity can be added to a cart.

## Variant Fulfillment Service
The product or variant fulfillment service used. Valid values are generics like: `manual`, `shipwire`, `amazon_marketplace_web`. If you use a custom fulfillment service that does not have a generic built for it, you can add the name of the service in this column. For the custom name, use only lowercase alphabet letters. Spaces aren't allowed, replace them with a dash `-` or underscore `_`. Periods and other special characters are removed. For example, if "Mr. Fulfiller" is your fulfillment service's name, enter "mr-fulfiller" in the CSV file.

### Note
You must have a custom fulfillment service set up in your admin before you can add the name of the service in this column.

## Variant Internal Price
The internal cost of the product or variant in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.

## Variant Price
The price of the product or variant in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.

## Variant Compare at Price
The "Compare at Price" of the product or variant in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.

## Variant Minimum Price 
The "Minimum Price" of the product or variant for creating offers in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.  Defaults to the Variant Price if left blank.

## Variant Maximum Price 
The "Maximum Price" of the product or variant for creating offers in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.  Defaults to the Variant Price if left blank.

## Variant Currency
The "Currency" of the product or variant. Defaults to `USD`.

## Variant Requires Shipping (blank = FALSE)
The option to require shipping. Valid values are "TRUE", "FALSE", or blank.

## Variant Taxable (blank = FALSE)
Apply taxes to this variant. Valid values are "TRUE", "FALSE", or blank.

## Variant Barcode (can be left blank)
The barcode, ISBN or UPC of the product.

## Variant Images
Put the URL for your variant image. Cart will download the images during the import and re-upload them into your data store.

## Variant Images Alt Text
The text that describes the images separated by a pipe character e.g. `|`. Useful if images cannot be displayed or a screenreader passes over an image—the text replaces this element.

## Variant Tax Code (can be left blank)
### _Note_
This column only applies if you are using a tax service generic.
Enter a tax code that applies to a specific variant of the product. E.g. `TX123`.

## Gift Card
States whether the product is a Gift Card or not. Valid values are "TRUE", or "FALSE". The addition of this column also allows you to edit other Gift Card details, such as the Body or Tags columns, and import these changes. A gift card can only be created and activated in the Cart admin. You can't initially create a gift card through a product CSV import.

## Metadata
JSON format of Metadata limited to __1,000 characters__. E.g.
```js
{
  hello: 'World',
  custom_field: 'This is a Custom Field I use else where in My Application and is not related to Goolge Merchant or Amazon'
}
```
Optionally, you can upload similar metadata structures using a different CSV named `product_meta_upload.csv`

# Subscriptions
## Subscription
If this product *requires* a subscription, use `true`. Otherwise leave blank.

## Subscription Unit
If this product is subscribable, then the amount of days, weeks, months, this subscription is in as an integer.

## Subscription Interval
If this product is subscribable, then the unit of measurement. Valid values are `0`,`d`,`w`,`ww`,`m`,`mm`,`y`,`yy`

# Metafields

### _Tip_
There are ten metafield columns that appear in every CSV file. Only two of them apply to all stores. The other eight apply if you have installed the Google Shopping App to submit your products to Google's Merchant Center. When exporting or importing, these ten columns can be placed in any order. Click here to read which metafields are required.


## Google Shopping / Google Product Category
Google has a proprietary set of product categories. The full list is quite large to allow merchants to be very specific towards their target audience. You can upload any value you want using the CSV file, however if your language format does not match Google's full product taxonomy, you might not be able to publish the products to Google.

## Google Shopping / Gender
What gender does this product target? Valid values are Female, Male, or Unisex

## Google Shopping / Age Group
What age group does this product target? Valid values are Adult or Kids only.

## Google Shopping / MPN
The MPN, or Manufacturer Part Number, is a string of alphanumeric digits of various lengths (0-9, A-Z).

## Google Shopping / Adwords Grouping
This is used to group products in an arbitrary way. It can be used for Product Filters to limit a campaign to a group of products, or Product Targets to bid differently for a group of products. You can enter any "string" data (letters and numbers).

For more information visit https://support.google.com/merchants/answer/188494?hl=en.

## Google Shopping / Adwords Labels
Very similar to adwords_grouping, but it will only only work on Cost Per Click (CPC). It can hold multiple values, allowing a product to be tagged with multiple labels.

For more information visit https://support.google.com/merchants/answer/188494?hl=en.

## Google Shopping / Condition
State what condition the product will be in at the time of sale (what quality?). Valid values are new, used, or refurbished.

## Google Shopping / Custom Product
False means that this product does not have an MPN or a unique product identifier (UPC, ISBN, EAN, JAN) set as a variant barcode. Valid values are TRUE or FALSE. Learn more here.

## Google Shopping / Custom Label 0
You can have up to 5 custom labels for your product numbered 0 through 4. You can identify a specific definition for each label and specify a value. For example, Sale.

## Google Shopping / Custom Label 1
You can have up to 5 custom labels for your product numbered 0 through 4. You can identify a specific definition for each label and specify a value. For example, ReleaseDate.

## Google Shopping / Custom Label 2
You can have up to 5 custom labels for your product numbered 0 through 4. You can identify a specific definition for each label and specify a value. For example, Season.

## Google Shopping / Custom Label 3
You can have up to 5 custom labels for your product numbered 0 through 4. You can identify a specific definition for each label and specify a value. For example, Clearance.

## Google Shopping / Custom Label 4
You can have up to 5 custom labels for your product numbered 0 through 4. You can identify a specific definition for each label and specify a value. For example, SellingRate.

### _Caution_

If you use an app that manipulates CSV files, reference all columns by name, not number.

To organize your products into collections during the CSV upload, you can add a new column anywhere in your CSV file with the header name Collection. This is and the additional option values are the only columns you can add to the CSV that will not break the format. Therefore:

## Collections (must create a new column, can be left blank)
Enter the name of the collections separated by a comma character `,` you want to add this product to. If the collection(s) does not already exist, one will be created for you.

## Shops (must create a new column, can be left blank)
Enter the name of the shops handles separated by a comma character `,` you want to add this product to. If the shop(s) does not already exist, one will be created for you.

## Shops Quantity (must create a new column, can be left blank)
Enter the quantity of the product/product variant separated by a comma character `,` that is stored at this shop.

# Create your product CSV file

For each product, you'll need to decide if it is a simple product or one with variants:

## Simple Product (Does Not Contain Variants)

If you are uploading a product that does not have variants, then enter all the fields (as described above) for the product on the first line along with the URL for the first image. On the following lines, enter just the handle and the URL for each additional additional image.

## Product With Variants

If you are uploading a product that has variants, then enter all the fields (as described above) for the product on the first line along with the URL for the first image. On the following lines, enter the handle. Then, skip the Title, Body (HTML), Vendor, and Tags. Fill out the rest of the variants details and each image URL.

Once you've added all your products and images, save your CSV file in UTF-8 format using LF-style linefeeds. If you are not familiar with encodings, please see your spreadsheet or text editor program's documentation.

