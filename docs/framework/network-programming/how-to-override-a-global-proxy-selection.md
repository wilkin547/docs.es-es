---
title: 'Cómo: Reemplazar una selección del Proxy Global'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: c10cff979a18d8e07a1e7089f96157e4c38f040e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33393911"
---
# <a name="how-to-override-a-global-proxy-selection"></a><span data-ttu-id="a1c26-102">Cómo: Reemplazar una selección del Proxy Global</span><span class="sxs-lookup"><span data-stu-id="a1c26-102">How to: Override a Global Proxy Selection</span></span>
<span data-ttu-id="a1c26-103">Este ejemplo envía **WebRequest** a www.contoso.com que reemplaza la selección global de proxy con un servidor proxy denominado `alternateproxy` en el puerto 80.</span><span class="sxs-lookup"><span data-stu-id="a1c26-103">This example sends a **WebRequest** to www.contoso.com that overrides the global proxy selection with a proxy server named `alternateproxy` on port 80.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1c26-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a1c26-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a1c26-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a1c26-105">Compiling the Code</span></span>  
 <span data-ttu-id="a1c26-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a1c26-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a1c26-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="a1c26-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c26-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1c26-108">See Also</span></span>  
 [<span data-ttu-id="a1c26-109">Usar protocolos de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a1c26-109">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="a1c26-110">Acceso a Internet a través de un proxy</span><span class="sxs-lookup"><span data-stu-id="a1c26-110">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
