# UTeach UTDK 3 Customizations
This repository provides a common set of configurations for UTeach sites based on the UTDK 3 codebase.

This should be added to a standard installation of UTDK 3 via `composer require uteach/uteach_utdk3_customizations`

After site installation, enable the `uteach_utdk3_customizations` module.

Currently, enabling the deployment module will:

- Enable Enterprise Login functionality (users and the activation of SAML still need to be done manually)
- Enable the UTProf, UTNews, & UTEvent functionality
- Enable a UTeach-tooled version of the Content Editor role, which includes permissions for the Profile content.

Subsequent deployment updates should be added as update hooks to `uteach_deploy.install`, and those same changes should be added to the `hook_install()` implementation so that new sites will receive those changes.

## Sites this repository is currently used on
- UTeach Main: https://github.austin.utexas.edu/eis1-wcs/uteach-main
- UTeach Outreach: https://github.austin.utexas.edu/eis1-wcs/uteach-outreach
