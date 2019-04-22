---
title: Atomización previa de objetos XName (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: 250b7aa8060c8196c28725fded090e2a63a0ee54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819299"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Atomización previa de objetos XName (LINQ to XML) (Visual Basic)
Una manera de mejorar el rendimiento en LINQ to XML es realizar una atomización previa de los objetos <xref:System.Xml.Linq.XName>. La atomización previa significa que asigna una cadena a un objeto <xref:System.Xml.Linq.XName> antes de crear el árbol XML utilizando los constructores de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>. A continuación, en lugar de pasar una cadena al constructor, que utilizaría la conversión implícita de cadena a <xref:System.Xml.Linq.XName>, pasa el objeto <xref:System.Xml.Linq.XName> inicializado.  
  
 Esto mejora el rendimiento si crear un árbol XML de gran tamaño en el que se repiten nombres específicos. Para ello, debe declarar e inicializar los objetos <xref:System.Xml.Linq.XName> antes de construir el árbol XML y, a continuación, utilizar los objetos <xref:System.Xml.Linq.XName> en lugar de especificar las cadenas para los nombres de atributo y elemento. Esta técnica puede producir un aumento significativo del rendimiento si va a crear un gran número de elementos (o atributos) con el mismo nombre.  
  
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

- [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
- [Objetos XName y XNamespace Atomizados (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
