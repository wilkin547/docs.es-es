---
title: Atomización previa de objetos XName (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: c0e75afa797d2b20f32fc55e6c19d0c1593d174c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740782"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a>Atomización previa de objetos XName (LINQ to XML) (Visual Basic)

Una manera de mejorar el rendimiento en LINQ to XML es realizar una atomización previa de los objetos <xref:System.Xml.Linq.XName>. La atomización previa significa que asigna una cadena a un <xref:System.Xml.Linq.XName> objeto antes de crear el árbol XML mediante los constructores de las clases <xref:System.Xml.Linq.XElement> y <xref:System.Xml.Linq.XAttribute>. A continuación, en lugar de pasar una cadena al constructor, que utilizaría la conversión implícita de cadena a <xref:System.Xml.Linq.XName>, pasa el objeto <xref:System.Xml.Linq.XName> inicializado.

Esto mejora el rendimiento si crear un árbol XML de gran tamaño en el que se repiten nombres específicos. Para ello, debe declarar e inicializar los objetos <xref:System.Xml.Linq.XName> antes de construir el árbol XML y, a continuación, utilizar los objetos <xref:System.Xml.Linq.XName> en lugar de especificar las cadenas para los nombres de atributo y elemento. Esta técnica puede producir un aumento significativo del rendimiento si va a crear un gran número de elementos (o atributos) con el mismo nombre.

Debería probar la atomización previa con su situación para decidir si debe utilizarla.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se muestra esto:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

En este ejemplo se produce la siguiente salida:

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
Dim root1 As XName = aw + "Root"
Dim data As XName = aw + "Data"
Dim id As XName = "ID"

Dim root2 As New XElement(root1, New XAttribute(XNamespace.Xmlns + "aw", aw),
                          New XElement(data, New XAttribute(id, "1"), "4,100,000"),
                          New XElement(data, New XAttribute(id, "2"), "3,700,000"),
                          New XElement(data, New XAttribute(id, "3"), "1,150,000"))

Console.WriteLine(root2)
```

En este ejemplo se produce la siguiente salida:

```xml
<aw:Root xmlns:aw="http://www.adventure-works.com">
  <aw:Data ID="1">4,100,000</aw:Data>
  <aw:Data ID="2">3,700,000</aw:Data>
  <aw:Data ID="3">1,150,000</aw:Data>
</aw:Root>
```

El ejemplo siguiente es más similar a lo que probablemente encontrará en el mundo real. En este ejemplo, una consulta proporciona el contenido del elemento:

```vb
Dim root1 As XName = "Root"
Dim data As XName = "Data"
Dim id As XName = "ID"
  
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root2 As New XElement(root1, From i In Enumerable.Range(1, 100000)
                                 Select New XElement(data, New XAttribute(ID, i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```  

El ejemplo anterior se ejecuta mejor que el siguiente, en el que los nombres no se atomizan previamente:

```vb
Dim sw As Stopwatch = Stopwatch.StartNew()
Dim root As New XElement("Root", From i In Enumerable.Range(1, 100000)
                                 Select New XElement("Data", New XAttribute("ID", i), i * 5))
sw.Stop()
Console.WriteLine($"Time to construct: {sw.ElapsedMilliseconds} milliseconds")
```

## <a name="see-also"></a>Consulte también

- [Rendimiento (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
- [Objetos XName y XNamespace atomizados (LINQ to XML) (Visual Basic)](atomized-xname-and-xnamespace-objects-linq-to-xml.md)
