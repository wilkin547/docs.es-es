---
title: "Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 937f4ac06ef4788c42b364fe03226e32a55572f3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="df3f9-102">Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet</span><span class="sxs-lookup"><span data-stu-id="df3f9-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="df3f9-103">En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet.</span><span class="sxs-lookup"><span data-stu-id="df3f9-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="df3f9-104">En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="df3f9-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df3f9-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df3f9-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="df3f9-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="df3f9-106">Compiling the Code</span></span>  
 <span data-ttu-id="df3f9-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="df3f9-107">This example requires:</span></span>  
  
-   <span data-ttu-id="df3f9-108">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="df3f9-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df3f9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="df3f9-109">See Also</span></span>  
 [<span data-ttu-id="df3f9-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="df3f9-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="df3f9-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="df3f9-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
