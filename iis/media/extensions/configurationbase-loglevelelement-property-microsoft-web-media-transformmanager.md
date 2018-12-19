﻿---
title: ConfigurationBase.LogLevelElement Property  (Microsoft.Web.Media.TransformManager)
TOCTitle: LogLevelElement Property
ms:assetid: P:Microsoft.Web.Media.TransformManager.ConfigurationBase.LogLevelElement
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.configurationbase.loglevelelement(v=VS.90)
ms:contentKeyID: 35520877
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.ConfigurationBase.set_LogLevelElement
- Microsoft.Web.Media.TransformManager.ConfigurationBase.get_LogLevelElement
- Microsoft.Web.Media.TransformManager.ConfigurationBase.LogLevelElement
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.Common.dll
api_name:
- Microsoft.Web.Media.TransformManager.ConfigurationBase.get_LogLevelElement
- Microsoft.Web.Media.TransformManager.ConfigurationBase.LogLevelElement
- Microsoft.Web.Media.TransformManager.ConfigurationBase.set_LogLevelElement
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# LogLevelElement Property

Gets or sets an XML element that contains log level details.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.Common (in Microsoft.Web.Media.TransformManager.Common.dll)

## Syntax

``` vb
'Declaration
PublicPropertyLogLevelElementAsXElementGetSet
'Usage
DiminstanceAsConfigurationBaseDimvalueAsXElementvalue = instance.LogLevelElement

instance.LogLevelElement = value
```

``` csharp
publicXElementLogLevelElement { get; set; }
```

``` c++
public:
propertyXElement^ LogLevelElement {
    XElement^ get ();
    voidset (XElement^ value);
}
```

``` fsharp
memberLogLevelElement : XElementwithget, set
```

``` jscript
function getLogLevelElement () : XElementfunction setLogLevelElement (value : XElement)
```

#### Property Value

Type: [System.Xml.Linq. . :: . .XElement](https://msdn.microsoft.com/en-us/library/bb340098\(v=vs.90\))  
The XML element that contains log level details.  

## See Also

#### Reference

[ConfigurationBase Class](configurationbase-class-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
