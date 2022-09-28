# Using Symfony UX Twig Components in Shopware 6
Example for the use of symfony/ux Twig Components in Shopware6 plugin scope
## 🚀 How to install
This repository delivers a sample plugin for your Shopware 6 project to show you how to use Symfony UX Twig Components to get data into the Shopware 6 storefront.
### Composer install (recommended)
```
composer require barbieswimcrew/sw6-ux-plugin
bin/console plugin:refresh
bin/console plugin:install --activate MyPlugin
```
### Registering the TwigComponentBundle
By requiring the `barbieswimcrew/sw-6-ux-plugin` via composer the `symfony/ux-twig-component` dependency has been added, too. 

This package is an ordinary Symfony bundle. Thus, we need to add the TwigComponentBundle manually to the list of bundles defined in `config/bundles.php` which you'll find in your project's root directory.

Just add the following line to the array of registered bundles:

```
// config/bundles.php

<?php declare(strict_types=1);
$bundles = [
  ...
  Symfony\UX\TwigComponent\TwigComponentBundle::class => ['all' => true]
];
...
```

## 👨‍💻 Just have a look
Installation process might be done. Great! After refreshing the storefront in your browser window you should see an additional text output in the footer section which looks like this:
```
This shop offers you 15 products
```
And this is what the plugin actually does:
- Register a custom Shopware 6 plugin
- Register a so-called Twig Component `ProductCountComponent` which outputs the number of all active products in the database
- Extending the `storefront/layoutfooter/footer.html.twig` file and call the Twig Component via `{{ component('product-count', {'context': context}) }}`

### But why this example?
This example is inspired by the official Shopware 6 docs on how to [Add data to storefront page](https://developer.shopware.com/docs/guides/plugins/plugins/storefront/add-data-to-storefront-page). 

As you might see, the lines of code in this example are much less than in the Shopware docs "how to". 

In contrast to the Shopware example, the Twig Component implemented here can be used anywhere in the storefront because there are no dependencies on specific events, pagelets or API routes.

### Wanna find out more about Symfony UX Twig Components?
Please check out the official Symfony docs about Twig Components under [https://symfony.com/bundles/ux-twig-component/current/index.html](https://symfony.com/bundles/ux-twig-component/current/index.html)

## 👷‍ Contribution
Please help with code, love, shares, feedback and bug reporting.

## ⚖️ Licence
This plugin is licensed under the MIT licence.
