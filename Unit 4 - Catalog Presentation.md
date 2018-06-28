#Catalog Presentation
> - Layered Navigation
  - Category permission
  - Arranging Products in a Category
  - Visual Merchandiser
  - Product Relations
  - Rule-Based Product Relations

## Layered Navigation
> Layered Navigation is a collection of one or more attributes which act as filters that customers can use to narrow down their search for products.
(such as only want to see blue t-shirt that cost less than $30)

- It's enabled in Category's display settings section by setting the *anchor* option to "Yes". Only possible with attributes which have a catalog input type of *dropdown*, *multi-select*, or *price*
- Layered nav can be furthered configured within Stores > Settings > Configuration > Catalog > Catalog > Layered Navigation
- Setup layered Navigation:
  + condition: *one of the category's products must contain an attribute that is enabled to be used in layered navigation*
  + makesure Store > Attributes > Product > attribute details > Storefront Properties > Use in Layered Navigation (Can be used only with catalog input type Dropdown, Multiple Select and Price.)
    -> Filterable (with Result): tells Magento to display the attribute in a category's layered navigation menu only if there are current products with that attribute
    -> Filterable (no result): tells Magento to display the attribute even if there are no current products with that attribute
  + category should have attribute *Anchor* (category details > Display settings > Anchor) set to be Yes (by default it's no)

## Category Permissions (magento EE)
> - Setup categories permission and recommended Setup
  - Settings category permissions defaults
  - Cache and reindexing

- allow restricting which customer group can view a category
- For specific customer groups, user can:
  + Default them to a landing page, so that they can not view the category
  + Allow them to view the category, but deny the ability to search, see prices, or add items to cart
  + Give them full access to the category

- Admin > Stores > Settings > configurations > Catalog > Catalog > Category Permissions (any default settings in this page will be applied to all categories)
  + Set Enable to yes to activate category permission
  + You can override the defaults on specific categories by settings their permissions individually, but that options is only available after you have enabled the Category Permissions feature on this Configuration page

- Go to product > catalog > select category and click on category permission section. This settings only appears in individual category sections after you have enabled Category Permissions system-wide
- Click New permission > new permission option appear, user can specify which customer group or gourps this permission should apply to, then set that group's permissions for browsing the category, displaying product prices, and allowing customer to add product to cart (use parent means using parent category's permission)

### Reindex
  - Open terminal > go to Magento root folder
  - type bin/magento indexer:reindex then enter
  - Note: will need linux admin access and appropriate permission to do this.

## Arranging Products in a Category
  - Change position in Stores > Settings > Configurations > Catalog > Catalog > Storefront
  - bản thân ở front-end cũng có option cho user sort theo position, name, price

##Visual Merchandiser (Magento EE)
> it's a set of advanced tools for merchant
  - Configuring and using Visual Merchandiser
  - Category rules and automatic sorting
  - Adding and deleting products in a Category
  - Saving changes

- used for managing large product catalogs, functionality:
  + drag and drop positioning
  + sort and filter products in a category
  + add products by SKU, change product presentation
  + evcreate whole new categories quickly and easily

- Visual Merchandiser at Stors > Settings > Configuration > Catalog > Visual Merchandiser
- Category rule: each category can have only 1 rule, although each rule can have multiple conditions (new added product will be sorted to this category automatically)
  + logic of a rule: Attribute - logic operator - value

- Adding/Deleting product in a category:
  + in category, select add product > add product by sku
    + enter SKUs you want to add or delete from the category
    + Then click Assign to add to category and Remove to remove from Category, then Save and close
  + or search product by its name
    + then select the filter products
    + Save and Close the filter list > product will appear in product category list

- Automatic sorting: sort by một vài attribute, xong save lại category theo trật tự đó

## Product Relations
> - How to set up related products
  - Upsells and cross-sells

- Product relations are groupings of products which are used to encourage customer to buy addtional products similar or related to the one theyve already selected
- 3 types of product relations: related product, upsells, cross-sells
  + Related products: are products which are similar to each other or often purchased together. They are shown on the product detail page under the Product Details block        
  + Upsells: are products which are of better quality or newer than the product being viewed. They are shown on the product detail page under the product details block, which is beneath (ở trên) the product image. Ì a product has both related products and upsells, the upsells are shown beneath the related products
  + Cross-sells: are products which are shown to encourage the customer to make an impulse purchase before they complete their order. They are displayed on the shopping cart, beneath the order summary

- Path: Admin > Product > Catalog > Product Details > Related Products, Up-sells and Cross-sells section

### Rule-based Product Relations (Magento EE)
> - Rule-based product relations
  - Configuration
  - Creating and using rules:
    - Creating a rule
    - Inactivating a rule

- Tự động tạo product relation
- Setup:
  + Stores > Settings > COnfiguration> Catalog > Catalog > Rule-based Product relations, select each type of product relation (related product, up-sell product, cross-sells product)
  + Then Sidebar > Marketing > Promotions > Related products rules > Add Rule

- Tips/Best Practice: when creating or modifying a rule, it's a good ideae to first inactivate other rules pertaining to the same products, so that you can the new rule without having others interfere
- To turn off (or "inactivate") a rule, navigate to Marketing > Promotions > Related Product Rules, in the list of rules, find the rule that needs to be inactivated by rule name or rule ID (edit rule may require refresh the Cache and re-index manually)
