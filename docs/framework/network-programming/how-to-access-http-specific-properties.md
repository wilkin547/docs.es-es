---
title: 'Cómo: obtener acceso a propiedades específicas de HTTP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: c883321d74bb4309f483604d51057390d00189e6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50043021"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="e1753-102">Cómo: obtener acceso a propiedades específicas de HTTP</span><span class="sxs-lookup"><span data-stu-id="e1753-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="e1753-103">En este ejemplo se muestra cómo desactivar el comportamiento de **conexión persistente** HTTP y obtener el número de versión del protocolo de servidor web.</span><span class="sxs-lookup"><span data-stu-id="e1753-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1753-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e1753-104">Example</span></span>  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1753-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e1753-105">Compiling the Code</span></span>  
 <span data-ttu-id="e1753-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e1753-106">This example requires:</span></span>  
  
-   <span data-ttu-id="e1753-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="e1753-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1753-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1753-108">See Also</span></span>  
 [<span data-ttu-id="e1753-109">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="e1753-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="e1753-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="e1753-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="e1753-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="e1753-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
