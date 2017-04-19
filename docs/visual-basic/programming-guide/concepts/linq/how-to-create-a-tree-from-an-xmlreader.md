---
title: "Cómo: crear un árbol de XmlReader (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a8dff4e518d8850b4050389e5677ac81ecd1e074
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Cómo: crear un árbol de XmlReader (Visual Basic)
Este tema muestra cómo crear un árbol XML directamente desde un <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> Para crear un <xref:System.Xml.Linq.XElement>de un <xref:System.Xml.XmlReader>, debe colocar el <xref:System.Xml.XmlReader>en un nodo element.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement> El <xref:System.Xml.XmlReader>omitirá los comentarios y el procesamiento de instrucciones, pero si el <xref:System.Xml.XmlReader>se coloca en un nodo de texto, se producirá un error.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Para evitar tales errores, coloque siempre <xref:System.Xml.XmlReader>en un elemento antes de crear un árbol XML desde <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader>  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo utiliza el siguiente documento XML: [archivo XML de ejemplo: libros (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 El siguiente código crea un objeto `T:System.Xml.XmlReader` y lee nodos hasta que encuentra el primer nodo de elemento. A continuación, carga el <xref:System.Xml.Linq.XElement>objeto.</xref:System.Xml.Linq.XElement>  
  
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
