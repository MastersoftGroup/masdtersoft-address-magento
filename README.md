# mastersoft-address-magento
Mastersoft Address Autocomplete extension or module for Magento2

Go to your Magento2 Home (usually is in `/var/www/html` directory).

## Composer Installation
Make sure git is installed: `apt-get install git`.

```bash
/var/www/html# cp composer.json composer.json.old
composer require mastersoft/address-widget
php bin/magento module:enable Mastersoft_AddressWidget
php bin/magento setup:upgrade
```

If successful, you should find the module source in `/var/www/html/vendor/mastersoft/address-widget/` directory.

Verify `Mastersoft_AddressWidget` module has been installed properly: `php bin/magento module:status`. It should be listed in the  Enabled Modules.

Next is to [configure Mastersoft Address Configuration](#configuration).

## Manual Installation
  1. Download the zip file in `ZIP` directory.
  2. Unzip it in your Magento2 Home directory, it will merge with existing directories and files.

You should find the module source in `/var/www/html/app/code/Mastersoft/AddressWidget/` directory.

```bash
/var/www/html# cp composer.json composer.json.old
php bin/magento module:enable Mastersoft_AddressWidget
php bin/magento setup:upgrade
```

Verify `Mastersoft_AddressWidget` module has been installed properly: `php bin/magento module:status`. It should be listed in the  Enabled Modules.

Next is to [configure Mastersoft Address Configuration](#configuration).

## Installation Troubleshooting

If the page is blank or encounter permission error or other errors in the store homepage.
```bash
php bin/magento cache:clean
php bin/magento cache:flush
chown -R www-data:www-data var/cache
chmod -R 777 app/ var/ pub/ generated/ 
rm -rf var/cache/* var/page_cache/*
```

## Configuration
In Magento2 Admin Dashboard of your Store: `Stores` -> `Configuration` -> `Services` -> `Mastersoft Address`.

**Get your FREE licence key [here](https://hosted.mastersoftgroup.com/console/#/).**

To configure the Widget Options, here is the full list of available [FeatureOption](http://developer.mastersoftgroup.com/harmony/api/object/address.html#FeatureOption).


## Disable/Enable Module
There are 2 ways to disable/enable this module:
1. In [Mastersoft Address Configuration](#configuration): `Enable Module` field OR
2. In Magento Command
   ```javascript
   // Disable module
   php bin/magento module:disable Mastersoft_AddressWidget --clear-static-content
   
   // Enable module
   php bin/magento module:enable Mastersoft_AddressWidget
   
   php bin/magento setup:upgrade
   php bin/magento module:status
   ```

## Composer Uninstallation
**This will work only if the module has been installed using Composer.**

```bash
php bin/magento module:disable Mastersoft_AddressWidget --clear-static-content
php bin/magento module:uninstall Mastersoft_AddressWidget -r -c
php bin/magento setup:upgrade
composer remove mastersoft/address-widget
```


## Manual Uninstallation

```javascript
php bin/magento module:disable Mastersoft_AddressWidget --clear-static-content
php bin/magento setup:upgrade

// If was installed using Composer
rm -rf vendor/mastersoft

// If was installed manually
rm -rf app/code/Mastersoft
```

In magento2 database:
```sql
DELETE FROM setup_module WHERE module='Mastersoft_AddressWidget';
DELETE FROM core_config_data WHERE path like 'Mastersoft_AddressWidget/%';
```

## User Guide
For more detail documentation, please refer to this [User Guide](user-guide.md).


## Support
If you have any questions or issues with this module, open an issue on [GitHub](https://github.com/MastersoftGroup/mastersoft-address-magento/issues). Alternatively you can contact us via e-mail or via our website below.

E-mail: <support@mastersoftgroup.com>

Homepage: <https://www.mastersoftgroup.com/>


## Copyright
(c) 2018 Mastersoft

