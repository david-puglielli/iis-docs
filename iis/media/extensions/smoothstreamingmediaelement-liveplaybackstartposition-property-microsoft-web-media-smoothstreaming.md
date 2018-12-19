﻿---
title: SmoothStreamingMediaElement.LivePlaybackStartPosition Property  (Microsoft.Web.Media.SmoothStreaming)
TOCTitle: LivePlaybackStartPosition Property
ms:assetid: P:Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePlaybackStartPosition
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.smoothstreaming.smoothstreamingmediaelement.liveplaybackstartposition(v=VS.90)
ms:contentKeyID: 23961197
ms.date: 05/02/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePlaybackStartPosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_LivePlaybackStartPosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.set_LivePlaybackStartPosition
dev_langs:
- CSharp
- JScript
- VB
- c++
api_location:
- Microsoft.Web.Media.SmoothStreaming.dll
api_name:
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.get_LivePlaybackStartPosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.LivePlaybackStartPosition
- Microsoft.Web.Media.SmoothStreaming.SmoothStreamingMediaElement.set_LivePlaybackStartPosition
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# LivePlaybackStartPosition Property

Gets or sets the starting position to use during live playback.

**Namespace:**  [Microsoft.Web.Media.SmoothStreaming](microsoft-web-media-smoothstreaming-namespace_1.md)  
**Assembly:**  Microsoft.Web.Media.SmoothStreaming (in Microsoft.Web.Media.SmoothStreaming.dll)

## Syntax

``` vb
'Declaration
PublicPropertyLivePlaybackStartPositionAsPlaybackStartPosition
'Usage
DiminstanceAsSmoothStreamingMediaElementDimvalueAsPlaybackStartPositionvalue = instance.LivePlaybackStartPosition

instance.LivePlaybackStartPosition = value
```

``` csharp
publicPlaybackStartPositionLivePlaybackStartPosition { get; set; }
```

``` c++
public:
propertyPlaybackStartPositionLivePlaybackStartPosition {
    PlaybackStartPositionget ();
    voidset (PlaybackStartPositionvalue);
}
```

``` jscript
function getLivePlaybackStartPosition () : PlaybackStartPositionfunction setLivePlaybackStartPosition (value : PlaybackStartPosition)
```

#### Property Value

Type: [Microsoft.Web.Media.SmoothStreaming. . :: . .PlaybackStartPosition](playbackstartposition-enumeration-microsoft-web-media-smoothstreaming_1.md)  
The position as specified by a member of the [PlaybackStartPosition](playbackstartposition-enumeration-microsoft-web-media-smoothstreaming_1.md) enumeration.  

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
