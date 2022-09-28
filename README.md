# Using Symfony UX Twig Components in Shopware 6
Example for the use of symfony/ux twig components in Shopware6 plugin scope
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
## 👷‍ Contribution
Please help with code, love, shares, feedback and bug reporting.

## ⚖️ Licence
This plugin is licensed under the MIT licence.
