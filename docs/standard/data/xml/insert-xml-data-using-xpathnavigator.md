---
title: Inserción de datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
ms.openlocfilehash: 1dbe1a709f7c1b527a1754ab943a0a10ff52c6e8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289192"
---
# <a name="insert-xml-data-using-xpathnavigator"></a>Inserción de datos XML con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados en un documento XML. Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.  
  
 El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML. Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.  
  
 Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="inserting-nodes"></a>Inserción de nodos  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados en un documento XML. Estos métodos permiten insertar nodos y atributos en diferentes ubicaciones en relación con la posición actual de un objeto <xref:System.Xml.XPath.XPathNavigator> y se describen en las siguientes secciones.  
  
### <a name="inserting-sibling-nodes"></a>Inserción de nodos relacionados  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos relacionados.  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 Estos métodos insertan nodos relacionados antes y después del nodo en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> están sobrecargados y aceptan un objeto `string`, <xref:System.Xml.XmlReader>, o un objeto <xref:System.Xml.XPath.XPathNavigator> que contiene el nodo relacionado para agregarlos como parámetros. Ambos métodos también devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos relacionados.  
  
 Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> insertan un solo nodo relacionado antes y después del nodo en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado.  
  
 En el siguiente ejemplo, se inserta un elemento `pages` nuevo antes del elemento secundario `price` del primer elemento `book` en el archivo `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="inserting-child-nodes"></a>Inserción de nodos secundarios  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos secundarios.  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 Estos métodos agregan nodos secundarios al final y al principio de la lista de nodos secundarios del nodo en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 Al igual que los métodos que se indican en la sección "Inserción de nodos relacionados", los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> aceptan un objeto `string`, <xref:System.Xml.XmlReader> o un objeto <xref:System.Xml.XPath.XPathNavigator> que contiene el nodo secundario, para agregarlos como parámetros. Ambos métodos también devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos secundarios.  
  
 Además, al igual que los métodos que se indican en la sección "Inserción de nodos relacionados", los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> insertan un solo nodo secundario al final y al principio de la lista de nodos secundarios del nodo en el que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado.  
  
 En el siguiente ejemplo se agrega un nuevo elemento secundario `pages` a la lista de elementos secundarios del primer elemento `book` del archivo `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
### <a name="inserting-attribute-nodes"></a>Inserción de nodos de atributos  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye los siguientes métodos para insertar nodos de atributos.  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
- <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 Estos métodos insertan nodos de atributos en el nodo de elementos en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>. El método <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> crea un nodo de atributos en el nodo de elementos en el que está situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, utilizando como parámetros el prefijo de espacio de nombres, el nombre local, el identificador URI de espacio de nombres y el valor especificado. El método <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> devuelve un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos de atributos.  
  
 En el siguiente ejemplo se crean nuevos atributos `discount` y `currency` en el elemento secundario `price` del primer elemento `book` del archivo `contosoBooks.xml` utilizando el objeto <xref:System.Xml.XmlWriter> devuelto desde el método <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>.  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> y <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
## <a name="copying-nodes"></a>Copia de nodos  
 En determinados casos, puede que desee llenar un documento XML con el contenido de otro documento XML. Tanto la clase <xref:System.Xml.XPath.XPathNavigator> como la clase <xref:System.Xml.XmlWriter> pueden copiar nodos en un objeto <xref:System.Xml.XmlDocument> desde un objeto <xref:System.Xml.XmlReader> existente o desde un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 Los métodos <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> y <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> tienen sobrecargas que pueden aceptar como parámetro un objeto <xref:System.Xml.XPath.XPathNavigator> o un objeto <xref:System.Xml.XmlReader>.  
  
 El método <xref:System.Xml.XmlWriter.WriteNode%2A> de la clase <xref:System.Xml.XmlWriter> tiene sobrecargas que pueden aceptar un objeto <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader> o <xref:System.Xml.XPath.XPathNavigator>.  
  
 En el siguiente ejemplo se copian todos los elementos `book` de un documento a otro.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a>Inserción de valores  
 La clase <xref:System.Xml.XPath.XPathNavigator> incluye los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> para insertar valores de un nodo en un objeto <xref:System.Xml.XmlDocument>.  
  
