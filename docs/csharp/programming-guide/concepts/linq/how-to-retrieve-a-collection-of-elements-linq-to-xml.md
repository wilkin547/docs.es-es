---
title: Procedimiento para recuperar una colección de elementos (LINQ to XML) (C#)
description: El método Elements de C# recupera una colección de los elementos secundarios de un elemento. En este ejemplo de LINQ to XML se itera por los elementos secundarios de un elemento.
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 4f9b6ae4713af9ce1a4eeb5257f57cd9724f68b2
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103358"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="b901c-104">Procedimiento para recuperar una colección de elementos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b901c-104">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b901c-105">En este tema se demuestra el método <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="b901c-105">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="b901c-106">Este método recupera una colección de elementos secundarios de un elemento.</span><span class="sxs-lookup"><span data-stu-id="b901c-106">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b901c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b901c-107">Example</span></span>  
 <span data-ttu-id="b901c-108">Este ejemplo recorre en iteración los elementos secundarios del elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="b901c-108">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="b901c-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="b901c-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="b901c-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b901c-110">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="b901c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b901c-111">See also</span></span>

- [<span data-ttu-id="b901c-112">Ejes de LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="b901c-112">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
