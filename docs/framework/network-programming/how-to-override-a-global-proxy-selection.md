---
title: Procedimiento para reemplazar una selección del proxy global
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 2389ea01a980f80c7723f9b481ede2e1fe915b28
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624541"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="488a1-102">Procedimiento para reemplazar una selección del proxy global</span><span class="sxs-lookup"><span data-stu-id="488a1-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="488a1-103">Este ejemplo envía una **WebRequest** a `www.contoso.com` que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="488a1-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="488a1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="488a1-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="488a1-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="488a1-105">Compiling the Code</span></span>  
 <span data-ttu-id="488a1-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="488a1-106">This example requires:</span></span>  
  
- <span data-ttu-id="488a1-107">Una [directiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="488a1-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="488a1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="488a1-108">See also</span></span>

- [<span data-ttu-id="488a1-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="488a1-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)
- [<span data-ttu-id="488a1-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="488a1-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
