---
title: Acceso a datos XML fuertemente tipados utilizando XPathNavigator
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
ms.openlocfilehash: 7051aeb8cdc25518f99fe093045e7e769ae7f6f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725422"
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a>Acceso a datos XML fuertemente tipados utilizando XPathNavigator

Como instancia del modelo de datos XPath 2.0, la clase <xref:System.Xml.XPath.XPathNavigator> puede contener datos fuertemente tipados que se asignen a tipos de Common Language Runtime (CLR). De acuerdo con el modelo de datos XPath 2.0, solo los elementos y los atributos pueden contener datos fuertemente tipados. La clase <xref:System.Xml.XPath.XPathNavigator> proporciona mecanismos para acceder a los datos en un objeto <xref:System.Xml.XPath.XPathDocument> o <xref:System.Xml.XmlDocument> como datos fuertemente tipados, así como mecanismos para convertir un tipo de datos en otro.  
  
## <a name="type-information-exposed-by-xpathnavigator"></a>Información de tipo proporcionada por XPathNavigator  

 Técnicamente, los datos de XML 1.0 no tienen tipo, a menos que se procesen con una DTD, un esquema del lenguaje de definición de esquemas XML (XSD) u otro mecanismo. Existe una serie de categorías de información de tipo que se pueden asociar a un atributo o elemento XML.  
  
- Tipos CLR simples: ninguno de los lenguajes de esquema XML es compatible directamente con los tipos CLR. Puesto que es útil poder ver el contenido simple de atributos y elementos como el tipo CLR más apropiado, todo el contenido simple puede tener información del tipo <xref:System.String> en ausencia de información de esquema con cualquier información de esquema agregada que potencialmente refine este contenido con un tipo más apropiado. Para encontrar el mejor tipo CLR coincidente del contenido simple de atributos y elementos, utilice la propiedad <xref:System.Xml.XPath.XPathNavigator.ValueType%2A>. Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).  
  
- Listas de tipos simples (CLR): un elemento o atributo con contenido simple puede incluir una lista de valores separados por un espacio en blanco. Un esquema XML especifica los valores para que sean un "tipo de lista". En ausencia de un esquema XML, ese contenido simple se trataría como un solo nodo de texto. Cuando hay disponible un esquema XML, este contenido simple se puede proporcionar como una serie de valores atómicos, cada uno de los cuales tiene un tipo simple que se asigna a una colección de objetos CLR. Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).  
  
- Valor con información de tipos: un atributo o elemento validado en el esquema con un tipo simple tiene un valor con información de tipos. Este valor es un tipo primitivo, como un tipo numérico, de cadena o fecha. Todos los tipos simples integrados en XSD se pueden asignar a tipos CLR que proporcionan acceso al valor de un nodo como tipo más apropiado, en lugar de simplemente como <xref:System.String>. Se considera que un elemento con atributos o elementos secundarios es un tipo complejo. El valor con información de tipos de un tipo complejo con contenido simple (solo nodos de texto como nodos secundarios) es el mismo que del tipo simple de su contenido. El valor con información tipos de un tipo complejo con contenido complejo (uno o varios elementos secundarios) es el valor de cadena de la concatenación de todos sus nodos secundarios que se devuelven como <xref:System.String>. Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).  
  
- Nombre del tipo específico del lenguaje de esquema: en la mayoría de los casos, los tipos CLR, que se establecen como un efecto secundario de la aplicación de un esquema externo, se usan para proporcionar acceso al valor de un nodo. Sin embargo, puede haber situaciones en las que es conveniente examinar el tipo asociado a un esquema particular aplicado a un documento XML. Por ejemplo, podría desear realizar una búsqueda en un documento XML para extraer todos los elementos que se determine que tienen contenido del tipo "PurchaseOrder" de acuerdo con un esquema adjunto. Esa información de tipo solo se puede establecer como resultado de la validación del esquema y se tiene acceso a ella a través de las propiedades <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> y <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>. Para obtener más información, vea la sección El conjunto de información posterior a la validación de esquemas.  
  
- Reflexión del tipo específico del lenguaje de esquema: en otros casos, es posible que quiera obtener más detalles del tipo específico del esquema que se aplica a un documento XML. Por ejemplo, al leer un archivo XML, puede que desee extraer el atributo `maxOccurs` para cada nodo válido del documento XML con el fin de realizar algún cálculo personalizado. Puesto que esta información solo se establece a través de la validación de esquemas, se tiene acceso a ella a través de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>. Para obtener más información, vea la sección El conjunto de información posterior a la validación de esquemas.  
  
## <a name="xpathnavigator-typed-accessors"></a>Descriptores de acceso con información de tipos de XPathNavigator  

 En la siguiente tabla se muestran las diversas propiedades y métodos de la clase <xref:System.Xml.XPath.XPathNavigator> que se pueden utilizar para tener acceso a la información de tipo sobre un nodo.  
  
