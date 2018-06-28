#Products
> 5 modules
- Understanding product types
- Product Creation Basics
- Product Creation
- Importing and Exporting Products
- Gift Card (EE)


## Understanding Product Types
> 7 types:
- Simple (Product custom option)
- Grouped
- Configurable
- Bundle
- Virtual
- Downloadable
- 1 type of Magento EE: Gift Cart

###Simple Product
  - unique sku and  unique inventory
  - grouped, configurable, bundle are make of simple products (inventory)
    + In case configurable has an option as simple product out of stock, the option will be dimmed, configurable still available
  - cart show single line of simple product with no other information

### Grouped Product
  - display a fixed set of multiple simple products in one page
  - only thing need to be specified to simple product's quantity

### Configurable Product
  - consists a variations of simple product, each variation is a simple product
  - does not have inventory, replace by inventory of simple product
  - price **show ở storefront** là thằng price nhỏ nhất của simple product
  - if none of configurable product variations have quantity or are set to be in stock, it will not be displayed on the storefront
  - show ở cart là single line kèm theo các option đã chọn

### Bundle Product
  - Bundle product can be fixed or dynamic
    + Fixed: show a fixed price, sku, weight for entire bundle product
    + Dynamic: show price, sku of bundle's associate simple products
  - In admin > order:
    + fixed: show a single sku of bundle product
    + dynamic: show both sku of bundle and sku of element selected by customer

  - In shopping cart: show as single line item và các element, number của single product đã chọn

### Downloadable Product
  - allow customer to purchae digital information such as songs, ebook...
  - consits link to download media product, this link can be stored and accessed by Magento or external link
  - cart: show as single line item with the downloadable access listed under product's title

### Virtual Product
  - has no physical or information item, just a service such as warranty
  - cart: show as a simple product

### Product Custom Options
  - All product types except grouped product, user can configure product custom options

## Product Creation Basics
> - About Products
  - Basic settings
  - Advanced Settings
  - Product attributes
  - Attributes sets and attributes group
  - demo

### Product's Image
  - Product has 3 image sizes
    - Base Image: show on product details (largest)
      - Image categories (appear in product details > image slider): show alternate images of based image
    - Small Image: show on categories landing page
    - Thumnail Image: show on cart (smallest)
  - Magento 2 auto resize these 3 image types, user should upload the optimized size and resolution of image

### SEO
  - url key is created auto based on product's name
  - change url key will make Magento auto create new link redirect to old key

### Attributes sets and attributes group
  - System attribute không edit được bởi chủ shop, other có thể edit được
  - ở các attribute có type là multiple select hay dropdown, có thể chọn các options được show, chỉnh thứ tự các otpion, nhãn của nó ở các enabled store view
  - attribute phải được add vào attributes set để dùng
  - create new attribute set:
    - Based On (default, top, bottom, ...): new attribute set cần dựa trên 1 pre existing one để kế thừa các attribute giống nhau
    - sau đó dùng Attribute Set screen để assign attribute vào attribute set, attribute ở attribute set được xếp vào các group

### Create Simple Product
### Create Configurable Product
  - Khi tạo Coonfigurable product, cần nhớ 2 thứ:
    1. Attribute cần set, thuộc tính "Catalog input type for storeowner" của attribute này cần là Dropdown, (có thể ko phải multiple select, visual swatch, Text swatch - chưa chắc) (swatch is Values of Your Attribute) và phải chứa các options value
    2. A configurable attribute (color) must have its scope set to "Global" within its "Advanced Attribute Properties" section (refer Magento user guide for more details)

  - Steps create new configurable product:
    1. Create Product as normal (by default it's Simple Product)
    2. After filling out required infomration fields, we can convert it to a configurable product simpley by clicking the Create Configurations button
    3. Vào wizard tạo configurable option > select attribute mà configurable product sẽ dùng. Magento 2 list toàn bộ configurable attribute của hệ thống, không theo attribute set
    4. select attribute value từ các attribute đã chọn ở bước 3, có thể sắp xếp trật tự các attribute xuất hiện ở product
    5. Specify image, price
    6. Review simple sku được tạo cho configurable product này và có thể thay đổi thêm ở đây

## Importing and Exporting Products
> System > Data Transfer > Import or Export

### Exporting
  - Entity is Product > ấn continue
  - muốn exclude field nào thì check vào checkbox
  - csv file: product are listed in rows, product's attributes are listed in columns
    categories of product are separated by slash (/)

### Importing
  - all product types can be imported with Magento 2
  - 3 options: add/update, replace, delete
    + Add/Update: adds new products and updates values for existing product records
    + Replace: has similar functionality as above, first it clears all data from all of the fields containing values for the product, and then repopulates the fields with the data from the file. It's useful when user wants to chagne a value which can not be altered via the Admin, such as a product's type or attribute set. The "Replace" behavior allows you to effectively erase everything and then fill it in again
    + Delete: aceepts a single column of SKUs and will delete the listed products from the catalog.

## Gift card (EE)
> - Uses for gift card
  - Types of gift cards
  - Creat gift card products
  - Gift card account

  - Reason:
    + allow customer purchases gift card as present for others
    + alternative to reward point or store credit (in RMA process)
  - Types:
    + Physical: a printed gift card to me mailed (posted) to the recipient
      -> has stock quantity
      -> use when have physical stores, gift card bring more traffic to physical stores
      -> use when user wants gift card to be used in other physical stores, where other merchants might give discounts or special offers
      -> use when user wants to offer customers the option to give physical cards as gifts - to slip into birthday cards, for instance
      -> physical card can contains a code that can be used to purchase item online
      -> customer when purchasing gift card only need to provide street address, not email address since card is sent only via physical mail
    + Virtual: virtual electronic card designed to be emailed to the recipient
      -> sent via email to recipient
      -> khoong theer set value cho stock và stock availibility
      -> use when have exclusively online busisness
      -> use when some products are exclusively available online
      -> customer need to provide recipient email's address, not street address, since card is sent via email
    + Combine: a gift card that has the attributes of both a physical and virtual card
      -> have stock quantity, the stock is decremented after each sale
      -> it's possible to email the card and redeem online
      -> use combined gift card if you want to allow the customer to send gift card via both email and regular mail (post)
      -> customer needs to enter both recipient's street address and email address, since the card is sent both via email and physical mail

    - when customer purchases a gift card product, magento creats a gift card account and assign it a code from the code pool (Marketing > Promotions > Gift Card Accounts)
    - when customer uses a gift card for a purchase, the balance stored in the account is decremented
    - Gift card amount phải được dùng hết trong 1 lần, nếu thiếu thì dùng thêm payment khác, thừa thì thôi
    - Steps to create gift card:
      + Product > Catalog > Add Product Gift Card
      + Select attribute set as Gift Card
      + pricing of a gift card: can offer customer a fixed amount or set amount from minimum and maximum number
      + Gift Card appear in list of product (Product > Catalog )

    - Steps to create Gift Card Account:
      + Marketing > Gift Card Account > Create Gift Card Account
