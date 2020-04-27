---
title: Compilar esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 8a5ea56c-0140-4b51-8997-875ae6a8e0cb
ms.openlocfilehash: c921331b00fe137d4ad52d62951e8c161768dfae
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711147"
---
# <a name="building-xml-schemas"></a><span data-ttu-id="77739-102">Compilar esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77739-102">Building XML Schemas</span></span>
<span data-ttu-id="77739-103">Las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType> se asignan a las estructuras definidas en la recomendación de esquemas XML del W3C (World Wide Web Consortium) y se pueden utilizar para compilar esquemas XML en memoria.</span><span class="sxs-lookup"><span data-stu-id="77739-103">The classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation and can be used to build XML schemas in-memory.</span></span>  
  
## <a name="building-an-xml-schema"></a><span data-ttu-id="77739-104">Compilar un esquema XML</span><span class="sxs-lookup"><span data-stu-id="77739-104">Building an XML Schema</span></span>  
 <span data-ttu-id="77739-105">En el código de ejemplo que se incluye a continuación, la API del SOM se utiliza para compilar un esquema XML del cliente en memoria.</span><span class="sxs-lookup"><span data-stu-id="77739-105">In the code examples that follow, the SOM API is used to build a customer XML schema in-memory.</span></span>  
  
### <a name="creating-element-and-attributes"></a><span data-ttu-id="77739-106">Creación de elementos y atributos</span><span class="sxs-lookup"><span data-stu-id="77739-106">Creating Element and Attributes</span></span>  
 <span data-ttu-id="77739-107">En el código de ejemplo, se compila el esquema del cliente de abajo arriba, creando primero los elementos secundarios, atributos y sus tipos correspondientes y, a continuación, los elementos de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="77739-107">The code examples build the customer schema from the bottom up, creating the child elements, attributes, and their corresponding types first, and then the top-level elements.</span></span>  
  
 <span data-ttu-id="77739-108">En el siguiente código de ejemplo, se crean los elementos `FirstName` y `LastName`, así como el atributo `CustomerId` del esquema del cliente utilizando las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute> del SOM.</span><span class="sxs-lookup"><span data-stu-id="77739-108">In the following code example, the `FirstName` and `LastName` elements, as well as the `CustomerId` attribute of the customer schema are created using the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes of the SOM.</span></span> <span data-ttu-id="77739-109">Aparte de las propiedades <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute>, que se corresponden al atributo "name" de los elementos `<xs:element />` y `<xs:attribute />` de un esquema XML, todos los demás atributos que permite el esquema (`defaultValue`, `fixedValue`, `form`, etc.) tienen propiedades correspondientes en las clases <xref:System.Xml.Schema.XmlSchemaElement> y <xref:System.Xml.Schema.XmlSchemaAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77739-109">Apart from the <xref:System.Xml.Schema.XmlSchemaElement.Name%2A> properties of the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes, which correspond to the "name" attribute of the `<xs:element />` and `<xs:attribute />` elements in an XML schema, all other attributes allowed by the schema (`defaultValue`, `fixedValue`, `form`, and so on) have corresponding properties in the <xref:System.Xml.Schema.XmlSchemaElement> and <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#2)]
 [!code-csharp[XmlSchemaCreateExample#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#2)]
 [!code-vb[XmlSchemaCreateExample#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#2)]  
  
### <a name="creating-schema-types"></a><span data-ttu-id="77739-110">Creación de tipos de esquemas</span><span class="sxs-lookup"><span data-stu-id="77739-110">Creating Schema Types</span></span>  
 <span data-ttu-id="77739-111">El contenido de los elementos y atributos está definido por sus tipos.</span><span class="sxs-lookup"><span data-stu-id="77739-111">The content of elements and attributes is defined by their types.</span></span> <span data-ttu-id="77739-112">Para crear elementos y atributos cuyos tipos sean uno de los tipos de esquemas integrados, la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> se establece con el nombre completo correspondiente del tipo integrado utilizando la clase <xref:System.Xml.XmlQualifiedName>.</span><span class="sxs-lookup"><span data-stu-id="77739-112">To create elements and attributes whose types are one of the built-in schema types, the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes are set with the corresponding qualified name of the built-in type using the <xref:System.Xml.XmlQualifiedName> class.</span></span> <span data-ttu-id="77739-113">Para crear un tipo definido por el usuario para elementos y atributos, se crea un nuevo tipo simple o complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSimpleType> o <xref:System.Xml.Schema.XmlSchemaComplexType>.</span><span class="sxs-lookup"><span data-stu-id="77739-113">To create a user-defined type for elements and attributes, a new simple or complex type is created using the <xref:System.Xml.Schema.XmlSchemaSimpleType> or <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77739-114">Para crear tipos simples o complejos sin nombre que sean elementos secundarios anónimos de un elemento o atributo (para los atributos sólo se aplican tipos simples), establezca la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute> en el tipo simple o complejo sin nombre, en lugar de la propiedad <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> de las clases <xref:System.Xml.Schema.XmlSchemaElement> o <xref:System.Xml.Schema.XmlSchemaAttribute>.</span><span class="sxs-lookup"><span data-stu-id="77739-114">To create unnamed simple or complex types that are anonymous children of an element or attribute (only simple types apply for attributes), set the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes to the unnamed simple or complex type, instead of the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> property of the <xref:System.Xml.Schema.XmlSchemaElement> or <xref:System.Xml.Schema.XmlSchemaAttribute> classes.</span></span>  
  
 <span data-ttu-id="77739-115">Los esquemas XML permiten derivar por restricción tipos simples con nombre y anónimos de otros tipos simples (integrados o definidos por el usuario) o crearlos como una lista o unión de otros tipos simples.</span><span class="sxs-lookup"><span data-stu-id="77739-115">XML schemas allow both anonymous and named simple types to be derived by restriction from other simple types (built-in or user-defined) or constructed as a list or union of other simple types.</span></span> <span data-ttu-id="77739-116">La clase <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> se utiliza para crear un tipo simple restringiendo el tipo `xs:string` integrado.</span><span class="sxs-lookup"><span data-stu-id="77739-116">The <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> class is used to create a simple type by restricting the built-in `xs:string` type.</span></span> <span data-ttu-id="77739-117">Puede utilizar también las clases <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> o <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> para crear tipos de lista o unión.</span><span class="sxs-lookup"><span data-stu-id="77739-117">You can also use the <xref:System.Xml.Schema.XmlSchemaSimpleTypeList> or <xref:System.Xml.Schema.XmlSchemaSimpleTypeUnion> classes to create list or union types.</span></span> <span data-ttu-id="77739-118">La propiedad <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> indica si se trata de una unión, lista o restricción de tipo simple.</span><span class="sxs-lookup"><span data-stu-id="77739-118">The <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A?displayProperty=nameWithType> property denotes whether it is a simple type restriction, list, or union.</span></span>  
  
 <span data-ttu-id="77739-119">En el siguiente código de ejemplo, el tipo del elemento `FirstName` es el tipo integrado `xs:string`, el tipo del elemento `LastName` es un tipo simple con nombre que es una restricción del tipo integrado `xs:string`, con un valor de faceta `MaxLength` de 20 y el tipo del atributo `CustomerId` es el tipo integrado `xs:positiveInteger`.</span><span class="sxs-lookup"><span data-stu-id="77739-119">In the following code example, the `FirstName` element's type is the built-in type `xs:string`, the `LastName` element's type is a named simple type that is a restriction of the built-in type `xs:string`, with a `MaxLength` facet value of 20, and the `CustomerId` attribute's type is the built-in type `xs:positiveInteger`.</span></span> <span data-ttu-id="77739-120">El elemento `Customer` es un tipo complejo anónimo cuya partícula es la secuencia de los elementos `FirstName` y `LastName` y cuyos atributos contienen el atributo `CustomerId`.</span><span class="sxs-lookup"><span data-stu-id="77739-120">The `Customer` element is an anonymous complex type whose particle is the sequence of the `FirstName` and `LastName` elements and whose attributes contains the `CustomerId` attribute.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77739-121">También puede utilizar las clases <xref:System.Xml.Schema.XmlSchemaChoice> o <xref:System.Xml.Schema.XmlSchemaAll> como partícula del tipo complejo para replicar la semántica de `<xs:choice />` o `<xs:all />`.</span><span class="sxs-lookup"><span data-stu-id="77739-121">You can also use the <xref:System.Xml.Schema.XmlSchemaChoice> or <xref:System.Xml.Schema.XmlSchemaAll> classes as the particle of the complex type to replicate `<xs:choice />` or `<xs:all />` semantics.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#3](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#3)]
 [!code-csharp[XmlSchemaCreateExample#3](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#3)]
 [!code-vb[XmlSchemaCreateExample#3](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#3)]  
  
### <a name="creating-and-compiling-schemas"></a><span data-ttu-id="77739-122">Creación y compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="77739-122">Creating and Compiling Schemas</span></span>  
 <span data-ttu-id="77739-123">En este punto, los atributos y elementos secundarios, sus tipos correspondientes y el elemento `Customer` de nivel superior se han creado en memoria utilizando la API del SOM.</span><span class="sxs-lookup"><span data-stu-id="77739-123">At this point, the child elements and attributes, their corresponding types, and the top-level `Customer` element have been created in-memory using the SOM API.</span></span> <span data-ttu-id="77739-124">En el siguiente código de ejemplo, el elemento de esquema se crea utilizando la clase <xref:System.Xml.Schema.XmlSchema>, los tipos y elementos de nivel superior se agregan a él utilizando la propiedad <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> y el esquema completo se compila utilizando la clase <xref:System.Xml.Schema.XmlSchemaSet> y se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="77739-124">In the following code example, the schema element is created using the <xref:System.Xml.Schema.XmlSchema> class, the top-level elements and types are added to it using the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> property and the complete schema is compiled using the <xref:System.Xml.Schema.XmlSchemaSet> class and written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaCreateExample#4](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaCreateExample/CPP/XmlSchemaCreateExample.cpp#4)]
 [!code-csharp[XmlSchemaCreateExample#4](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaCreateExample/CS/XmlSchemaCreateExample.cs#4)]
 [!code-vb[XmlSchemaCreateExample#4](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaCreateExample/VB/XmlSchemaCreateExample.vb#4)]  
  
 <span data-ttu-id="77739-125">El método <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> valida el esquema del cliente con las reglas de un esquema XML y hace que las propiedades posteriores a la compilación del esquema estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="77739-125">The <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A?displayProperty=nameWithType> method validates the customer schema against the rules for an XML schema and makes post-schema-compilation properties available.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="77739-126">Todas las propiedades posteriores a la compilación del esquema de la API del SOM son diferentes a las del conjunto de información posterior a la validación del esquema.</span><span class="sxs-lookup"><span data-stu-id="77739-126">All post-schema-compilation properties in the SOM API differ from the Post-Schema-Validation-Infoset.</span></span>  
  
 <span data-ttu-id="77739-127">El <xref:System.Xml.Schema.ValidationEventHandler> que se agrega al <xref:System.Xml.Schema.XmlSchemaSet> es un delegado que llama al método de devolución de llamada `ValidationCallback` para controlar los errores y advertencias de validación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="77739-127">The <xref:System.Xml.Schema.ValidationEventHandler> added to the <xref:System.Xml.Schema.XmlSchemaSet> is a delegate that calls the callback method `ValidationCallback` to handle schema validation warnings and errors.</span></span>  
  
 <span data-ttu-id="77739-128">A continuación, se ofrece el código de ejemplo completo y el esquema del cliente escrito en la consola.</span><span class="sxs-lookup"><span data-stu-id="77739-128">The following is the complete code example, and the customer schema written to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77739-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="77739-129">See also</span></span>

- [<span data-ttu-id="77739-130">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="77739-130">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="77739-131">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77739-131">Reading and Writing XML Schemas</span></span>](../../../../docs/standard/data/xml/reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="77739-132">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77739-132">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="77739-133">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77739-133">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="77739-134">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="77739-134">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="77739-135">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="77739-135">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="77739-136">Conjunto de información posterior a la compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="77739-136">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
