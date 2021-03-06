## malscan

#### Version 1.8.1
*Release: Nov 26, 2018*
* Fixed: Malscan now provides better information when attempting a run with the lockfile present.

#### Version 1.8.0
*Release: Oct 15, 2018*
* New: Added a proper `CHANGELOG.md` file.
* Updated: Substantial Installer update
    * Fixed: Installer was referencing bad download URLs. Fixed.
    * Fixed: `which` may not be available in some distributions. Changed to `command -v`
    * Updated: Added support for Ubuntu 16.04 and 18.04.
    * Updated: Added support for Debian 8 and 9.
    * Updated: Added support for Alpine Linux.
    * Updated: Substantially refactored Installer code to remove duplicate lines.
* Updated: Fixed some non-portable code in the mimescan function.
* Updated: Cleaned up some shellcheck notices in the avscan function.

#### Version 1.7.2-1
*Release: May 15, 2018*
* Fixed: Updater will now properly pull the malscan core version from the right git branch.
* Updated: Updated all documentation to point to new docs site and new 1.x branch

#### Version 1.7.1
*Release: April 20, 2018*
* New: Tripwire detection mode
* Fixed: Corrected permission issue on log file. (fixes #15)
* Updated: Changed the save path for the Tripwire whitelist file

#### Version 1.7.0
*Release: March 22, 2018*
* Feature: Lock files are used to ensure multiple runs of malscan don't stack.
* Feature: Configuration options can now be viewed using the malscan -c command. (fixes #10)
* Feature: Configuration options can now be set using the malscan -s OPTION value command.
* Fixed: malscan will now correctly check for sudo.
* Fixed: malscan will now check to see if the user is in the malscan group, in lieu of being run as sudo.
* Fixed: Notifications are now sent in a more spam-checker-friendly format, reducing issues with notifications ending up in the spam folder.
* Updated: malscan will now use its own freshclam.conf file and /var/lib/malscan signatures directory, to prevent conflicts with ClamAV.
* Updated: The malscan file structure has been updated to conform with the FHS. (fixes #7)
* Updated: Rewrote the install.sh script to support Fedora, Debian, and CentOS/RHEL 7.
* Updated: Created RPM packaging for CentOS/RHEL 6, 7, and Fedora 26/27. (fixes #8)
* Updated: New exhaustive build testing CI pipeline for automated malscan testing.
* Removed: Removed whitelisting and tripwire scanning until it can be re-worked in a later release.
* Removed: Removed reporting until it can be re-developed in a later release.
* Removed: Removed Ubuntu/Debian support while working on packaging.

#### Version 1.5.3
*Release: September 4, 2015*
* Bugfix: Corrected text coloring on the update.sh script to terminate properly
* Bugfix: Removed some excess text from the Mimescan
* Updated: All malscan runs now include the current Malscan version and the time that signatures were last updated.
* Updated: Unified logging files for all scantypes into a single scan log for each scan
* Feature: Added new -u update functionality, which updates both the core application as well as the signatures

#### Version 1.5.2
*Release: July 13, 2015*
* Bugfix: Corrected the Mimetype scan to properly ignore files listed in conf.malscan

#### Version 1.5.1
*Release: June 16, 2015*
* Bugfix: Corrected a bug with update.sh causing a fatal error.
* Updated: Added output identifying when different scan types are starting, for more verbose and informative output.
* Updated: Incremented the version in malscan.sh
* Updated: Removed the version information in the comment header in install.sh, added a Since version header instead.
* Updated: Removed the output text from the freshclam updater, which was getting too messy.
* Updated: Added a warning in update.sh indicating the now-silent freshclam update portion can take a long time.

#### Version 1.5.0
*Release: June 1, 2015*
* Feature: Added automated whitelisting of file trees for known clean files (such as imports from development enviroments or fresh installs)
* Feature: New Tripwire scanning mode. Identifies any files that have been changed or did not exist from the whitelist reference. Excellent for static sites or minimally changing applications.
* Feature: New installer.
  * New installer is compatible with and fully tested on CentOS 6, CentOS 7, and Ubuntu 14.04.
    * Installer may work with other 6.x and 7.x RHEL derivatives as well as Ubuntu 12.x, 13.x, 14.x, and 15.x, however these are officially unsupported.
    * If you run into issues with any non-supported Operating Systems, please submit a Github issue so that I can correct it and add that OS to the supported list.
    * Added package installation sanity checking, to ensure everything is set up properly
  * New installer may work with other RHEL derivatives as well as RHEL/CentOS 5
* Updated: Mimetype scanning to add additional filetypes to the scan.
* Updated: A substantial number of prompts, both in text and color.

#### Version 1.4.4
*Released: May 6, 2015*
* Bugfix: Corrected an issue with notifications not being sent because there was no way to specify receiving email addresses. Fixed in conf.malscan-blank.
* Bugfix: Corrected an issue with whitelisting not working properly. It should now function correctly, and is working in test RHEL 6 and CentOS 7 testing environments.
* Special Note: The changes to conf.malscan-blank will need to be manually added to any active conf.malscan files.

#### Version 1.4.3
*Released: May 5, 2015*
* Bugfix: Corrected a logging path issue. All log files will now be correctly generated in the 'log' directory inside your chosen path in conf.malscan
* Bugfix: Corrected the URL for the custom virus definitions
* Feature: Included freshclam updates within the cron_update.sh script

#### Version 1.4.2
*Released: April 09, 2015*
* Bugfix: Corrected an error with the AV-Scan whitelisting functionality, causing malscan to ignore whitelistings. It is now working properly.

#### Version 1.4.1
*Released: March 18, 2015*
* Bugfix: Proper detection of the malscan program path when run as a cronjob or from outside of the Malscan directory.

#### Version 1.4.0
*Released: March 16, 2015*
* First offical public release