### <a name="inserting-untyped-values"></a>Inserción de valores sin información de tipos  
 El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>. Este valor se inserta sin ningún tipo o sin comprobar si el nuevo valor es válido de acuerdo con el tipo del nodo si hay disponible información de esquema.  
  
 En el siguiente ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> se utiliza para actualizar todos los elementos `price` del archivo `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a>Inserción de valores con información de tipos  
 Cuando un nodo es de un tipo simple de esquema XML del W3C, el valor nuevo que ha insertado el método <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> se comprueba en las facetas del tipo simple antes de establecer el valor. Si el valor nuevo no es válido de acuerdo con el tipo del nodo (por ejemplo, si se establece un valor de `-1` en un elemento cuyo tipo es `xs:positiveInteger`), se produce una excepción.  
  
 En el siguiente ejemplo se intenta cambiar el valor del elemento `price` del primer elemento `book` en el archivo `contosoBooks.xml` por un valor <xref:System.DateTime>. Dado que el tipo de esquema XML del elemento `price` está definido como `xs:decimal` en los archivos `contosoBooks.xsd`, se produce una excepción.  
  
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
  
navigator.SetTypedValue(DateTime.Now)  
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
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a>Propiedades InnerXml y OuterXml  
 Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada. Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.  
  
 Además de los métodos que se describen en este tema, se pueden utilizar las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para insertar nodos y valores en un documento XML. Para más información sobre el uso de las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para insertar nodos y valores, vea el tema [Modificación de datos XML con XPathNavigator](modify-xml-data-using-xpathnavigator.md).  
  
## <a name="namespace-and-xmllang-conflicts"></a>Conflictos de xml:lang y espacios de nombres  
 Se pueden producir determinados conflictos relacionados con el ámbito del espacio de nombres y las declaraciones `xml:lang` al insertar datos XML utilizando los métodos <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> y <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> que toman objetos <xref:System.Xml.XmlReader> como parámetros.  
  
 A continuación, se indican los posibles conflictos de espacios de nombres.  
  
- Si hay un espacio de nombres en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader>, en donde el prefijo de la asignación del identificador URI del espacio de nombres no está en el contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar.  
  
- Si el mismo identificador URI de espacio de nombres está en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero tiene otro prefijo asignado en ambos contextos, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar, con el prefijo y el identificador URI de espacio de nombres tomados del objeto <xref:System.Xml.XmlReader>.  
  
- Si el mismo prefijo de espacio de nombres está en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero tiene otro identificador URI de espacio de nombres asignado en ambos contextos, se agrega una nueva declaración de espacio de nombres al nodo que se acaba de insertar, que vuelve a declarar ese prefijo con el identificador URI de espacio de nombres tomado del objeto <xref:System.Xml.XmlReader>.  
  
- Si el prefijo y el identificador URI de espacio de nombres en el contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator> son los mismos, no se agrega ninguna declaración de espacio de nombres nueva al nodo que se acaba de insertar.  
  
> [!NOTE]
> La descripción anterior también se aplica a declaraciones de espacios de nombres con la `string` vacía como prefijo (por ejemplo, la declaración de espacio de nombres predeterminada).  
  
 A continuación, se indican los posibles conflictos de `xml:lang`.  
  
- Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader>, pero no en el contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, se agrega al nodo que se acaba de insertar un atributo `xml:lang` cuyo valor se toma del objeto <xref:System.Xml.XmlReader>.  
  
- Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto <xref:System.Xml.XPath.XPathNavigator>, pero cada uno con un valor diferente, se agrega al nodo que se acaba de insertar un atributo `xml:lang` cuyo valor se toma del objeto <xref:System.Xml.XmlReader>.  
  
- Si hay un atributo en el ámbito `xml:lang` dentro del contexto del objeto <xref:System.Xml.XmlReader> y del objeto<xref:System.Xml.XPath.XPathNavigator> y cada uno tiene el mismo valor, no se agrega al nodo que se acaba de insertar ningún atributo `xml:lang` nuevo.  
  
- Si hay un atributo `xml:lang` en el ámbito dentro del contexto del objeto <xref:System.Xml.XPath.XPathNavigator>, pero no existe ninguno en el contexto del objeto <xref:System.Xml.XmlReader>, no se agrega al nodo que se acaba de insertar ningún atributo `xml:lang`.  
  
## <a name="inserting-nodes-with-xmlwriter"></a>Inserción de nodos con XmlWriter  
 Los métodos que se utilizan para insertar nodos de atributos, secundarios y relacionados que se describen en la sección "Inserción de nodos y valores" están sobrecargados. Los métodos <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> y <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> devuelven un objeto <xref:System.Xml.XmlWriter> que se utiliza para insertar nodos.  
  
### <a name="unsupported-xmlwriter-methods"></a>Métodos XmlWriter incompatibles  
 No todos los métodos que se utilizan para escribir información en un documento XML con la clase <xref:System.Xml.XmlWriter> son compatibles con la clase <xref:System.Xml.XPath.XPathNavigator>. Esto se debe a la diferencia entre el modelo de datos XPath y el Modelo de objetos de documento (DOM).  
  
 En la siguiente tabla se describen los métodos de la clase <xref:System.Xml.XmlWriter> que no son compatibles con la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
|Método|Descripción|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|Inicia una excepción <xref:System.NotSupportedException>.|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|Se omite en el nivel raíz e inicia una excepción <xref:System.NotSupportedException> si se llama desde cualquier otro nivel del documento XML.|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|Se trata como una llamada al método <xref:System.Xml.XmlWriter.WriteString%2A> para el carácter o caracteres equivalentes.|  
  
 Para obtener más información sobre la clase <xref:System.Xml.XmlWriter>, vea la documentación de referencia de la clase <xref:System.Xml.XmlWriter>.  
  
### <a name="multiple-xmlwriter-objects"></a>Varios objetos XmlWriter  
 Es posible tener varios objetos <xref:System.Xml.XPath.XPathNavigator> apuntando a diferentes partes de un documento XML con uno o varios objetos <xref:System.Xml.XmlWriter> abiertos. Se permite tener varios objetos <xref:System.Xml.XmlWriter> en situaciones en las que solo hay un subproceso.  
  
 A continuación se indican una serie de puntos importantes que hay que tener en cuenta al utilizar varios objetos <xref:System.Xml.XmlWriter>.  
  
- Se agregan fragmentos XML escritos por objetos <xref:System.Xml.XmlWriter> al documento XML cuando se llama al método <xref:System.Xml.XmlWriter.Close%2A> de cada objeto <xref:System.Xml.XmlWriter>. Hasta ese punto, el objeto <xref:System.Xml.XmlWriter> está escribiendo un fragmento desconectado. Si se realiza una operación en el documento XML, cualquier fragmento que estuviera escribiendo un objeto <xref:System.Xml.XmlWriter> antes de que se haya llamado a <xref:System.Xml.XmlWriter.Close%2A>, no resulta afectado.  
  
- Si hay un objeto <xref:System.Xml.XmlWriter> abierto en un subárbol XML en concreto y ese subárbol se elimina, todavía es posible agregar el objeto <xref:System.Xml.XmlWriter> al subárbol. El subárbol se convierte simplemente en un fragmento eliminado.  
  
- Si se abren varios objetos <xref:System.Xml.XmlWriter> en el mismo punto del documento XML, se agregan al documento XML en el orden en el que se cierran los objetos <xref:System.Xml.XmlWriter>, no en el orden en el que se han abierto.  
  
 En el siguiente ejemplo se crea un objeto <xref:System.Xml.XmlDocument> y un objeto <xref:System.Xml.XPath.XPathNavigator> y, a continuación, se utiliza el objeto <xref:System.Xml.XmlWriter> que devuelve el método <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> para crear la estructura del primer libro en el archivo `books.xml`. A continuación, se guarda como el archivo `book.xml` en el ejemplo.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a>Cómo guardar un documento XML  
 Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>. Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Modificación de datos XML con XPathNavigator](modify-xml-data-using-xpathnavigator.md)
- [Eliminación de datos XML con XPathNavigator](remove-xml-data-using-xpathnavigator.md)
