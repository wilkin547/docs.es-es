---
title: "Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest"
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
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ef42c2cdc4d3b230195f89580a7c7abf0952f487
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="3398b-102">Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest</span><span class="sxs-lookup"><span data-stu-id="3398b-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="3398b-103">En este ejemplo se muestra cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest.</span><span class="sxs-lookup"><span data-stu-id="3398b-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3398b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3398b-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3398b-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3398b-105">Compiling the Code</span></span>  
 <span data-ttu-id="3398b-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="3398b-106">This example requires:</span></span>  
  
-   <span data-ttu-id="3398b-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="3398b-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3398b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3398b-108">See Also</span></span>  
 [<span data-ttu-id="3398b-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="3398b-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
