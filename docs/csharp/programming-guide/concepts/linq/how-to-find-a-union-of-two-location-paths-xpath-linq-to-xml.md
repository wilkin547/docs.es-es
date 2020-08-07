---
title: Procedimiento para buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML) (C#)
description: Aprenda a buscar una unión de dos rutas de acceso de ubicación de XPath mediante una expresión XPath. Revise un ejemplo de código que usa un archivo XML de ejemplo.
ms.date: 07/20/2015
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
ms.openlocfilehash: 65b20fe25a0990fd82ce3bd08c3433499e728512
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303327"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="0560e-104">Procedimiento para buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0560e-104">How to find a union of two location paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0560e-105">XPath permite buscar la unión de los resultados de dos rutas de ubicación XPath.</span><span class="sxs-lookup"><span data-stu-id="0560e-105">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="0560e-106">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="0560e-106">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="0560e-107">Puede conseguir los mismos resultados usando el operador de consulta estándar <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="0560e-107">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0560e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0560e-108">Example</span></span>  
 <span data-ttu-id="0560e-109">Este ejemplo busca todos los elementos `Category` y todos los elementos `Price` y los concatena en una única recopilación.</span><span class="sxs-lookup"><span data-stu-id="0560e-109">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="0560e-110">Tenga en cuenta que la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] llama a <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="0560e-110">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="0560e-111">Los resultados de la evaluación de la expresión XPath también están en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="0560e-111">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="0560e-112">Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Datos numéricos (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="0560e-112">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="0560e-113">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="0560e-113">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  