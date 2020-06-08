---
title: Edición de esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fa09c8e5-c2b9-49d2-bb0d-40330cd13e4d
ms.openlocfilehash: b309c390ede3afc38122188337fa0dc3336e3ad5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84292064"
---
# <a name="editing-xml-schemas"></a><span data-ttu-id="c63e8-102">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-102">Editing XML Schemas</span></span>

<span data-ttu-id="c63e8-103">La edición de un esquema XML es una de las características más importantes del Modelo de objetos de esquema (SOM).</span><span class="sxs-lookup"><span data-stu-id="c63e8-103">Editing an XML schema is one of the most important features of the Schema Object Model (SOM).</span></span> <span data-ttu-id="c63e8-104">Se pueden utilizar todas las propiedades previas a la compilación de esquemas del SOM para cambiar los valores existentes de un esquema XML.</span><span class="sxs-lookup"><span data-stu-id="c63e8-104">All of the pre-schema-compilation properties of the SOM can be used to change the existing values in an XML schema.</span></span> <span data-ttu-id="c63e8-105">Luego, el esquema XML se puede recompilar para reflejar los cambios.</span><span class="sxs-lookup"><span data-stu-id="c63e8-105">The XML schema can then be recompiled to reflect the changes.</span></span>

<span data-ttu-id="c63e8-106">El primer paso para editar un esquema cargado en el SOM consiste en atravesar el esquema.</span><span class="sxs-lookup"><span data-stu-id="c63e8-106">The first step in editing a schema loaded into the SOM is to traverse the schema.</span></span> <span data-ttu-id="c63e8-107">Debería familiarizarse con el proceso de atravesar un esquema utilizando la API del SOM antes de intentar editar un esquema.</span><span class="sxs-lookup"><span data-stu-id="c63e8-107">You should be familiar with traversing a schema using the SOM API before you attempt to edit a schema.</span></span> <span data-ttu-id="c63e8-108">También debería familiarizarse con las propiedades posteriores y anteriores a la compilación de esquemas del conjunto de información posterior a la compilación de esquemas (PSCI).</span><span class="sxs-lookup"><span data-stu-id="c63e8-108">You should also be familiar with the pre- and post-schema-compilation properties of the Post-Schema-Compilation-Infoset (PSCI).</span></span>

## <a name="editing-an-xml-schema"></a><span data-ttu-id="c63e8-109">Edición de un esquema XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-109">Editing an XML Schema</span></span>

