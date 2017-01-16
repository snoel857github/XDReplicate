# XenDesktop 7 Export and Import Utility
Exports XenDesktop 7.x site information and imports to another 'Site' via remote command or XML file.

**PLEASE USE WITH CAUTION.  THIS WILL OVERWRITE SETTINGS ON IMPORT**

## Requirments
* PC\Server with Citrix Snapins installed
* Admin access to XenDesktop site
* PowerShell v3 or greater

## Changelog
* 01-16-2017: Initial release

## XenDesktop Versions Tested
* 7.11
* 7.12

## What is synced for XenDesktop?
* Administrators
  * Accounts
  * Roles
* Delivery Groups
  * Settings
  * Users
* Desktops
  * Settings
  * User Restrictions
* Published Applications
  * Settings
  * "Limit Visibilty"
  * Icon
  * File Type Associaton
  * Admin folders
  
## What this doesn't sync?
* Citrix Policy (use GPO)
* Machine Catalogs
* Hypervisor connections
* App Disks
* Zones
* Scopes (Trying to think through this)
* TAGS (coming soon)

## Usage

Exports data from localhost and exports to C:\temp\my.xml

```.\XDReplicate.ps1 -mode export -XMLPATH "C:\temp\my.xml"```
   
Imports data from C:\temp\my.xml and imports to localhost

```.\XDReplicate.ps1 -mode import -XMLPATH "C:\temp\my.xml"```

Exports data from localhost and imports on DDC02.DOMAIN.COM

```.\XDReplicate.ps1 -mode both -destination DDC02.DOMAIN.COM```

Exports data from DDC01.DOMAIN.COM and imports on DDC02.DOMAIN.COM

```.\XDReplicate.ps1 -mode both -source DDC01.DOMAIN.COM -destination DDC02.DOMAIN.COM```
   
