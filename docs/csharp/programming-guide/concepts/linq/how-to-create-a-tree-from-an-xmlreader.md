---
title: Procedimiento para crear un árbol a partir de un objeto XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 9ead6352112d9e1b56bd70699c90133e432f96b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169277"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a>Procedimiento para crear un árbol a partir de un objeto XmlReader (C#)
En este tema se muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>. Para crear un <xref:System.Xml.Linq.XElement> de <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader> en un nodo de elemento. <xref:System.Xml.XmlReader> omitirá los comentarios y las instrucciones de procesamiento, pero si <xref:System.Xml.XmlReader> se coloca en un nodo de texto, se producirá un error. Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader> en un elemento ante de crear un árbol XML de <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: libros (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).  
  
 El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento. A continuación, carga el objeto <xref:System.Xml.Linq.XElement>.  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
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

- [Parsing XML (C#)](how-to-parse-a-string.md) (Analizar XML [C#])
