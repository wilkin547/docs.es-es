---
title: Seleccionar datos XML con XPathNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c268c49e-32b9-4171-b782-dcb7b065fa73
ms.openlocfilehash: 791c1d16db6a2079ccccebf4dc33d5a0eb12d3c5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94824979"
---
# <a name="select-xml-data-using-xpathnavigator"></a>Seleccionar datos XML con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath. Una vez seleccionado, puede iterar por el conjunto de nodos seleccionado.  
  
## <a name="xpathnavigator-selection-methods"></a>Métodos de selección de XPathNavigator  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para seleccionar un conjunto de nodos de un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> utilizando una expresión XPath. La clase <xref:System.Xml.XPath.XPathNavigator> también incluye un conjunto de métodos optimizados para seleccionar nodos antecesores, secundarios y descendientes más rápido que con una expresión XPath. El conjunto seleccionado de nodos se devuelve en un objeto <xref:System.Xml.XPath.XPathNodeIterator> o un objeto <xref:System.Xml.XPath.XPathNavigator> en el caso de haya un solo nodo seleccionado.  
  
### <a name="selecting-nodes-using-xpath-expressions"></a>Selección de nodos con expresiones XPath  
 Para seleccionar un conjunto de nodos con una expresión XPath, utilice uno de los siguientes métodos de selección.  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 Cuando se llama a estos métodos, éstos devuelven un conjunto de nodos por los que puede navegar libremente utilizando un objeto <xref:System.Xml.XPath.XPathNodeIterator> o un objeto <xref:System.Xml.XPath.XPathNavigator> en el caso de que haya un solo nodo seleccionado.  
  
 La navegación por un objeto <xref:System.Xml.XPath.XPathNodeIterator> no afecta a la posición del objeto <xref:System.Xml.XPath.XPathNavigator> que se ha utilizado para crearlo. El objeto <xref:System.Xml.XPath.XPathNavigator> que devuelven los métodos <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> se sitúa en el único nodo devuelto y tampoco afecta a la posición del objeto <xref:System.Xml.XPath.XPathNavigator> que se ha utilizado para crearlo.  
  
 En el siguiente ejemplo, se muestra la creación de un objeto <xref:System.Xml.XPath.XPathNavigator> a partir de un objeto <xref:System.Xml.XPath.XPathDocument>, el uso del método <xref:System.Xml.XPath.XPathNavigator.Select%2A> para seleccionar nodos en el objeto <xref:System.Xml.XPath.XPathDocument> y el uso del objeto <xref:System.Xml.XPath.XPathNodeIterator> para iterar por los nodos seleccionados.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim nodes As XPathNodeIterator = navigator.Select("/bookstore/book")  
  
While nodes.MoveNext()  
    Console.WriteLine(nodes.Current.Name)  
End While  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathNodeIterator nodes = navigator.Select("/bookstore/book");  
  
while(nodes.MoveNext())  
{  
    Console.WriteLine(nodes.Current.Name);  
}  
```  
  
 En el ejemplo se toma como entrada el archivo `books.xml`.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="optimized-selection-methods"></a>Métodos de selección optimizados  
 Los métodos <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> y <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> representan expresiones XPath que se utilizan habitualmente para recuperar nodos secundarios, descendientes y antecesores. Estos métodos tienen optimizado su rendimiento y son más rápidos que sus expresiones XPath correspondientes. Los métodos <xref:System.Xml.XPath.XPathNavigator.SelectChildren%2A>, <xref:System.Xml.XPath.XPathNavigator.SelectAncestors%2A> y <xref:System.Xml.XPath.XPathNavigator.SelectDescendants%2A> seleccionan nodos antecesores, secundarios y descendientes basándose en un valor <xref:System.Xml.XPath.XPathNodeType> o el nombre local e identificador URI de espacio de nombres de los nodos que se van a seleccionar. Los nodos antecesores, secundarios y descendientes se devuelven en un objeto <xref:System.Xml.XPath.XPathNodeIterator>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Evaluación de expresiones XPath con XPathNavigator](evaluate-xpath-expressions-using-xpathnavigator.md)
- [Coincidencia de nodos con XPathNavigator](matching-nodes-using-xpathnavigator.md)
- [Tipos de nodos reconocidos con consultas XPath](node-types-recognized-with-xpath-queries.md)
- [Espacios de nombres y consultas XPath](xpath-queries-and-namespaces.md)
- [Expresiones XPath compiladas](compiled-xpath-expressions.md)
