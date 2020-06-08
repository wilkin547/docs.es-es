---
title: Compilar esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: adc1a10bb9acb14ee88589c13e28c49773e42100
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291596"
---
# <a name="building-xml-schemas"></a>Compilar esquemas XML
Las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> se asignan a las estructuras definidas en la recomendación de esquemas XML del W3C (World Wide Web Consortium) y se pueden utilizar para compilar esquemas XML en memoria.  
  
## <a name="building-an-xml-schema"></a>Compilar un esquema XML  
 En el código de ejemplo que se incluye a continuación, la API del SOM se utiliza para compilar un esquema XML del cliente en memoria.  
  
### <a name="creating-element-and-attributes"></a>Creación de elementos y atributos  
 En el código de ejemplo, se compila el esquema del cliente de abajo arriba, creando primero los elementos secundarios, atributos y sus tipos correspondientes y, a continuación, los elementos de nivel superior.  
  
 En el siguiente código de ejemplo, se crean los elementos `FirstName` y `LastName`, así como el atributo `CustomerId` del esquema del cliente utilizando las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute> del SOM. Aparte de las propiedades <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute>, que se corresponden al atributo "name" de los elementos `<xs:element />` y `<xs:attribute />` de un esquema XML, todos los demás atributos que permite el esquema (`defaultValue`, `fixedValue`, `form`, etc.) tienen propiedades correspondientes en las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute>.  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a>Creación de tipos de esquemas  
 El contenido de los elementos y atributos está definido por sus tipos. Para crear elementos y atributos cuyos tipos sean uno de los tipos de esquemas integrados, la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> se establece con el nombre completo correspondiente del tipo integrado utilizando la clase <xref:System.Xml.XmlQualifiedName>. Para crear un tipo definido por el usuario para elementos y atributos, se crea un nuevo tipo simple o complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSimpleType> o <xref:System.Xml.Schema.XmlSchemaComplexType>.  
  
> [!NOTE]
> Para crear tipos simples o complejos sin nombre que sean elementos secundarios anónimos de un elemento o atributo (para los atributos sólo se aplican tipos simples), establezca la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> en el tipo simple o complejo sin nombre, en lugar de la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute>.  
  
 Los esquemas XML permiten derivar por restricción tipos simples con nombre y anónimos de otros tipos simples (integrados o definidos por el usuario) o crearlos como una lista o unión de otros tipos simples. La clase <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> se utiliza para crear un tipo simple restringiendo el tipo `xs:string` integrado. Puede utilizar también las clases <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> o <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> para crear tipos de lista o unión. La propiedad <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> indica si se trata de una unión, lista o restricción de tipo simple.  
  
 En el siguiente código de ejemplo, el tipo del elemento `FirstName` es el tipo integrado `xs:string`, el tipo del elemento `LastName` es un tipo simple con nombre que es una restricción del tipo integrado `xs:string`, con un valor de faceta `MaxLength` de 20 y el tipo del atributo `CustomerId` es el tipo integrado `xs:positiveInteger`. El elemento `Customer` es un tipo complejo anónimo cuya partícula es la secuencia de los elementos `FirstName` y `LastName` y cuyos atributos contienen el atributo `CustomerId`.  
  
> [!NOTE]
> También puede utilizar las clases <xref:System.Xml.Schema.XmlSchemaChoice> o <xref:System.Xml.Schema.XmlSchemaAll> como partícula del tipo complejo para replicar la semántica de `<xs:choice />` o `<xs:all />`.  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a>Creación y compilación de esquemas  
 En este punto, los atributos y elementos secundarios, sus tipos correspondientes y el elemento `Customer` de nivel superior se han creado en memoria utilizando la API del SOM. En el siguiente código de ejemplo, el elemento de esquema se crea utilizando la clase <xref:System.Xml.Schema.XmlSchema>, los tipos y elementos de nivel superior se agregan a él utilizando la propiedad <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> y el esquema completo se compila utilizando la clase <xref:System.Xml.Schema.XmlSchemaSet> y se escribe en la consola.  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 El método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> valida el esquema del cliente con las reglas de un esquema XML y hace que las propiedades posteriores a la compilación del esquema estén disponibles.  
  
> [!NOTE]
> Todas las propiedades posteriores a la compilación del esquema de la API del SOM son diferentes a las del conjunto de información posterior a la validación del esquema.  
  
 El <xref:System.Xml.Schema.ValidationEventHandler> que se agrega al <xref:System.Xml.Schema.XmlSchemaSet> es un delegado que llama al método de devolución de llamada `ValidationCallback` para controlar los errores y advertencias de validación de esquemas.  
  
 A continuación, se ofrece el código de ejemplo completo y el esquema del cliente escrito en la consola.  
  
 [!code-cpp[XmlSchemaCreateExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#1)]
 [!code-csharp[XmlSchemaCreateExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#1)]
 [!code-vb[XmlSchemaCreateExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
   <xs:element name="Customer">  
      <xs:complexType>  
         <xs:sequence>  
            <xs:element name="FirstName" type="xs:string" />  
            <xs:element name="LastName" type="tns:LastNameType" />  
         </xs:sequence>  
         <xs:attribute name="CustomerId" type="xs:positiveInteger" use="required" />  
      </xs:complexType>  
   </xs:element>  
   <xs:simpleType name="LastNameType">  
      <xs:restriction base="xs:string">  
         <xs:maxLength value="20" />  
      </xs:restriction>  
   </xs:simpleType>  
</xs:schema>  
```  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el Modelo de objetos de esquema XML](xml-schema-object-model-overview.md)
- [Lectura y escritura de esquemas XML](reading-and-writing-xml-schemas.md)
- [Recorrido de esquemas XML](traversing-xml-schemas.md)
- [Edición de esquemas XML](editing-xml-schemas.md)
- [Inclusión o importación de esquemas XML](including-or-importing-xml-schemas.md)
- [XmlSchemaSet para compilación de esquemas](xmlschemaset-for-schema-compilation.md)
- [Conjunto de información posterior a la compilación de esquemas](post-schema-compilation-infoset.md)
