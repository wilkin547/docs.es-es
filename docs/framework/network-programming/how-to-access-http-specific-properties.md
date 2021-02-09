---
description: 'Más información acerca de: Procedimiento: para acceder a propiedades específicas de HTTP'
title: 'Cómo: obtener acceso a propiedades específicas de HTTP'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: a54ef247b479cf6cdec8dc28732304cf03b0b202
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729307"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="ed722-103">Procedimiento para acceder a propiedades específicas de HTTP</span><span class="sxs-lookup"><span data-stu-id="ed722-103">How to: Access HTTP-Specific Properties</span></span>

<span data-ttu-id="ed722-104">En este ejemplo se muestra cómo desactivar el comportamiento de **conexión persistente** HTTP y obtener el número de versión del protocolo de servidor web.</span><span class="sxs-lookup"><span data-stu-id="ed722-104">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed722-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed722-105">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="ed722-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ed722-106">Compiling the Code</span></span>  

 <span data-ttu-id="ed722-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ed722-107">This example requires:</span></span>  
  
- <span data-ttu-id="ed722-108">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="ed722-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed722-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed722-109">See also</span></span>

- [<span data-ttu-id="ed722-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="ed722-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="ed722-111">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ed722-111">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="ed722-112">HTTP</span><span class="sxs-lookup"><span data-stu-id="ed722-112">HTTP</span></span>](http.md)
