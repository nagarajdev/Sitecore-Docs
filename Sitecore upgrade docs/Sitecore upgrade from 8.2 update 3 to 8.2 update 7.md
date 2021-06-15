# Sitecore upgrade from 8.2 update 3 to 8.2 update 7
The purpose of this post is to provide details of Sitecore version upgrade from 8.2 update 3 to 8.2 update 7.


## Overview
The purpose of this post is to provide details of Sitecore version upgrades from 8.2 update 3 to 8.2 update 7. Here you will learn about what information are required before upgrading to latest version of Sitecore, recommendations and approach followed.
{% hint style="info" %}
This upgrade is consists of 4 versions of update versions and 1 version of update for commerce(this will carried out only after Sitecore 8.2(Update-7))
{% endhint %}

## Preliminaries
Preliminaries for upgrade.

### Sitecore modules compatibility
Collecting all the information regrading Sitecore modules compatibility that you are going to upgrade. Please refer from Sitecore KB https://support.sitecore.com/kb?id=kb_article_view&sysparm_article=KB0541788

Below table checks for compatibility of the Sitecore modules or Marketplace modules installed in our solution with the required Target version.

| Sitecore/Modules | Update 3(Current) | Update 4 | Update 5 | Update 6 | Update 7 | 
| ---------------- | ----------------- | -------- | -------- | -------- | -------- |
| Sitecore Version | Sitecore.NET 8.2 (rev. 170407) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 170614) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 170728) | UPGRADE REQUIRED <br/> Sitecore.NET 8.2 (rev. 171121) | UPGRADE REQUIREDSitecore.NET 8.2 (rev. 180406) |
| WFFM	| WFFM Update-3 | UPGRADE REQUIRED <br/> WFFM Update-4 | UPGRADE REQUIRED <br/> WFFM Update-5 | UPGRADE REQUIRED <br/> WFFM Update-6 | UPGRADE REQUIRED <br/> WFFM Update-7 |





{% hint style="warn" %}
This post is written based on my hands on experience and might not be work fit for you
{% endhint %}
