---
title: "Cómo: buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83b3ddca-830a-4b71-9756-9e4bdf907302
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 751d9559ae3b0bfe62fc866baf52fbef7babb7e3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-visual-basic"></a>Cómo: buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (Visual Basic)
En este tema se muestra cómo buscar todos los atributos de los elementos secundarios del nodo de contexto. Sólo se devuelven los atributos con un nombre específico en la recopilación.  
  
 La expresión XPath es:  
  
 `../Book/@id`  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo primero busca un elemento `Book`, después busca todos los elementos secundarios con el nombre `Book` y después busca todos los atributos con el nombre `id`. El resultado es una colección de atributos.  
  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```vb  
Dim books as XDocument = XDocument.Load("Books.xml")  
Dim book As XElement = books.Root.<Book>(0)  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XAttribute) = _  
    From el In book.Parent.<Book> _  
    Select el.Attribute("id")  
  
' XPath expression  
Dim list2 As IEnumerable(Of XAttribute) = DirectCast(book. _  
    XPathEvaluate("../Book/@id"), IEnumerable).Cast(Of XAttribute)()  
  
If list1.Count() = list2.Count() And _  
        (list1.Intersect(list2)).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
  
For Each el As XAttribute In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a>Vea también  
 [LINQ to XML para usuarios de XPath (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
