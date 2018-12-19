﻿---
title: SmoothStreamingMediaElement.CanPause Property  (Microsoft.Web.Media.SmoothStreaming)
TOCTitle: CanPause Property
ms:assetid: P:Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.CanPause
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.smoothstreaming.smoothstreamingmediaelement.canpause(v=VS.90)
ms:contentKeyID: 23961255
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.CanPause
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_CanPause
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.set_CanPause
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Media.SmoothStreaming.dll
api_name:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.CanPause
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_CanPause
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.set_CanPause
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# CanPause Property

Gets or sets a value that specifies whether the stream can be paused.

**Namespace:**  [Microsoft.Web.Media.SmoothStreaming](microsoft-web-media-smoothstreaming-namespace_1.md)  
**Assembly:**  Microsoft.Web.Media.SmoothStreaming (in Microsoft.Web.Media.SmoothStreaming.dll)

## Syntax

``` vb
'Declaration
PublicPropertyCanPauseAsBoolean
'Usage
DiminstanceAsSmoothStreamingMediaElementDimvalueAsBooleanvalue = instance.CanPause

instance.CanPause = value
```

``` csharp
publicboolCanPause { get; set; }
```

``` c++
public:
propertyboolCanPause {
    boolget ();
    voidset (boolvalue);
}
```

``` jscript
function getCanPause () : booleanfunction setCanPause (value : boolean)
```

#### Property Value

Type: [System. . :: . .Boolean](https://msdn.microsoft.com/en-us/library/a28wyd50\(v=vs.90\))  
true if the media stream can be paused; otherwise, false.  

## Version Information

#### Silverlight

Supported in: 4  

#### Silverlight for Windows Phone

Supported in: Windows Phone OS 7.0  

## Permissions

  - Full trust for the immediate caller. This member cannot be used by partially trusted code. For more information, see [Using Libraries from Partially Trusted Code](https://msdn.microsoft.com/en-us/library/8skskf63\(v=vs.90\)).

## See Also

#### Reference

[SmoothStreamingMediaElement Class](smoothstreamingmediaelement-class-microsoft-web-media-smoothstreaming_1.md)

[Microsoft.Web.Media.SmoothStreaming Namespace](microsoft-web-media-smoothstreaming-namespace_1.md)
