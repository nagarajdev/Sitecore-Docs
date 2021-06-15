# Sitecore upgrade from 8.2 update 3 to 8.2 update 7
The purpose of this post is to provide details of Sitecore version upgrade from 8.2 update 3 to 8.2 update 7.


## Overview
The purpose of this post is to provide details of Sitecore version upgrades from 8.2 update 3 to 8.2 update 7. Here you will learn about what information are required before upgrading to latest version of Sitecore, recommendations and approach followed.

{% hint style="info" %}
This upgrade is consists of 4 versions of update versions and 1 version of update for commerce(this will carried out only after Sitecore 8.2(Update-7))
{% endhint %}

## Preliminaries
Preliminaries for checking Sitecore compatibility with your current installation.

### Sitecore modules compatibility
Collecting all the information regrading Sitecore modules compatibility that you are going to upgrade. Please refer from Sitecore KB https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0541788

#### Sitecore modules
Below table checks for compatibility of the Sitecore modules or Marketplace modules installed in our solution with the required Target version.

| Sitecore/Modules | Update 3(Current) | Update 4 | Update 5 | Update 6 | Update 7 | 
| ---------------- | ----------------- | -------- | -------- | -------- | -------- |
| Sitecore Version | Sitecore.NET 8.2 (rev. 170407) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 170614) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 170728) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 171121) | UPGRADE REQUIREDSitecore.NET 8.2 (rev. 180406) |
| WFFM	| WFFM Update-3 | UPGRADE REQUIRED <br/> WFFM Update-4 | UPGRADE REQUIRED <br/> WFFM Update-5 | UPGRADE REQUIRED <br/> WFFM Update-6 | UPGRADE REQUIRED <br/> WFFM Update-7 |
| PXM	| PXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 |
| Commerce	| Sitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE REQUIRED Sitecore Commerce 8.2.1 Update-3 |
| Sitecore Powershell Extenstion	| SPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 Can be upgraded to SPE 4.7+ (for Sitecore 8) has been verified to be fully functional on Sitecore 9. |

#### Sitecore community modules
These below modules you may or may not be used.

| Sitecore/Modules | Update 3(Current) | Update 4 | Update 5 | Update 6 | Update 7 | 
| ---------------- | ----------------- | -------- | -------- | -------- | -------- |
| Sitecore Scheduled Publish	| Community SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 |
| ASR(Advanced System Reporter)	| Community SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 |
| Personalize Rendering Parameters	Community SC module supported SC 8.2	| UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED |

#### Sitecore support patches
Scan through your current installation and code solution to list down all the Sitecore support patches being applied on your installation.

| Reference number | Purpose | Compatibility | Details | Remarks | Keep/Remove |
| ---------------- | ------- | ------------- | ------- | ------- | ----------- |
| 131168 | Issues with special symbols in the Experience Editor | Sitecore CMS 8.2 rev. 170614 (Update-4) and Sitecore CMS 8.2 rev. 180406 (Update-7) | https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0502008 | Fixed In: 9.0 rev. 171002 (Initial Release) | Keep |



#### Sitecore compatibility with your current installation
| Sitecore/Modules | Compatibility |
| ---------------- | ------------- |
| .NET Framework | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table https://kb.sitecore.net/articles/087164 |
| ASP.NET MVC | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table https://kb.sitecore.net/articles/087164 |
| Operating System | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table https://kb.sitecore.net/articles/087164 |
| Database Server | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table https://kb.sitecore.net/articles/087164 |

## Recommendation

### Sitecore XP upgrade
In the past, the upgrade for Sitecore update versions will be performed sequentially. After each upgrades, we will perform a full regression test to make sure all functionality working as expected and version upgrade was successful prior to performing the next update version.

At present, new Sitecore update packages have those steps(update versions) inside of them so we don't have to do one update upgrade at a time and we can perform a full regression test after upgraded to Sitecore 8.2(Update-7)

Please refer below Sitecore 8.2(Update-7) package which contains all update packages already.

IMG

As per prerequisites section in Sitecore XP upgrade guide for Sitecore 8.2(Update-7)
> "If you are upgrading from Sitecore 8.1 rev. 151003 (Initial Release) or later, you can upgrade directly to Sitecore 8.2 rev. 180406 (Update-7). However, if your solution is based on an earlier version of Sitecore, you must first upgrade to Sitecore 8.1 rev. 151003 (Initial Release)."

by looking into [Sitecore XP upgrade guide for Sitecore 8.2(Update-7),](https://dev.sitecore.net/~/media/B50CA65AA6844B4B81BF36A01E9DD269.ashx), we have decided to upgrade directly to Sitecore 8.2(Update-7) and follow Sitecore upgrade guide.

### Sitecore modules/Community modules upgrade
As per above listed modules, we need to upgrade WFFM update-3 module to WFFM Update-7 in order to have compatibility with the Sitecore 8.2(Update-7).

As part of modules upgrade process we will run upgrade package(WFFM 8.2 Update-7) as per upgrade guide


{% hint style="warn" %}
This post is written based on my hands on experience and might not be work fit for you
{% endhint %}