|Propiedad.|Descripción|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|Contiene la información de tipo del esquema XML para el nodo si es válido.|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|Contiene el conjunto de información posterior a la validación del esquema del nodo que se agrega después de la validación. Esto incluye la información de tipo del esquema XML, así como la información de validez.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|El tipo CLR del valor con información de tipos del nodo.|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|El contenido del nodo como uno o más valores CLR cuyo tipo es la coincidencia más cercana al tipo del esquema XML del nodo.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Boolean>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:boolean`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.DateTime>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:datetime`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Double>, de acuerdo con las reglas de conversión de XPath 2.0 para `xsd:double`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Int32>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:integer`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|El valor <xref:System.String> del nodo actual convertido en un valor <xref:System.Int64>, de acuerdo con las reglas de conversión de XPath 2.0 para `xs:integer`.|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|El contenido del nodo convertido en el tipo de destino de acuerdo con las reglas de conversión de XPath 2.0.|  
  
 Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).  
  
## <a name="the-post-schema-validation-infoset-psvi"></a>El conjunto de información posterior a la validación de esquemas (PSVI)  

 Un procesador de esquemas XML acepta un conjunto de información XML como entrada y lo convierte en un conjunto de información posterior a la validación de esquemas. Un conjunto de información posterior a la validación de esquemas es el conjunto de información XML original en el que se han agregado nuevos elementos de información y nuevas propiedades a elementos de información existentes. Existen tres clases de información muy amplias que se agregan al conjunto de información XML del conjunto de información posterior a la validación de esquemas que proporciona el <xref:System.Xml.XPath.XPathNavigator>.  
  
1. Resultados de la validación: información referente a si un elemento o atributo se ha validado correctamente o no. Esta información la proporciona la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
2. Información predeterminada: indicaciones referentes a si el valor del elemento o atributo se ha obtenido o no a través de los valores predeterminados especificados en el esquema. Esta información la proporciona la propiedad <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
3. Anotaciones de tipo: referencias a componentes del esquema que pueden ser definiciones de tipo o declaraciones de atributos o elementos. La propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> de <xref:System.Xml.XPath.XPathNavigator> contiene la información de tipo específica del nodo si es válido. Si la validez del nodo es desconocida como, por ejemplo, cuándo se validó y posteriormente se editó, la propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> se establece en `null` pero la información de tipo sigue estando disponible en varias propiedades de la propiedad <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> de la clase <xref:System.Xml.XPath.XPathNavigator>.  
  
 Los siguientes ejemplos ilustran el uso de información en el conjunto de información posterior a la validación de esquemas que proporciona <xref:System.Xml.XPath.XPathNavigator>.  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 En el ejemplo se toma como entrada el archivo `books.xml`.  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 En el ejemplo también se toma como entrada el esquema `books.xsd`.  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"
attributeFormDefault="unqualified" elementFormDefault="qualified"
targetNamespace="http://www.contoso.com/books"
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a>Obtención de valores con información de tipos utilizando propiedades ValueAs  

 El valor con información de tipos de un nodo se puede recuperar obteniendo acceso a la propiedad <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> de <xref:System.Xml.XPath.XPathNavigator>. En determinados casos, puede que desee convertir el valor con información de tipos de un nodo en un tipo diferente. Un ejemplo muy común es la obtención de un valor numérico de un nodo XML. Por ejemplo, considere los siguientes documentos XML no validados y sin información de tipos.  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 Si <xref:System.Xml.XPath.XPathNavigator> está situado en el elemento `price`, la propiedad <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> sería `null`, la propiedad <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> sería <xref:System.String> y la propiedad <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> sería la cadena `10.00`.  
  
 Sin embargo, sigue siendo posible extraer el valor como un valor numérico utilizando los métodos y propiedades <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A> o <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>. El siguiente ejemplo ilustra la realización de dicha conversión utilizando el método <xref:System.Xml.XPath.XPathItem.ValueAs%2A>.  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 Para obtener más información sobre la asignación de tipos integrados de esquemas a tipos CLR, vea [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [Compatibilidad de tipos en las clases System.Xml](type-support-in-the-system-xml-classes.md)
- [Procesamiento de datos XML con el modelo de datos XPath](process-xml-data-using-the-xpath-data-model.md)
- [Navegación por un conjunto de nodos con XPathNavigator](node-set-navigation-using-xpathnavigator.md)
- [Navegación por nodos de espacios de nombres y atributos con XPathNavigator](attribute-and-namespace-node-navigation-using-xpathnavigator.md)
- [Extracción de datos XML con XPathNavigator](extract-xml-data-using-xpathnavigator.md)
