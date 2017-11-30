---
title: "Cómo: crear un árbol de un objeto XmlReader (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ceae7c2bee85e7b368322c8ba195dea9feff672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Cómo: crear un árbol de un objeto XmlReader (Visual Basic)
En este tema se muestra cómo crear un árbol XML directamente de <xref:System.Xml.XmlReader>. Para crear un <xref:System.Xml.Linq.XElement> de <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader> en un nodo de elemento. <xref:System.Xml.XmlReader> omitirá los comentarios y las instrucciones de procesamiento, pero si <xref:System.Xml.XmlReader> se coloca en un nodo de texto, se producirá un error. Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader> en un elemento ante de crear un árbol XML de <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el siguiente documento XML: [Archivo XML de muestra: Libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento. A continuación, carga el objeto <xref:System.Xml.Linq.XElement>.  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
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
 [Analizar XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
