# Collection CSV file format
The first line of your collection CSV has to include the field headers described below with each separated by a comma. Subsequent lines in the file should contain data for your customer using those same fields in that exact same order. Here's a description of each field:

## Handle
The unique handle of the collection.

## Title
The title of your collection. Example: Women's Snowboards

## SEO Title
The SEO Title has a character (letters & numbers) limit of 70.

## Description (Markdown or HTML)
The small description of the collection in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown. This creates the field `excerpt_html`.

## SEO Description
The SEO Description has a character (letters & numbers) limit of 160.

## Excerpt (Markdown or HTML)
The medium description of the collection in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown. This creates the field `excerpt_html`.

## Body (Markdown or HTML)
The description of the collection in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown. This creates the field `body_html`.

## Purpose
The Purpose of the Collection.  Campaigns can hold customers and offers while Categories can hold products. Valid Values are:
* campaign
* category

## Sort Order
The Order in which the collection sorts products in it (if any). Valid Values are:
* alpha-asc // Alphabetically, in ascending order (A - Z).
* alpha-desc // Alphabetically, in descending order (Z - A).
* best-selling // By best-selling offers.
* created // By date created, in ascending order (oldest - newest).
* created-desc // By date created, in descending order (newest - oldest).
* manual // Order created by the channel administrators.
* price-asc // By price, in ascending order (lowest - highest).
* price-desc // By price, in descending order (highest - lowest).

## Published
States whether or not a collection is published on your storefront. Valid values are TRUE if the collection is published on your storefront, or FALSE if the product is hidden from your storefront. Leaving the field blank will leave the collection unpublished.

## Published Scope (can be left blank)
If published, the scope at which the Collection is available to other channels and channel users. Valid Values are:
* global
* local
* private

Defaults to *global*

### Global
A Published Scope of `global` means that the collection will be searchable by any system with a RiSE api connection.  This is helpful for when categorizing products that will be resold in the market place

### Local
A Published Scope of `local` means that the collection will be searchable by your channel and your sub-channels.

### Private
A Published Scope of `private` means that the collection will be searchable by only your channel

## Products *For Categories* (can be left blank)
A comma separated list of product handles

## Customers *For Campaigns* (can be left blank)
A comma separated list of customer emails or handles

## Offers *For Campaigns* (can be left blank)
A comma separated list of offer handles
