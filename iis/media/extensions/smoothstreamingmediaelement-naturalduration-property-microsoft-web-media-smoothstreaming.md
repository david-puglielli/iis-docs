﻿---
title: SmoothStreamingMediaElement.NaturalDuration Property  (Microsoft.Web.Media.SmoothStreaming)
TOCTitle: NaturalDuration Property
ms:assetid: P:Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.NaturalDuration
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.smoothstreaming.smoothstreamingmediaelement.naturalduration(v=VS.90)
ms:contentKeyID: 23961123
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.NaturalDuration
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_NaturalDuration
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Media.SmoothStreaming.dll
api_name:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_NaturalDuration
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.NaturalDuration
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# NaturalDuration Property

Gets the duration of the current stream when it plays to the end.

**Namespace:**  [Microsoft.Web.Media.SmoothStreaming](microsoft-web-media-smoothstreaming-namespace_1.md)  
**Assembly:**  Microsoft.Web.Media.SmoothStreaming (in Microsoft.Web.Media.SmoothStreaming.dll)

## Syntax

``` vb
'Declaration
PublicReadOnlyPropertyNaturalDurationAsDuration
'Usage
DiminstanceAsSmoothStreamingMediaElementDimvalueAsDurationvalue = instance.NaturalDuration
```

``` csharp
publicDurationNaturalDuration { get; }
```

``` c++
public:
propertyDurationNaturalDuration {
    Durationget ();
}
```

``` jscript
function getNaturalDuration () : Duration
```

#### Property Value

Type: [System.Windows. . :: . .Duration](https://msdn.microsoft.com/en-us/library/ms602372\(v=vs.90\))  
The duration of the stream.  

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
