---
title: "Compilados estáticamente consultas (LINQ to XML) (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: 3f4825c7-c3b0-48da-ba4e-8e97fb2a2f34
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 2ea8e71acf861b93a21296c74254b3ca4d977d0a
ms.lasthandoff: 03/13/2017


---
# <a name="statically-compiled-queries-linq-to-xml-visual-basic"></a>Compilados estáticamente consultas (LINQ to XML) (Visual Basic)
Una del rendimiento más importante ventajas de LINQ to XML, contando <xref:System.Xml.XmlDocument>, es que las consultas de LINQ to XML se compilan estáticamente, mientras que las consultas XPath deben interpretarse en tiempo de ejecución.</xref:System.Xml.XmlDocument> Esta característica está incorporada en LINQ to XML, de modo que no tiene que efectuar pasos adicionales para aprovecharla, pero resulta útil comprender la distinción a la hora de elegir entre las dos tecnologías. Este tema explica la diferencia.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Comparación de consultas compiladas de forma estática y XPath  
 En el ejemplo siguiente se muestra cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado.  
  
 A continuación figura la expresión XPath equivalente:  
  
```  
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
  
 El <xref:System.Linq.Enumerable.Where%2A>es un método de extensión.</xref:System.Linq.Enumerable.Where%2A> Para obtener más información, consulte [métodos de extensión](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md). Porque <xref:System.Linq.Enumerable.Where%2A>es un método de extensión, la consulta anterior se compila como si estuviera escrita como sigue:</xref:System.Linq.Enumerable.Where%2A>  
  
```vb  
Dim po = XDocument.Load("PurchaseOrders.xml")  
  
Dim list1 = Enumerable.Where(po.Descendants("Address"), Function(el) el.@Type = "Shipping")  
  
For Each el In list1  
    Console.WriteLine(el)  
Next  
```  
  
 Este ejemplo produce exactamente los mismos resultados que los dos ejemplos anteriores. Esto ilustra el hecho de que las consultas se compilan de forma efectiva en llamadas a método vinculadas estáticamente. Esto, combinado con la semántica de ejecución aplazada de los iteradores, mejora el rendimiento. Para obtener más información acerca de la semántica de ejecución aplazada de iteradores, vea [la ejecución aplazada y evaluación diferida en LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
>  Estos ejemplos son representativos del código que el compilador podría escribir. La implementación real podría diferir ligeramente de estos ejemplos, pero el rendimiento será el mismo o similar a estos ejemplos.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Ejecutar expresiones XPath con XmlDocument  
 En el ejemplo siguiente se utiliza <xref:System.Xml.XmlDocument>para lograr los mismos resultados que los ejemplos anteriores:</xref:System.Xml.XmlDocument>  
  
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
  
 Esta consulta devuelve el mismo resultado que los ejemplos que usan LINQ to XML; la única diferencia es que LINQ to XML aplica sangría al XML impreso, mientras que <xref:System.Xml.XmlDocument>no.</xref:System.Xml.XmlDocument>  
  
 Sin embargo, la <xref:System.Xml.XmlDocument>enfoque generalmente no funciona así como LINQ to XML, porque la <xref:System.Xml.XmlNode.SelectNodes%2A>método debe hacer lo siguiente internamente cada vez que se llama:</xref:System.Xml.XmlNode.SelectNodes%2A> </xref:System.Xml.XmlDocument>  
  
-   Analiza la cadena que contiene la expresión XPath, y divide la cadena en tokens.  
  
-   Valida los tokens para asegurarse de que la expresión XPath es válida.  
  
-   Traduce la expresión a un árbol de expresión interno.  
  
-   Recorre en iteración los nodos, y selecciona de forma adecuada los nodos del conjunto de resultados basándose en la evaluación de la expresión.  
  
 Esto es bastante más que el trabajo realizado por la consulta LINQ to XML correspondiente. La diferencia de rendimiento específica varía para distintos tipos de consultas, pero en general realizar menos trabajo consultas LINQ to XML y, por tanto, se ejecutan mejor, que evalúan las expresiones de XPath con <xref:System.Xml.XmlDocument>.</xref:System.Xml.XmlDocument>  
  
## <a name="see-also"></a>Vea también  
 [Rendimiento (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
