# Differences in Business Logic

> Mustom benchmarked other ecommerce platforms like Magento. So most business logic is simular to these platforms. But, some logics are different from others.&#x20;

**Storefront and admin panel are decoupled from backend**

Frontend of Mustom is completely decoupled from backend. Yes! it is so called headless architecture. There's almost zero limitation to customizing your storefront, and you can build your store with any platforms or libraries like React, Angular, or Vue. Not only storefront, admin panel also decoupled from backend. That means you are free to change admin panel.

**SKU is not an unique value**

Unlike other ecommerce platforms, SKU is not a unique value in Mustom because of some reasons. However you can make it unique, if you want, by adding unique constraint of database table scheme.

**Order is created as soon as checkout process has begin**

To simplify cart logic, order is created much earlier than some ecommerce platform. So cart feature don't need to take care of additional processes like address and discount.

{% hint style="info" %}
But there are some drawbacks. For instance, lots of abandon orders will be generated.
{% endhint %}

**Buy now feature**

Mustom provide built-in buy now feature. So, customer can place order very quickly. Buy now button can be displayed both product detail page, and product list page (catalog page).

**Stock quantity is managed by both Redis and DB**

To prepare high traffic due to special promotions like exclusive sale, Mustom use Redis for stock deduction process of order creation. But basically, stock is stored in database. And it will be synced each other.

**Guest order**

Guest user can place order. And they can track\&trace their order, request cancellation, and even opening a dispute.

{% hint style="info" %}
If you want you can disallow guest order through admin panel.
{% endhint %}

**Definition of Cancellation**

Some ecommerce platfrom define that 'cancellation' is reversal order of pending payment. But in Mustom, cancellation can be requested even if payment is made. The cancallation of Mustom is reverse order that has not shipped.

{% hint style="info" %}
Admin user can set which order statuses can accept cancallation throught admin panel.
{% endhint %}

**Cancellation and dispute scope**

Cancellation and dispute can be requested by item level, and quantity level. Let's say you've ordered 3pcs of item A, and 1pc of item B. In this case you can request cancellation for 2pcs of item A.

**Order/Dispute statuses are adderble and editable**

Like Magento, statuses are adderble, and editable. But each state should have at least one status.

**Replacement**

Mustom provide 'Replacement' as a resolution of dispute. If replacement request is completed, new order for this case will be generated automatically.

**Order by admin user**

Mustom offer admin order through admin panel. But, there is some limitation. The feature can not support real payment through payment service, because of personal information issue. Only offline payment methods like bank transfer can be set.

**Multiple Channels**

I thought there were many of drawbacks behind multiple store feature and it will make overall logic complicated. The concept of multiple channel in mustom is a bit different from multiple store feature of other ecommerce platform. It short, it is minimal version of multiple store feature. Channel feature designed for multiple storefront(device) of customers in same country. It is not designed for multiple storefronts, or websites of multiple countries, and different localization.

**Product type**

Mustom only provide simple product at this stage. There's no feature to combine multiple products to one product. Instead, you could use product option feature for this case. You can set stock, and additional price for each option.&#x20;

**Product options and its stock**

Like I mentioned above, each product option can have their stock, and price.

{% hint style="info" %}
An item can have multiple options. For example a 'T-Shirt' can have 'Color', 'Size' as a option.
{% endhint %}

**Definition of module and app**

New features can be added by adding custom modules, or apps. The difference between modules apps are written below.

* App is managed by service registry. So it is not registered in service registry, it will not working.
* App provide its own menu on admin panel, and easy to install.&#x20;



{% hint style="info" %}
It is recommended to develop as a custom module, in case newly added features can be affect, or override, core modules.&#x20;
{% endhint %}

**CMS features are quite simple**

CMS features like pages, and static blocks are quite simple. And there's no plan to add huge enhancement for this features. The reason behind this is, you can integrate other great content s management system, or digital asset management solutions for your storefront.
