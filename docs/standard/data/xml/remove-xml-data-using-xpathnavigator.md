---
title: Cómo quitar datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 9f436bca-1b96-494b-a6d2-e102c7551752
ms.openlocfilehash: 062a98a9cc10e6be00f165cf617de2d92d65acbf
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710367"
---
# <a name="remove-xml-data-using-xpathnavigator"></a>Cómo quitar datos XML con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para quitar nodos y valores de un documento XML. Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.  
  
 El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML. Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.  
  
 Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="removing-nodes"></a>Cómo quitar nodos  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> para quitar nodos de un documento XML.  
  
### <a name="removing-a-node"></a>Cómo quitar un nodo  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A> para eliminar el nodo actual en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator> de un documento XML.  
  
 Una vez eliminado un nodo con el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, ya no se puede llegar a él desde la raíz del objeto <xref:System.Xml.XmlDocument>. Una vez eliminado un nodo, <xref:System.Xml.XPath.XPathNavigator> se sitúa en el nodo primario del nodo eliminado.  
  
 La operación de eliminación no afecta a la posición de ningún objeto <xref:System.Xml.XPath.XPathNavigator> situado en el nodo eliminado. Estos objetos <xref:System.Xml.XPath.XPathNavigator> son válidos en el sentido de que se pueden mover en el subárbol eliminado, pero no se pueden mover al árbol del nodo principal utilizando los métodos normales de navegación por conjuntos de nodos de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
> [!NOTE]
> El método <xref:System.Xml.XPath.XPathNavigator.MoveTo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> se puede utilizar para mover estos objetos <xref:System.Xml.XPath.XPathNavigator> de nuevo al árbol del nodo principal, o desde el árbol del nodo principal al subárbol eliminado.  
  
 En el siguiente ejemplo se elimina el elemento `price` del primer elemento `book` del archivo `contosoBooks.xml` utilizando el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>. La posición del objeto <xref:System.Xml.XPath.XPathNavigator> después de eliminar el elemento `price` se encuentra en el elemento `book` primario.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.DeleteSelf()  
  
Console.WriteLine("Position after delete: {0}", navigator.Name)  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.DeleteSelf();  
  
Console.WriteLine("Position after delete: {0}", navigator.Name);  
Console.WriteLine(navigator.OuterXml);  
```  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-an-attribute-node"></a>Cómo quitar un nodo de atributos  
 Los nodos de atributos se quitan de un documento XML utilizando el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>.  
  
 Después de eliminar un nodo de atributos, ya no se puede llegar a él desde el nodo raíz de un objeto <xref:System.Xml.XmlDocument> y el objeto <xref:System.Xml.XPath.XPathNavigator> se sitúa en el elemento primario.  
  
#### <a name="default-attributes"></a>Atributos predeterminados  
 Con independencia del método que se utilice para quitar atributos, existen unas limitaciones especiales para quitar atributos que se hayan definido como predeterminados en la DTD o el esquema XML del documento XML. Los atributos predeterminados no se pueden quitar a menos que se quite también el elemento al que pertenecen. Los atributos predeterminados siempre están presentes en los elementos que los tengan declarados y, como resultado, al eliminar un atributo predeterminado, se inserta un atributo de reemplazo en el elemento y se inicializa en el valor predeterminado que se haya declarado.  
  
## <a name="removing-values"></a>Cómo quitar valores  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> para quitar valores con y sin información de tipos de un documento XML.  
  
### <a name="removing-untyped-values"></a>Cómo quitar valores sin información de tipos  
 El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>. Al pasar una cadena vacía al método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>, se quita el valor del nodo actual.  
  
 En el siguiente ejemplo, se quita el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` utilizando el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A>.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetValue("")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("contosoBooks.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetValue("");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="removing-typed-values"></a>Cómo quitar valores con información de tipos  
 Cuando un nodo es de un tipo simple de esquema XML del W3C, el valor nuevo que ha insertado el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> se comprueba en las facetas del tipo simple antes de establecer el valor. Si el valor nuevo no es válido de acuerdo con el tipo del nodo (por ejemplo, si se establece un valor de `-1` en un elemento cuyo tipo es `xs:positiveInteger`), se produce una excepción. El método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> tampoco se puede pasar `null` como parámetro. Como resultado, al quitar el valor de un nodo con tipo, se debe cumplir el tipo de esquema del nodo.  
  
 En el siguiente ejemplo, se quita el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` con el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> estableciendo el valor en `0`. El valor del nodo no se quita, pero sí el precio del libro de acuerdo con su tipo de datos de `xs:decimal`.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(0)  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(0);  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
## <a name="namespace-nodes"></a>Nodos de espacios de nombres  
 Los nodos de espacios de nombres no se pueden eliminar de un objeto <xref:System.Xml.XmlDocument>. Si se intenta eliminar nodos de espacios de nombres con el método <xref:System.Xml.XPath.XPathNavigator.DeleteSelf%2A>, se produce una excepción.  
  
## <a name="the-innerxml-and-outerxml-properties"></a>Propiedades InnerXml y OuterXml  
 Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada. Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.  
  
 Además de los métodos que se describen en este tema, se pueden utilizar las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para quitar nodos y valores de un documento XML. Para más información sobre el uso de las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para modificar nodos, vea el tema [Modificación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md).  
  
## <a name="saving-an-xml-document"></a>Cómo guardar un documento XML  
 Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>. Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Inserción de datos XML con XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [Modificación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)
