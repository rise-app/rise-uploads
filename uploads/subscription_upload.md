# Subscription CSV file format
A Subscription is a Recurring Order

The first line of your product CSV has to include the field headers described below with each separated by a comma character `,`. Subsequent lines in the file should contain data for your product using those same fields in that exact same order. Here's a description of each field:

## Customer
The email address of the customer

## Billing Model
The model_name for this subscription, if emtpy, a model will be created.

## Unit
The enum unit for the subscription eg. `w`, `m`, `y`

## Interval
The number foreach unit to occur eg. `1`, `2`, etc..

## Offers
The comma separated list of offer handle, a colon, the sku of the offer variant, a colon, and the quantity
eg. best-product:sku1234:1,another-product:sku5678:2,

## Active
True or false, defaults to True
