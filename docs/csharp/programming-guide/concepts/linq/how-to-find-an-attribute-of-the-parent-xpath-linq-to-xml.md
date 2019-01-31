---
title: Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: e139e278141a8f42cddf8103f1c5d8d3195751e4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621817"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Procedimiento para buscar un atributo del elemento principal (XPath-LINQ to XML) (C#)
En este tema se muestra cómo desplazarse hasta el elemento primario y buscar un atributo en él.  
  
 La expresión XPath es:  
  
 `../@id`  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo busca primero un elemento `Author`. Después busca el atributo `id` del elemento primario.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement author =   
    books  
    .Root  
    .Element("Book")  
    .Element("Author");  
  
// LINQ to XML query  
XAttribute att1 =  
    author  
    .Parent  
    .Attribute("id");  
  
// XPath expression  
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();  
  
if (att1 == att2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(att1);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a>Vea también

- [LINQ to XML para usuarios de XPath (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
