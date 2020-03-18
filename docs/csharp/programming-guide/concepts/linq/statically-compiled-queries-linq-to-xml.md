---
title: Consultas compiladas estáticamente (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 3bf558fe-0705-479d-86d4-00188f5fcf9c
ms.openlocfilehash: 98725cece1006ba13afb64bb8ae17ae6e62c53cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253029"
---
# <a name="statically-compiled-queries-linq-to-xml-c"></a>Consultas compiladas estáticamente (LINQ to XML) (C#)
Una de las ventajas de rendimiento más importantes de LINQ to XML, a diferencia de <xref:System.Xml.XmlDocument>, es que las consultas LINQ to XML se compilan estáticamente, mientras que las consultas XPath deben interpretarse durante la ejecución. Esta característica está incorporada en LINQ to XML, de modo que no tiene que efectuar pasos adicionales para aprovecharla, pero resulta útil comprender la distinción a la hora de elegir entre las dos tecnologías. Este tema explica la diferencia.  
  
## <a name="statically-compiled-queries-vs-xpath"></a>Consultas compiladas de forma estática frente a XPath  
 En el ejemplo siguiente se muestra cómo obtener los elementos descendientes con un nombre especificado y con un atributo con un valor especificado.  
  
 Esta es la expresión XPath equivalente: `//Address[@Type='Shipping']`
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    from el in po.Descendants("Address")  
    where (string)el.Attribute("Type") == "Shipping"  
    select el;  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 El compilador reescribe la expresión de consulta de este ejemplo con la sintaxis de consulta basada en métodos. En el ejemplo siguiente, que está escrito en la sintaxis de consulta basada en métodos, se producen los mismos resultados que en el anterior:  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    po  
    .Descendants("Address")  
    .Where(el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 El método <xref:System.Linq.Enumerable.Where%2A> es una extensión del método. Para más información, vea [Métodos de extensión](../../classes-and-structs/extension-methods.md). Dado que <xref:System.Linq.Enumerable.Where%2A> es un método de extensión, la consulta anterior se compila como si estuviera escrita como se muestra a continuación:  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
IEnumerable<XElement> list1 =  
    System.Linq.Enumerable.Where(  
        po.Descendants("Address"),  
        el => (string)el.Attribute("Type") == "Shipping");  
  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 Este ejemplo produce exactamente los mismos resultados que los dos ejemplos anteriores. Esto ilustra el hecho de que las consultas se compilan de forma efectiva en llamadas a método vinculadas estáticamente. Esto, combinado con la semántica de ejecución aplazada de los iteradores, mejora el rendimiento. Para obtener más información sobre la semántica de ejecución aplazada de iteradores, vea [Ejecución aplazada y evaluación diferida en LINQ to XML](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).  
  
> [!NOTE]
> Estos ejemplos son representativos del código que el compilador podría escribir. La implementación real podría diferir ligeramente de estos ejemplos, pero el rendimiento será el mismo o similar a estos ejemplos.  
  
## <a name="executing-xpath-expressions-with-xmldocument"></a>Ejecutar expresiones XPath con XmlDocument  
 En el ejemplo de código siguiente se usa <xref:System.Xml.XmlDocument> para lograr los mismos resultados que en los ejemplos anteriores:  
  
```csharp  
XmlReader reader = XmlReader.Create("PurchaseOrders.xml");  
XmlDocument doc = new XmlDocument();  
doc.Load(reader);  
XmlNodeList nl = doc.SelectNodes(".//Address[@Type='Shipping']");  
foreach (XmlNode n in nl)  
    Console.WriteLine(n.OuterXml);  
reader.Close();  
```  
  
 Esta consulta devuelve el mismo resultado que los ejemplos que usan LINQ to XML; la única diferencia es que LINQ to XML aplica sangría al XML impreso, mientras que <xref:System.Xml.XmlDocument> no.  
  
 No obstante, el enfoque de <xref:System.Xml.XmlDocument> generalmente no funciona tan bien como LINQ to XML, porque el método <xref:System.Xml.XmlNode.SelectNodes%2A> debe realizar lo siguiente internamente cada vez que se le llama:  
  
- Analiza la cadena que contiene la expresión XPath, y divide la cadena en tokens.  
  
- Valida los tokens para asegurarse de que la expresión XPath es válida.  
  
- Traduce la expresión a un árbol de expresión interno.  
  
- Recorre en iteración los nodos, y selecciona de forma adecuada los nodos del conjunto de resultados basándose en la evaluación de la expresión.  
  
 Esto es bastante más que el trabajo realizado por la consulta LINQ to XML correspondiente. La diferencia de rendimiento específica varía para distintos tipos de consultas, pero en general las consultas LINQ to XML efectúan menos operaciones y, por lo tanto, se ejecutan mejor, que si se evalúan las expresiones XPath con <xref:System.Xml.XmlDocument>.  
