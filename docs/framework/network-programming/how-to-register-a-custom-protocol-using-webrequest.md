---
title: "Cómo: registrar un protocolo personalizado mediante WebRequest"
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
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 4fdb1188aeb7fd754ab21a268070830f55347441
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-a-custom-protocol-using-webrequest"></a><span data-ttu-id="f96c2-102">Cómo: registrar un protocolo personalizado mediante WebRequest</span><span class="sxs-lookup"><span data-stu-id="f96c2-102">How to: Register a Custom Protocol Using WebRequest</span></span>
<span data-ttu-id="f96c2-103">En este ejemplo se muestra cómo registrar una clase específica del protocolo que se define en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="f96c2-103">This example shows how to register a protocol specific classthat is defined elsewhere.</span></span> <span data-ttu-id="f96c2-104">En este ejemplo, `CustomWebRequestCreator` es el objeto implementado por el usuario que implementa el método **Create** que devuelve el objeto `CustomWebRequest`.</span><span class="sxs-lookup"><span data-stu-id="f96c2-104">In this example, `CustomWebRequestCreator` is the user-implemented object that implements the **Create** method that returns the `CustomWebRequest` object.</span></span> <span data-ttu-id="f96c2-105">El ejemplo del código presupone que ha escrito el código `CustomWebRequest` que implementa el protocolo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f96c2-105">The code example assumes that you have written the `CustomWebRequest` code that implements the custom protocol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f96c2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f96c2-106">Example</span></span>  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f96c2-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="f96c2-107">Compiling the Code</span></span>  
 <span data-ttu-id="f96c2-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="f96c2-108">This example requires:</span></span>  
  
 <span data-ttu-id="f96c2-109">Referencias al espacio de nombres <xref:System.Net>.</span><span class="sxs-lookup"><span data-stu-id="f96c2-109">References to the <xref:System.Net> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f96c2-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f96c2-110">See Also</span></span>  
 [<span data-ttu-id="f96c2-111">Programming Pluggable Protocols (Programar protocolos acoplables)</span><span class="sxs-lookup"><span data-stu-id="f96c2-111">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
