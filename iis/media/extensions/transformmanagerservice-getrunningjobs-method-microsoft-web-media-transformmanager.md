﻿---
title: TransformManagerService.GetRunningJobs Method  (Microsoft.Web.Media.TransformManager)
TOCTitle: GetRunningJobs Method
ms:assetid: M:Microsoft.Web.Media.TransformManager.TransformManagerService.GetRunningJobs
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/microsoft.web.media.transformmanager.transformmanagerservice.getrunningjobs(v=VS.90)
ms:contentKeyID: 35521050
ms.date: 06/14/2012
mtps_version: v=VS.90
f1_keywords:
- Microsoft.Web.Media.TransformManager.TransformManagerService.GetRunningJobs
dev_langs:
- CSharp
- JScript
- VB
- FSharp
- c++
api_location:
- Microsoft.Web.Media.TransformManager.ServiceLibrary.dll
api_name:
- Microsoft.Web.Media.TransformManager.TransformManagerService.GetRunningJobs
api_type:
- Managed
topic_type:
- apiref
- kbSyntax
product_family_name: VS
ROBOTS: INDEX,FOLLOW
---

# GetRunningJobs Method

Returns a collection of all of the running jobs for all [JobDefinition](jobdefinition-class-microsoft-web-media-transformmanager.md) objects.

**Namespace:**  [Microsoft.Web.Media.TransformManager](microsoft-web-media-transformmanager-namespace.md)  
**Assembly:**  Microsoft.Web.Media.TransformManager.ServiceLibrary (in Microsoft.Web.Media.TransformManager.ServiceLibrary.dll)

## Syntax

``` vb
'Declaration
<PrincipalPermissionAttribute(SecurityAction.Demand, Role := "Administrators")> _
PublicFunctionGetRunningJobsAsCollection(OfJobDetails)
'Usage
DiminstanceAsTransformManagerServiceDimreturnValueAsCollection(OfJobDetails)

returnValue = instance.GetRunningJobs()
```

``` csharp
[PrincipalPermissionAttribute(SecurityAction.Demand, Role = "Administrators")]
publicCollection<JobDetails> GetRunningJobs()
```

``` c++
[PrincipalPermissionAttribute(SecurityAction::Demand, Role = L"Administrators")]
public:
virtualCollection<JobDetails^>^ GetRunningJobs() sealed
```

``` fsharp
[<PrincipalPermissionAttribute(SecurityAction.Demand, Role = "Administrators")>]
abstractGetRunningJobs : unit->Collection<JobDetails> 
[<PrincipalPermissionAttribute(SecurityAction.Demand, Role = "Administrators")>]
overrideGetRunningJobs : unit->Collection<JobDetails> 
```

``` jscript
publicfinalfunctionGetRunningJobs() : Collection<JobDetails>
```

#### Return Value

Type: [System.Collections.ObjectModel. . :: . .Collection](https://msdn.microsoft.com/en-us/library/ms132397\(v=vs.90\))\< (Of \< ( \<'[JobDetails](jobdetails-class-microsoft-web-media-transformmanager.md)\> ) \> ) \>  
The collection of running jobs.  

#### Implements

[IMonitoringService. . :: . .GetRunningJobs() () () ()](imonitoringservice-getrunningjobs-method-microsoft-web-media-transformmanager.md)  

## See Also

#### Reference

[TransformManagerService Class](transformmanagerservice-class-microsoft-web-media-transformmanager.md)

[Microsoft.Web.Media.TransformManager Namespace](microsoft-web-media-transformmanager-namespace.md)
