# UTeach UTDK 3 Customizations
This repository provides a common set of configurations for UTeach sites based on the UTDK 3 codebase.

Modules in this repository should be located in any given site's `web/modules/custom` directory.

The `composer.json` file includes the canonical version of sites' Composer dependencies, which currently include SAML functionality and the UTProf Add-on.

Upon initial creation of a *new* site that should use this configuration:

1. Copy the `composer.json` into the site project root
1. Copy the contents of `web/modules/custom` into its respective directory
1. Build the site via Composer as normal. After site installation, enable the `uteach_deploy` module should be programmatically.

Currently, enabling the deployment module will:

- Enable SAML functionality (users and the activation of SAML still need to be done manually)
- Enable the UTProf, UTNews, & UTEvent functionality
- Enable a UTeach-tooled version of the Content Editor role, which includes permissions for the Profile content.

Subsequent deployment updates should be added as update hooks to `uteach_deploy.install`, and those same changes should be added to the `hook_install()` implementation so that new sites will receive those changes.

## Sites this repository is currently used on
- UTeach Main: https://github.austin.utexas.edu/eis1-wcs/uteach-main
- UTeach Outreach: https://github.austin.utexas.edu/eis1-wcs/uteach-outreach

## Updates for existing sites 

```
austinclone uteach-main && cd ..
austinclone uteach-outreach && cd ..
austinclone uteach_utdk3_customizations && cd ..
cp -R uteach_utdk3_customizations/web/modules/custom/* uteach-main/web/modules/custom/
cp -R uteach_utdk3_customizations/web/modules/custom/* uteach-outreach/web/modules/custom/
cp uteach_utdk3_customizations/composer.json uteach-main/composer.json
cp uteach_utdk3_customizations/composer.json uteach-outreach/composer.json
cd uteach-main && composer update && cd ..
cd uteach-outreach && composer update && cd ..
```
