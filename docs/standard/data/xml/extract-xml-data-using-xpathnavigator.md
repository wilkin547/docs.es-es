---
title: Extraer datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 095b0987-ee4b-4595-a160-da1c956ad576
ms.openlocfilehash: e639931204a416c3cde87044730364a4f387799a
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287771"
---
# <a name="extract-xml-data-using-xpathnavigator"></a>Extraer datos XML con XPathNavigator
Existen varias formas de representar un documento XML en Microsoft .NET Framework. Entre ellas se incluye el uso de <xref:System.String> o de las clases <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, <xref:System.Xml.XmlDocument> o <xref:System.Xml.XPath.XPathDocument>. Para que sea más fácil moverse entre estas diferentes representaciones de un documento XML, la clase <xref:System.Xml.XPath.XPathNavigator> incluye una serie de métodos y propiedades para extraer el código XML como un objeto <xref:System.String>, <xref:System.Xml.XmlReader> o <xref:System.Xml.XmlWriter>.  
  
## <a name="convert-an-xpathnavigator-to-a-string"></a>Conversión de XPathNavigator en una cadena  
 La propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> se utiliza para obtener el marcado de todo el documento XML o tan sólo el de un nodo y sus nodos secundarios.  
  
> [!NOTE]
> La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> obtiene solamente el marcado de los nodos secundarios de un nodo.  
  
 El siguiente código muestra cómo guardar todo un documento XML contenido en un objeto <xref:System.Xml.XPath.XPathNavigator> como <xref:System.String>, así como un solo nodo y sus nodos secundarios.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("input.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Save the entire input.xml document to a string.  
Dim xml As String = navigator.OuterXml  
  
' Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element)  
Dim root As String = navigator.OuterXml  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Save the entire input.xml document to a string.  
string xml = navigator.OuterXml;  
  
// Now save the Root element and its child nodes to a string.  
navigator.MoveToChild(XPathNodeType.Element);  
string root = navigator.OuterXml;  
```  
  
## <a name="convert-an-xpathnavigator-to-an-xmlreader"></a>Conversión de XPathNavigator en XmlReader  
 El método <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> se utiliza para secuenciar todo el contenido de un documento XML o tan sólo un nodo y sus nodos secundarios en un objeto <xref:System.Xml.XmlReader>.  
  
 Cuando se crea el objeto <xref:System.Xml.XmlReader> con el nodo actual y sus nodos secundarios, la propiedad <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.ReadState%2A> se establece en <xref:System.Xml.ReadState.Initial>. Cuando por primera vez se llama al método <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.Read%2A>, <xref:System.Xml.XmlReader> se desplaza al nodo actual de <xref:System.Xml.XPath.XPathNavigator>. El nuevo objeto <xref:System.Xml.XmlReader> continúa leyendo hasta llegar al final del árbol de XML. En este punto, el método <xref:System.Xml.XmlReader.Read%2A> devuelve `false` y la propiedad <xref:System.Xml.XmlReader> del objeto <xref:System.Xml.XmlReader.ReadState%2A> se establece en <xref:System.Xml.ReadState.EndOfFile>.  
  
 La posición del objeto <xref:System.Xml.XPath.XPathNavigator> no cambia debido a la creación o el movimiento del objeto <xref:System.Xml.XmlReader>. El método <xref:System.Xml.XPath.XPathNavigator.ReadSubtree%2A> sólo es válido cuando se encuentra situado en un elemento o en un nodo raíz.  
  
 En el siguiente ejemplo se muestra cómo obtener un objeto <xref:System.Xml.XmlReader> que contiene todo el documento XML de un objeto <xref:System.Xml.XPath.XPathDocument>, así como un solo nodo y sus nodos secundarios.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlReader.  
Dim xml As XmlReader = navigator.ReadSubtree()  
  
While xml.Read()  
    Console.WriteLine(xml.ReadInnerXml())  
End While  
  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlReader = navigator.ReadSubtree()  
  
While book.Read()  
    Console.WriteLine(book.ReadInnerXml())  
End While  
  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlReader.  
XmlReader xml = navigator.ReadSubtree();  
  
while (xml.Read())  
{  
    Console.WriteLine(xml.ReadInnerXml());  
}  
  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlReader.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlReader book = navigator.ReadSubtree();  
  
while (book.Read())  
{  
    Console.WriteLine(book.ReadInnerXml());  
}  
  
book.Close();  
```  
  
 En el ejemplo se toma como entrada el archivo `books.xml`.  
  
 [!code-xml[XPathXMLExamples#1](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/books.xml#1)]  
  
## <a name="converting-an-xpathnavigator-to-an-xmlwriter"></a>Conversión de XPathNavigator en XmlWriter  
 El método <xref:System.Xml.XPath.XPathNavigator.WriteSubtree%2A> se utiliza para secuenciar todo el contenido de un documento XML o tan sólo un nodo y sus nodos secundarios en un objeto <xref:System.Xml.XmlWriter>.  
  
 La posición del objeto <xref:System.Xml.XPath.XPathNavigator> no cambia debido a la creación del objeto <xref:System.Xml.XmlWriter>.  
  
 En el siguiente ejemplo se muestra cómo obtener un objeto <xref:System.Xml.XmlWriter> que contiene todo el documento XML de un objeto <xref:System.Xml.XPath.XPathDocument>, así como un solo nodo y sus nodos secundarios.  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
' Stream the entire XML document to the XmlWriter.  
Dim xml As XmlWriter = XmlWriter.Create("newbooks.xml")  
navigator.WriteSubtree(xml)  
xml.Close()  
  
' Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "")  
navigator.MoveToChild("book", "")  
  
Dim book As XmlWriter = XmlWriter.Create("book.xml")  
navigator.WriteSubtree(book)  
book.Close()  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
// Stream the entire XML document to the XmlWriter.  
XmlWriter xml = XmlWriter.Create("newbooks.xml");  
navigator.WriteSubtree(xml);  
xml.Close();  
  
// Stream the book element and its child nodes to the XmlWriter.  
navigator.MoveToChild("bookstore", "");  
navigator.MoveToChild("book", "");  
  
XmlWriter book = XmlWriter.Create("book.xml");  
navigator.WriteSubtree(book);  
book.Close();  
```  
  
 El ejemplo toma como entrada el archivo `books.xml` que aparecía anteriormente en este tema.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Navegación por un conjunto de nodos con XPathNavigator](node-set-navigation-using-xpathnavigator.md)
- [Navegación por nodos de espacios de nombres y atributos con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Acceso a datos XML fuertemente tipados utilizando XPathNavigator](accessing-strongly-typed-xml-data-using-xpathnavigator.md)
