---
title: "IHttpConnection::IsConnected Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a2b6d5e7-48d7-2eba-6fe3-1fec9586b846
caps.latest.revision: 21
author: "shirhatti"
manager: "wpickett"
---
# IHttpConnection::IsConnected Method
Determines whether a Web client is still connected to the current request.  
  
## Syntax  
  
```cpp  
virtual BOOL IsConnected(  
   VOID  
) const = 0;  
```  
  
#### Parameters  
 This method takes no parameters.  
  
## Return Value  
 `true` if the Web client is still connected; otherwise, `false`.  
  
## Remarks  
 The `IsConnected` method determines whether a Web client has remained connected to the current request or has disconnected from the current request. For example, if a request is taking a long time to process, a Web client may choose to end the connection. If an HTTP module calls the `IsConnected` method and determines that the connection has been terminated by the client, the module can bypass remaining notifications and end additional request processing by returning [RQ_NOTIFICATION_FINISH_REQUEST](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-notification-status-enumeration.md). This frees IIS from continuing to process a request for a disconnected Web client.  
  
## Example  
 The following code example demonstrates how to use the [IHttpContext::GetConnection](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-getconnection-method.md) method to create an HTTP module that retrieves a pointer to an [IHttpConnection](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpconnection-interface.md) interface. The example then calls the `IHttpConnection::IsConnected` method to determine whether the Web client that initiated the current request is still connected. If the client is still connected, the HTTP module will return a status message to the Web client. If the client is not connected, the module will return `RQ_NOTIFICATION_FINISH_REQUEST` to end additional processing.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpConnectionIsConnected#1](IHttpConnectionIsConnected#1)]  -->  
  
 Your module must export the [RegisterModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/pfn-registermodule-function.md) function. You can export this function by creating a module definition (.def) file for your project, or you can compile the module by using the `/EXPORT:RegisterModule` switch. For more information, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 You can optionally compile the code by using the `__stdcall (/Gz)` calling convention instead of explicitly declaring the calling convention for each function.  
  
## Requirements  
  
|Type|Description|  
|----------|-----------------|  
|Client|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winvista](../../../wmi-provider/includes/winvista-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[win7](../../../wmi-provider/includes/win7-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[win8](../../../wmi-provider/includes/win8-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[win10](../../../wmi-provider/includes/win10-md.md)]|  
|Server|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)] on [!INCLUDE[winsrv2008](../../../wmi-provider/includes/winsrv2008-md.md)]<br />-   [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)] on [!INCLUDE[winsrv2008r2](../../../wmi-provider/includes/winsrv2008r2-md.md)]<br />-   [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)] on [!INCLUDE[winsrv2012](../../../wmi-provider/includes/winsrv2012-md.md)]<br />-   [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)] on [!INCLUDE[winsrv2012r2](../../../wmi-provider/includes/winsrv2012r2-md.md)]<br />-   [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)] on [!INCLUDE[winsrv2016](../../../wmi-provider/includes/winsrv2016-md.md)]|  
|Product|-   [!INCLUDE[iis70](../../../wmi-provider/includes/iis70-md.md)], [!INCLUDE[iis75](../../../wmi-provider/includes/iis75-md.md)], [!INCLUDE[iis80](../../../wmi-provider/includes/iis80-md.md)], [!INCLUDE[iis85](../../../wmi-provider/includes/iis85-md.md)], [!INCLUDE[iis100](../../../wmi-provider/includes/iis100-md.md)]<br />-   [!INCLUDE[iisexp75](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp75-md.md)], [!INCLUDE[iisexp80](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp80-md.md)], [!INCLUDE[iisexp100](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/includes/iisexp100-md.md)]|  
|Header|Httpserv.h|  
  
## See Also  
 [IHttpConnection Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpconnection-interface.md)