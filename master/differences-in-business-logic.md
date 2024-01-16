# Differences in Business Logic

Mustom benchmarked other ecommerce platforms like Magento. So most business logic is simular to these platform. But, some logics are different from others.



**Storefront and admin panel are decoupled from backend**

Frontend of Mustom is completely decoupled from backend. Yes! it is so called headless architecture. There's almost zero limitation to customizing your storefront, and you can build your store with any platforms or libraries like React, Angular, or Vue. Not only storefront, admin panel also decoupled from backend. That means you are free to change admin panel.

**SKU is not an unique value**

Unlike other ecommerce platforms, SKU is not a unique value in Mustom, because of multiple channel feature.

**Order is created as soon as checkout process has begin**

To simplify cart logic, order is created much earlier than other ecommerce platform. So cart feature don't need to handle additional logics like address and discount. (But there are some drawbacks. For instance, lots of abandon orders will be generated.

**Buy now feature**

Mustom provide built-in buy now feature. So, customer can place order very quickly.

Stock quantity is managed by both Redis and DB

**Guest order**

Guest user can place order. And they can track\&trace their order, and request cancellation. (If you want you can disallow guest order through admin panel.)

**Definition of Cancellation**

Some ecommerce platfrom define that 'cancellation' is reversal order of pending payment. But in Mustom, cancellation can be requested even if payment is made. The cancallation of Mustom is reverse order that has not shipped. (Admin user can set which order statuses can accept cancallation throught admin panel.)&#x20;

Cancellation and dispute scope

**Order/Dispute statuses are adderble and editable**

Like Magento, statuses are adderble, and editable. But each state should have at least one status.

**Replacement**

Mustom provide 'Replacement' as a resolution of dispute. If replacement request is completed, new order for this case will be generated automatically.

**Order by admin user**

Mustom offer admin order through admin panel. But, there is some limitation. Only offline  Real payment through payment service can not made, because of personal information issue.

Multiple Channels

The concept of multiple channel is a bit different from multiple store feature of other ecommerce platform.&#x20;

Multiple Currencies

**Product type**

Mustom only provide simple product at this stage. There's no feature to combine multiple products to one product. Instead you can use option feature.

Options and its stock

Some actions are not real-time

**Definition of module and app**

New features can be added by adding new modules, or apps. The difference between modules apps are 1) App is managed by service registry. So it is not registered in service registry, it will not working. 2) App provide its own menu on admin panel, and easy to install. &#x20;

**CMS features are quite simple**

CMS features like pages, and static blocks are quite simple. And there's no plan to add huge enhancement for this features. The reason behind this is, you can integrate other great content s management system, or digital asset management solutions for your storefront.
