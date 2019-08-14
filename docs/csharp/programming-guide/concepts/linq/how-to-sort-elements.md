---
title: Procedimiento para ordenar elementos (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: ac79690ce45f6875900418b39e0f5e86596dceff
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710049"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="d8d47-102">Procedimiento para ordenar elementos (C#)</span><span class="sxs-lookup"><span data-stu-id="d8d47-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="d8d47-103">Este ejemplo muestra cómo escribir una consulta que ordene sus resultados.</span><span class="sxs-lookup"><span data-stu-id="d8d47-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8d47-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8d47-104">Example</span></span>  
 <span data-ttu-id="d8d47-105">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d8d47-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="d8d47-106">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d8d47-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="d8d47-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d8d47-107">Example</span></span>  
 <span data-ttu-id="d8d47-108">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d8d47-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d8d47-109">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="d8d47-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d8d47-110">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos de un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="d8d47-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="d8d47-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="d8d47-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="d8d47-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d8d47-112">See also</span></span>

- <span data-ttu-id="d8d47-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md) (Ordenación de datos [C#])</span><span class="sxs-lookup"><span data-stu-id="d8d47-113">[Sorting Data (C#)](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)</span></span>
