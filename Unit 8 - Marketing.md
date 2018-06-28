# Marketing
> SEO, Customer engagement, reward points, reports for marketing users

## SEO (Search Engine Optimization)
> URL Rewrites, Metadata, other SEO Tools

- control how search engines such as Google and Bing display results from your site

### URL Rewrites
- URL rewrite is used to replace one URL with another
- reason:
  + SEO friendly
- Type of redirect:
  + Permanent redirect (301 Redirect)
  + "No" Redirect: will not redirect customer's browser to a new URL, Magento still return the content that customer expects (redirect the customer to the correct Magento content without changing the URL in the browser bar)

- 4 types of URL rewrites:
  + Product Rewrites: specify a product url to be rewritten
  + Category Rewrites: specify the product's category path as part of the redirect so that when your customer clicks a search result with an outdated category path, the customer is redirected to the product via the current category path of that product
  + CMS (or "Content Page") Rewrites: allow users to update URLs for site pages which are not related to products or categories. For example, use them to redirect your company's old About Us or Shipping and Returns policy page URLs to their proper content
  + Custom Rewrites: allow you to redirect any of your website's URLs to external URLs. For example, if you have a blog or a corporate website which resides at a completely separate URL, you can use a custom rewrite to redirect your customers there
- Below Setting should be "Yes" to allow URL rewrite: STores > Settings > Configuration > General > Web > Search Engine Optimization, also make sure that the Apache server has Mod_Rewrite enabled
- URL rewrites are created in Admin using Marketing > SEO & Search > URL Rewrite > Add new
  + Choose type of URL rewrite
  + Request Path: is the URL requested by the customer -- in this case, an outdated or otherwise SEO-unfriendly URL
  + Target Path: is the URL Magento will use to retrieve the requested content
cut and pasted the reference URL from the Request Path field to the Target Path field, then fill in the request path with the old, SEO unfriendly-URL

### Metadata & Other SEO Tools
> how to customize keywords and other metadata to improve SEO, cover how Magento handles canonical URLs, search terms, site maps, Google API - for Google Ananlytics and Adwords

- Metadata is data used by Search Engines to evaluate the relevance of page content to user searches.
- Types of metadata: Titles, Descriptions, Keywords relevant to sites, pages
- side-wide or store-wide titles, descriptions, and keywords in the Sidebar > Content > Design > Configuration menu > select scope > click edit
  + go to Other Settings
  + expand the HTML Head section: titles, descriptions, keywords you specify here will appear at the top of every page in the scope you've selected
  + have any CSS or Javascript code which needs to be inserted into the head of every page on your site, you can use the "Scripts and Style Sheets"
  + additional code to be inserted at the end of every page can be placed in the "Miscellaneous HTML" field in the Footer section of same window
  + robots.txt file: is managed in Stores > Configuration > General > Design. Robots.txt is a text file paced on your web server which tells search engine whether they should access a file or directory or not
    ++ for example: if site is under development, robots.txt will tell the site present on the web for testing, while hiding its existence from search engines

  - Canonical URL: is an HTML element that helps webmasters prevent duplicate content issues by specifying the preferred (or "canonical") versions of a web page that a Search Engine should index
    + manage at: Stores > Settings > Configuration > Catalog > Catalog > Search Engine Optimization

  - Magento Search Terms: (Marketing > SEO * Search page): see what terms your customers are searching for and to make adjustments to search queries
    + khi người dùng gõ sai -> thêm từ gõ sai này vào search term để trỏ về expected product
    + tạo group of synonyms: Marketing > SEO & Search > Search Synonyms. Terms in synonym group tell the Search Engine to conduct an "OR" search for items that contain any of the terms.

  - Sitemap: Magento 2 XML sitemap functionality will auto create a sitemap XML file for search engines, which contains information about your products, categories, content pages
    + before it's generated, it should be enabled at Stores > Settings > Configurations > Catalog > XML Sitemap > Generation settings section
    + can specify the frequency at which file should be generated to ensure its contents are up-to-date
    + to create sitemap file, Marketing > SEO & Search  menu and click Add Sitemap
    + enter file name and path (should be accessible to google's web crawler)

  - Google Analytics and AdWords: Mage 2 integrates with both Google Analytics and Adwords: Stors > Settings > Configuration > Sales > Google API
## Customer engagement
### Product Reviews:
  - can enable/disable product review of guest customer
  - each review is approved or rejected by admin user: Marketing > User Content > Reviews

  - Persistent Shopping: saves some of a customer's information so that shopping cart and product comparisons can be accessed without the need to log in to the site again, all needs to do is check "Remember Me" box when logging in
    + Configured at: Stores > SEttings > Configurations > Customers > Persistent SHopping: enable/disable, set the length of time persistence should last, enable "Remember Me" (also wish list, product comparisons...)

## Reward Points (EE)
> is the way of increasing customer loyalty by rewarding actions such as: registering, making purchase, subscribing, review prodouct, inviting friend

- COnfigure: Settings > Configurations > Customers > Reward Points

## Reports for Marketing
> Search Term Reports, Best Seller Report, Coupons Report, Product in carts Report, Abandoned carts report

- Report > Marketing > show which search terms report, Most Viwwed product, Product in cart report
- Best seller report: Reports > Products -> in order to get a better look: pairing this report with Products Ordered report
- Coupon Report: Report > Sales
- Product in Cart: Report > Marketing
- Abandoned Cart Report: Report > Marketing
