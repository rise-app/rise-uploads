# Offer CSV file format
An Offer is a special version of a Product that can be sold through Channels.

The first line of your offer CSV has to include the field headers described below with each separated by a comma character `,`. Subsequent lines in the file should contain data for your offer using those same fields in that exact same order. Here's a description of each field:

## Handle
Handles are unique names for each offer. They can contain letters, dashes and numbers, but no spaces. A handle is used in the URL for each offer. For example, the handle for a "Women's Snowboard" should be `womens-snowboard`, and the offer's URL would be `https://yourstore.com/offer/womens-snowboard`.

Every line in the CSV starting with a different handle is treated as a new offer. If you want to add multiple images to a offer, or want the offer to have variants, you should have multiple lines with the same handle.

## Product Handle
Use an existing product Handle to associate the offer to a product.

## Title
The title of your offer. Example: Women's Snowboard

## SEO Title
The SEO Title has a character (letters & numbers) limit of 70.

## Description (Markdown or HTML)
The description of the offer in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown.

## SEO Description
The SEO Description has a character (letters & numbers) limit of 160.

## Body (Markdown or HTML)
The content of the offer in Markdown or HTML format. This can also be plain text without any formatting which defaults to Markdown. You can also use RiSE media short codes inside the body, see the Media section of your channel's administrative panel.

## Tags (can be left blank)
Comma-separated list of tags used to tag the offer. For example, `tag1, tag2, tag3`.

## Up Sells (can be left blank)
Comma-separated list of associations used to relate a offer with a different offer variant. The schema is the "offer handle" plus a "colon" and optional a "variant sku". If no variant sku is specified, the default sku will be used. For example, `offer-handle1:sku-1, offer-handle2, offer-handle3:sku-1`.

## Cross Sells (can be left blank)
Comma-separated list of associations used to relate a offer with a different offer variant. The schema is the "offer handle" plus a "colon" and optional a "variant sku". If no variant sku is specified, the default sku will be used. For example, `offer-handle1:sku-1, offer-handle2, offer-handle3:sku-1`.

## Down Sells (can be left blank)
Comma-separated list of associations used to relate a offer with a different offer variant. The schema is the "offer handle" plus a "colon" and optional a "variant sku". If no variant sku is specified, the default sku will be used. For example, `offer-handle1:sku-1, offer-handle2, offer-handle3:sku-1`.

## Published
States whether or not a offer is published on your storefront. Valid values are TRUE if the offer is published on your storefront, or FALSE if the offer is hidden from your storefront. Leaving the field blank will leave the offer unpublished.


## Published Scope (can be left blank)
If published, the scope at which the Offer is available to other channels and channel users. Valid Values are:
* global
* local
* private

Defaults to *global*

### Global
A Published Scope of `global` means that the offer will be searchable by any system with a RiSE api connection.  This is helpful for when listing offers that are promoted across other channels not within your tree.

### Local
A Published Scope of `local` means that the offer will be searchable by your channel and your sub-channels.

### Private
A Published Scope of `private` means that the offer will be searchable by only your channel.

## Variant Price
The price of the offer or variant in __cents__. Don't place any currency symbol there. For example, $9.99 would be 999.

## Variant Currency
The "Currency" of the offer or variant. Defaults to `USD`.

# Create your offer CSV file

For each offer, you'll need to decide if it is a simple offer or one with variants:

## Simple Offer (Does Not Contain Variants)

If you are uploading a offer that does not have variants, then enter all the fields (as described above) for the offer on the first line. On the following lines, enter just the handle.

## Offer With Variants

If you are uploading a offer that has variants, then enter all the fields (as described above) for the offer on the first line along with the URL for the first image. On the following lines, enter the handle. Then, skip the Title, Body (HTML), Vendor, and Tags. Fill out the rest of the variants details.

Once you've added all your offers, save your CSV file in UTF-8 format using LF-style linefeeds. If you are not familiar with encodings, please see your spreadsheet or text editor program's documentation.

