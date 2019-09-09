---
title: Procedimiento para buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 0d7842f190f7ce7869668929b69c2336d33c6183
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253737"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a>Procedimiento para buscar atributos de elementos del mismo nivel con un nombre específico (XPath-LINQ to XML) (C#)
En este tema se muestra cómo buscar todos los atributos de los elementos secundarios del nodo de contexto. Sólo se devuelven los atributos con un nombre específico en la recopilación.  
  
 La expresión XPath es:  
  
 `../Book/@id`  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo primero busca un elemento `Book`, después busca todos los elementos secundarios con el nombre `Book` y después busca todos los atributos con el nombre `id`. El resultado es una colección de atributos.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```output  
Results are identical  
id="bk101"  
id="bk102"  
```  
  