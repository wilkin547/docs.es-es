---
title: "Atomización previa de objetos XName (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 519b64a96e03e098d7325cfb779bcd5d53db3741
ms.lasthandoff: 03/13/2017


---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Atomización previa de objetos XName (LINQ to XML) (Visual Basic)
Es una manera de mejorar el rendimiento en LINQ to XML para la atomización previa <xref:System.Xml.Linq.XName>objetos.</xref:System.Xml.Linq.XName> Atomización previa significa que asigna una cadena a un <xref:System.Xml.Linq.XName>objeto antes de crear el árbol XML utilizando los constructores de la <xref:System.Xml.Linq.XElement>y <xref:System.Xml.Linq.XAttribute>clases.</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XName> A continuación, en lugar de pasar una cadena al constructor, que utilizaría la conversión implícita de cadena a <xref:System.Xml.Linq.XName>, pasa el inicializado <xref:System.Xml.Linq.XName>objeto.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName>  
  
 Esto mejora el rendimiento si crear un árbol XML de gran tamaño en el que se repiten nombres específicos. Para ello, debe declarar e inicializar <xref:System.Xml.Linq.XName>objetos antes de construir el árbol XML y, a continuación, utilice el <xref:System.Xml.Linq.XName>objetos en lugar de especificar las cadenas para los nombres de elemento y atributo.</xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XName> Esta técnica puede producir un aumento significativo del rendimiento si va a crear un gran número de elementos (o atributos) con el mismo nombre.  
  
 Debería probar la atomización previa con su situación para decidir si debe utilizarla.  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo se muestra cómo hacerlo.  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 En el siguiente ejemplo se muestra la misma técnica donde el documento XML se encuentra en un espacio de nombres:  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 Este ejemplo produce el siguiente resultado:  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 El ejemplo siguiente es más similar a lo que probablemente encontrará en el mundo real. En este ejemplo, una consulta proporciona el contenido del elemento:  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 El ejemplo anterior se ejecuta mejor que el siguiente, en el que los nombres no se atomizan previamente:  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a>Vea también  
 [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)   
 [Subdividida objetos XName y XNamespace (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
