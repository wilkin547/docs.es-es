---
title: Evaluación de expresiones XPath con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 2913ccf3-f932-4363-8028-9e2d22ce6093
ms.openlocfilehash: 1a17aea66be7f9d35336434408c49bae8046b7e7
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710913"
---
# <a name="evaluate-xpath-expressions-using-xpathnavigator"></a>Evaluación de expresiones XPath con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> para evaluar una expresión XPath. El método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> toma una expresión XPath, la evalúa y devuelve un tipo XPath del W3C de tipo booleano, numérico, de cadena o de conjunto de nodos basándose en el resultado de la expresión XPath.  
  
## <a name="the-evaluate-method"></a>Método de evaluación  
 El método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> toma una expresión XPath, la evalúa y devuelve un resultado con tipo de tipo booleano (<xref:System.Boolean>), numérico (<xref:System.Double>), de cadena (<xref:System.String>) o de conjunto de nodos (<xref:System.Xml.XPath.XPathNodeIterator>). Por ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> se podría utilizar en un método matemático. El siguiente código de ejemplo calcula el precio total de todos los libros del archivo `books.xml`.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Dim query As XPathExpression = navigator.Compile("sum(//price/text())")  
Dim total As Double = CType(navigator.Evaluate(query), Double)  
Console.WriteLine(total)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
XPathExpression query = navigator.Compile("sum(//price/text())");  
Double total = (Double)navigator.Evaluate(query);  
Console.WriteLine(total);  
```  
  
 En el ejemplo se toma como entrada el archivo `books.xml`.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="position-and-last-functions"></a>Funciones position y last  
 El método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> está sobrecargado. Uno de los métodos <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> toma un objeto <xref:System.Xml.XPath.XPathNodeIterator> como parámetro. Este método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> en concreto es idéntico al método <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> que solo toma un objeto <xref:System.Xml.XPath.XPathExpression> como parámetro, excepto en que permite que un argumento de un conjunto de nodos especifique el contexto actual en el que realizar la evaluación. Este contexto es necesario para las funciones XPath `position()` y `last()`, ya que son relativas al nodo de contexto actual. A menos que se utilicen como predicado en un paso de ubicación, las funciones `position()` y `last()` necesitan una referencia a un conjunto de nodos para poder ser evaluadas; de lo contrario, las funciones `position` y `last` devuelven `0`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Seleccionar datos XML con XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Coincidencia de nodos con XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [Tipos de nodos reconocidos con consultas XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [Espacios de nombres y consultas XPath](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
- [Expresiones XPath compiladas](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)
