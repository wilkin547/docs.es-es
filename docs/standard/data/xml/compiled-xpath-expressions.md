---
title: Expresiones XPath compiladas
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: e25dd95f-b64c-4d8b-a3a4-379e1aa0ad55
ms.openlocfilehash: b4675765849299050eb6cddeaaa497bc6cdc620a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711108"
---
# <a name="compiled-xpath-expressions"></a>Expresiones XPath compiladas
Un objeto <xref:System.Xml.XPath.XPathExpression> representa una consulta XPath compilada devuelta desde el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> estático de la clase <xref:System.Xml.XPath.XPathExpression> o desde el método <xref:System.Xml.XPath.XPathNavigator.Compile%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="the-xpathexpression-class"></a>La clase XPathExpression  
 Una consulta XPath compilada que está representada por un objeto <xref:System.Xml.XPath.XPathExpression> es útil si esa misma consulta XPath se utiliza más de una vez.  
  
 Por ejemplo, al llamar varias veces al método <xref:System.Xml.XPath.XPathNavigator.Select%2A>, en lugar de utilizar una cadena que represente a la consulta XPath cada una de esas veces, utilice el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> de la clase <xref:System.Xml.XPath.XPathExpression> o el método <xref:System.Xml.XPath.XPathNavigator.Compile%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> para compilar y almacenar en caché la consulta XPath en un objeto <xref:System.Xml.XPath.XPathExpression>, para poder reutilizarla y mejorar el rendimiento.  
  
 Una vez compilado, el objeto <xref:System.Xml.XPath.XPathExpression> se puede utilizar como entrada en los siguientes métodos de la clase <xref:System.Xml.XPath.XPathNavigator> dependiendo del tipo devuelto desde la consulta XPath.  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A?displayProperty=nameWithType>  
  
- <xref:System.Xml.XPath.XPathNavigator.Matches%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
 En la siguiente tabla se describe cada uno de los tipos de valores devueltos de XPath del W3C, sus equivalencias en Microsoft .NET Framework y con qué métodos se puede utilizar el objeto <xref:System.Xml.XPath.XPathExpression> basándose en su tipo de valor devuelto.  
  
|Tipo de valor devuelto de XPath del W3C|Tipo equivalente en .NET Framework|Descripción|Métodos|  
|---------------------------|------------------------------------|-----------------|-------------|  
|`Node set`|<xref:System.Xml.XPath.XPathNodeIterator>|Una colección no ordenada de nodos sin duplicados creados en el orden del documento.|<xref:System.Xml.XPath.XPathNavigator.Select%2A> o <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`Boolean`|<xref:System.Boolean>|Un valor `true` o `false`.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>, o bien<br /><br /> <xref:System.Xml.XPath.XPathNavigator.Matches%2A>|  
|`Number`|<xref:System.Double>|Número en punto flotante.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
|`String`|<xref:System.String>|Una secuencia de caracteres UCS.|<xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>|  
  
> [!NOTE]
> El método <xref:System.Xml.XPath.XPathNavigator.Matches%2A> acepta una expresión XPath como parámetro. El método <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A> devuelve un objeto <xref:System.Xml.XPath.XPathNavigator>, no uno de los tipos de valores devueltos de XPath del W3C.  
  
### <a name="the-returntype-property"></a>La propiedad ReturnType  
 Una vez compilada una consulta XPath en un objeto <xref:System.Xml.XPath.XPathExpression>, puede utilizar la propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> del objeto <xref:System.Xml.XPath.XPathExpression> para determinar qué devuelve la consulta XPath.  
  
 La propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> devuelve uno de los siguientes valores de enumeración <xref:System.Xml.XPath.XPathResultType> que representan los tipos de valores devueltos de XPath del W3C.  
  
- <xref:System.Xml.XPath.XPathResultType.Any>  
  
- <xref:System.Xml.XPath.XPathResultType.Boolean>  
  
- <xref:System.Xml.XPath.XPathResultType.Error>  
  
- <xref:System.Xml.XPath.XPathResultType.Navigator>  
  
- <xref:System.Xml.XPath.XPathResultType.NodeSet>  
  
- <xref:System.Xml.XPath.XPathResultType.Number>  
  
- <xref:System.Xml.XPath.XPathResultType.String>  
  
 En el siguiente ejemplo se utiliza el objeto <xref:System.Xml.XPath.XPathExpression> para devolver un número y un conjunto de nodos desde el archivo `books.xml`. La propiedad <xref:System.Xml.XPath.XPathExpression.ReturnType%2A> de cada objeto <xref:System.Xml.XPath.XPathExpression>, así como los resultados de los métodos <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A> y <xref:System.Xml.XPath.XPathNavigator.Select%2A>, se escriben en la consola.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Returns a number.  
Dim query1 As XPathExpression = navigator.Compile("bookstore/book/price/text()*10")  
Console.WriteLine(query1.ReturnType)  
  
Dim number As Double = CType(navigator.Evaluate(query1), Double)  
Console.WriteLine(number)  
  
' Returns a node set.  
Dim query2 As XPathExpression = navigator.Compile("bookstore/book/price")  
Console.WriteLine(query2.ReturnType)  
  
Dim nodes As XPathNodeIterator = navigator.Select(query2)  
nodes.MoveNext()  
Console.WriteLine(nodes.Current.Value)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Returns a number.  
XPathExpression query1 = navigator.Compile("bookstore/book/price/text()*10");  
Console.WriteLine(query1.ReturnType);  
  
Double number = (Double)navigator.Evaluate(query1);  
Console.WriteLine(number);  
  
// Returns a node set.  
XPathExpression query2 = navigator.Compile("bookstore/book/price");  
Console.WriteLine(query2.ReturnType);  
  
XPathNodeIterator nodes = navigator.Select(query2);  
nodes.MoveNext();  
Console.WriteLine(nodes.Current.Value);  
```  
  
 En el ejemplo se toma como entrada el archivo `books.xml`.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
### <a name="higher-performance-xpath-expressions"></a>Expresiones XPath de mayor rendimiento  
 Para mejorar el rendimiento, utilice la expresión XPath lo más específica posible en las consultas. Por ejemplo, si el nodo `book` es un nodo secundario del nodo `bookstore` y el nodo `bookstore` es el elemento superior de un documento XML, es más rápido utilizar la expresión XPath `/bookstore/book` que `//book`. La expresión XPath `//book` examinará cada nodo del árbol XML para identificar nodos coincidentes.  
  
 Además, el uso de métodos de navegación por conjuntos de nodos que proporciona la clase <xref:System.Xml.XPath.XPathNavigator>, puede producir una mejora del rendimiento con respecto a los métodos de selección que proporciona la clase <xref:System.Xml.XPath.XPathNavigator> en los casos en los que los criterios de selección sean sencillos. Por ejemplo, si tiene que seleccionar el primer nodo secundario del nodo actual, es más rápido utilizar el método <xref:System.Xml.XPath.XPathNavigator.MoveToFirst%2A> que la expresión XPath `child::*[1]` y el método <xref:System.Xml.XPath.XPathNavigator.Select%2A>.  
  
 Para obtener más información sobre los métodos de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>, vea [Navegación por un conjunto de nodos con XPathNavigator](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Seleccionar datos XML con XPathNavigator](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)
- [Evaluación de expresiones XPath con XPathNavigator](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)
- [Coincidencia de nodos con XPathNavigator](../../../../docs/standard/data/xml/matching-nodes-using-xpathnavigator.md)
- [Tipos de nodos reconocidos con consultas XPath](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)
- [Espacios de nombres y consultas XPath](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)
