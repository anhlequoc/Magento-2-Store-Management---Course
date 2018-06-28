#Module overview
> - Customer Accounts and Wish Lists
  - Customer Management
  - Customer Attributes (EE)
  - Gift Registries (EE)

##Customer Accounts and Wish Lists
- Key areas: Account information, address book, orders, and wish list
- User can setup to not display option in left sidebar, such as "My downloadable products" (almost functions can be setup by this way, others will require editing CSS, magento's template)

##Gift Registries (EE)
- Gift Registries are a way for customers to inform friends and family about items they might want or need from your store, as presents, or for a special occasion
- customer of website can:
  + create gift registries and then share them with friends and family. Magento keep tracks of registry items purchased and quantities remaining.
    For instance, if a gift registry lists 8 sets of dinner plates, Magento keeps track of the number of sets purchased and the number still needed to fulfill request
  + the Gift registry's owner can add products to the registry by transferring them from their shopping cart

- Steps of creating gift registry:
  + go to account -> navigate to Gift Registries on sidebar, here customer can have multiple lists of gift registries
  + create Add New list of gift registries
  + Select Gift Registry type (birthday, baby registry, wedding)
  + Then display the form of Gift Registry, each type of Gift Registry has its own form (separated with other types)
  + after form is filled completely, the new list of gift registry will display on first page

- Adding items to a Gift Registry: go to cart -> add all items to gift registry (only has this function)
- Share Gift Registry:
  + add sender's name, sender's message
  + add invitee, add invitee's name, email
  + Invitee receive an email with a link to the site where they can view the registry and  make purchases from it

- Setup store:
  + Make sure Gift Registry is enabled by going to Stores > Settings > Configurations > Customers > Gift Registry Enable
  + Then set the "maximum registrants" - are number of people who will be informed of purchases
  + set the email's template and email's sender to be used for each section ("General Contact" is the primary email contact address for the store)
  + "maximum Sent Emails Threshold" refers to the number of repeat emails sent to friends and colleagues, setting this value so that customers are not tempted to "spam" their friends with requests

- After enabling and configuring Gift Registry, shop owner can start modify gift registry types and create new whole types (new type will appear in dropdown list of customer's account)
- Steps in back-end to create new registry type:
  + go to Stores > Other Settings > Gift Registry
  + click Add Gift registry type, or edit current type
  + enter General Information
  + enter attributes fields: code, input type, attribute group (such as Event Information, GIft Registry Details, Privacy settings), label, is required?, sort order

## Customer Management
- This task (customer management) is often handled by CSR (Customer Service Representative)
- disable wish list: Stores > Settings > Configurations > Customers > Wish List > General Options

### Customer Group:
> - Customer groups are managed in Stores > Other Settings > Customer Groups
- the primary purpose of a customer group is to provide a way to assign a tax class to a set of customers in order to calculate taxes based on their shipping or billing address
- 2nd purpose: use to offer certain promotion (price) to specific groups of customers

## Customer Attributes (EE)
> for better understanding: compare it with product attributes

- Customer Attributes are the data variables that Magento stores about your customers - things like "email address" and "date of birth"
- User can create custom customer attribute
- Steps to create new customer attributes:
  + Stores > Attributes > Customer (not Attribute Set)
  + Click Add New Attribute
  + fill detaila and click Save
