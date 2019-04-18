# Torque for Magento
Torque Payment Gateway for Magento 2

## Dependencies
- Magento2 This can be downloaded from [magento.com](https://magento.com/) or from cloning their [GitHub repo](https://github.com/magento/magento2)
- A webserver! preferably with the latest versions of PHP and MySQL
- A Torque wallet and torque-wallet-rpc This can be downloaded from [contribute-torque](https://github.com/contribute-torque/Torque/releases) or cloned from the [Torque-Project GitHub repo](https://github.com/torque-project/torque)

## Install Instructions
### Install with composer
Installing with composer is the easiest way to install this plugin.
- First, add this repo to your root composer.json file. The `"repositories"` section of your root composer.json should look like this:
`"repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/contribute-torque/torquemagento"
        }
    ],`
- Make sure that your `"minimum-stability"` is set to `"dev"`. It should look like this `"minimum-stability": "dev",`
- Then you can simply type `php composer require torqueintegrations/torquepayment`

## After Install
### Clear Cache
- Run `php bin/magento setup:upgrade`
- Flush cache with `php bin/magento cache:flush`
- Clean cache with `php bin/magento cache:clean`

### Setting-Up torque-wallet-rpc
- Start up your torque-wallet-rpc with the following command: `./torque-wallet-rpc --rpc-bind-port 20189 --disable-rpc-login --log-level 2 --wallet-file /path/walletfile`. It is recommended that you use the `--rpc-login` flag.

### Setup
- First, navigate to you site admin panel
-Within that admin panel, navigate to `Stores > Configuration > Sales > Payment Methods`.
- Under "Other Payment Methods" select "Torque Payment"
- Select "Yes" for "Enabled" and enter your torque-wallet-rpc address and port
