---
title: Edición de esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: d7d9f8e0d4ec2f343b50e68e942bf94e93576f25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710952"
---
# <a name="editing-xml-schemas"></a>Edición de esquemas XML

La edición de un esquema XML es una de las características más importantes del Modelo de objetos de esquema (SOM). Se pueden utilizar todas las propiedades previas a la compilación de esquemas del SOM para cambiar los valores existentes de un esquema XML. Luego, el esquema XML se puede recompilar para reflejar los cambios.

El primer paso para editar un esquema cargado en el SOM consiste en atravesar el esquema. Debería familiarizarse con el proceso de atravesar un esquema utilizando la API del SOM antes de intentar editar un esquema. También debería familiarizarse con las propiedades posteriores y anteriores a la compilación de esquemas del conjunto de información posterior a la compilación de esquemas (PSCI).

## <a name="editing-an-xml-schema"></a>Edición de un esquema XML

En esta sección se incluyen dos ejemplos de código que editan el esquema del cliente que se creó en el tema [Compilar esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md). En el primer ejemplo de código se agrega un nuevo elemento `PhoneNumber` al elemento `Customer` y, en el segundo, se agrega un nuevo atributo `Title` al elemento `FirstName`. En el primer ejemplo también se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas como medio para atravesar el esquema del cliente, mientras que en el segundo ejemplo se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.

### <a name="phonenumber-element-example"></a>Ejemplo del elemento PhoneNumber

En el primer ejemplo de código se agrega un nuevo elemento `PhoneNumber` al elemento `Customer` del esquema del cliente. El ejemplo de código edita el esquema del cliente en los siguientes pasos.

1. Agrega el esquema del cliente a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego lo compila. Cualquier error o advertencia de validación de esquemas que se encuentre durante la lectura o compilación del esquema se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.

2. Recupera el objeto <xref:System.Xml.Schema.XmlSchema> compilado desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Puesto que el esquema se compila, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.

3. Crea el elemento `PhoneNumber` utilizando la clase <xref:System.Xml.Schema.XmlSchemaElement>, la restricción de tipos simples `xs:string` utilizando las clases <xref:System.Xml.Schema.XmlSchemaSimpleType> y <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>, agrega una faceta de patrón a la propiedad <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> de la restricción, y agrega la restricción a la propiedad <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> del tipo simple y el tipo simple al <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> del elemento `PhoneNumber`.

4. Itera por cada <xref:System.Xml.Schema.XmlSchemaElement> de la colección <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> de la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas.

5. Si el <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> del elemento es `"Customer"`, se obtiene el tipo complejo del elemento `Customer` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType> y la partícula de secuencia del tipo complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSequence>.

6. Agrega el nuevo elemento `PhoneNumber` a la secuencia que contiene los elementos `FirstName` y `LastName` existentes utilizando la colección <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> previa a la compilación de esquemas de la secuencia.

7. Por último, vuelve a procesar y compilar el objeto <xref:System.Xml.Schema.XmlSchema> modificado utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> y <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de la clase <xref:System.Xml.Schema.XmlSchemaSet> y lo escribe en la consola.

Éste es el ejemplo de código completo.

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

A continuación se ofrece el esquema del cliente modificado que se creó en el tema [Compilar esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="xs:string" />
        <xs:element name="LastName" type="tns:LastNameType" />
        <xs:element name="PhoneNumber">           <xs:simpleType>             <xs:restriction base="xs:string">               <xs:pattern value="\d{3}-\d{3}-\d(4)" />             </xs:restriction>           </xs:simpleType>         </xs:element>
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
</xs:schema>
```

### <a name="title-attribute-example"></a>Ejemplo del atributo Title

En este segundo ejemplo de código se agrega un nuevo atributo `Title` al elemento `FirstName` del esquema del cliente. En el primer ejemplo de código el tipo del elemento `FirstName` es `xs:string`. Para que el elemento `FirstName` tenga un atributo junto con contenido de cadena, se debe cambiar su tipo por un tipo complejo con un modelo de contenido de extensión de contenido simple.

El ejemplo de código edita el esquema del cliente en los siguientes pasos.

1. Agrega el esquema del cliente a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego lo compila. Cualquier error o advertencia de validación de esquemas que se encuentre durante la lectura o compilación del esquema se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.

2. Recupera el objeto <xref:System.Xml.Schema.XmlSchema> compilado desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Puesto que el esquema se compila, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.

3. Crea un nuevo tipo complejo del elemento `FirstName` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType>.

4. Crea una nueva extensión de contenido simple con un tipo base de `xs:string` utilizando las clases <xref:System.Xml.Schema.XmlSchemaSimpleContent> y <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.

5. Crea el nuevo atributo `Title` utilizando la clase <xref:System.Xml.Schema.XmlSchemaAttribute> con un <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> de `xs:string` y agrega el atributo a la extensión de contenido simple.

6. Establece el modelo de contenido del contenido simple en la extensión de contenido simple y el modelo de contenido del tipo simple en el contenido simple.

7. Agrega el nuevo tipo complejo a la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.

8. Itera por cada <xref:System.Xml.Schema.XmlSchemaObject> de la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.

> [!NOTE]
> Puesto que el elemento `FirstName` no es un elemento global del esquema, no está disponible en las colecciones <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> o <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>. El ejemplo de código localiza el elemento `FirstName`, localizando primero el elemento `Customer`.
>
> El primer ejemplo de código atravesó el esquema utilizando la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas. En este ejemplo se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas para atravesar el esquema. Aunque ambas colecciones proporcionan acceso a los elementos globales del esquema, la iteración por la colección <xref:System.Xml.Schema.XmlSchema.Items%2A> tarda más tiempo porque hay que iterar por todos los elementos globales del esquema y no tiene ninguna propiedad PSCI. Las colecciones PSCI (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, etc.) proporcionan acceso directo a sus elementos, atributos y tipos globales y a sus propiedades PSCI.

1. Si <xref:System.Xml.Schema.XmlSchemaObject> es un elemento, cuyo <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> es `"Customer"`, se obtiene el tipo complejo del elemento `Customer` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType> y la partícula de secuencia del tipo complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSequence>.

2. Itera por cada <xref:System.Xml.Schema.XmlSchemaParticle> de la colección <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.

3. Si <xref:System.Xml.Schema.XmlSchemaParticle> es un elemento, cuyo <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> es `"FirstName"`, establece el <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> del elemento `FirstName` en el nuevo tipo complejo `FirstName`.

4. Por último, vuelve a procesar y compilar el objeto <xref:System.Xml.Schema.XmlSchema> modificado utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> y <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de la clase <xref:System.Xml.Schema.XmlSchemaSet> y lo escribe en la consola.

Éste es el ejemplo de código completo.

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

A continuación se ofrece el esquema del cliente modificado que se creó en el tema [Compilar esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md).

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
        <xs:element name="LastName" type="tns:LastNameType" />
      </xs:sequence>
      <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" /
>
    </xs:complexType>
  </xs:element>
  <xs:simpleType name="LastNameType">
    <xs:restriction base="xs:string">
      <xs:maxLength value="20" />
    </xs:restriction>
  </xs:simpleType>
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a>Vea también

- [Información general sobre el Modelo de objetos de esquema XML](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Lectura y escritura de esquemas XML](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Compilación de esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Recorrido de esquemas XML](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [Inclusión o importación de esquemas XML](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Conjunto de información posterior a la compilación de esquemas](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
