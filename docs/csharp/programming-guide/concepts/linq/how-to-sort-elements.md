---
title: Procedimiento para ordenar elementos (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 66a41fc018b2df64aa95c24d1d698b6c38fd189a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640789"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="7d2e1-102">Procedimiento para ordenar elementos (C#)</span><span class="sxs-lookup"><span data-stu-id="7d2e1-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="7d2e1-103">Este ejemplo muestra cómo escribir una consulta que ordene sus resultados.</span><span class="sxs-lookup"><span data-stu-id="7d2e1-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d2e1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d2e1-104">Example</span></span>  
 <span data-ttu-id="7d2e1-105">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d2e1-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="7d2e1-106">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7d2e1-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="7d2e1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7d2e1-107">Example</span></span>  
 <span data-ttu-id="7d2e1-108">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7d2e1-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="7d2e1-109">Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="7d2e1-109">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="7d2e1-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos de un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="7d2e1-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="7d2e1-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="7d2e1-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d2e1-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d2e1-112">See also</span></span>

- <span data-ttu-id="7d2e1-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos [C#])</span><span class="sxs-lookup"><span data-stu-id="7d2e1-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)</span></span>
- [<span data-ttu-id="7d2e1-114">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d2e1-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
