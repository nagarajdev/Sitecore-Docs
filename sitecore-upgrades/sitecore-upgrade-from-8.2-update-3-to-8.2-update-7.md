---
description: >-
  The purpose of this post is to provide details of Sitecore version upgrade
  from 8.2 update 3 to 8.2 update 7.
---

# Sitecore upgrade from 8.2 update 3 to 8.2 update 7

## 🗻Overview

The purpose of this post is to provide details of Sitecore version upgrades from 8.2 update 3 to 8.2 update 7. Here you will learn about what information are required before upgrading to latest version of Sitecore, recommendations and approach followed.

{% hint style="info" %}
This upgrade is consists of 4 versions of update versions and 1 version of update for commerce\(this will carried out only after Sitecore 8.2\(Update-7\)\)
{% endhint %}

## 📑Preliminaries

Preliminaries for checking Sitecore compatibility with your current installation.

### ⚽Sitecore modules compatibility

Collecting all the information regrading Sitecore modules compatibility that you are going to upgrade. Please refer from Sitecore KB [https://support.sitecore.com/kb?id=kb\_article\_view&sysparm\_article=KB0541788](https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0541788)

#### ✅Sitecore modules

Below table checks for compatibility of the Sitecore modules or Marketplace modules installed in our solution with the required Target version.

| Sitecore/Modules | Update 3\(Current\) | Update 4 | Update 5 | Update 6 | Update 7 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Sitecore Version | Sitecore.NET 8.2 \(rev. 170407\) | ![](../.gitbook/assets/upgrade-req.jpg)     Sitecore.NET 8.2 \(rev. 170614\) | UPGRADE REQUIRED   Sitecore.NET 8.2 \(rev. 170728\) | UPGRADE REQUIRED   Sitecore.NET 8.2 \(rev. 171121\) | UPGRADE REQUIREDSitecore.NET 8.2 \(rev. 180406\) |
| WFFM | WFFM Update-3 | UPGRADE REQUIRED   WFFM Update-4 | UPGRADE REQUIRED   WFFM Update-5 | UPGRADE REQUIRED   WFFM Update-6 | UPGRADE REQUIRED   WFFM Update-7 |
| PXM | PXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 | UPGRADE NOT REQUIREDPXM Core 8.2 |
| Commerce | Sitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE NOT REQUIREDSitecore Commerce 8.2.1 Update-2 | UPGRADE REQUIRED Sitecore Commerce 8.2.1 Update-3 |
| Sitecore Powershell Extenstion | SPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 | UPGRADE NOT REQUIREDSPE 4.3.0.17491 Can be upgraded to SPE 4.7+ \(for Sitecore 8\) has been verified to be fully functional on Sitecore 9. |

#### ✅Sitecore community modules

These below modules you may or may not be used.

| Sitecore/Modules | Update 3\(Current\) | Update 4 | Update 5 | Update 6 | Update 7 |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Sitecore Scheduled Publish | Community SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 |
| ASR\(Advanced System Reporter\) | Community SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 | UPGRADE NOT REQUIREDCommunity SC module supported SC 8.0 |
| Personalize Rendering Parameters    Community SC module supported SC 8.2 | UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED | UPGRADE NOT REQUIRED |  |

#### ✅Sitecore support patches

Scan through your current installation and code solution to list down all the Sitecore support patches being applied on your installation.

| Reference number | Purpose | Compatibility | Details | Remarks | Keep/Remove |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 131168 | Issues with special symbols in the Experience Editor | Sitecore CMS 8.2 rev. 170614 \(Update-4\) and Sitecore CMS 8.2 rev. 180406 \(Update-7\) | [https://support.sitecore.com/kb?id=kb\_article\_view&sysparm\_article=KB0502008](https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0502008) | Fixed In: 9.0 rev. 171002 \(Initial Release\) | Keep |

#### ✅Sitecore compatibility with your current installation

| Sitecore/Modules | Compatibility |
| :--- | :--- |
| .NET Framework | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table [https://kb.sitecore.net/articles/087164](https://kb.sitecore.net/articles/087164) |
| ASP.NET MVC | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table [https://kb.sitecore.net/articles/087164](https://kb.sitecore.net/articles/087164) |
| Operating System | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table [https://kb.sitecore.net/articles/087164](https://kb.sitecore.net/articles/087164) |
| Database Server | UPGRADE NOT REQUIRED Please refer Sitecore compatibility table [https://kb.sitecore.net/articles/087164](https://kb.sitecore.net/articles/087164) |

## 🧮Recommendation

### ✅Sitecore XP upgrade

In the past, the upgrade for Sitecore update versions will be performed sequentially. After each upgrades, we will perform a full regression test to make sure all functionality working as expected and version upgrade was successful prior to performing the next update version.

At present, new Sitecore update packages have those steps\(update versions\) inside of them so we don't have to do one update upgrade at a time and we can perform a full regression test after upgraded to Sitecore 8.2\(Update-7\)

Please refer below Sitecore 8.2\(Update-7\) package which contains all update packages already.

IMG

As per prerequisites section in Sitecore XP upgrade guide for Sitecore 8.2\(Update-7\)

> "If you are upgrading from Sitecore 8.1 rev. 151003 \(Initial Release\) or later, you can upgrade directly to Sitecore 8.2 rev. 180406 \(Update-7\). However, if your solution is based on an earlier version of Sitecore, you must first upgrade to Sitecore 8.1 rev. 151003 \(Initial Release\)."

by looking into [Sitecore XP upgrade guide for Sitecore 8.2\(Update-7\)](https://dev.sitecore.net/~/media/B50CA65AA6844B4B81BF36A01E9DD269.ashx), we have decided to upgrade directly to Sitecore 8.2\(Update-7\) and follow Sitecore upgrade guide.

### ✅Sitecore modules/Community modules upgrade

As per above listed modules, we need to upgrade WFFM update-3 module to WFFM Update-7 in order to have compatibility with the Sitecore 8.2\(Update-7\).

As part of modules upgrade process we will run upgrade package\(WFFM 8.2 Update-7\) as per upgrade guide

## 🚜Approach

* Ensure that, upgrading version has right versions of modules and patches or hot fixes.\( please refer above table \)
* Same branching strategy will be followed however, set up a separate branch will not be merged into integration or release branch until a full regression test is performed.

### ![](../.gitbook/assets/sc-logo.jpg) Sitecore XP upgrade approach

Upgrade approach has been divided into 3 sections

#### ✅Upgrade Sitecore solution

**Structure of our Visual Studio solution:**

We have a decoupled Sitecore solution that is, Sitecore website's all folder/files are reside in a Sitecore.Custom.8.2.xx NuGet package and custom code/component are managed as part of Visual Studio solution. NuGet package is being referenced in Visual Studio solution. During build process, extact NuGet package then copies over to the destination folder.

**How do we update new version of Sitecore files into Sitecore.Custom.8.2.xx Nuget package:**

* Download Zip archive of the [Sitecore 8.2 Update-7 file](https://dev.sitecore.net/Downloads/Sitecore_Experience_Platform/82/Sitecore_Experience_Platform_82_Update7.aspx)
* Copy over to Sitecore.Custom.8.2.xx Nuget package and publish.
* Reference new version of Sitecore.Custom.8.2.xx Nuget package.
* Update Sitecore NuGet packages references from various projects. -
* Apply/remove hot-fixes from Sitecore.
* Update any Sitecore modules \(as part of the above table\).

#### ✅Upgrade Sitecore Items

How do I find which Sitecore items are newly added/updated/renamed/deleted?

* Create an isolated Sitecore 8.2\(update-3\) new vanilla instance.
* Perform upgrade as per [Sitecore XP upgrade guide for Sitecore 8.2\(Update-7\)](https://dev.sitecore.net/~/media/B50CA65AA6844B4B81BF36A01E9DD269.ashx) - the guide explains how to install upgrade packages, how to get all log of changed/updated/deleted items or files or folder and how to resolve if configuration files has conflicts.
* [Sitecore XP upgrade guide for Sitecore 8.2\(Update-7\)](https://dev.sitecore.net/~/media/B50CA65AA6844B4B81BF36A01E9DD269.ashx) also cover how to upgrade WFFM module.
* Create Sitecore Items package - The one time install package for upgrading SC.
  * How do we create SC item package:
    * As we follow the steps provided to us by Sitecore and execute the Sitecore Update Installation Wizard then, Sitecore mentioned every change of file or item into the log and report of Analysis and Installation. We should save these Logs and Reports and we can easily find the files that are added, changed or deleted by any particular version of Sitecore. Alternatively, we can use the [Sitecore History Viewer Module](https://marketplace.sitecore.net/en/Modules/Sitecore_History_Viewer.aspx) to be able to identify the Item changes for the databases.

#### ✅Upgrade Sitecore databases

* To upgrade the databases on solutions that are running Sitecore 8.2 rev. 161115 \(Update-1\) to Sitecore Experience Platform 8.2 rev. 170728 \(8.2 Update-5\)
  * If we are using the Sitecore Experience Database \(xDB\) functionality, then we must need to execute the SXP82U6\_BeforeInstall.sql script for the Reporting database.

{% hint style="warning" %}
This post is written based on my experience and may or may not be fit for you.
{% endhint %}

