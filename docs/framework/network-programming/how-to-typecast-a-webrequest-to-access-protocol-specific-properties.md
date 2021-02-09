---
description: 'Más información acerca de: Procedimiento: para convertir un elemento WebRequest a propiedades específicas del protocolo de acceso'
title: 'Cómo: convertir una WebRequest a propiedades específicas del protocolo de acceso'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
ms.openlocfilehash: 24c07a3f2d77dec180476dec3c58f07b40e00c8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662746"
---
# <a name="how-to-typecast-a-webrequest-to-access-protocol-specific-properties"></a><span data-ttu-id="146cf-103">Procedimiento para convertir un elemento WebRequest a propiedades específicas del protocolo de acceso</span><span class="sxs-lookup"><span data-stu-id="146cf-103">How to: Typecast a WebRequest to Access Protocol Specific Properties</span></span>

<span data-ttu-id="146cf-104">En este ejemplo se muestra cómo convertir una WebRequest de manera que pueda tener acceso a las propiedades específicas del protocolo.</span><span class="sxs-lookup"><span data-stu-id="146cf-104">This example shows how to typecast a WebRequest so that you can access protocol specific properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="146cf-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="146cf-105">Example</span></span>  
  
```csharp  
HttpWebRequest httpreq =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## <a name="see-also"></a><span data-ttu-id="146cf-106">Vea también</span><span class="sxs-lookup"><span data-stu-id="146cf-106">See also</span></span>

- [<span data-ttu-id="146cf-107">Programming Pluggable Protocols (Programar protocolos acoplables)</span><span class="sxs-lookup"><span data-stu-id="146cf-107">Programming Pluggable Protocols</span></span>](programming-pluggable-protocols.md)
