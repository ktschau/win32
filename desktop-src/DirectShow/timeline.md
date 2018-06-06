---
Description: Timeline
ms.assetid: 4909f797-d296-4c9f-83fb-543e48bbe75d
title: Timeline
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Timeline

> [!Note]  
> \[Deprecated. This API may be removed from future releases of Windows.\]

 

The timeline object manages all of the objects in a video editing project. To create this object, call **CoCreateInstance**. The class identifier is CLSID\_AMTimeline.

To read Windows Media™ files, the application must provide a software certificate, also called a key. Register the application as a key provider through the timeline's **IObjectWithSite** interface. For more information, see [Unlocking the Windows Media Format SDK](unlocking-the-windows-media-format-sdk.md).

The timeline object exposes the following interfaces:

-   [**IAMSetErrorLog**](iamseterrorlog.md)
-   [**IAMTimeline**](iamtimeline.md)
-   **IObjectWithSite**
-   **IPersistStream**

## Related topics

<dl> <dt>

[The Timeline Model](the-timeline-model.md)
</dt> <dt>

[Constructing a Timeline](constructing-a-timeline.md)
</dt> </dl>

 

 


