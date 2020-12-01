---
title: 'Cómo: registrar un protocolo personalizado mediante WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 86ad862dbff9f4a982eec27a6806bcbb6c16f3ae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255811"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="2091b-102">Cómo: registrar un protocolo personalizado mediante WebRequest</span><span class="sxs-lookup"><span data-stu-id="2091b-102">How to: Register a Custom Protocol Using WebRequest</span></span>

<span data-ttu-id="2091b-103">En este ejemplo se muestra cómo registrar una clase específica del protocolo que se define en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="2091b-103">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="2091b-104">En este ejemplo, `CustomWebRequestCreator` es el objeto implementado por el usuario que implementa el método **Create** que devuelve el objeto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="2091b-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="2091b-105">El ejemplo del código presupone que ha escrito el código `CustomWebRequest` que implementa el protocolo personalizado.</span><span class="sxs-lookup"><span data-stu-id="2091b-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2091b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2091b-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2091b-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="2091b-107">Compiling the Code</span></span>  

 <span data-ttu-id="2091b-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="2091b-108">This example requires:</span></span>  
  
 <span data-ttu-id="2091b-109">Referencias al espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="2091b-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2091b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2091b-110">See also</span></span>

- [<span data-ttu-id="2091b-111">Programar protocolos acoplables</span><span class="sxs-lookup"><span data-stu-id="2091b-111">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
