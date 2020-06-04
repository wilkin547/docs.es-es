---
title: Rendimiento de consultas encadenadas (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
ms.openlocfilehash: 6b87f2744f663ebd45dceb036dcaac71b80765fc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396394"
---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a>Rendimiento de consultas encadenadas (LINQ to XML) (Visual Basic)

Una de las ventajas más importantes de LINQ (y LINQ to XML) es que las consultas encadenadas funcionan igual de bien que una sola consulta más grande y complicada.

Una consulta encadenada es una consulta que usa otra consulta como su origen. Por ejemplo, en el siguiente código simple, `query2` es el origen de `query1`:

```vb
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))

Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x

Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e

For Each i As var In query2
    Console.WriteLine("{0}", CInt(i))
Next
```

Este ejemplo produce el siguiente resultado:

```console
4
```

Esta consulta encadenada proporciona el mismo perfil de rendimiento que si se recorriese en iteración una lista vinculada.

- El eje <xref:System.Xml.Linq.XContainer.Elements%2A> tiene básicamente el mismo rendimiento que si se recorriese en iteración una lista vinculada. <xref:System.Xml.Linq.XContainer.Elements%2A> se implementa como iterador con ejecución aplazada. Es decir, realiza trabajo adicional además de recorrer en iteración la lista vinculada, como asignar el objeto iterador y mantener el seguimiento del estado de la ejecución. Este trabajo se puede dividir en dos categorías: el trabajo que se realiza cuando se configura el iterador y el que se lleva a cabo durante cada iteración. El trabajo de configuración es un trabajo mínimo y fijo, mientras que el realizado durante cada iteración es proporcional al número de elementos de la colección de origen.

- En `query1`, la cláusula `Where` provoca la llamada al método <xref:System.Linq.Enumerable.Where%2A> por parte de la consulta. Este método también se implementa como iterador. El trabajo de configuración está formado por la creación de una instancia del delegado que hará referencia a la expresión lambda, más la configuración normal de un iterador. Con cada iteración, se llama al delegado para que ejecute el predicado. El trabajo de configuración y el realizado durante cada iteración es parecido al llevado a cabo mientras se recorre en iteración el eje.

- En `query1`, la cláusula Select provoca la llamada al método <xref:System.Linq.Enumerable.Select%2A> por parte de la consulta. Este método tiene el mismo perfil de rendimiento que el método <xref:System.Linq.Enumerable.Where%2A>.

- En `query2`, tanto la cláusula `Where` como la cláusula `Select` tienen el mismo perfil de rendimiento que en `query1`.

 Por lo tanto, la iteración por `query2` es directamente proporcional al número de elementos del origen de la primera consulta, es decir, tiempo lineal.

## <a name="see-also"></a>Consulte también

- [Rendimiento (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
