---
title: Cómo atravesar esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: cce69574-5861-4a30-b730-2e18d915d8ee
ms.openlocfilehash: dbe02242f9bb8654e3f12d87b6ff6c2aea1f76b1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710120"
---
# <a name="traversing-xml-schemas"></a>Cómo atravesar esquemas XML

Al atravesar un esquema XML con la API del Modelo de objetos de esquema (SOM), se obtiene acceso a los elementos, atributos y tipos almacenados en el SOM. Atravesar un esquema XML cargado en el SOM es también el primer paso para editar un esquema XML utilizando la API del SOM.

## <a name="traversing-an-xml-schema"></a>Cómo atravesar un esquema XML

Las siguientes propiedades de la clase <xref:System.Xml.Schema.XmlSchema> proporcionan acceso a la colección de todos los elementos globales que se agregan al esquema XML.

|Propiedad.|Tipo de objeto almacenado en la colección o matriz|
|--------------|---------------------------------------------------|
|<xref:System.Xml.Schema.XmlSchema.Elements%2A>|<xref:System.Xml.Schema.XmlSchemaElement>|
|<xref:System.Xml.Schema.XmlSchema.Attributes%2A>|<xref:System.Xml.Schema.XmlSchemaAttribute>|
|<xref:System.Xml.Schema.XmlSchema.AttributeGroups%2A>|<xref:System.Xml.Schema.XmlSchemaAttributeGroup>|
|<xref:System.Xml.Schema.XmlSchema.Groups%2A>|<xref:System.Xml.Schema.XmlSchemaGroup>|
|<xref:System.Xml.Schema.XmlSchema.Includes%2A>|<xref:System.Xml.Schema.XmlSchemaExternal>, <xref:System.Xml.Schema.XmlSchemaInclude>, <xref:System.Xml.Schema.XmlSchemaImport> o <xref:System.Xml.Schema.XmlSchemaRedefine>|
|<xref:System.Xml.Schema.XmlSchema.Items%2A>|<xref:System.Xml.Schema.XmlSchemaObject> (proporciona acceso a todos los tipos, atributos y elementos de nivel globales).|
|<xref:System.Xml.Schema.XmlSchema.Notations%2A>|<xref:System.Xml.Schema.XmlSchemaNotation>|
|<xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A>|<xref:System.Xml.Schema.XmlSchemaType>, <xref:System.Xml.Schema.XmlSchemaSimpleType>, <xref:System.Xml.Schema.XmlSchemaComplexType>|
|<xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A>|<xref:System.Xml.XmlAttribute> (proporciona acceso a atributos que no pertenecen al espacio de nombres del esquema)|

> [!NOTE]
> Todas las propiedades que se enumeran en la tabla anterior, excepto la propiedad <xref:System.Xml.Schema.XmlSchema.Items%2A>, son propiedades del conjunto de información posterior a la compilación de esquemas que no están disponibles hasta que se ha compilado el esquema. La propiedad <xref:System.Xml.Schema.XmlSchema.Items%2A> es una propiedad anterior a la compilación del esquema que se puede utilizar antes de que se haya compilado el esquema para tener acceso y editar todos los tipos, atributos y elementos de nivel globales.
>
> La propiedad <xref:System.Xml.Schema.XmlSchema.UnhandledAttributes%2A> proporciona acceso a todos atributos que no pertenecen al espacio de nombres del esquema. El procesador de esquemas no procesa estos atributos.

En el código de ejemplo que se incluye a continuación se muestra cómo se atraviesa el esquema del cliente que se creó en el tema [Compilar esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md). El código de ejemplo muestra cómo se atraviesa el esquema utilizando las colecciones que se han descrito anteriormente y escribe todos los elementos y atributos del esquema en la consola.

El ejemplo atraviesa el esquema del cliente en los siguientes pasos.

1. Agrega el esquema del cliente a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego lo compila. Cualquier error o advertencia de validación de esquemas que se encuentre durante la lectura o compilación del esquema se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.

2. Recupera el objeto <xref:System.Xml.Schema.XmlSchema> compilado desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>. Puesto que el esquema se compila, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.

3. Itera por cada <xref:System.Xml.Schema.XmlSchemaElement> en la colección <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> de la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación del esquema escribiendo el nombre de cada elemento en la consola.

4. Obtiene el tipo complejo del elemento `Customer` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType>.

5. Si el tipo complejo tiene algún atributo, obtiene un <xref:System.Collections.IDictionaryEnumerator> para realizar la enumeración por cada <xref:System.Xml.Schema.XmlSchemaAttribute> y escribe su nombre en la consola.

6. Obtiene la partícula de secuencia del tipo complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSequence>.

7. Itera por cada <xref:System.Xml.Schema.XmlSchemaElement> de la colección <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> escribiendo el nombre de cada elemento secundario en la consola.

Éste es el ejemplo de código completo.

[!code-cpp[XmlSchemaTraverseExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaTraverseExample/CPP/XmlSchemaTraverseExample.cpp#1)]
[!code-csharp[XmlSchemaTraverseExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaTraverseExample/CS/XmlSchemaTraverseExample.cs#1)]
[!code-vb[XmlSchemaTraverseExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaTraverseExample/VB/XmlSchemaTraverseExample.vb#1)]

La propiedad <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A?displayProperty=nameWithType> puede ser <xref:System.Xml.Schema.XmlSchemaSimpleType> o <xref:System.Xml.Schema.XmlSchemaComplexType> si se trata de un tipo complejo o un tipo simple definido por el usuario. También puede ser <xref:System.Xml.Schema.XmlSchemaDatatype> si es uno de los tipos de datos integrados que se definen en la recomendación de esquemas XML del W3C. En el esquema del cliente, el <xref:System.Xml.Schema.XmlSchemaElement.ElementSchemaType%2A> del elemento `Customer` es <xref:System.Xml.Schema.XmlSchemaComplexType>, y los elementos `FirstName` y `LastName` son <xref:System.Xml.Schema.XmlSchemaSimpleType>.

El código de ejemplo del tema [Compilar esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md) utilizaba la colección <xref:System.Xml.Schema.XmlSchemaComplexType.Attributes%2A?displayProperty=nameWithType> para agregar el atributo `CustomerId` al elemento `Customer`. Se trata de una propiedad anterior a la compilación del esquema. La propiedad del conjunto de información posterior a la compilación del esquema correspondiente es la colección <xref:System.Xml.Schema.XmlSchemaComplexType.AttributeUses%2A?displayProperty=nameWithType>, que contiene todos los atributos del tipo complejo, incluyendo los que se heredan a través de la derivación de tipos.

## <a name="see-also"></a>Vea también

- [Información general sobre el Modelo de objetos de esquema XML](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [Lectura y escritura de esquemas XML](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [Compilación de esquemas XML](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [Edición de esquemas XML](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [Inclusión o importación de esquemas XML](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [XmlSchemaSet para compilación de esquemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Conjunto de información posterior a la compilación de esquemas](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
