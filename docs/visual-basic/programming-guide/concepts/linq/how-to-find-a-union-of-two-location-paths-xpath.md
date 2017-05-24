---
title: "Cómo: buscar la unión de dos rutas de ubicación (XPath-LINQ to XML) (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c82c09b4-cb0a-47ec-8cc3-a124144c2788
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 90fe1bd9a7992c5e3f4c57f5596a88e5be506917
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017


---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-visual-basic"></a>Cómo: buscar la unión de dos rutas de ubicación (XPath-LINQ to XML) (Visual Basic)
XPath permite buscar la unión de los resultados de dos rutas de ubicación XPath.  
  
 La expresión XPath es:  
  
 `//Category|//Price`  
  
 Puede conseguir los mismos resultados mediante la <xref:System.Linq.Enumerable.Concat%2A>operador de consulta estándar.</xref:System.Linq.Enumerable.Concat%2A>  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo busca todos los elementos `Category` y todos los elementos `Price` y los concatena en una única recopilación. Tenga en cuenta que el [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] consulta llama <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A>para ordenar los resultados.</xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> Los resultados de la evaluación de la expresión XPath también están en el orden del documento.  
  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de muestra: datos numéricos (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).  
  
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
 [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)

