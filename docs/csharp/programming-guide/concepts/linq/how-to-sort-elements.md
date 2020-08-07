---
title: Procedimiento para ordenar elementos (C#)
description: Aprenda a ordenar elementos. Vea ejemplos de cómo escribir una consulta que ordene sus resultados en un documento XML.
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 669d9cf583e6ab70c93be39ad271eaf104f88718
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301442"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="b6faf-104">Procedimiento para ordenar elementos (C#)</span><span class="sxs-lookup"><span data-stu-id="b6faf-104">How to sort elements (C#)</span></span>
<span data-ttu-id="b6faf-105">Este ejemplo muestra cómo escribir una consulta que ordene sus resultados.</span><span class="sxs-lookup"><span data-stu-id="b6faf-105">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6faf-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6faf-106">Example</span></span>  
 <span data-ttu-id="b6faf-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b6faf-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b6faf-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b6faf-108">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="b6faf-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6faf-109">Example</span></span>  
 <span data-ttu-id="b6faf-110">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="b6faf-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b6faf-111">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="b6faf-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="b6faf-112">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos de un espacio de nombres](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="b6faf-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="b6faf-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="b6faf-113">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6faf-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b6faf-114">See also</span></span>

- [<span data-ttu-id="b6faf-115">Ordenación de datos (C#)</span><span class="sxs-lookup"><span data-stu-id="b6faf-115">Sorting Data (C#)</span></span>](./sorting-data.md)
