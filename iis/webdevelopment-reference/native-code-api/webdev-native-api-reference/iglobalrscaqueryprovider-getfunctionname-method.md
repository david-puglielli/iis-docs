---
title: "IGlobalRSCAQueryProvider::GetFunctionName Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c55da23c-5526-427f-6583-55b584e6ada3
caps.latest.revision: 30
author: "shirhatti"
manager: "wpickett"
---
# IGlobalRSCAQueryProvider::GetFunctionName Method
Returns the name of the dynamic function call that caused the event.  
  
## Syntax  
  
```cpp  
virtual PCWSTR GetFunctionName(  
   VOID  
) const = 0;  
```  
  
#### Parameters  
 This method takes no parameters.  
  
## Return Value  
 A pointer to a constant null-terminated Unicode string that contains name of the function that caused the event.  
  
## Remarks  
 [CGlobalModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/cglobalmodule-class.md) derived classes that register for [GL_RSCA_QUERY](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) events receive an [IGlobalRscaQueryProvider](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/iglobalrscaqueryprovider-interface.md) pointer as a parameter on the [CGlobalModule::OnGlobalRSCAQuery](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/cglobalmodule-onglobalrscaquery-method.md)`virtual` method. You can then retrieve the function name by calling the `GetFunctionName` method on the `IGlobalRSCAQueryProvider` pointer.  
  
 The return value of the `GetFunctionName` method depends on implementation. You should use the following information as a guideline, but it may not be correct in all scenarios:  
  
-   The default implementer of the [IProtocolManager](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/iprotocolmanager-interface.md), [IPmCustomActions](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ipmcustomactions-interface.md), [IPmHealthAndIdleMonitor](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ipmhealthandidlemonitor-interface.md), and [IPmListenerChannelManager](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ipmlistenerchannelmanager-interface.md) interfaces raises events when you call the [IRSCA_WorkerProcess::EnumerateAppDomains](http://msdn.microsoft.com/en-us/8be86f01-4f15-4f9c-8b65-aec64061d497) and [IRSCA_AppDomain::Unload](http://msdn.microsoft.com/en-us/f6e9a6a6-3029-4bbe-8454-b82b2e4b2bfb) methods. These methods map to the PMH_App_Domain_Enum_V1 and PMH_App_Domain_Unload_V1 values, respectively, which are returned when you call `GetFunctionName`. The parameters of this function are, in turn, returned when you call the [GetFunctionParameters](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/iglobalrscaqueryprovider-getfunctionparameters-method.md) method.  
  
-   The `IGlobalRSCAQueryProvider` implementer receives the function name and function parameter values as strings when either of the [IRSCA_AppDomain](http://msdn.microsoft.com/en-us/0ac45ca7-4e5c-4ac2-9152-42465f4511fa) events is raised, and the implementer holds references to these strings. If a string is NULL, `GetFunctionName` returns the empty string. Otherwise, `GetFunctionName` returns a pointer to this shared string.  
  
## Notes for Implementers  
 `IGlobalRSCAQueryProvider` implementers are responsible for memory management with this data; therefore, `IGlobalRSCAQueryProvider` implementers that use dynamic memory allocation must release or call `delete` on the `PCWSTR` pointer when it is no longer needed.  
  
## Notes for Callers  
 `IGlobalRSCAQueryProvider` implementers are responsible for memory management with this data; therefore, `IGlobalRSCAQueryProvider` clients must not release or call `delete` on the returned `PCWSTR` pointer when this data is no longer needed. Furthermore, clients must not cast this data to a pointer that is not a `const` or change the state of the memory referenced by this `PCWSTR`, because either an access violation will be raised or the data will become invalid.  
  
## Example  
 The following code example demonstrates how to create a global module that listens for [GL_RSCA_QUERY](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) events and then writes the function name information to the Event Viewer.  
  
> [!CAUTION]
>  [!INCLUDE[iisver](../../../wmi-provider/includes/iisver-md.md)] generates a large number of events in the Event Viewer. To avoid a log overflow error in a production environment, you should generally avoid writing cache information to the event log. For demonstration purposes, this code example writes an entry to the Event Viewer in debug mode only.  
  
<!-- TODO: review snippet reference  [!CODE [IGlobalRSCAQueryProvider#2](IGlobalRSCAQueryProvider#2)]  -->  
  
 For more information on how to create and deploy a native DLL module, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 The above code writes two new events to the application log of the Event Viewer, where the Data box contains a string similar to the following:  
  
```  
Function Name: PMH_App_Domain_Enum_V1  
```  
  
 You can optionally compile the code by using the __`stdcall (/Gz)` calling convention instead of explicitly declaring the calling convention for each function.  
  
## Requirements  
  
|Type|Description|  
|----------|-----------------|  
|Client|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winvista](../../../wmi-provider/includes/winvista-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[win7](../../../wmi-provider/includes/win7-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[win8](../../../wmi-provider/includes/win8-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[win10](../../../wmi-provider/includes/win10-md.md)]|  
|Server|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winsrv2008](../../../wmi-provider/includes/winsrv2008-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[winsrv2008r2](../../../wmi-provider/includes/winsrv2008r2-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[winsrv2012](../../../wmi-provider/includes/winsrv2012-md.md)]<br />-   [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)] on [!INCLUDE[winsrv2012r2](../../../wmi-provider/includes/winsrv2012r2-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[winsrv2016](../../../wmi-provider/includes/winsrv2016-md.md)]|  
|Product|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)], [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)], [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)], [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)], [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)]<br />-   [!INCLUDE[iisexp75](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp75-md.md)], [!INCLUDE[iisexp80](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp80-md.md)], [!INCLUDE[iisexp100](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp100-md.md)]|  
|Header|Httpserv.h|  
  
## See Also  
 [IGlobalRSCAQueryProvider Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/iglobalrscaqueryprovider-interface.md)