---
title: Modificación de datos XML con XPathNavigator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 03a7c5a1-b296-4af4-b209-043c958dc0a5
ms.openlocfilehash: 1770eb08055fd244bd0f220fed6d1641c35174fd
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82794356"
---
# <a name="modify-xml-data-using-xpathnavigator"></a>Modificación de datos XML con XPathNavigator
La clase <xref:System.Xml.XPath.XPathNavigator> incluye un conjunto de métodos que se utilizan para modificar nodos y valores en un documento XML. Para utilizar estos métodos, el objeto <xref:System.Xml.XPath.XPathNavigator> debe ser editable, es decir, su propiedad <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> debe ser `true`.  
  
 El método <xref:System.Xml.XPath.XPathNavigator> de la clase <xref:System.Xml.XmlDocument.CreateNavigator%2A> crea los objetos <xref:System.Xml.XmlDocument> que pueden editar un documento XML. Los objetos <xref:System.Xml.XPath.XPathNavigator> que crea la clase <xref:System.Xml.XPath.XPathDocument> son de solo lectura y cualquier intento de utilizar los métodos de edición de un objeto <xref:System.Xml.XPath.XPathNavigator> creado por un objeto <xref:System.Xml.XPath.XPathDocument> producirá una excepción <xref:System.NotSupportedException>.  
  
 Para más información sobre cómo crear objetos <xref:System.Xml.XPath.XPathNavigator> editables, vea [Lectura de datos XML con XPathDocument y XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).  
  
## <a name="modifying-nodes"></a>Modificación de nodos  
 Una técnica muy sencilla para cambiar el valor de un nodo consiste en utilizar los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
 En la siguiente tabla se enumeran los efectos de estos métodos en diferentes tipos de nodos.  
  
|<xref:System.Xml.XPath.XPathNodeType>|Datos cambiados|  
|---------------------------------------------------------------------------------------------------------------------------------------------|------------------|  
|<xref:System.Xml.XPath.XPathNodeType.Root>|No se admite.|  
|<xref:System.Xml.XPath.XPathNodeType.Element>|El contenido del elemento.|  
|<xref:System.Xml.XPath.XPathNodeType.Attribute>|El valor del atributo.|  
|<xref:System.Xml.XPath.XPathNodeType.Text>|Contenido de texto.|  
|<xref:System.Xml.XPath.XPathNodeType.ProcessingInstruction>|El contenido, sin incluir el destino.|  
|<xref:System.Xml.XPath.XPathNodeType.Comment>|El contenido del comentario.|  
|<xref:System.Xml.XPath.XPathNodeType.Namespace>|No admitido.|  
  
> [!NOTE]
> No se permite editar los nodos <xref:System.Xml.XPath.XPathNodeType.Namespace> ni el nodo <xref:System.Xml.XPath.XPathNodeType.Root>.  
  
 La clase <xref:System.Xml.XPath.XPathNavigator> también incluye un conjunto de métodos que se utilizan para insertar y quitar nodos. Para más información sobre cómo insertar y quitar nodos de un documento XML, vea los temas [Inserción de datos XML con XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md) y [Cómo quitar datos XML con XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md).  
  
### <a name="modifying-untyped-values"></a>Modificación de valores sin información de tipos  
 El método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> simplemente inserta el valor `string` sin información de tipos, que se pasa como parámetro, como valor del nodo en el que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator>. Este valor se inserta sin ningún tipo o sin comprobar si el nuevo valor es válido de acuerdo con el tipo del nodo si hay disponible información de esquema.  
  
 En el siguiente ejemplo, el método <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> se utiliza para actualizar todos los elementos `price` del archivo `contosoBooks.xml`.  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="modifying-typed-values"></a>Modificación de valores con información de tipos  
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
  
#### <a name="the-effects-of-editing-strongly-typed-xml-data"></a>Efectos de la edición de datos XML fuertemente tipados  
 La clase <xref:System.Xml.XPath.XPathNavigator> utiliza el esquema XML del W3C como base para describir XML fuertemente tipado. Se pueden anotar los elementos y atributos con la información de tipos basándose en la validación realizada en un documento de esquema XML del W3C. Los elementos que pueden contener otros elementos o atributos se denominan tipos complejos, mientras que los que solo pueden incluir contenido textual, se denominan tipos simples.  
  
