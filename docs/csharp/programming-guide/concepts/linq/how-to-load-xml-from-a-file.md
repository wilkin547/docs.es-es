---
title: Procedimiento para cargar un documento XML desde un archivo (C#)
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: f97e99a3d5fb2dd5628e1dc00909b6608255a967
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688137"
---
# <a name="how-to-load-xml-from-a-file-c"></a>Procedimiento para cargar un documento XML desde un archivo (C#)
En este tema se muestra cómo cargar XML de una dirección URI usando el método <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo muestra cómo cargar un documento XML desde un archivo. El siguiente ejemplo carga books.xml y produce el árbol XML en la consola.  
  
 Este ejemplo utiliza el siguiente documento XML: [Archivo XML de ejemplo: Libros (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 Este código genera el siguiente resultado:  
  
```xml  
<Catalog>  
  <Book id="bk101">  
    <Author>Garghentini, Davide</Author>  
    <Title>XML Developer's Guide</Title>  
    <Genre>Computer</Genre>  
    <Price>44.95</Price>  
    <PublishDate>2000-10-01</PublishDate>  
    <Description>An in-depth look at creating applications   
      with XML.</Description>  
  </Book>  
  <Book id="bk102">  
    <Author>Garcia, Debra</Author>  
    <Title>Midnight Rain</Title>  
    <Genre>Fantasy</Genre>  
    <Price>5.95</Price>  
    <PublishDate>2000-12-16</PublishDate>  
    <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
  </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Vea también

- [Analizar XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
