---
title: Procedimiento Prefijos de espacio de nombres de control (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709817"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="cce5c-102">Procedimiento Prefijos de espacio de nombres de control (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="cce5c-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="cce5c-103">En este tema se describe cómo puede controlar prefijos de espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cce5c-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cce5c-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cce5c-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="cce5c-105">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="cce5c-105">Description</span></span>  
 <span data-ttu-id="cce5c-106">Este ejemplo declara dos espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="cce5c-106">This example declares two namespaces.</span></span> <span data-ttu-id="cce5c-107">Especifica `http://www.adventure-works.com` que el espacio de nombres tiene el `aw`prefijo y que `www.fourthcoffee.com` el espacio de `fc`nombres tiene el prefijo.</span><span class="sxs-lookup"><span data-stu-id="cce5c-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="cce5c-108">Código</span><span class="sxs-lookup"><span data-stu-id="cce5c-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="cce5c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cce5c-109">Comments</span></span>  
 <span data-ttu-id="cce5c-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="cce5c-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cce5c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cce5c-111">See also</span></span>

- [<span data-ttu-id="cce5c-112">Información general sobre espacios de nombres (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cce5c-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
