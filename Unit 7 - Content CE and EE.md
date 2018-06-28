## Content in Magento 2
  - let user communicate important message to customers
  - 3 types: blocks of content, pages of content, widgets (or content-driven apps)

    + Pages:
    + Widgets:
  - each of these content types can interact with and nest inside the others -> be a powerful feature in magento 2
  - In magento 1, blocks are referred to as "CMS static blocks" and pages as "CMS pages". CMS here stands for "Content Management System"
  - example:
    + catalog landing page is a *content block* that consists images, text, and links
    + Customer service page: is a *content page*
    + example of widget: display a collection of website's newest products

## Blocks
> Blocks:
    - the most basic unit in Mageto 2
    - it's a block of anything: text, code, images
    - may even contain other blocks, and other types of Magento 2 content

- Content Blocks are reusable: a single block may be inserted into any number of other blocks or pages
-> user can break down large pieces of content into smaller chunks which can then be used in multiple places

- In order to insert a content block into another block or page, Magento uses a specific mechanism called the CMS Static Block widget (using WYSIWYG editor)
- Content block can be nested (different with Content Page)
- Content blocks are managed in Side bar > Content > Elements > Blocks

## Pages
> Pages:
  - are used for content that is meant to be shown at one unique URL. This is information that users would access through a link provided on your site, or a link found via a search engine.
  - such a page is a good way to display information that is not updated often, such as company policies

- default Homepage of Magento 2 (LUMA) shows the full range of nested content in Magento 2: content *page* nested inside it is a content *block*, which has been inserted into the page using a CMS Static block *widget*
- Content Page is managed at Sidebar > Content > Elements > Pages (edit, delete, disable, enable)
- Content Page can not be nested

## Widgets
> Widgets can be thought of as a small "app" which is used to pull dta out of Magento's db and display it on the storefront
  - example: "Hot Sellers", can specified which products are pulled out, shows as grid or list, pagination or not, how often the product content should be refreshed

- To create widgets, select Sidebar > Content > Elements > Widgets > Add new
- Choose type which containt the word "link", meaning it extracts "links" from Magento db and insert them into pages or blocks throughout the site
- choose Content Block to be nested in widget

## Promotions in Magento 2
> 2 types of price rules: Catalog Rule and Cart rules
  - Catalog rule: affect product pricing shown to customers while browsing catalog
  - Cart rule: apply discounts to customer's order before they proceed to checkout

- 2 elements which apply to both catalog and cart price rules:
  + 1st - condition: which tell Magento which items should be discounted, or what other criteria must be met for a discount to be applied (any discount has no condition will be applied to all products since conditions are not required to apply a discount)
  + 2nd - Actions: define how the discount would be applied and what amount will be discounted

## Catalog Price rules
> Sidebar > Marketing > Promotions > Catalog Price Rules > Add New

## Cart Price Rules
> Sidebar > Marketing > Promotions > Cart Price Rules > Add New

- different with Catalog Price Rules:
  + 1st - has more 2 sections: "Labels" and "Manage Coupon Codes" (In EE, there is a third one: Related Banners)
  + 2nd - Rule Information section has 4 additional settings: "Coupon", "Uses per Coupon", "Users per Custome", "Public in RSS Feed"
  + 3rd - Conditions section has the set of attributes available for you to use: add additional group of "Cart attributes" is included to cover condition related to cart information (total quantity, payment method, shipping method)...
  + 4th - Actions tab: (if user want to offer only a free shipping promotion, you can select a value in the Free Shipping dropdown and leave the value in the "Discount Amount" field at zero):
    ++ "Maximum Quantity Discount" is applied to "field limits the quantity of a product that can qualify for a discount in one purchase"
    ++ The Free Shipping settings specifies whether free shipping will be offered for an order, and the whether free shipping will be applied to certain items only, or to the whole shipment. *This is the only way to designate that free shipping should be applied to an order*
  + 5th - The cart items section allows you to specify that a discount should only apply to specific items which match the conditions you specify

- Manage coupon code section is only displayed after rule is saved

## For Magento EE
> Content Staging, examning changes, updates, and campaigns

- schedules changes or updates
  + open a block > click Schedule new update

- customer segment: allow dynamically display content and promotions to specific customers, based on properties such as customer address, order history, shipping cart contents, and so on...
