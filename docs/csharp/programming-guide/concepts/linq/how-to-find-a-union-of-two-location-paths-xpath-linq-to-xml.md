---
title: "Cómo: Buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c1e63adc27b32475b4cff908e72157464e0e5097
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a>Cómo: Buscar la unión de dos rutas de acceso a ubicaciones (XPath-LINQ to XML (C#)
XPath permite buscar la unión de los resultados de dos rutas de ubicación XPath.  
  
 La expresión XPath es:  
  
 `//Category|//Price`  
  
 Se pueden conseguir los mismos resultados mediante el operador de consulta estándar <xref:System.Linq.Enumerable.Concat%2A>.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo busca todos los elementos `Category` y todos los elementos `Price` y los concatena en una única recopilación. Tenga en cuenta que la consulta [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] llama a <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> para ordenar los resultados. Los resultados de la evaluación de la expresión XPath también están en el orden del documento.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Datos numéricos (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
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
  
 Este ejemplo produce el siguiente resultado:  
  
```  
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
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
