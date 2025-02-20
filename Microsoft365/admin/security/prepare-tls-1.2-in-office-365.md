---
title: Preparing for TLS 1.2 in Office 365 and Office 365 GCC
description: How to prepare to use TLS 1.2 for all client-server and browser-server combinations in Office 365 and Office 365 GCC after support for TLS 1.0 and 1.1 is disabled.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
audience: ITPro
ms.prod: office 365
ms.topic: article
ms.author: v-six
appliesto:
- Office 365 Business
- SharePoint Server 2016
- SharePoint Server 2013
- SharePoint Server 2010
---

# Preparing for TLS 1.2 in Office 365 and Office 365 GCC 

## Summary

To provide the best-in-class encryption to our customers, Microsoft plans to discontinue the support for Transport Layer Security (TLS) versions 1.0 and 1.1 in Office 365 and Office 365 GCC as of June 2020.

We understand that the security of your data is important, and we're committed to transparency about changes that may affect your use of the TLS service.

The [Microsoft TLS 1.0 implementation](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n) has no known security vulnerabilities. But because of the potential for future protocol downgrade attacks and other TLS vulnerabilities, we are discontinuing support for TLS 1.0 and 1.1 in Microsoft Office 365 and Office 365 GCC.

For information about how to remove TLS 1.0 and 1.1 dependencies, see the whitepaper [Solving the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).

## More information

As of June 2020, Office 365 will begin deprecating TLS 1.0 and 1.1 in worldwide environments for commercial customers and in GCC environments for GCC customers. This means that starting in June 2020, any commercial and GCC clients, devices or services that connect to Office 365 by using TLS 1.0 and 1.1 will not succeed.

We recommend that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services. You might have to update certain client-server and browser-server combinations.  

The following clients are known to be unable to use TLS 1.2. Update these clients to ensure uninterrupted access to the service.

- Android 4.3 and earlier versions
- Firefox version 5.0 and earlier versions
- Internet Explorer 8-10 on Windows 7 and earlier versions
- Internet Explorer 10 on Windows Phone 8
- Safari 6.0.4/OS X10.8.4 and earlier versions

### TLS 1.2 for Microsoft Teams Rooms and Surface Hub

Microsoft Teams Rooms (previously known as Skype Room System V2 SRS V2) have supported TLS 1.2 since December 2018. We recommend that Rooms devices have Microsoft Teams Rooms app version 4.0.64.0 or later installed. For more information, see the [Release notes](https://docs.microsoft.com/microsoftteams/room-systems/srs2-release-note). The changes are backward and forward compatible.

Surface Hub released TLS 1.2 support in May 2019.

TLS 1.2 support for Microsoft Teams Rooms and Surface Hub products also requires the following server-side code changes:

- Skype for Business Online server changes were made live in April 2019. Now, Skype for Business Online supports connecting Microsoft Teams Rooms and Surface Hub devices by using TLS 1.2.
- Skype for Business Server customers must install a cumulative update (CU) to use TLS 1.2 for Teams Rooms Systems and Surface Hub.

  - For Skype for Business Server 2015, CU9 is already released in May 2019.
  - For Skype for Business Server 2019, CU1 was previously planned for April 2019 but is delayed to June 2019.

  > [!NOTE]
  > Skype for Business on-premises customers should not disable TLS 1.0/1.1 before installing specific CUs for Skype for Business Server.

If you are using any on-premises infrastructure for hybrid scenarios or Active Directory Federation Services, make sure that the infrastructure can support both inbound and outbound connections that use TLS 1.2.

## References

The following resources provide guidance to help make sure that your clients are using TLS 1.2 or a later version and to disable TLS 1.0 and 1.1.

- For Windows 7 clients that connect to Office 365, make sure that TLS 1.2 is the default secure protocol in WinHTTP in Windows. For more information see [KB 3140245 - Update to enable TLS 1.1 and TLS 1.2 as a default secure protocols in WinHTTP in Windows](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in).
- To start addressing weak TLS use by removing TLS 1.0 and 1.1 dependencies, see [TLS 1.2 support at Microsoft](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/).
- [New IIS functionality](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/) makes it easier to find clients on [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) and [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) that connect to the service by using weak security protocols.
- Get more information about how to [solve the TLS 1.0 problem](https://www.microsoft.com/download/details.aspx?id=55266).
- For general information about our approach to security, go to the [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365).
- [Enable TLS 1.1 and TLS 1.2 support in SharePoint Server 2016](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/enable-tls-1-1-and-tls-1-2-support-in-sharepoint-server-2016)
- [Enable TLS and SSL support in SharePoint 2013](https://docs.microsoft.com/SharePoint/security-for-sharepoint-server/enable-tls-and-ssl-support-in-sharepoint-2013)
- [Enable TLS 1.1 and TLS 1.2 support in SharePoint Server 2010](https://docs.microsoft.com/previous-versions/office/sharepoint-server-2010/mt773992%28v=office.14%29)
- [Preparing for TLS 1.0/1.1 Deprecation - O365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS guidance, part 1: Getting Ready for TLS 1.2](https://blogs.technet.microsoft.com/exchange/2018/01/26/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/)
- [Exchange Server TLS guidance Part 2: Enabling TLS 1.2 and Identifying Clients Not Using It](https://blogs.technet.microsoft.com/exchange/2018/04/02/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and-identifying-clients-not-using-it/)
- [Exchange Server TLS guidance Part 3: Turning Off TLS 1.0/1.1](https://blogs.technet.microsoft.com/exchange/2018/05/23/exchange-server-tls-guidance-part-3-turning-off-tls-1-01-1/)
- [Enable TLS 1.1 and TLS 1.2 support in Office Online Server](https://docs.microsoft.com/en-gb/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)