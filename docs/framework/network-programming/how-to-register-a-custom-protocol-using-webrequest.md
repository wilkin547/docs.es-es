---
description: 'Más información acerca de: Procedimiento: para registrar un protocolo personalizado mediante WebRequest'
title: 'Cómo: registrar un protocolo personalizado mediante WebRequest'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
ms.openlocfilehash: 7415017f20c0c6ed80570992e249fb8121907de2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785762"
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="fd7ad-103">Procedimiento para registrar un protocolo personalizado mediante WebRequest</span><span class="sxs-lookup"><span data-stu-id="fd7ad-103">How to: Register a Custom Protocol Using WebRequest</span></span>

<span data-ttu-id="fd7ad-104">En este ejemplo se muestra cómo registrar una clase específica del protocolo que se define en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-104">This example shows how to register a protocol specific class that is defined elsewhere.</span></span> <span data-ttu-id="fd7ad-105">En este ejemplo, `CustomWebRequestCreator` es el objeto implementado por el usuario que implementa el método **Create** que devuelve el objeto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-105">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="fd7ad-106">El ejemplo del código presupone que ha escrito el código `CustomWebRequest` que implementa el protocolo personalizado.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-106">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fd7ad-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd7ad-107">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fd7ad-108">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fd7ad-108">Compiling the Code</span></span>  

 <span data-ttu-id="fd7ad-109">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fd7ad-109">This example requires:</span></span>  
  
 <span data-ttu-id="fd7ad-110">Referencias al espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="fd7ad-110">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7ad-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd7ad-111">See also</span></span>

- [<span data-ttu-id="fd7ad-112">Programming Pluggable Protocols (Programar protocolos acoplables)</span><span class="sxs-lookup"><span data-stu-id="fd7ad-112">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
