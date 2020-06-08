---
title: Espacios de nombres y consultas XPath
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ef6402be-2f8e-4be2-8d3e-a80891cdef8b
ms.openlocfilehash: d3314a7ff4cf957dac4cd8ad0416aad434b19af2
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283200"
---
# <a name="xpath-queries-and-namespaces"></a>Espacios de nombres y consultas XPath
Las consultas XPath distinguen los espacios de nombres de un documento XML y pueden utilizar prefijos de espacio de nombres para calificar nombres de atributos y elementos. Al calificar los nombres de atributos y elementos con un prefijo de espacio de nombres, se limitan los nodos que devuelve la consulta XPath a únicamente aquellos nodos que pertenecen a un espacio de nombres específico.  
  
 Por ejemplo, si el prefijo `books` se asigna al espacio de nombres `http://www.contoso.com/books`, la siguiente consulta XPath `/books:books/books:book` solo selecciona los elementos `book` en el espacio de nombres `http://www.contoso.com/books`.  
  
## <a name="the-xmlnamespacemanager"></a>XmlNamespaceManager  
 Para utilizar espacios de nombres en una consulta XPath, se crea un objeto derivado de la interfaz <xref:System.Xml.IXmlNamespaceResolver> como la clase <xref:System.Xml.XmlNamespaceManager> con el prefijo e identificador URI de espacio de nombres para incluirlo en la consulta XPath.  
  
 El objeto <xref:System.Xml.XmlNamespaceManager> se puede utilizar en la consulta en cada una de las siguientes formas.  
  
- El objeto <xref:System.Xml.XmlNamespaceManager> se asocia a un objeto <xref:System.Xml.XPath.XPathExpression> existente utilizando el método <xref:System.Xml.XPath.XPathExpression.SetContext%2A> del objeto <xref:System.Xml.XPath.XPathExpression>. También se puede compilar un nuevo objeto <xref:System.Xml.XPath.XPathExpression> utilizando el método <xref:System.Xml.XPath.XPathExpression.Compile%2A> estático que toma una cadena que representa la expresión XPath y un objeto <xref:System.Xml.XmlNamespaceManager> como parámetros y devuelve un nuevo objeto <xref:System.Xml.XPath.XPathExpression>.  
  
- El propio objeto <xref:System.Xml.XmlNamespaceManager> se pasa como parámetro a un método de la clase <xref:System.Xml.XPath.XPathNavigator> de aceptación junto con una cadena que representa la expresión XPath.  
  
 A continuación se enumeran los métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que aceptan un objeto derivado de la interfaz <xref:System.Xml.IXmlNamespaceResolver> como parámetro.  
  
- <xref:System.Xml.XPath.XPathNavigator.Evaluate%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.Select%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.SelectSingleNode%2A>  
  
### <a name="the-default-namespace"></a>Espacio de nombres predeterminado  
 En el siguiente documento XML, se utiliza el espacio de nombres predeterminado con un prefijo vacío para declarar el espacio de nombres `http://www.contoso.com/books`.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <author>Author Name</author>  
        <price>5.50</price>  
    </book>  
</books>  
```  
  
 XPath trata el prefijo vacío como el espacio de nombres `null`. Dicho de otro modo, en las consultas XPath solo se pueden utilizar prefijos asignados a espacios de nombres. Esto significa que si desea realizar una consulta en un espacio de nombres de un documento XML, aunque se trate del espacio de nombres predeterminado, tiene que definir un prefijo para él.  
  
 Por ejemplo, si no se define un prefijo para el documento XML anterior, la consulta XPath `/books/book` no devolvería ningún resultado.  
  
 Se debe utilizar un prefijo para evitar ambigüedades al consultar documentos que tienen algunos nodos que no están en un espacio de nombres y otros que están en un espacio de nombres predeterminado.  
  
 En el siguiente código se define un prefijo para el espacio de nombres predeterminado y se seleccionan todos los elementos `book` del espacio de nombres `http://www.contoso.com/books`.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
Dim query As XPathExpression = navigator.Compile("/books:books/books:book")  
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(navigator.NameTable)  
manager.AddNamespace("books", "http://www.contoso.com/books")  
query.SetContext(manager)  
Dim nodes As XPathNodeIterator = navigator.Select(query)  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
XPathExpression query = navigator.Compile("/books:books/books:book");  
XmlNamespaceManager manager = new XmlNamespaceManager(navigator.NameTable);  
manager.AddNamespace("books", "http://www.contoso.com/books");  
query.SetContext(manager);  
XPathNodeIterator nodes = navigator.Select(query);  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Seleccionar datos XML con XPathNavigator](select-xml-data-using-xpathnavigator.md)
- [Evaluación de expresiones XPath con XPathNavigator](evaluate-xpath-expressions-using-xpathnavigator.md)
- [Coincidencia de nodos con XPathNavigator](matching-nodes-using-xpathnavigator.md)
- [Tipos de nodos reconocidos con consultas XPath](node-types-recognized-with-xpath-queries.md)
- [Expresiones XPath compiladas](compiled-xpath-expressions.md)
