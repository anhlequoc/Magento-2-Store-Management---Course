##Settings Up Taxes
> - Tax Management
  - Tax Classes
  - Tax Rates
  - Tax rules
  - Tax configurations, calculation options, shipping origin
  - Configuring tax display
  - Creating tax rates and tax rules

- taxes are calculated based on the combination of two criteria: the products in an order, and an address of some kind - either your business's shipping origin address, or a customer's shipping or billing address
  + tax rate is applied to a product or products depending on the address. For the purposes of tax definition, products and customers that should be considered for specific tax rates are associates with product and customer tax classes
- tax rules define the rate or rates that should be applied to each combination of customer and product
- Store > Taxes > Tax rules or Store > Taxes > Tax Zones and Rates
- define default customer group and default tax class: Stores > Settings > Cofigurations > Customer > Customer configurations > create new account options
- *Each tax rule must have a unique combination of classes and rates*
- Setting which define tax calculation and display are located at Stores > Settings > Configuration > Sales > Tax section

##Payments and Shipping
> Payment providers and Shipping carriers are either API-based or manually configured
  - API-based payment and shipping options are dynamically updated with information from their respetive providers and carriers, while manually configured options need to be actively maintained by an Admin user

###Payments Provider
- configured in Stores > Settings > Configuration > Sales > Payment Methods
- some popular API-based payment provider: Braintree, Paypal, Authorize.NET...(others on Magento marketplace)
- some manually configured payment methods: Check and Money Orders, Cash on Delivery, Purchase Order, Bank Transfer...

###Shipping Carriers
- both API-based shipping carriers and manually configured shipping methods are configured in Stores > Settings > Configuration > Sales > Shipping Methods
- some manually configured shipping methods: Free Shipping, Flat Rate, Table Rates
  + Flat rate: allow user to specify a fixed price to ship items to customer. The fee can be per item or per order, as required. The type can be set to "None", in which case the flat rate method appears as a shipping option, but with a price of zero, this is essentially the same as offering free shipping via a flat rate method
  + Table Rate: use an uploaded spreadsheet called a shipping rate table to specify rates based on certain conditions: Weight vs Destination, Price vs Destination, Number of Items vs Destination (should use storeview scope for each website in different countries)
  + Free Shipping

##Checkout Experience
  > - Guest checkout, reorders, totals display
    - Options for gift messages
    - Terms and conditions

- Locate a Stores > Settings > Configurations > Sales > Checkout
- Sort order of subtota, discount...: Stors > SEttings > configurations > Sales> Sales > Checkout totals Sort Order
- Gift: Stores > settings > Configurations > Sales > Sales > Gift Options
- Term and Condition is enabled in Stores > Settings > Configurations > Sales > Checkout > Checkout Options. They are managed in Stores > settings > Terms and COnditions

###Gift Wrapping and Gift Receipts (EE)
> Stores > Other settings > Gift Wrapping and Gift Receipt

##Store Communications
> Marketing > Communications > Email Templates

- Configurations: Stores > Settings > Configuration > Sales > Sales Email

## Business Operations Reports
> Reports section

- In order to see the most current reporting data, you must refresh the statistics for the reports you want to generate

## Fulfillment Process
> - consists 4 main stages: orders, invoices, shipments, and credit memos
  - each of this main stage is configured at Sales > Operations (Orders, Invoices, Shipments, Credit Memos)

- Orders are the base unit of fulfillment in Magento 2, all of the other fulfillment units - invoices, shipments, and credit memos - are connected to individual orders
- depending on Payment gateway settings, funds can either be authorized and captured at point of sale (thời điểm thanh toán), or authorized first and captured later. By default, Magento instructs the payment gateway to capture funds when an invoice is created, however, you can change this settngs as needed for individual payment providers, in most cases
- if user both authorize and also capture funds at point of sale, Magento will automatically create an invoice when an order is placed
- partial invoice: specified the number of item which is invoiced
- both user business's shipping origin address and your store information need to be populated before shipping labels can be generated:
  + Shipping Origin Address: Sales > Shipping SEttings > Origin
  + Store Information settings in Stores > Settings > Configuration > General > General > Store Information

###Return
- Credit memo's purpose is to refund a purchase, *it should not be confused with an RMA (or Return Merchandise Authorization), whose purpose is to facilitate the physical return of merchandise* (RMA is a feature of Magento 2 EE)
- Creating a credit memo from the order record will trigger an offline (manual) refund regardless of payment method
- To trigger an online (automatic) refund through a payment provider, you need to initiate the credit memo from the invoice
- Order which is partially refunded will still keep its status

### RMA (EE)
- RMA - Return Merchandise Authorization - used to refer to the processes and procedure whereby a business allows customers to return merchandise for a refund a store credit
- Flow: customer contacts the merchant to request a refund. If the request is approved, a unique RMA number is assigned to identify the returned products
- RMAs can be issued for Simple, Grouped, Configurable, and Bundle product types. However, RMAs are not available for virtual, downloadable product and gift cards
- Configure RMA: Stores > Settings > Configurations > Sales > Sales > RMA settings

- Returns Attributes: are data variables created specifically for use during the Returns process.
  + Some are system variables used by Magento; there are hidden from the customer and used only by the CSR or other Admin staff
  + Other returns attributes create fields in the Returns form that the customer fills out
- User can create custom Return Attribute at Stores > Attributes > Returns > Add new Attributes
- To view Return Request, CSR should go to Sales > Returns:
  + Customer create Return Request
  + CSR view in back-end and approve
  + CSR generate a Return Shipping Label for the customer, specific details depend on the carrier, general is:
    1. General Infomration section of Return Request, CSR clicks Create Shipping Label
    2. CSR completes Return Request in form (package weight, size)..., the label is create as a PDF, and can be sent to customer
    3. once Customer is notified that the return has been approved, and has received the shipping label, the customer return items
    4. After being notified that the returned item have been received, CSR fills out the Returned field in the Returned items section with the number of items received, and then changes the status to Return Received and clicks Save (status is updated both in Admin and customer's My Return window)
    5. When satisfied that the returned item is acceptable, the CSR goes back once again to the Return Items section, updates the Approved field with the number of items approved, sets the Status to Approved, and clicks Save -> status of Return is auto updated as Process anded Closed both in Admin and customer's My return windows
