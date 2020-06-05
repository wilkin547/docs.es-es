---
title: Procedimiento para buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML)
ms.date: 07/20/2015
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
ms.openlocfilehash: 36528d1748d5675231f14de92dcd78734a696711
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406877"
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="01344-102">Cómo: buscar una Unión de dos rutas de acceso de ubicación (XPath-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01344-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="01344-103">XPath permite buscar la unión de los resultados de dos rutas de ubicación XPath.</span><span class="sxs-lookup"><span data-stu-id="01344-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="01344-104">La expresión XPath es:</span><span class="sxs-lookup"><span data-stu-id="01344-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="01344-105">Puede conseguir los mismos resultados usando el operador de consulta estándar <xref:System.Linq.Enumerable.Concat%2A>.</span><span class="sxs-lookup"><span data-stu-id="01344-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01344-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="01344-106">Example</span></span>  
 <span data-ttu-id="01344-107">Este ejemplo busca todos los elementos `Category` y todos los elementos `Price` y los concatena en una única recopilación.</span><span class="sxs-lookup"><span data-stu-id="01344-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="01344-108">Tenga en cuenta que la consulta [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] llama a <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> para ordenar los resultados.</span><span class="sxs-lookup"><span data-stu-id="01344-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="01344-109">Los resultados de la evaluación de la expresión XPath también están en el orden del documento.</span><span class="sxs-lookup"><span data-stu-id="01344-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="01344-110">En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="01344-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim data As XDocument = XDocument.Load("Data.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    data...<Category>.Concat(data...<Price>).InDocumentOrder()  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    data.XPathSelectElements("//Category|//Price")  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="01344-111">Este ejemplo produce el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="01344-111">This example produces the following output:</span></span>  
  
```console
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
  
## <a name="see-also"></a><span data-ttu-id="01344-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="01344-112">See also</span></span>

- [<span data-ttu-id="01344-113">LINQ to XML para los usuarios de XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="01344-113">LINQ to XML for XPath Users (Visual Basic)</span></span>](linq-to-xml-for-xpath-users.md)
