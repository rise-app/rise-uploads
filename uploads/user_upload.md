# User CSV file format
A User is a role based RiSE account with a username/email and a password.

The first line of your user CSV has to include the field headers described below with each separated by a comma. Subsequent lines in the file should contain data for your user using those same fields in that exact same order. Here's a description of each field:

## Email
User Email address

## Name Prefix (can be left blank)
User's Name Prefix eg. Mr., Mrs., Lord

## First Name (can be left blank)
User First Name

## Last Name (can be left blank)
User Last Name

## Name Suffix (can be left blank)
User's Name Suffix eg. Jr., Dr.

## Phone (can be left blank)
User Phone Number

## Accepts Marketing (can be left blank)
If the User has opted into receiving promotional emails. Eg. TRUE, FALSE

## Tags (can be left blank)
Comma-separated list of tags used to tag the user. For example, `tag1, tag2, tag3`.

## Roles
This is a list of Roles that the user possesses for the channel. Eg. admin, manager, registered.  All users receive the `registered` role by default

## Customers(can be left blank)
Comma-separated list of customer emails for the user. For example, `example@example.com, example1@example.com, example2@example.com`. If the customer with the associated email does not exist, one will be created.

