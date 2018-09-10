---
title: 'Cómo: Calcular valores intermedios (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 15ccf58738b64ebfaef77deb162ddb29db0ae33a
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259735"
---
# <a name="how-to-calculate-intermediate-values-c"></a><span data-ttu-id="63819-102">Cómo: Calcular valores intermedios (C#)</span><span class="sxs-lookup"><span data-stu-id="63819-102">How to: Calculate Intermediate Values (C#)</span></span>
<span data-ttu-id="63819-103">Este ejemplo muestra cómo calcular valores intermedios que se pueden usar para ordenar, filtrar y seleccionar.</span><span class="sxs-lookup"><span data-stu-id="63819-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63819-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63819-104">Example</span></span>  
 <span data-ttu-id="63819-105">El siguiente ejemplo utiliza la cláusula `Let`.</span><span class="sxs-lookup"><span data-stu-id="63819-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="63819-106">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="63819-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="63819-107">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="63819-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="63819-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="63819-108">Example</span></span>  
 <span data-ttu-id="63819-109">El siguiente ejemplo muestra la misma consulta sobre un XML que se encuentra en un espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="63819-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="63819-110">Para obtener más información, vea [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md) (Trabajar con espacios de nombres XML [C#]).</span><span class="sxs-lookup"><span data-stu-id="63819-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="63819-111">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos en un espacio de nombres](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="63819-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="63819-112">Este código genera el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="63819-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="63819-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="63819-113">See Also</span></span>

- [<span data-ttu-id="63819-114">Consultas básicas (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63819-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
