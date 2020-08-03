---
title: Procedimiento para calcular valores intermedios (C#)
description: En este ejemplo de LINQ to XML en C# se muestra cómo calcular valores intermedios que se pueden usar para ordenar, filtrar y seleccionar elementos.
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: fc648f20550de13735a1f6da6b2f811fd0d39004
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103621"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="70a9c-103">Procedimiento para calcular valores intermedios (C#)</span><span class="sxs-lookup"><span data-stu-id="70a9c-103">How to calculate intermediate values (C#)</span></span>
<span data-ttu-id="70a9c-104">Este ejemplo muestra cómo calcular valores intermedios que se pueden usar para ordenar, filtrar y seleccionar.</span><span class="sxs-lookup"><span data-stu-id="70a9c-104">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="70a9c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a9c-105">Example</span></span>  
 <span data-ttu-id="70a9c-106">El siguiente ejemplo utiliza la cláusula `Let`.</span><span class="sxs-lookup"><span data-stu-id="70a9c-106">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="70a9c-107">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="70a9c-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="70a9c-108">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="70a9c-108">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="70a9c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="70a9c-109">Example</span></span>  
 <span data-ttu-id="70a9c-110">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="70a9c-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="70a9c-111">Para más información, consulte [Información general sobre los espacios de nombres (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="70a9c-111">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="70a9c-112">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos de un espacio de nombres](./sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="70a9c-112">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 <span data-ttu-id="70a9c-113">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="70a9c-113">This code produces the following output:</span></span>  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
