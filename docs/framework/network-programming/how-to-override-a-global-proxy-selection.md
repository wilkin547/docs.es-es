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
ms.openlocfilehash: dc9f8f4e958d1988cecd769431e99d70ff2a4cfd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="534c2-102">Cómo: Reemplazar una selección del Proxy Global</span><span class="sxs-lookup"><span data-stu-id="534c2-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="534c2-103">Este ejemplo envía **WebRequest** a www.contoso.com que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="534c2-103">This example sends a **WebRequest** to www.contoso.com that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="534c2-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="534c2-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="534c2-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="534c2-105">Compiling the Code</span></span>  
 <span data-ttu-id="534c2-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="534c2-106">This example requires:</span></span>  
  
-   <span data-ttu-id="534c2-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="534c2-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534c2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="534c2-108">See Also</span></span>  
 [<span data-ttu-id="534c2-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="534c2-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="534c2-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="534c2-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
