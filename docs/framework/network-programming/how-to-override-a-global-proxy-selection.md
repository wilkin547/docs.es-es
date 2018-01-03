---
title: "Cómo: Reemplazar una selección del Proxy Global"
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
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 970b428343f4e2dec73e7eceec20414cd8bdfbac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="b63c3-102">Cómo: Reemplazar una selección del Proxy Global</span><span class="sxs-lookup"><span data-stu-id="b63c3-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="b63c3-103">Este ejemplo envía **WebRequest** a www.contoso.com que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="b63c3-103">This example sends a **WebRequest** to www.contoso.com that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b63c3-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b63c3-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b63c3-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="b63c3-105">Compiling the Code</span></span>  
 <span data-ttu-id="b63c3-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="b63c3-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b63c3-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="b63c3-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b63c3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="b63c3-108">See Also</span></span>  
 [<span data-ttu-id="b63c3-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="b63c3-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="b63c3-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="b63c3-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
