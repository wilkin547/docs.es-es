---
title: Procedimiento para recuperar un elemento WebResponse específico del protocolo que coincida con un elemento WebRequest
description: Obtenga información sobre cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest en .NET Framework.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: fd163c115dcd19c05f93f4c202b043440834ba9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266745"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="005ff-103">Procedimiento para recuperar un elemento WebResponse específico del protocolo que coincida con un elemento WebRequest</span><span class="sxs-lookup"><span data-stu-id="005ff-103">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>

<span data-ttu-id="005ff-104">En este ejemplo se muestra cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest.</span><span class="sxs-lookup"><span data-stu-id="005ff-104">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="005ff-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="005ff-105">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="005ff-106">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="005ff-106">Compiling the Code</span></span>  

 <span data-ttu-id="005ff-107">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="005ff-107">This example requires:</span></span>  
  
- <span data-ttu-id="005ff-108">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="005ff-108">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005ff-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="005ff-109">See also</span></span>

- [<span data-ttu-id="005ff-110">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="005ff-110">Requesting Data</span></span>](requesting-data.md)
