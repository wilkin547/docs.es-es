---
title: 'Cómo: Reemplazar una selección del Proxy Global'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2be271123e34f155a79269d3b810c50fe24a40c6
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2018
ms.locfileid: "48849937"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="45a84-102">Cómo: Reemplazar una selección del Proxy Global</span><span class="sxs-lookup"><span data-stu-id="45a84-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="45a84-103">Este ejemplo envía una **WebRequest** a `www.contoso.com` que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="45a84-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45a84-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45a84-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="45a84-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="45a84-105">Compiling the Code</span></span>  
 <span data-ttu-id="45a84-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="45a84-106">This example requires:</span></span>  
  
-   <span data-ttu-id="45a84-107">Una [directiva `using`](~/docs/csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="45a84-107">A [`using` directive](~/docs/csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a84-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="45a84-108">See Also</span></span>  
 [<span data-ttu-id="45a84-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="45a84-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="45a84-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="45a84-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
