# UTeach UTDK 3 Customizations
This repository provides a common set of configurations for UTeach sites based on the UTDK 3 codebase.

Modules in this repository should be located in any given site's `web/modules/custom` directory.

Upon initial creation of a new site, the `uteach_deploy` module should be programmatically enabled in the LIVE environment. Currently, this repository:

- Enables the UTProf functionality
- Enables as a UTeach-tooled version of the Content Editor role, which includes permissions for the Profile content.

Subsequent deployment updates should be added as update hooks to `uteach_deploy.install`, and those same changes should be added to the `hook_install()` implementation so that new sites will receive those changes.