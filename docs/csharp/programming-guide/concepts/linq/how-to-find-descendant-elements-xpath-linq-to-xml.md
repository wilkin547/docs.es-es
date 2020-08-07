---
title: Procedimiento para buscar elementos descendientes (XPath-LINQ to XML) (C#)
description: Aprenda a buscar elementos descendientes con un nombre determinado mediante una expresión XPath. Revise un ejemplo de código que usa un archivo XML de ejemplo.
ms.date: 07/20/2015
ms.assetid: b318da39-bb8b-4c56-a019-e13b12b01831
ms.openlocfilehash: c5a998a05f866203f3b684b8847a4a5647c12e5b
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303275"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-c"></a><span data-ttu-id="a474c-104">Procedimiento para buscar elementos descendientes (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a474c-104">How to find descendant elements (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="a474c-105">En este tema se muestra cómo obtener los elementos descendientes con un nombre particular.</span><span class="sxs-lookup"><span data-stu-id="a474c-105">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="a474c-106">La expresión XPath es `//Name`.</span><span class="sxs-lookup"><span data-stu-id="a474c-106">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a474c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a474c-107">Example</span></span>  
 <span data-ttu-id="a474c-108">Este ejemplo busca todos los descendientes con el nombre `Name`.</span><span class="sxs-lookup"><span data-stu-id="a474c-108">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="a474c-109">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Varios pedidos de compra (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a474c-109">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = po.Root.Descendants("Name");  
  
// XPath expression  
IEnumerable<XElement> list2 = po.XPathSelectElements("//Name");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="a474c-110">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="a474c-110">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
