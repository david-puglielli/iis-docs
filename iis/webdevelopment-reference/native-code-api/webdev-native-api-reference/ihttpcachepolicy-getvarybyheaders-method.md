---
title: "IHttpCachePolicy::GetVaryByHeaders Method | Microsoft Docs"
ms.custom: ""
ms.date: "10/07/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fe12d854-b4bb-4c68-bcdb-a0294bd8cffd
caps.latest.revision: 26
author: "shirhatti"
manager: "wpickett"
---
# IHttpCachePolicy::GetVaryByHeaders Method
Returns the custom header values for the cache policy.  
  
## Syntax  
  
```cpp  
virtual PCSTR GetVaryByHeaders(  
   VOID  
) const = 0;  
```  
  
#### Parameters  
 This method takes no parameters.  
  
## Return Value  
 A null-terminated `PCSTR` that contains a comma-delimited list of custom header values.  
  
## Remarks  
 [CHttpModule](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/chttpmodule-class.md) derived classes that register for request or response events receive an [IHttpContext](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-interface.md) pointer as a parameter on the corresponding `virtual` method. Call the [IHttpContext::GetResponse](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcontext-getresponse-method.md) method, then the [IHttpResponse::GetCachePolicy](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpresponse-getcachepolicy-method.md) method, and finally the `GetVaryByHeaders` method to retrieve the custom headers.  
  
 `GetVaryByHeaders` behavior depends on implementation. You should use the following information as a guideline, but it may not be correct in all scenarios:  
  
-   The current default implementer of the [IHttpCachePolicy](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcachepolicy-interface.md) interface declares a `private` buffer that contains variable header data. During the construction of an implementer, this buffer is initialized to empty. If the supplied parameter is NULL, the [AppendVaryByHeader](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcachepolicy-appendvarybyheader-method.md) method immediately returns S_OK. Otherwise, the buffer is expanded to hold a copy of the parameter, including the null-termination character, plus 1 if the buffer is not currently empty. If the buffer is not empty, the "," character is appended to the buffer. Finally, the contents of the parameter, including the null-termination character, are appended to the buffer.  
  
-   `GetVaryByHeaders` returns the comma-delimited list of custom headers set through successive calls to `AppendVaryByHeader`.  
  
## Notes for Implementers  
 `IHttpCachePolicy` implementers are responsible for memory management with this data; therefore, `IHttpCachePolicy` implementers that use dynamic memory allocation must release or call `delete` on the `PCSTR` pointer when it is no longer needed.  
  
## Notes for Callers  
 `IHttpCachePolicy` implementers are responsible for memory management with this data; therefore, `IHttpCachePolicy` clients must not release or call `delete` on the returned `PCSTR` pointer when this data is no longer needed. Furthermore, clients must not cast this data to a pointer that is not a `const` or change the state of the memory referenced by this `PCSTR`, because an access violation will be thrown or the data will become invalid.  
  
## Example  
 The following code example demonstrates how to create a global module that listens for [RQ_BEGIN_REQUEST](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) and [RQ_SEND_RESPONSE](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/request-processing-constants.md) events. The module then retrieves an `IHttpCachePolicy` pointer and writes variable header information to the response stream.  
  
<!-- TODO: review snippet reference  [!CODE [IHttpCachePolicy#7](IHttpCachePolicy#7)]  -->  
  
 For more information on how to create and deploy a native DLL module, see [Walkthrough: Creating a Request-Level HTTP Module By Using Native Code](../../../webdevelopment-reference\native-code-development-overview\native-code-dev-overview/walkthrough-creating-a-request-level-http-module-by-using-native-code.md).  
  
 The above code writes data that is similar to the following to the response stream:  
  
```  
Vary-by-Headers:   
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
 [IHttpCachePolicy Interface](../../../webdevelopment-reference\native-code-api\webdev-native-api-reference/ihttpcachepolicy-interface.md)