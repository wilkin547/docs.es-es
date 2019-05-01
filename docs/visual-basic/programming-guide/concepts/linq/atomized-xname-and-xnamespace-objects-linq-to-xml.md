---
title: Objetos XName y XNamespace Atomizados (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: fe0c4429c89e0028b3b012c87684bd14048de27a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61951936"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Objetos XName y XNamespace Atomizados (LINQ to XML) (Visual Basic)

Los objetos <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> se *atomizan*; es decir, si contienen el mismo nombre completo, hacen referencia al mismo objeto. Esto da como resultado mejoras de rendimiento para las consultas: cuando se compara la igualdad de dos nombres atomizados, el lenguaje intermedio subyacente solo debe determinar si los dos puntos de referencia apuntan al mismo objeto. El código subyacente no debe hacer comparaciones de cadenas, ya que sería un proceso muy lento.

## <a name="atomization-semantics"></a>Semántica de atomización

Atomización significa que si dos objetos <xref:System.Xml.Linq.XName> tienen el mismo nombre local y se encuentran en el mismo espacio de nombres, comparten la misma instancia. De igual forma, si dos objetos <xref:System.Xml.Linq.XNamespace> tienen el mismo URI de espacio de nombres, comparten la misma instancia.

Para que una clase habilite objetos atomizados, el constructor de la clase debe ser privado y no público. La razón es que si el constructor fuera público, podría crea un objeto no atomizado. Las clases <xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> implementan un operador de conversión implícita para convertir una cadena en <xref:System.Xml.Linq.XName> o <xref:System.Xml.Linq.XNamespace>. De esta forma, obtiene una instancia de estos objetos. No puede obtener ninguna instancia mediante un constructor, ya que no se puede tener acceso a él.

<xref:System.Xml.Linq.XName> y <xref:System.Xml.Linq.XNamespace> también implementan los operadores de igualdad y desigualdad, para determinar si los dos objetos que se comparan son referencias a la misma instancia.

## <a name="example"></a>Ejemplo

El siguiente código crea algunos objetos <xref:System.Xml.Linq.XElement> y muestra que nombres idénticos comparten la misma instancia.

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

Este ejemplo produce el siguiente resultado:

```
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

Como se ha mencionado anteriormente, la ventaja de los objetos atomizados es que el usuario utiliza uno de los métodos de eje que toman <xref:System.Xml.Linq.XName> como parámetro, el método de eje solo debe determinar que los dos nombres hagan referencia a la misma instancia para seleccionar los elementos deseados.

El siguiente ejemplo pasa <xref:System.Xml.Linq.XName> a la llamada del método <xref:System.Xml.Linq.XContainer.Descendants%2A>, cuyo rendimiento mejora gracias al patrón de atomización.

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

Este ejemplo produce el siguiente resultado:

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a>Vea también

- [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
