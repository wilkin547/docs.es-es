---
title: 'Cómo: Reemplazar una selección del Proxy Global'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
ms.openlocfilehash: 44845fb67aac4ff9ab9dda8cf4934153c8c4f23c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048271"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="72296-102">Cómo: Reemplazar una selección del Proxy Global</span><span class="sxs-lookup"><span data-stu-id="72296-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="72296-103">Este ejemplo envía una **WebRequest** a `www.contoso.com` que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="72296-103">This example sends a **WebRequest** to `www.contoso.com` that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72296-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72296-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72296-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="72296-105">Compiling the Code</span></span>  
 <span data-ttu-id="72296-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="72296-106">This example requires:</span></span>  
  
- <span data-ttu-id="72296-107">Una [directiva `using`](../../csharp/language-reference/keywords/using-directive.md) para el espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="72296-107">A [`using` directive](../../csharp/language-reference/keywords/using-directive.md) for the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72296-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="72296-108">See also</span></span>

- [<span data-ttu-id="72296-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="72296-109">Using Application Protocols</span></span>](using-application-protocols.md)
- [<span data-ttu-id="72296-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="72296-110">Accessing the Internet Through a Proxy</span></span>](accessing-the-internet-through-a-proxy.md)
