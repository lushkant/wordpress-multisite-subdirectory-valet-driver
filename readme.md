# WordPress Multisite Subdirectory Valet Driver (Latest/Updated For Valet v4+)
A custom driver for [Laravel Valet](https://laravel.com/docs/10.x/valet#custom-valet-drivers) that adds compatibility for WordPress multisite installs that use the subdirectory configuration.

This is a fork of a Valet Driver made by [Objectivco](https://github.com/Objectivco/WordPressMultisiteSubdirectoryValetDriver/tree/master). But that driver got outdated and didn't work for the latest Valet, so I fixed it and thought why not publish it for anyone else who is looking for the same, without needing to look into the What and Whys of Laravel Valet.

## Installation
1. `git clone https://github.com/lushkant/wordpress-multisite-subdirectory-valet-driver.git`
2. `cd wordpress-multisite-subdirectory-valet-driver`
3. `cp WordPressMultisiteSubdirectoryValetDriver.php ~/.config/valet/Drivers`
4. Make sure your wp-config.php file has at least one of `WP_ALLOW_MULTISITE` or `MULTISITE` constants defined.
5. Celebrate the pain you just avoided!

## Installs with WordPress root files in a subdirectory
If your install has WordPress root files in a subdirectory (such as a submodule), simply change the class property `$wp_root` from false to the root directory name.

## Caveats
This only works with the subdirectory URL scheme. If you have a subdomain site setup with Valet, this driver will probably break it. You'll need to modify the `serves()` function to prevent this driver from handling the request.