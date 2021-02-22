---
title: Procedimiento para recuperar un elemento WebResponse específico del protocolo que coincida con un elemento WebRequest
description: Obtenga información sobre cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: 920704bedce478ed5a4f7906379a634a3b2a4e31
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584348"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="62425-103">Procedimiento para recuperar un elemento WebResponse específico del protocolo que coincida con un elemento WebRequest</span><span class="sxs-lookup"><span data-stu-id="62425-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="62425-104">En este ejemplo se muestra cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest.</span><span class="sxs-lookup"><span data-stu-id="62425-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62425-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="62425-105">Example</span></span>  
  
```csharp  
HttpWebRequest req = (HttpWebRequest)WebRequest.Create("http://www.contoso.com/");
HttpWebResponse resp = (HttpWebResponse)req.GetResponse();
```  
  
```vb  
Dim req As HttpWebRequest = CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)
Dim resp As HttpWebResponse = CType(req.GetResponse(), HttpWebResponse)
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="62425-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="62425-106">Compiling the Code</span></span>  

 <span data-ttu-id="62425-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="62425-107">This example requires:</span></span>  
  
- <span data-ttu-id="62425-108">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="62425-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62425-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="62425-109">See also</span></span>

- [<span data-ttu-id="62425-110">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="62425-110">Requesting Data</span></span>](requesting-data.md)
