# who is this course for?
  - business professional
  - technical employee

# objectives
  - setup, manage catalog: catalog structure, product types, layered navigation, product relations
  - manage customer account and group
  - setup and use tax rules, payment and shipping mehtods, store emails, reports
  - create and manage orders, invoices, shipments, and credit memos
  - magento's marketing features to create promotions and coupons

# Admin ovewview
  - product, promotion, customer, orders, configure magento store
  - landing page, default is dashboard, see user guide for customizing dashboard or specifing different landing page
  - sidebar là main navigation, bấm vào sẽ show ra flyout menu, khi muốn làm gì thì hỏi yourself rồi đối chiếu ở sidebar

### 2 menu quan trọng ở sidebar là STORES menu và SYSTEM menu
    1. STORES: control configuration of store. Configurations: STORES > Configuration, configuration có 2 phần chính là Panels (left) và Sections (right)
      - Panels có topic và subtopic
      - Section: show nội dung của topic, subtopic ở panel

    2. SYSTEM: chức năng gồm
      - Transfer of data
      - Install extensions
      - user permission and other settings
      - system notification
      - server-side system management

### Data Grids: 2 loại Fixed Grid và Customizable Grid (các section chính có grid là sales, product, customer, marketing, content, report có grid)
  1. Fixed Grid: ví dụ Cart Price rules
    - column headers không thể thay đổi

  2. Customizable grid: ví dụ ở sales, catalog, content - cho phép add custom column
    - có thể save customzied view for later user
    - product's attribute sẽ có 1 thuộc tính là field đó có filerable hay không
    - các column có thể drag and drop theo trật tự người dùng muốn
    - save view sẽ save luôn cả filter lúc đó, custom view đc save theo user và chỉ available cho user đã save chúng

# Magento 2 Overall Application Architecture
- Application scopes
- Websites, stores, and store views
- Cache and index management
- Demonstration and exercises

Use single magento installation to setup multiple websites, stores and store views
Simple installation 1 website, at least 1 store, and one or more store views

2 cusotmer experience need to considered:
  - 1st: add đc sp từ nhiều catalog khác nhau vào cùng 1 cart (giống shopping mall - 1 single website có nhiều store)
  - 2nd: keep

### Application scopes
  - Show which level in magento data should be unique
  - global, website, storeview scope

### Websites, stores and store views
  - Website: unique shippieng and payment methods with options for unique base prices and URLS. It used for  large business such as different brands, different countries. basedURL can be optionaly configured per website
  - Stores: stores allow unique catalogs, but are managed from the same Admin. 1 Website can have many stores, customer can add products from multiple stores in to same cart
  - Store views: allow catalogs to be displayed in different languages and currencies

### Cache and Index Management
> System > Tools > Cache Management

- Cache is data to be remembered for later use
- Flush Magento Cache = Refresh all types of cache

> System > Tools > Index Management

- Update on Save: index will be updated whenever admin saves a record of corresponding type
- Update on Schedule
- can use Magento CLI (command line interface) to force reindex

#Users and Roles
- Create new user, new role
  - User có Interface Language, khi logi vào sẽ đc nhìn UI ở language này
- Assign role permission
- Magento EE: Role scopes

### Role scopes
  - Role scopes define how configuration settings affect your installation. The scopes of settings can be:
    - Store view
    - Website
    - Global
  - The ability of assigning scope to role is exclusive feature of Magento EE
  - Reason to have this feature:
    - prevent problem, restrict different teams' access privileges (manager team from US website should not access to manager team from UK website)
  - How?
    - In Role Resouces, there is an option Role scopes (dropdown list: All or custom). Custom means selecting specified website and storeview, user can only access to selected one.
    - Next select role's resource normally
  > Role scopes allow you to restrict your user's acess to different parts of your Magento 2 EE store

# Setup for Business
- Local settings: Stores > Configurations > General: timezone, language, for setup new wwebsite
- Store Information: stores > settings > configurations > general > general > store information
- Secure and unsecure URLs: basedURL and based Link url, note that it has scope is store view > different domain for store view
- Website title: Sidebar > Content > Design Configuration
- Website logo: Sidebar > Content > Design Configuration
- Website copyright information: Sidebar > Content > Design Configuration
- Store communication email logos: Sidebar > Content > Design Configuration
- Store email addresses: Stores > Settings > configurations > GENERAL > Store Email Addresses
- Invoice, shipment, and credit memo logos: stores > settings > Configurations > SALES > Sales > Invoice and Packing Slip design
- Currency options
  - Base Currency: is primary currency that is used for online transaction
  - Default Display Currency: is currency that is used for displaying pricing on store
  - Allowed currencies: are currencies in which you allow product's price to be displayed to customer as well as accepted payment in store. When selecting allow currencies, make sure to select the primary currency (base currency), this is option to configure if there are multiple currencies accepted in store
- Currency rates: Stores > Currency > Currency Rates
- Demonstration and Ex
