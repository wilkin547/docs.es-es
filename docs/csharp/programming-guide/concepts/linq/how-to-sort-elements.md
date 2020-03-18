---
title: Procedimiento para ordenar elementos (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7fad9fcb43905072c88a5704c56672917bfc377c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75347362"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="bbfe8-102">Procedimiento para ordenar elementos (C#)</span><span class="sxs-lookup"><span data-stu-id="bbfe8-102">How to sort elements (C#)</span></span>
<span data-ttu-id="bbfe8-103">Este ejemplo muestra cómo escribir una consulta que ordene sus resultados.</span><span class="sxs-lookup"><span data-stu-id="bbfe8-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbfe8-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbfe8-104">Example</span></span>  
 <span data-ttu-id="bbfe8-105">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bbfe8-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="bbfe8-106">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bbfe8-106">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="bbfe8-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bbfe8-107">Example</span></span>  
 <span data-ttu-id="bbfe8-108">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bbfe8-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="bbfe8-109">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bbfe8-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="bbfe8-110">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos en un espacio de nombres](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="bbfe8-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="bbfe8-111">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="bbfe8-111">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="bbfe8-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbfe8-112">See also</span></span>

- <span data-ttu-id="bbfe8-113">[Ordenación de datos [C#]](./sorting-data.md)</span><span class="sxs-lookup"><span data-stu-id="bbfe8-113">[Sorting Data (C#)](./sorting-data.md)</span></span>
