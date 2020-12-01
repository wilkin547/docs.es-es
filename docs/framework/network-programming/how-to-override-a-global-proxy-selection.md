---
title: Procedimiento para reemplazar una selección del proxy global
description: Siga este ejemplo para invalidar la selección de proxy global mediante el envío de una solicitud WebRequest a una dirección URL, lo que invalida la selección con un servidor proxy.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 8931cdc471b957447277c333ba482a0cec0e6aa5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96265744"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="dcbf6-103">Procedimiento para reemplazar una selección del proxy global</span><span class="sxs-lookup"><span data-stu-id="dcbf6-103">How to: Override a Global Proxy Selection</span></span>

<span data-ttu-id="dcbf6-104">Este ejemplo envía una **WebRequest** a `www.contoso.com` que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="dcbf6-104">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcbf6-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcbf6-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dcbf6-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="dcbf6-106">Compiling the Code</span></span>  

 <span data-ttu-id="dcbf6-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="dcbf6-107">This example requires:</span></span>  
  
- <span data-ttu-id="dcbf6-108">Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="dcbf6-108">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcbf6-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcbf6-109">See also</span></span>

- [<span data-ttu-id="dcbf6-110">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="dcbf6-110">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="dcbf6-111">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="dcbf6-111">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
