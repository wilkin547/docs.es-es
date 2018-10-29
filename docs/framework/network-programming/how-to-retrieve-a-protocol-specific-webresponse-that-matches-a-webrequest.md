---
title: 'Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
ms.openlocfilehash: f1da226fb62c55f37183404765430c094f1cd63f
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188279"
---
# <a name="how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest"></a><span data-ttu-id="a01e9-102">Cómo: recuperar una WebResponse específica de protocolo que coincida con una WebRequest</span><span class="sxs-lookup"><span data-stu-id="a01e9-102">How to: Retrieve a Protocol-Specific WebResponse that Matches a WebRequest</span></span>
<span data-ttu-id="a01e9-103">En este ejemplo se muestra cómo recuperar una WebResponse específica de protocolo que coincide con una WebRequest.</span><span class="sxs-lookup"><span data-stu-id="a01e9-103">This example shows how to retrieve a protocol-specific WebResponse that matches a WebRequest.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a01e9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a01e9-104">Example</span></span>  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a01e9-105">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="a01e9-105">Compiling the Code</span></span>  
 <span data-ttu-id="a01e9-106">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="a01e9-106">This example requires:</span></span>  
  
-   <span data-ttu-id="a01e9-107">Referencias al espacio de nombres **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="a01e9-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a01e9-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a01e9-108">See Also</span></span>  
 [<span data-ttu-id="a01e9-109">Solicitud de datos</span><span class="sxs-lookup"><span data-stu-id="a01e9-109">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
