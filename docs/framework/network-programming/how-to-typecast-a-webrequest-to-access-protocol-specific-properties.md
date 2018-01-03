---
title: "Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso"
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
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: e398fa0dce066aec735f149f20e2803e7cd5ce80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="31bba-102">Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso</span><span class="sxs-lookup"><span data-stu-id="31bba-102">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>
<span data-ttu-id="31bba-103">En este ejemplo se muestra cómo convertir una WebRequest de manera que pueda tener acceso a las propiedades específicas del protocolo.</span><span class="sxs-lookup"><span data-stu-id="31bba-103">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31bba-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bba-104">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="31bba-105">Vea también</span><span class="sxs-lookup"><span data-stu-id="31bba-105">See Also</span></span>  
 [<span data-ttu-id="31bba-106">Programming Pluggable Protocols (Programar protocolos acoplables)</span><span class="sxs-lookup"><span data-stu-id="31bba-106">Programming Pluggable Protocols</span></span>](../../../docs/framework/network-programming/programming-pluggable-protocols.md)
