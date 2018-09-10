---
title: 'Cómo: Recuperar una colección de elementos (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 9ad75ce4d3ca113ed432d2b2351067babe33a74f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857069"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="9c631-102">Cómo: Recuperar una colección de elementos (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9c631-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="9c631-103">En este tema se demuestra el método <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="9c631-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="9c631-104">Este método recupera una colección de elementos secundarios de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9c631-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c631-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c631-105">Example</span></span>  
 <span data-ttu-id="9c631-106">Este ejemplo recorre en iteración los elementos secundarios del elemento `purchaseOrder`.</span><span class="sxs-lookup"><span data-stu-id="9c631-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="9c631-107">En este ejemplo se usa el siguiente documento XML: [Archivo XML de ejemplo: Pedido de compra común (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="9c631-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="9c631-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="9c631-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="9c631-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c631-109">See Also</span></span>

- <span data-ttu-id="9c631-110">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md) (Ejes de LINQ to XML [C#])</span><span class="sxs-lookup"><span data-stu-id="9c631-110">[LINQ to XML Axes (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)</span></span>
