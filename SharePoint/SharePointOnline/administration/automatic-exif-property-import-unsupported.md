---
title: Can't automatically import the EXIF properties into the image properties
description: SharePoint Online no longer automatically imports the EXIF properties into the image properties because the feature relied on an underlying platform capability that's no longer available.
author: MaryQiu1987
manager: dcscontentpm
localization_priority: Normal
audience: ITPro
ms.service: o365-solutions
ms.topic: article
ms.author: v-maqiu
localization_priority: Normal
appliesto:
- SharePoint Online
---

# SharePoint Online no longer supports automatic import of EXIF properties after image upload

## Symptoms

After you upload images that contain EXIF data, SharePoint Online no longer automatically imports the EXIF properties into the image properties.

## Cause

The Automatic EXIF property import feature in SharePoint relied on an underlying platform capability that is no longer available. When this capability was removed from the platform, the dependent feature was also removed in SharePoint Online.

## Resolution

You can import EXIF property fields into a SharePoint library column by running the CSOM script. However, you have to run the script every time that you upload new images to the library.