> [!NOTE]
> Los atributos solo pueden tener tipos simples.  
  
 Se considera que un elemento o atributo tiene un esquema válido si cumple todas las normas específicas a la definición de su tipo. Un elemento que tenga el tipo simple `xs:int` debe contener un valor numérico entre -2147483648 y 2147483647 para que su esquema sea válido. En los tipos complejos, la validez del esquema del elemento depende de la validez del esquema de sus elementos y atributos secundarios. De esta manera, si un elemento es válido de acuerdo con la definición de su tipo complejo, todos sus elementos y atributos secundarios son válidos de acuerdo con las definiciones de sus tipos. De igual forma, si tan solo uno de los elementos o atributos secundarios de un elemento no es válido de acuerdo con la definición de su tipo, o tiene una validez desconocida, dicho elemento tampoco es válido o también tiene una validez desconocida.  
  
 Dado que la validez de un elemento depende de la validez de sus elementos y atributos secundarios, las modificaciones que se realicen en cualquiera de ellos cambian la validez del elemento si previamente era válido. Concretamente, si se insertan, actualizan o eliminan elementos o atributos secundarios de un elemento, la validez de dicho elemento pasa a ser desconocida. Esto lo representa la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> del elemento que se establece en <xref:System.Xml.Schema.XmlSchemaValidity.NotKnown>. Asimismo, esto tiene un efecto en cascada ascendente y recursivo en todo el documento XML, porque la validez del elemento primario del elemento (y de su elemento primario y así, sucesivamente) también pasa a ser desconocida.  
  
 Para más información sobre la validación de esquemas y la clase <xref:System.Xml.XPath.XPathNavigator>, vea [Validación de esquemas con XPathNavigator](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md).  
  
### <a name="modifying-attributes"></a>Modificación de atributos  
 Los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> pueden utilizarse para modificar nodos de atributos con y sin información de tipos, así como los otros tipos de nodos que se enumeran en la sección "Modificación de nodos".  
  
 En el siguiente ejemplo se cambia el valor del atributo `genre` del primer elemento `book` en el archivo `books.xml`.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
navigator.MoveToChild("book", String.Empty)  
navigator.MoveToAttribute("genre", String.Empty)  
  
navigator.SetValue("non-fiction")  
  
navigator.MoveToRoot()  
Console.WriteLine(navigator.OuterXml)  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
navigator.MoveToChild("book", String.Empty);  
navigator.MoveToAttribute("genre", String.Empty);  
  
navigator.SetValue("non-fiction");  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 Para obtener más información sobre los métodos <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> y <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A>, vea las secciones "Modificación de valores sin información de tipos" y "Modificación de valores con información de tipos".  
  
## <a name="innerxml-and-outerxml-properties"></a>Propiedades InnerXml y OuterXml  
 Las propiedades <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> y <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> de la clase <xref:System.Xml.XPath.XPathNavigator> cambian el marcado XML de los nodos en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>.  
  
 La propiedad <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente el objeto <xref:System.Xml.XPath.XPathNavigator> por el contenido analizado de la `string` XML especificada. Igualmente, la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> cambia el marcado XML de los nodos secundarios en los que se encuentra situado actualmente un objeto <xref:System.Xml.XPath.XPathNavigator>, así como el propio nodo actual.  
  
 En el siguiente ejemplo se utiliza la propiedad <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> para modificar el valor del elemento `price` e insertar un nuevo atributo `discount` en el primer elemento `book` del archivo `contosoBooks.xml`.  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("contosoBooks.xml");  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>"  
  
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
  
navigator.OuterXml = "<price discount=\"0\">10.99</price>";  
  
navigator.MoveToRoot();  
Console.WriteLine(navigator.OuterXml);  
```  
  
 En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
## <a name="modifying-namespace-nodes"></a>Modificación de nodos de espacios de nombres  
 En el Modelo de objetos de documento (DOM), las declaraciones de espacios de nombres se tratan como si fueran atributos normales que se pueden insertar, actualizar y eliminar. La clase <xref:System.Xml.XPath.XPathNavigator> no permite realizar estas operaciones en nodos de espacios de nombres ya que, si se cambia el valor de un nodo de espacio de nombres, puede cambiar la identidad de los elementos y atributos en el ámbito del nodo de espacio de nombres, tal y como se ilustra en el siguiente ejemplo.  
  
```xml  
<root xmlns="http://www.contoso.com">  
    <child />  
