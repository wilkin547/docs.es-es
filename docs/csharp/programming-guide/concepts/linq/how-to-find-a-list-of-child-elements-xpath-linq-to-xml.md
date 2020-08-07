---
title: Procedimiento para buscar una lista de elementos secundarios (XPath-LINQ to XML) (C#)
description: Aprenda a buscar una lista de elementos secundarios mediante una expresión XPath. Revise un ejemplo de código que encuentra todos los elementos secundarios de un elemento específico.
ms.date: 07/20/2015
ms.assetid: 7c589dd8-f680-4cdb-9d6a-78d57e2555e8
ms.openlocfilehash: a3025aca7fb1055acd55e5ce98914d8359ebe4b7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301728"
---
# <a name="how-to-find-a-list-of-child-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="60080-104">Procedimiento para buscar una lista de elementos secundarios (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="60080-104">How to find a list of child elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="60080-105">En este tema se compara el eje de los elementos secundarios de XPath con el eje [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A>.</span><span class="sxs-lookup"><span data-stu-id="60080-105">This topic compares the XPath child elements axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>  
  
 <span data-ttu-id="60080-106">La expresión XPath es: `./*`</span><span class="sxs-lookup"><span data-stu-id="60080-106">The XPath expression is: `./*`</span></span>  
  
## <a name="example"></a><span data-ttu-id="60080-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="60080-107">Example</span></span>  
 <span data-ttu-id="60080-108">Este ejemplo busca todos los elementos secundarios del elemento `Address`.</span><span class="sxs-lookup"><span data-stu-id="60080-108">This example finds all of the child elements of the `Address` element.</span></span>  
  
 <span data-ttu-id="60080-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="60080-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="60080-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="60080-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Street>123 Maple Street</Street>  
<City>Mill Valley</City>  
<State>CA</State>  
<Zip>10999</Zip>  
<Country>USA</Country>  
```  
