---
title: Validación basada en inserción de XmlSchemaValidator
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 911d4460-dd91-4958-85b2-2ca3299f9ec6
ms.openlocfilehash: 6a0cc110c2b8bcd97b9f5c16a344db5a63046353
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709808"
---
# <a name="xmlschemavalidator-push-based-validation"></a>Validación basada en inserción de XmlSchemaValidator

La clase <xref:System.Xml.Schema.XmlSchemaValidator> incluye un mecanismo eficiente y de alto rendimiento para validar datos XML con esquemas XML mediante inserción. Por ejemplo, la clase <xref:System.Xml.Schema.XmlSchemaValidator> le permite validar un conjunto de información XML en el lugar sin tener que serializarla como un documento XML y, a continuación, volver a analizar el documento utilizando un sistema de lectura XML de validación.

La clase <xref:System.Xml.Schema.XmlSchemaValidator> se puede utilizar en situaciones avanzadas como, por ejemplo, durante la creación de motores de validación en orígenes de datos XML o como forma de crear un sistema de escritura XML de validación.

A continuación se ofrece un ejemplo del uso de la clase <xref:System.Xml.Schema.XmlSchemaValidator> para validar el archivo `contosoBooks.xml` con el esquema `contosoBooks.xsd`. El ejemplo utiliza la clase <xref:System.Xml.Serialization.XmlSerializer> para deserializar el archivo `contosoBooks.xml` y pasar el valor de los nodos a los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

> [!NOTE]
> Este ejemplo se utiliza a lo largo de las secciones de este tema.

