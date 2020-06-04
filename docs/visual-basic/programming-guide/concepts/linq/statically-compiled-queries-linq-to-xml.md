---
title: Consultas compiladas estáticamente (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
ms.openlocfilehash: f020c1ed8627df8c8386a059f0cea372e8df363e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406773"
---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Consultas compiladas estáticamente (LINQ to XML) (Visual Basic)

Una de las ventajas de rendimiento más importantes de LINQ to XML, a diferencia de <xref:System.Xml.XmlDocument>, es que las consultas LINQ to XML se compilan estáticamente, mientras que las consultas XPath deben interpretarse durante la ejecución. Esta característica está incorporada en LINQ to XML, de modo que no tiene que efectuar pasos adicionales para aprovecharla, pero resulta útil comprender la distinción a la hora de elegir entre las dos tecnologías. Este tema explica la diferencia.

## <a name="statically-compiled-queries-vs-xpath"></a>Consultas compiladas de forma estática frente a XPath

En el ejemplo siguiente se muestra cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado.

A continuación figura la expresión XPath equivalente:

```vb
//Address[@Type='Shipping']
```

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = From el In po.Descendants("Address")
            Where el.@Type = "Shipping"

For Each el In list1
    Console.WriteLine(el)
Next
```

El compilador reescribe la expresión de consulta de este ejemplo con la sintaxis de consulta basada en métodos. En el ejemplo siguiente, que está escrito en la sintaxis de consulta basada en métodos, se producen los mismos resultados que en el anterior:

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 As IEnumerable(Of XElement) = po.Descendants("Address").Where(Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

El método <xref:System.Linq.Enumerable.Where%2A> es una extensión del método. Para más información, vea [Métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Dado que <xref:System.Linq.Enumerable.Where%2A> es un método de extensión, la consulta anterior se compila como si estuviera escrita como se muestra a continuación:

```vb
Dim po = XDocument.Load("PurchaseOrders.xml")

Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")

For Each el In list1
    Console.WriteLine(el)
Next
```

Este ejemplo produce exactamente los mismos resultados que los dos ejemplos anteriores. Esto ilustra el hecho de que las consultas se compilan de forma efectiva en llamadas a método vinculadas estáticamente. Esto, combinado con la semántica de ejecución aplazada de los iteradores, mejora el rendimiento. Para obtener más información sobre la semántica de ejecución aplazada de los iteradores, vea [ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)](deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).

> [!NOTE]
> Estos ejemplos son representativos del código que el compilador podría escribir. La implementación real podría diferir ligeramente de estos ejemplos, pero el rendimiento será el mismo o similar a estos ejemplos.

## <a name="executing-xpath-expressions-with-xmldocument"></a>Ejecutar expresiones XPath con XmlDocument

En el ejemplo de código siguiente se usa <xref:System.Xml.XmlDocument> para lograr los mismos resultados que en los ejemplos anteriores:

```vb
Dim reader = Xml.XmlReader.Create("PurchaseOrders.xml")
Dim doc As New Xml.XmlDocument()
doc.Load(reader)
Dim nl As Xml.XmlNodeList = doc.SelectNodes(".//Address[@Type='Shipping']")
For Each n As Xml.XmlNode In nl
    Console.WriteLine(n.OuterXml)
Next
reader.Close()
```

Esta consulta devuelve el mismo resultado que los ejemplos que usan LINQ to XML; la única diferencia es que LINQ to XML aplica sangría al XML impreso, mientras que <xref:System.Xml.XmlDocument> no.

No obstante, el enfoque de <xref:System.Xml.XmlDocument> generalmente no funciona tan bien como LINQ to XML, porque el método <xref:System.Xml.XmlNode.SelectNodes%2A> debe realizar lo siguiente internamente cada vez que se le llama:

- Analiza la cadena que contiene la expresión XPath, y divide la cadena en tokens.

- Valida los tokens para asegurarse de que la expresión XPath es válida.

- Traduce la expresión a un árbol de expresión interno.

- Recorre en iteración los nodos, y selecciona de forma adecuada los nodos del conjunto de resultados basándose en la evaluación de la expresión.

Esto es bastante más que el trabajo realizado por la consulta LINQ to XML correspondiente. La diferencia de rendimiento específica varía para distintos tipos de consultas, pero en general las consultas LINQ to XML efectúan menos operaciones y, por lo tanto, se ejecutan mejor, que si se evalúan las expresiones XPath con <xref:System.Xml.XmlDocument>.

## <a name="see-also"></a>Consulte también

- [Rendimiento (LINQ to XML) (Visual Basic)](performance-linq-to-xml.md)
