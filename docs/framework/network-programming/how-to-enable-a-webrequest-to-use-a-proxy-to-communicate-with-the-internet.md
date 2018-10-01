---
title: 'Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86bf21580db9bc6d9890f0935e283b653ba2e0b5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47397795"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a><span data-ttu-id="6d6f2-102">Cómo: habilitar un elemento WebRequest para usar un proxy para comunicarse con Internet</span><span class="sxs-lookup"><span data-stu-id="6d6f2-102">How to: Enable a WebRequest to Use a Proxy to Communicate With the Internet</span></span>
<span data-ttu-id="6d6f2-103">En este ejemplo se crea una instancia de proxy global que permitirá que cualquier <xref:System.Net.WebRequest> use un proxy para comunicarse con Internet.</span><span class="sxs-lookup"><span data-stu-id="6d6f2-103">This example creates a global proxy instance that will enable any <xref:System.Net.WebRequest> to use a proxy to communicate with the Internet.</span></span> <span data-ttu-id="6d6f2-104">En el ejemplo se da por supuesto que el servidor proxy se denomina `webproxy` y que se comunica en el puerto 80, el puerto HTTP estándar.</span><span class="sxs-lookup"><span data-stu-id="6d6f2-104">The example assumes that the proxy server is named `webproxy` and that it communicates on port 80, the standard HTTP port.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d6f2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d6f2-105">Example</span></span>  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6d6f2-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="6d6f2-106">Compiling the Code</span></span>  
 <span data-ttu-id="6d6f2-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="6d6f2-107">This example requires:</span></span>  
  
-   <span data-ttu-id="6d6f2-108">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="6d6f2-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d6f2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d6f2-109">See Also</span></span>  
 [<span data-ttu-id="6d6f2-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="6d6f2-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="6d6f2-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="6d6f2-111">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