[!code-csharp[XmlSchemaValidatorExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaValidatorExamples/CS/XmlSchemaValidatorExamples.cs#1)]
[!code-vb[XmlSchemaValidatorExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaValidatorExamples/VB/XmlSchemaValidatorExamples.vb#1)]

En el ejemplo se toma como entrada el archivo `contosoBooks.xml`.

[!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]

En el ejemplo también se toma como entrada el archivo `contosoBooks.xsd`.

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" targetNamespace="http://www.contoso.com/books" xmlns:xs="http://www.w3.org/2001/XMLSchema">
    <xs:element name="bookstore">
        <xs:complexType>
            <xs:sequence>
                <xs:element maxOccurs="unbounded" name="book">
                    <xs:complexType>
                        <xs:sequence>
                            <xs:element name="title" type="xs:string" />
                            <xs:element name="author">
                                <xs:complexType>
                                    <xs:sequence>
                                        <xs:element minOccurs="0" name="name" type="xs:string" />
                                        <xs:element minOccurs="0" name="first-name" type="xs:string" />
                                        <xs:element minOccurs="0" name="last-name" type="xs:string" />
                                    </xs:sequence>
                                </xs:complexType>
                            </xs:element>
                            <xs:element name="price" type="xs:decimal" />
                        </xs:sequence>
                        <xs:attribute name="genre" type="xs:string" use="required" />
                        <xs:attribute name="publicationdate" type="xs:date" use="required" />
                        <xs:attribute name="ISBN" type="xs:string" use="required" />
                    </xs:complexType>
                </xs:element>
            </xs:sequence>
        </xs:complexType>
    </xs:element>
</xs:schema>
```

## <a name="validating-xml-data-using-xmlschemavalidator"></a>Validación de datos XML con XmlSchemaValidator

Para comenzar la validación de un conjunto de información XML, primero se debe inicializar una instancia nueva de la clase <xref:System.Xml.Schema.XmlSchemaValidator> utilizando el constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>.

El constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A> toma los objetos <xref:System.Xml.XmlNameTable>, <xref:System.Xml.Schema.XmlSchemaSet> y <xref:System.Xml.XmlNamespaceManager> como parámetros, así como un valor <xref:System.Xml.Schema.XmlSchemaValidationFlags> como parámetro. El objeto <xref:System.Xml.XmlNameTable> se utiliza para atomizar cadenas de espacios de nombres bien conocidas (como el espacio de nombres del esquema, el espacio de nombres XML, etc.), y se pasa al método <xref:System.Xml.Schema.XmlSchemaDatatype.ParseValue%2A> mientras se valida contenido simple. El objeto <xref:System.Xml.Schema.XmlSchemaSet> contiene los esquemas XML que se utilizan para validar el conjunto de información XML. El objeto <xref:System.Xml.XmlNamespaceManager> se utiliza para resolver espacios de nombres que se encuentran durante la validación. El valor <xref:System.Xml.Schema.XmlSchemaValidationFlags> se utiliza para deshabilitar determinadas características de la validación.

Para obtener más información sobre el constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="initializing-validation"></a>Inicialización de la validación

Una vez construido un objeto <xref:System.Xml.Schema.XmlSchemaValidator>, existen dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> sobrecargados que se utilizan para inicializar el estado del objeto <xref:System.Xml.Schema.XmlSchemaValidator>. Éstos son los dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

- <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>

El método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> predeterminado inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial y el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> sobrecargado, que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro, inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial para realizar una validación parcial.

Los dos métodos <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> solo se pueden llamar inmediatamente después de construir un objeto <xref:System.Xml.Schema.XmlSchemaValidator> o después de una llamada a <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>.

Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>, vea el ejemplo de la introducción. Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="partial-validation"></a>Validación parcial

El método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType> que toma un objeto <xref:System.Xml.Schema.XmlSchemaObject> como parámetro inicializa un objeto <xref:System.Xml.Schema.XmlSchemaValidator> en su estado inicial para realizar una validación parcial.

En el siguiente ejemplo, se inicializa un <xref:System.Xml.Schema.XmlSchemaObject> para realizar una validación parcial utilizando el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A?displayProperty=nameWithType>. Para pasar el elemento de esquema `orderNumber`, se selecciona por <xref:System.Xml.XmlQualifiedName> en la colección <xref:System.Xml.Schema.XmlSchemaObjectTable> que devuelve la propiedad <xref:System.Xml.Schema.XmlSchemaSet.GlobalElements%2A> del objeto <xref:System.Xml.Schema.XmlSchemaSet>. A continuación, el objeto <xref:System.Xml.Schema.XmlSchemaValidator> valida este elemento específico.

```vb
Dim schemaSet As XmlSchemaSet = New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
schemaSet.Compile()
Dim nameTable As NameTable = New NameTable()
Dim manager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)

Dim validator As XmlSchemaValidator = New XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None)
validator.Initialize(schemaSet.GlobalElements.Item(New XmlQualifiedName("orderNumber")))

validator.ValidateElement("orderNumber", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateText("123")
validator.ValidateEndElement(Nothing)
```

```csharp
XmlSchemaSet schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
schemaSet.Compile();
NameTable nameTable = new NameTable();
XmlNamespaceManager manager = new XmlNamespaceManager(nameTable);

XmlSchemaValidator validator = new XmlSchemaValidator(nameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize(schemaSet.GlobalElements[new XmlQualifiedName("orderNumber")]);

validator.ValidateElement("orderNumber", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateText("123");
validator.ValidateEndElement(null);
```

En el ejemplo, se toma como entrada el siguiente esquema XML.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="orderNumber" type="xs:int" />
</xs:schema>
```

Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="adding-additional-schemas"></a>Adición de esquemas adicionales

El método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> se utiliza para agregar un esquema XML al conjunto de esquemas que se utiliza durante la validación. El método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> se puede utilizar para simular el efecto de encontrarse un esquema XML alineado en el conjunto de información XML que se está validando.

> [!NOTE]
> El espacio de nombres de destino del parámetro <xref:System.Xml.Schema.XmlSchema> no puede coincidir con el de ningún elemento o atributo que ya haya encontrado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.
>
> Si el valor <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessInlineSchema?displayProperty=nameWithType> no se hubiera pasado como parámetro al constructor <xref:System.Xml.Schema.XmlSchemaValidator.%23ctor%2A>, el método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> no haría nada.

El resultado del método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> depende del contexto del nodo XML actual que se está validando. Para obtener más información sobre los contextos de validación, vea la sección "Contexto de validación" en este tema.

Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="validating-elements-attributes-and-content"></a>Validación de elementos, atributos y contenido

La clase <xref:System.Xml.Schema.XmlSchemaValidator> incluye varios métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML con esquemas XML. En la siguiente tabla se describen cada uno de estos métodos.

|Método|Descripción|
|------------|-----------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Valida el nombre del elemento en el contexto actual.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Valida el atributo en el contexto del elemento actual o con el objeto <xref:System.Xml.Schema.XmlSchemaAttribute> que se pasa como parámetro al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|Comprueba si todos los atributos requeridos del contexto del elemento están presentes y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar el contenido secundario del elemento.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Valida si se permite texto en el contexto del elemento actual y acumula el texto para validar si el elemento actual tiene contenido simple.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Valida si se permite espacio en blanco en el contexto del elemento actual y acumula el espacio en blanco para validar si el elemento actual tiene contenido simple.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|Comprueba si el contenido de texto del elemento es válido de acuerdo con su tipo de datos para elementos con contenido simple, y comprueba si el contenido del elemento actual está completo para los elementos con contenido complejo.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Omite la validación del contenido del elemento actual y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar contenido en el contexto del elemento primario.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Termina la validación y comprueba las restricciones de identidad de todo el documento XML si se establece la opción de validación <xref:System.Xml.Schema.XmlSchemaValidationFlags.ProcessIdentityConstraints>.|

> [!NOTE]
> La clase <xref:System.Xml.Schema.XmlSchemaValidator> tiene una transición de estado definida que exige la secuencia y ocurrencia de las llamadas realizadas a cada uno de los métodos que se describen en la tabla anterior. La transición de estado específica de la clase <xref:System.Xml.Schema.XmlSchemaValidator> se describe en la sección "Transición de estado de XmlSchemaValidator" de este tema.

Para obtener un ejemplo de los métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML, vea el ejemplo de la sección anterior. Para obtener más información sobre estos métodos, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="validating-content-using-an-xmlvaluegetter"></a>Validación de contenido con XmlValueGetter

<xref:System.Xml.Schema.XmlValueGetter>`delegate` se puede utilizar para pasar el valor de los nodos de atributos, textos o espacios en blanco como tipos Common Language Runtime (CLR) compatibles con el tipo del lenguaje de definición de esquema XML (XSD) del nodo de atributos, textos o espacios en blanco. <xref:System.Xml.Schema.XmlValueGetter>`delegate` es útil si el valor CLR de un nodo de atributos, textos o espacios en blanco ya está disponible y evita el costo de convertirlo en un valor `string` y luego volver a analizarlo para validarlo.

Los métodos <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> están sobrecargados y aceptan el valor de los nodos de atributos, textos o espacios en blanco como un `string` o <xref:System.Xml.Schema.XmlValueGetter>`delegate`.

Los siguientes métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> aceptan un <xref:System.Xml.Schema.XmlValueGetter>`delegate` como parámetro.

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>

A continuación, se ofrece un ejemplo de un <xref:System.Xml.Schema.XmlValueGetter>`delegate` tomado del ejemplo de la clase <xref:System.Xml.Schema.XmlSchemaValidator> de la introducción. <xref:System.Xml.Schema.XmlValueGetter>`delegate` devuelve el valor de un atributo como un objeto <xref:System.DateTime>. Para validar este objeto <xref:System.DateTime> que devuelve <xref:System.Xml.Schema.XmlValueGetter>, el objeto <xref:System.Xml.Schema.XmlSchemaValidator> primero lo convierte en ValueType (ValueType es la asignación CLR predeterminada para el tipo XSD) para el tipo de datos del atributo y, a continuación, comprueba las facetas en el valor convertido.

```vb
Shared dateTimeGetterContent As Object

Shared Function DateTimeGetterHandle() As Object
    Return dateTimeGetterContent
End Function

Shared Function DateTimeGetter(dateTime As DateTime) As XmlValueGetter
    dateTimeGetterContent = dateTime
    Return New XmlValueGetter(AddressOf DateTimeGetterHandle)
End Function
```

```csharp
static object dateTimeGetterContent;

static object DateTimeGetterHandle()
{
    return dateTimeGetterContent;
}

static XmlValueGetter DateTimeGetter(DateTime dateTime)
{
    dateTimeGetterContent = dateTime;
    return new XmlValueGetter(dateTimeGetterHandle);
}
```

Para obtener un ejemplo completo de <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vea el ejemplo de la introducción. Para obtener más información sobre <xref:System.Xml.Schema.XmlValueGetter>`delegate`, vea la documentación de referencia de las clases <xref:System.Xml.Schema.XmlValueGetter> y <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="post-schema-validation-information"></a>Información posterior a la validación del esquema

La clase <xref:System.Xml.Schema.XmlSchemaInfo> representa parte de la información posterior a la validación del esquema de un nodo XML que valida la clase <xref:System.Xml.Schema.XmlSchemaValidator>. Hay varios métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que aceptan un objeto <xref:System.Xml.Schema.XmlSchemaInfo> como un parámetro `null` opcional (`out`).

Después de realizar la validación correctamente, se establecen las propiedades del objeto <xref:System.Xml.Schema.XmlSchemaInfo> con los resultados de la validación. Por ejemplo, después de validar correctamente un atributo utilizando el método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, las propiedades <xref:System.Xml.Schema.XmlSchemaInfo>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaInfo.SchemaType%2A> y <xref:System.Xml.Schema.XmlSchemaInfo.MemberType%2A> del objeto <xref:System.Xml.Schema.XmlSchemaInfo.Validity%2A> se establecen con los resultados de la validación.

Los siguientes métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> aceptan un objeto <xref:System.Xml.Schema.XmlSchemaInfo> como parámetro out.

- <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>

- <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>

Para obtener un ejemplo completo de la clase <xref:System.Xml.Schema.XmlSchemaInfo>, vea el ejemplo de la introducción. Para obtener más información sobre la clase <xref:System.Xml.Schema.XmlSchemaInfo>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaInfo>.

### <a name="retrieving-expected-particles-attributes-and-unspecified-default-attributes"></a>Recuperación de partículas y atributos esperados y atributos predeterminados no especificados

La clase <xref:System.Xml.Schema.XmlSchemaValidator> proporciona los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> para recuperar las partículas y atributos esperados y los atributos predeterminados no especificados en el contexto de validación actual.

#### <a name="retrieving-expected-particles"></a>Recuperación de partículas esperadas

El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz de objetos <xref:System.Xml.Schema.XmlSchemaParticle> que contienen las partículas esperadas en el contexto del elemento actual. Las partículas válidas que puede devolver el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> son instancias de las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAny>.

Cuando el compositor del modelo de contenido es `xs:sequence`, solo se devuelve la siguiente partícula de la secuencia. Si el compositor del modelo de contenido es `xs:all` o `xs:choice`, se devuelven todas las partículas válidas que pueden ir a continuación en el contexto del elemento actual.

> [!NOTE]
> Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> inmediatamente después de llamar al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>, el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve todos los elementos globales.

Por ejemplo, en el esquema del lenguaje de definición de esquemas XML (XSD) y en el documento XML que sigue, después de validar el elemento `book`, el elemento `book` es el contexto del elemento actual. El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaElement> que representa el elemento `title`. Cuando el contexto de validación es el elemento `title`, el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía. Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> después de que se haya validado el elemento `title`, pero antes de validar el elemento `description`, devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaElement> que representa el elemento `description`. Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> después de que se haya validado el elemento `description`, devuelve una matriz que contiene un solo objeto <xref:System.Xml.Schema.XmlSchemaAny> que representa el comodín.

```vb
Dim reader As XmlReader =  XmlReader.Create("input.xml")

Dim schemaSet As New XmlSchemaSet()
schemaSet.Add(Nothing, "schema.xsd")
Dim manager As New XmlNamespaceManager(reader.NameTable)

Dim validator As New XmlSchemaValidator(reader.NameTable,schemaSet,manager,XmlSchemaValidationFlags.None)
validator.Initialize()

validator.ValidateElement("book", "", Nothing)

validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("title", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next
validator.ValidateEndElement(Nothing)

For Each element As XmlSchemaElement In validator.GetExpectedParticles()
    Console.WriteLine(element.Name)
Next

validator.ValidateElement("description", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

For Each particle As XmlSchemaParticle In validator.GetExpectedParticles()
    Console.WriteLine(particle.GetType())
Next

validator.ValidateElement("namespace", "", Nothing)
validator.ValidateEndOfAttributes(Nothing)
validator.ValidateEndElement(Nothing)

validator.ValidateEndElement(Nothing)
```

```csharp
XmlReader reader = XmlReader.Create("input.xml");

var schemaSet = new XmlSchemaSet();
schemaSet.Add(null, "schema.xsd");
var manager = new XmlNamespaceManager(reader.NameTable);

var validator = new XmlSchemaValidator(reader.NameTable, schemaSet, manager, XmlSchemaValidationFlags.None);
validator.Initialize();

validator.ValidateElement("book", "", null);

validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("title", "", null);
validator.ValidateEndOfAttributes(null);
foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}
validator.ValidateEndElement(null);

foreach (XmlSchemaElement element in validator.GetExpectedParticles())
{
    Console.WriteLine(element.Name);
}

validator.ValidateElement("description", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

foreach (XmlSchemaParticle particle in validator.GetExpectedParticles())
{
    Console.WriteLine(particle.GetType());
}

validator.ValidateElement("namespace", "", null);
validator.ValidateEndOfAttributes(null);
validator.ValidateEndElement(null);

validator.ValidateEndElement(null);
```

 En el ejemplo se toma como entrada el siguiente XML:

```xml
<xs:schema xmlns:xs="http://www.w3c.org/2001/XMLSchema">
  <xs:element name="book">
    <xs:sequence>
      <xs:element name="title" type="xs:string" />
      <xs:element name="description" type="xs:string" />
      <xs:any processContent="lax" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:element>
</xs:schema>
```

En el ejemplo se toma como entrada el siguiente esquema XSD:

```xml
<book>
  <title>My Book</title>
  <description>My Book's Description</description>
  <namespace>System.Xml.Schema</namespace>
</book>
```

> [!NOTE]
> Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando. Para obtener más información, vea la sección "Contexto de validación" de este tema.

Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vea el ejemplo de la introducción. Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-expected-attributes"></a>Recuperación de atributos esperados

El método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz de objetos <xref:System.Xml.Schema.XmlSchemaAttribute> que contienen los atributos esperados en el contexto del elemento actual.

Por ejemplo, en el ejemplo de la introducción, se utiliza el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> para recuperar todos los atributos del elemento `book`.

Si llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> inmediatamente después del método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>, se devuelven todos los atributos que podrían aparecer en el documento XML. Sin embargo, si llama al método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> después de una o más llamadas al método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, se devuelven los atributos que aún no se han validado para el elemento actual.

> [!NOTE]
> Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando. Para obtener más información, vea la sección "Contexto de validación" de este tema.

Para obtener un ejemplo del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vea el ejemplo de la introducción. Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

#### <a name="retrieving-unspecified-default-attributes"></a>Recuperación de atributos predeterminados no especificados

El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> rellena el <xref:System.Collections.ArrayList> especificado con objetos <xref:System.Xml.Schema.XmlSchemaAttribute> para cualquier atributo con valores predeterminados que no haya sido validado previamente con el método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> en el contexto del elemento. El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> se debería llamar después de llamar al método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> en cada atributo del contexto del elemento. El método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A> se debería utilizar para determinar qué atributos predeterminados se van a insertar en el documento XML que se está validando.

Para obtener más información sobre el método <xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

### <a name="handling-schema-validation-events"></a>Control de eventos de validación de esquemas

Las advertencias y errores de validación de esquemas que se encuentran durante la validación se controlan por medio del evento <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler> de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

Las advertencias de validación de esquemas tienen un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Warning> y los errores de validación de esquemas tienen un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Error>. Si no se ha asignado ningún <xref:System.Xml.Schema.XmlSchemaValidator.ValidationEventHandler>, se inicia una <xref:System.Xml.Schema.XmlSchemaValidationException> para todos los errores de validación de esquemas con un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Error>. Sin embargo, no se inicia una <xref:System.Xml.Schema.XmlSchemaValidationException> para las advertencias de validación de esquemas con un valor <xref:System.Xml.Schema.XmlSeverityType> de <xref:System.Xml.Schema.XmlSeverityType.Warning>.

A continuación, se ofrece un ejemplo de un <xref:System.Xml.Schema.ValidationEventHandler> que recibe errores y advertencias de validación de esquemas que se encuentran durante la validación de esquemas tomada del ejemplo de la introducción.

```vb
Shared Sub SchemaValidationEventHandler(sender As Object, e As ValidationEventArgs)

    Select Case e.Severity
        Case XmlSeverityType.Error
            Console.WriteLine(vbCrLf & "Error: {0}", e.Message)
            Exit Sub
        Case XmlSeverityType.Warning
            Console.WriteLine(vbCrLf & "Warning: {0}", e.Message)
            Exit Sub
    End Select
End Sub
```

```csharp
static void SchemaValidationEventHandler(object sender, ValidationEventArgs e)
{
    switch (e.Severity)
    {
        case XmlSeverityType.Error:
            Console.WriteLine("\nError: {0}", e.Message);
            break;
        case XmlSeverityType.Warning:
            Console.WriteLine("\nWarning: {0}", e.Message);
            break;
    }
}
```

Para obtener un ejemplo completo de <xref:System.Xml.Schema.ValidationEventHandler>, vea el ejemplo de la introducción. Para obtener más información, vea la documentación de referencia de la clase <xref:System.Xml.Schema.XmlSchemaInfo>.

## <a name="xmlschemavalidator-state-transition"></a>Transición de estado de XmlSchemaValidator

La clase <xref:System.Xml.Schema.XmlSchemaValidator> tiene una transición de estado definida que exige la secuencia y ocurrencia de las llamadas realizadas a cada uno de los métodos que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML.

En la siguiente tabla se describe la transición de estado de la clase <xref:System.Xml.Schema.XmlSchemaValidator> y la secuencia y ocurrencia de las llamadas de método que se pueden realizar en cada estado.

|Estado|Transición|
|-----------|----------------|
|Validate|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> (<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A> &#124; TopLevel*) <xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|
|TopLevel|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|
|Elemento|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>* (\*de contenido<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>) <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A> &#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>&#124;<br /><br /> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A> <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>\* <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A> contenido\* <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>&#124;|
|Contenido|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A> &#124; <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A> &#124; Element|

> [!NOTE]
> Cada uno de los métodos de la tabla anterior inicia una <xref:System.InvalidOperationException> cuando se realiza la llamada al método en la secuencia incorrecta de acuerdo con el estado actual de un objeto <xref:System.Xml.Schema.XmlSchemaValidator>.

La tabla de transición de estado anterior utiliza signos de puntuación para describir los métodos y otros estados que se pueden llamar para cada estado de la transición de la clase <xref:System.Xml.Schema.XmlSchemaValidator>. Los signos que se utilizan son los mismos que se encuentran en la referencia de estándares XML de la definición de tipos de documento (DTD).

En la siguiente tabla se describe cómo los signos de puntuación que se encuentran en la tabla de transiciones de estado anterior afectan a los métodos y otros estados que se pueden llamar para cada estado de la transición de la clase <xref:System.Xml.Schema.XmlSchemaValidator>.

|Símbolo|Descripción|
|------------|-----------------|
|&#124;|Se puede llamar al método o al estado (al que está antes o después de la barra).|
|?|El método o estado que precede al signo de interrogación es opcional, pero si se llama, solo se puede llamar una vez.|
|*|El método o estado que precede al símbolo * es opcional y se puede llamar más de una vez.|

## <a name="validation-context"></a>Contexto de validación

Los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que se utilizan para validar elementos, atributos y contenido en un conjunto de información XML cambian el contexto de validación de un objeto <xref:System.Xml.Schema.XmlSchemaValidator>. Por ejemplo, el método <xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A> omite la validación del contenido del elemento actual y prepara el objeto <xref:System.Xml.Schema.XmlSchemaValidator> para validar contenido en el contexto del elemento primario; es equivalente a la omisión de la validación para todos los elementos secundarios del elemento actual y luego a la llamada del método <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.

Los resultados de los métodos <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> y <xref:System.Xml.Schema.XmlSchemaValidator.AddSchema%2A> de la clase <xref:System.Xml.Schema.XmlSchemaValidator> dependen del contexto actual que se está validando.

En la siguiente tabla se describen los resultados de las llamadas a estos métodos después de llamar a uno de los métodos de la clase <xref:System.Xml.Schema.XmlSchemaValidator> que se utiliza para validar elementos, atributos y contenido en un conjunto de información XML.

|Método|GetExpectedParticles|GetExpectedAttributes|AddSchema|
|------------|--------------------------|---------------------------|---------------|
|<xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A>|Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> predeterminado, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz que contiene todos los elementos globales.<br /><br /> Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> sobrecargado que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro para inicializar la validación parcial de un elemento, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve solo el elemento en el cual se ha inicializado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.|Si se llama al método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> predeterminado, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.<br /><br /> Si se llama a la sobrecarga del método <xref:System.Xml.Schema.XmlSchemaValidator.Initialize%2A> que toma un <xref:System.Xml.Schema.XmlSchemaObject> como parámetro para inicializar la validación parcial de un atributo, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve solo el atributo en el cual se ha inicializado el objeto <xref:System.Xml.Schema.XmlSchemaValidator>.|Agrega el esquema al <xref:System.Xml.Schema.XmlSchemaSet> del objeto <xref:System.Xml.Schema.XmlSchemaValidator> si no tiene errores de procesamiento previo.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateElement%2A>|Si el elemento del contexto es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como elementos secundarios del elemento del contexto.<br /><br /> Si el elemento del contexto no es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.|Si el elemento del contexto es válido, y si no se ha realizado previamente ninguna llamada a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de todos los atributos definidos en el elemento del contexto.<br /><br /> Si ya se han validado algunos atributos, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de los atributos restantes que hay que validar.<br /><br /> Si el elemento del contexto no es válido, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateAttribute%2A>|Si el atributo del contexto es un atributo de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.<br /><br /> De lo contrario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.|Si el atributo del contexto es un atributo de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.<br /><br /> De lo contrario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos restantes que hay que validar.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.GetUnspecifiedDefaultAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista de los atributos requeridos y opcionales que aún quedan por validar en el elemento del contexto.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndOfAttributes%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada como primer elemento secundario del elemento del contexto.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>|Si contentType del elemento del contexto es Mixed, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada en la siguiente posición.<br /><br /> Si contentType del elemento del contexto es TextOnly o Empty, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.<br /><br /> Si contentType del elemento del contexto es ElementOnly, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada en la siguiente posición, pero ya se ha producido un error de validación.|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos del elemento del contexto no validada.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateWhitespace%2A>|Si el espacio en blanco del contexto es un espacio en blanco de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve una matriz vacía.<br /><br /> De lo contrario, el comportamiento del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> es el mismo que en <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Si el espacio en blanco del contexto es un espacio en blanco de nivel superior, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una matriz vacía.<br /><br /> De lo contrario, el comportamiento del método <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> es el mismo que en <xref:System.Xml.Schema.XmlSchemaValidator.ValidateText%2A>.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedParticles%2A> devuelve la secuencia de elementos esperada después del elemento del contexto (posibles elementos relacionados).|<xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve la lista de atributos del elemento del contexto no validada.<br /><br /> Si el elemento del contexto no tiene elemento primario, <xref:System.Xml.Schema.XmlSchemaValidator.GetExpectedAttributes%2A> devuelve una lista vacía (el elemento del contexto es el elemento primario del elemento actual en el que se ha llamado a <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>).|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.SkipToEndElement%2A>|Igual que <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Igual que <xref:System.Xml.Schema.XmlSchemaValidator.ValidateEndElement%2A>.|Como anteriormente.|
|<xref:System.Xml.Schema.XmlSchemaValidator.EndValidation%2A>|Devuelve una matriz vacía.|Devuelve una matriz vacía.|Como anteriormente.|

> [!NOTE]
> Los valores devueltos por las diversas propiedades de la clase <xref:System.Xml.Schema.XmlSchemaValidator> no cambian al llamar a cualquiera de los métodos de la tabla anterior.

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Schema.XmlSchemaValidator>