<span data-ttu-id="c63e8-110">En esta sección se incluyen dos ejemplos de código que editan el esquema del cliente que se creó en el tema [Compilar esquemas XML](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c63e8-110">In this section, two code examples are provided, both of which edit the customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span> <span data-ttu-id="c63e8-111">En el primer ejemplo de código se agrega un nuevo elemento `PhoneNumber` al elemento `Customer` y, en el segundo, se agrega un nuevo atributo `Title` al elemento `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="c63e8-111">The first code example adds a new `PhoneNumber` element to the `Customer` element and the second code example adds a new `Title` attribute to the `FirstName` element.</span></span> <span data-ttu-id="c63e8-112">En el primer ejemplo también se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas como medio para atravesar el esquema del cliente, mientras que en el segundo ejemplo se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-112">The first sample also uses the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection as the means of traversing the customer schema while the second code example uses the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

### <a name="phonenumber-element-example"></a><span data-ttu-id="c63e8-113">Ejemplo del elemento PhoneNumber</span><span class="sxs-lookup"><span data-stu-id="c63e8-113">PhoneNumber Element Example</span></span>

<span data-ttu-id="c63e8-114">En el primer ejemplo de código se agrega un nuevo elemento `PhoneNumber` al elemento `Customer` del esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="c63e8-114">This first code example adds a new `PhoneNumber` element to the `Customer` element of the customer schema.</span></span> <span data-ttu-id="c63e8-115">El ejemplo de código edita el esquema del cliente en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c63e8-115">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="c63e8-116">Agrega el esquema del cliente a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego lo compila.</span><span class="sxs-lookup"><span data-stu-id="c63e8-116">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="c63e8-117">Cualquier error o advertencia de validación de esquemas que se encuentre durante la lectura o compilación del esquema se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-117">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="c63e8-118">Recupera el objeto <xref:System.Xml.Schema.XmlSchema> compilado desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-118">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="c63e8-119">Puesto que el esquema se compila, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.</span><span class="sxs-lookup"><span data-stu-id="c63e8-119">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="c63e8-120">Crea el elemento `PhoneNumber` utilizando la clase <xref:System.Xml.Schema.XmlSchemaElement>, la restricción de tipos simples `xs:string` utilizando las clases <xref:System.Xml.Schema.XmlSchemaSimpleType> y <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction>, agrega una faceta de patrón a la propiedad <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> de la restricción, y agrega la restricción a la propiedad <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> del tipo simple y el tipo simple al <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> del elemento `PhoneNumber`.</span><span class="sxs-lookup"><span data-stu-id="c63e8-120">Creates the `PhoneNumber` element using the <xref:System.Xml.Schema.XmlSchemaElement> class, the `xs:string` simple type restriction using the <xref:System.Xml.Schema.XmlSchemaSimpleType> and <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction> classes, adds a pattern facet to the <xref:System.Xml.Schema.XmlSchemaSimpleTypeRestriction.Facets%2A> property of the restriction, and adds the restriction to the <xref:System.Xml.Schema.XmlSchemaSimpleType.Content%2A> property of the simple type and the simple type to the <xref:System.Xml.Schema.XmlSchemaElement.SchemaType%2A> of the `PhoneNumber` element.</span></span>

4. <span data-ttu-id="c63e8-121">Itera por cada <xref:System.Xml.Schema.XmlSchemaElement> de la colección <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> de la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-121">Iterates over each <xref:System.Xml.Schema.XmlSchemaElement> in the <xref:System.Xml.Schema.XmlSchemaObjectTable.Values%2A> collection of the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span>

5. <span data-ttu-id="c63e8-122">Si el <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> del elemento es `"Customer"`, se obtiene el tipo complejo del elemento `Customer` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType> y la partícula de secuencia del tipo complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-122">If the <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> of the element is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

6. <span data-ttu-id="c63e8-123">Agrega el nuevo elemento `PhoneNumber` a la secuencia que contiene los elementos `FirstName` y `LastName` existentes utilizando la colección <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> previa a la compilación de esquemas de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="c63e8-123">Adds the new `PhoneNumber` element to the sequence containing the existing `FirstName` and `LastName` elements using the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A> collection of the sequence.</span></span>

7. <span data-ttu-id="c63e8-124">Por último, vuelve a procesar y compilar el objeto <xref:System.Xml.Schema.XmlSchema> modificado utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> y <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de la clase <xref:System.Xml.Schema.XmlSchemaSet> y lo escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="c63e8-124">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="c63e8-125">Éste es el ejemplo de código completo.</span><span class="sxs-lookup"><span data-stu-id="c63e8-125">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample1#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample1/CPP/XmlSchemaEditExample1.cpp#1)]
[!code-csharp[XmlSchemaEditExample1#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample1/CS/XmlSchemaEditExample1.cs#1)]
[!code-vb[XmlSchemaEditExample1#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample1/VB/XmlSchemaEditExample1.vb#1)]

<span data-ttu-id="c63e8-126">A continuación se ofrece el esquema del cliente modificado que se creó en el tema [Compilar esquemas XML](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c63e8-126">The following is the modified customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span>

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

### <a name="title-attribute-example"></a><span data-ttu-id="c63e8-127">Ejemplo del atributo Title</span><span class="sxs-lookup"><span data-stu-id="c63e8-127">Title Attribute Example</span></span>

<span data-ttu-id="c63e8-128">En este segundo ejemplo de código se agrega un nuevo atributo `Title` al elemento `FirstName` del esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="c63e8-128">This second code example, adds a new `Title` attribute to the `FirstName` element of the customer schema.</span></span> <span data-ttu-id="c63e8-129">En el primer ejemplo de código el tipo del elemento `FirstName` es `xs:string`.</span><span class="sxs-lookup"><span data-stu-id="c63e8-129">In the first code example, the type of the `FirstName` element is `xs:string`.</span></span> <span data-ttu-id="c63e8-130">Para que el elemento `FirstName` tenga un atributo junto con contenido de cadena, se debe cambiar su tipo por un tipo complejo con un modelo de contenido de extensión de contenido simple.</span><span class="sxs-lookup"><span data-stu-id="c63e8-130">For the `FirstName` element to have an attribute along with string content, its type must be changed to a complex type with a simple content extension content model.</span></span>

<span data-ttu-id="c63e8-131">El ejemplo de código edita el esquema del cliente en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="c63e8-131">The code example edits the customer schema in the following steps.</span></span>

1. <span data-ttu-id="c63e8-132">Agrega el esquema del cliente a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego lo compila.</span><span class="sxs-lookup"><span data-stu-id="c63e8-132">Adds the customer schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles it.</span></span> <span data-ttu-id="c63e8-133">Cualquier error o advertencia de validación de esquemas que se encuentre durante la lectura o compilación del esquema se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-133">Any schema validation warnings and errors encountered reading or compiling the schema are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>

2. <span data-ttu-id="c63e8-134">Recupera el objeto <xref:System.Xml.Schema.XmlSchema> compilado desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-134">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> object from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="c63e8-135">Puesto que el esquema se compila, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.</span><span class="sxs-lookup"><span data-stu-id="c63e8-135">Because the schema is compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>

3. <span data-ttu-id="c63e8-136">Crea un nuevo tipo complejo del elemento `FirstName` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-136">Creates a new complex type for the `FirstName` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class.</span></span>

4. <span data-ttu-id="c63e8-137">Crea una nueva extensión de contenido simple con un tipo base de `xs:string` utilizando las clases <xref:System.Xml.Schema.XmlSchemaSimpleContent> y <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-137">Creates a new simple content extension, with a base type of `xs:string`, using the <xref:System.Xml.Schema.XmlSchemaSimpleContent> and <xref:System.Xml.Schema.XmlSchemaSimpleContentExtension> classes.</span></span>

5. <span data-ttu-id="c63e8-138">Crea el nuevo atributo `Title` utilizando la clase <xref:System.Xml.Schema.XmlSchemaAttribute> con un <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> de `xs:string` y agrega el atributo a la extensión de contenido simple.</span><span class="sxs-lookup"><span data-stu-id="c63e8-138">Creates the new `Title` attribute using the <xref:System.Xml.Schema.XmlSchemaAttribute> class, with a <xref:System.Xml.Schema.XmlSchemaAttribute.SchemaTypeName%2A> of `xs:string` and adds the attribute to the simple content extension.</span></span>

6. <span data-ttu-id="c63e8-139">Establece el modelo de contenido del contenido simple en la extensión de contenido simple y el modelo de contenido del tipo simple en el contenido simple.</span><span class="sxs-lookup"><span data-stu-id="c63e8-139">Sets the content model of the simple content to the simple content extension and the content model of the complex type to the simple content.</span></span>

7. <span data-ttu-id="c63e8-140">Agrega el nuevo tipo complejo a la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-140">Adds the new complex type to the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

8. <span data-ttu-id="c63e8-141">Itera por cada <xref:System.Xml.Schema.XmlSchemaObject> de la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-141">Iterates over each <xref:System.Xml.Schema.XmlSchemaObject> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection.</span></span>

> [!NOTE]
> <span data-ttu-id="c63e8-142">Puesto que el elemento `FirstName` no es un elemento global del esquema, no está disponible en las colecciones <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> o <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-142">Because the `FirstName` element is not a global element in the schema, it is not available in the <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> or <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collections.</span></span> <span data-ttu-id="c63e8-143">El ejemplo de código localiza el elemento `FirstName`, localizando primero el elemento `Customer`.</span><span class="sxs-lookup"><span data-stu-id="c63e8-143">The code example locates the `FirstName` element by first locating the `Customer` element.</span></span>
>
> <span data-ttu-id="c63e8-144">El primer ejemplo de código atravesó el esquema utilizando la colección <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> posterior a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-144">The first code example traversed the schema using the post-schema-compilation <xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType> collection.</span></span> <span data-ttu-id="c63e8-145">En este ejemplo se utiliza la colección <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas para atravesar el esquema.</span><span class="sxs-lookup"><span data-stu-id="c63e8-145">In this sample, the pre-schema-compilation <xref:System.Xml.Schema.XmlSchema.Items%2A?displayProperty=nameWithType> collection is used to traverse the schema.</span></span> <span data-ttu-id="c63e8-146">Aunque ambas colecciones proporcionan acceso a los elementos globales del esquema, la iteración por la colección <xref:System.Xml.Schema.XmlSchema.Items%2A> tarda más tiempo porque hay que iterar por todos los elementos globales del esquema y no tiene ninguna propiedad PSCI.</span><span class="sxs-lookup"><span data-stu-id="c63e8-146">While both collections provide access to the global elements in the schema, iterating through the <xref:System.Xml.Schema.XmlSchema.Items%2A> collection is more time consuming because you must iterate over all global elements in the schema and it does not have any PSCI properties.</span></span> <span data-ttu-id="c63e8-147">Las colecciones PSCI (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, etc.) proporcionan acceso directo a sus elementos, atributos y tipos globales y a sus propiedades PSCI.</span><span class="sxs-lookup"><span data-stu-id="c63e8-147">The PSCI collections (<xref:System.Xml.Schema.XmlSchema.Elements%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.Attributes%2A?displayProperty=nameWithType>, <xref:System.Xml.Schema.XmlSchema.SchemaTypes%2A?displayProperty=nameWithType>, and so on) provide direct access to their global elements, attributes, and types and their PSCI properties.</span></span>

1. <span data-ttu-id="c63e8-148">Si <xref:System.Xml.Schema.XmlSchemaObject> es un elemento, cuyo <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> es `"Customer"`, se obtiene el tipo complejo del elemento `Customer` utilizando la clase <xref:System.Xml.Schema.XmlSchemaComplexType> y la partícula de secuencia del tipo complejo utilizando la clase <xref:System.Xml.Schema.XmlSchemaSequence>.</span><span class="sxs-lookup"><span data-stu-id="c63e8-148">If the <xref:System.Xml.Schema.XmlSchemaObject> is an element, whose <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"Customer"`, gets the complex type of the `Customer` element using the <xref:System.Xml.Schema.XmlSchemaComplexType> class and the sequence particle of the complex type using the <xref:System.Xml.Schema.XmlSchemaSequence> class.</span></span>

2. <span data-ttu-id="c63e8-149">Itera por cada <xref:System.Xml.Schema.XmlSchemaParticle> de la colección <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> previa a la compilación de esquemas.</span><span class="sxs-lookup"><span data-stu-id="c63e8-149">Iterates over each <xref:System.Xml.Schema.XmlSchemaParticle> in the pre-schema-compilation <xref:System.Xml.Schema.XmlSchemaSequence.Items%2A?displayProperty=nameWithType> collection.</span></span>

3. <span data-ttu-id="c63e8-150">Si <xref:System.Xml.Schema.XmlSchemaParticle> es un elemento, cuyo <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> es `"FirstName"`, establece el <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> del elemento `FirstName` en el nuevo tipo complejo `FirstName`.</span><span class="sxs-lookup"><span data-stu-id="c63e8-150">If the <xref:System.Xml.Schema.XmlSchemaParticle> is an element, who's <xref:System.Xml.Schema.XmlSchemaElement.QualifiedName%2A> is `"FirstName"`, sets the <xref:System.Xml.Schema.XmlSchemaElement.SchemaTypeName%2A> of the `FirstName` element to the new `FirstName` complex type.</span></span>

4. <span data-ttu-id="c63e8-151">Por último, vuelve a procesar y compilar el objeto <xref:System.Xml.Schema.XmlSchema> modificado utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> y <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de la clase <xref:System.Xml.Schema.XmlSchemaSet> y lo escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="c63e8-151">Finally, reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>

<span data-ttu-id="c63e8-152">Éste es el ejemplo de código completo.</span><span class="sxs-lookup"><span data-stu-id="c63e8-152">The following is the complete code example.</span></span>

[!code-cpp[XmlSchemaEditExample2#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaEditExample2/CPP/XmlSchemaEditExample2.cpp#1)]
[!code-csharp[XmlSchemaEditExample2#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaEditExample2/CS/XmlSchemaEditExample2.cs#1)]
[!code-vb[XmlSchemaEditExample2#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaEditExample2/VB/XmlSchemaEditExample2.vb#1)]

<span data-ttu-id="c63e8-153">A continuación se ofrece el esquema del cliente modificado que se creó en el tema [Compilar esquemas XML](building-xml-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="c63e8-153">The following is the modified customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic.</span></span>

```xml
<?xml version="1.0" encoding=" utf-8"?>
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:element name="Customer">
    <xs:complexType>
      <xs:sequence>
        <xs:element name="FirstName" type="tns:FirstNameComplexType" />
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
  <xs:complexType name="FirstNameComplexType">     <xs:simpleContent>       <xs:extension base="xs:string">         <xs:attribute name="Title" type="xs:string" />       </xs:extension>     </xs:simpleContent>   </xs:complexType>
</xs:schema>
```

## <a name="see-also"></a><span data-ttu-id="c63e8-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="c63e8-154">See also</span></span>

- [<span data-ttu-id="c63e8-155">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-155">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="c63e8-156">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-156">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="c63e8-157">Compilación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-157">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="c63e8-158">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-158">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="c63e8-159">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="c63e8-159">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="c63e8-160">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="c63e8-160">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="c63e8-161">Conjunto de información posterior a la compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="c63e8-161">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
