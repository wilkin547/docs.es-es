---
title: Procedimiento para buscar una lista de elementos secundarios (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
ms.openlocfilehash: 2b6f6031441e7d1bd015e25a8debad7dd7f3b261
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141228"
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="e0b4a-102">Procedimiento para buscar una lista de elementos secundarios (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e0b4a-102">How to find a list of child elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="e0b4a-103">En este tema se compara el eje de los elementos secundarios de XPath con el eje [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="e0b4a-103">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="e0b4a-104">La expresión XPath es: `./*`</span><span class="sxs-lookup"><span data-stu-id="e0b4a-104">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0b4a-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0b4a-105">Example</span></span>  
 <span data-ttu-id="e0b4a-106">Este ejemplo busca todos los elementos secundarios del elemento `Address`.</span><span class="sxs-lookup"><span data-stu-id="e0b4a-106">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="e0b4a-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e0b4a-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder").Element("Address");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Elements();  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("./*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="e0b4a-108">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="e0b4a-108">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