</root>  
```  
  
 Si se cambia el ejemplo de XML anterior de la siguiente manera, cambiará el nombre de todos los elementos del documento de manera efectiva, ya que se cambia el valor del identificador URI del espacio de nombres de cada elemento.  
  
```xml  
<root xmlns="urn:contoso.com">  
    <child />  
</root>  
```  
  
 La clase <xref:System.Xml.XPath.XPathNavigator> permite insertar nodos de espacios de nombres que no entren en conflicto con las declaraciones de espacios de nombres en el ámbito en el que se insertan. En este caso, las declaraciones de espacios de nombres no se declaran en ámbitos inferiores del documento XML y no se produce el cambio de nombres, tal y como se ilustra en el siguiente ejemplo.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent>  
        <a:child />  
    </parent>  
</root>  
```  
  
 Si el ejemplo de XML anterior se cambia de la siguiente forma, las declaraciones de espacios de nombres se propagan correctamente por el documento XML por debajo del ámbito de la otra declaración de espacio de nombres.  
  
```xml  
<root xmlns:a="http://www.contoso.com">  
    <parent a:parent-id="1234" xmlns:a="http://www.contoso.com/parent-id">  
        <a:child xmlns:a="http://www.contoso.com/" />  
    </parent>  
</root>  
```  
  
 En el ejemplo de XML anterior, se inserta el atributo `a:parent-id` en el elemento `parent` del espacio de nombres `http://www.contoso.com/parent-id`. Se utiliza el método <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> para insertar el atributo mientras se encuentra situado en el elemento `parent`. La clase `http://www.contoso.com` inserta automáticamente la declaración de espacio de nombres <xref:System.Xml.XPath.XPathNavigator> para mantener la coherencia del resto del documento XML.  
  
## <a name="modifying-entity-reference-nodes"></a>Modificación de nodos de referencia de entidad  
 Los nodos de referencia de entidad de un objeto <xref:System.Xml.XmlDocument> son de solo lectura y no se pueden editar con las clases <xref:System.Xml.XPath.XPathNavigator> o <xref:System.Xml.XmlNode>. Cualquier intento de modificar un nodo de referencia de entidad produce una <xref:System.InvalidOperationException>.  
  
## <a name="modifying-xsinil-nodes"></a>Modificación de nodos xsi:nil  
 La recomendación del esquema XML del W3C introduce el concepto de elemento "nillable". Cuando un elemento es "nillable", es posible que sea válido sin tener contenido. El concepto de elemento "nillable" es similar al concepto de objeto `null`. La principal diferencia es que no es posible obtener acceso de ninguna forma a un objeto `null`, mientras que un elemento `xsi:nil` sigue teniendo propiedades (por ejemplo, atributos) a las que se puede tener acceso, pero no tiene contenido (es decir, texto ni elementos secundarios). La existencia del atributo `xsi:nil` con un valor de `true` en un elemento de un documento XML se utiliza para indicar que un elemento no tiene contenido.  
  
 Si se utiliza un objeto <xref:System.Xml.XPath.XPathNavigator> para agregar contenido a un elemento válido con un atributo `xsi:nil` que tiene un valor de `true`, el valor de su atributo `xsi:nil` se establece en `false`.  
  
> [!NOTE]
> Si se elimina el contenido de un elemento con un atributo `xsi:nil` establecido en `false`, el valor del atributo no se cambia por `true`.  
  
## <a name="saving-an-xml-document"></a>Cómo guardar un documento XML  
 Para guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument> como resultado de los métodos de edición que se describen en este tema, se utilizan los métodos de la clase <xref:System.Xml.XmlDocument>. Para obtener más información sobre cómo guardar los cambios realizados en un objeto <xref:System.Xml.XmlDocument>, vea [Guardar y escribir un documento](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Procesamiento de datos XML con el modelo de datos XPath](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)
- [Inserción de datos XML con XPathNavigator](../../../../docs/standard/data/xml/insert-xml-data-using-xpathnavigator.md)
- [Eliminación de datos XML con XPathNavigator](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)
