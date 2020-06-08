---
title: Inclusión o importación de esquemas XML
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: fe1b4a11-37f4-4e1a-93c9-239f4fe736c0
ms.openlocfilehash: f6c2829d45db147c81592c00710f04168b40679e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287706"
---
# <a name="including-or-importing-xml-schemas"></a><span data-ttu-id="beabb-102">Inclusión o importación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="beabb-102">Including or Importing XML Schemas</span></span>
<span data-ttu-id="beabb-103">Un esquema XML puede contener elementos `<xs:import />`, `<xs:include />` y `<xs:redefine />`.</span><span class="sxs-lookup"><span data-stu-id="beabb-103">An XML schema may contain `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements.</span></span> <span data-ttu-id="beabb-104">Estos elementos de esquema hacen referencia a otros esquemas XML que se pueden utilizar para complementar la estructura del esquema que los incluye o importa.</span><span class="sxs-lookup"><span data-stu-id="beabb-104">These schema elements refer to other XML schemas that can be used to supplement the structure of the schema that includes or imports them.</span></span> <span data-ttu-id="beabb-105">Las clases <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> y <xref:System.Xml.Schema.XmlSchemaRedefine> se asignan estos elementos en la API del modelo de objetos de esquema (SOM).</span><span class="sxs-lookup"><span data-stu-id="beabb-105">The <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, map to these elements in the Schema Object Model (SOM) API.</span></span>  
  
## <a name="including-or-importing-an-xml-schema"></a><span data-ttu-id="beabb-106">Inclusión o importación de un esquema XML</span><span class="sxs-lookup"><span data-stu-id="beabb-106">Including or Importing an XML Schema</span></span>  
 <span data-ttu-id="beabb-107">En el siguiente ejemplo de código se complementa el esquema del cliente que se creó en el tema [Compilar esquemas XML](building-xml-schemas.md) con el esquema de direcciones.</span><span class="sxs-lookup"><span data-stu-id="beabb-107">The following code example supplements the customer schema created in the [Building XML Schemas](building-xml-schemas.md) topic with the address schema.</span></span> <span data-ttu-id="beabb-108">Al complementar el esquema del cliente con el esquema de direcciones, los tipos de direcciones están disponibles en el esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="beabb-108">Supplementing the customer schema with the address schema makes address types available in the customer schema.</span></span>  
  
 <span data-ttu-id="beabb-109">El esquema de direcciones se puede incorporar utilizando los elementos `<xs:include />` o `<xs:import />` para utilizar los componentes del esquema de direcciones tal y como están, o utilizando un elemento `<xs:redefine />` para modificar cualquiera de sus componentes con el fin de satisfacer la necesidad del esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="beabb-109">The address schema can be incorporated using either `<xs:include />` or `<xs:import />` elements to use the components of the address schema as-is, or using an `<xs:redefine />` element to modify any of its components to suit the need of the customer schema.</span></span> <span data-ttu-id="beabb-110">Puesto que el esquema de direcciones tiene un `targetNamespace` que es diferente del que tiene el esquema del cliente, se utiliza el elemento `<xs:import />` y, por tanto, la semántica de importación.</span><span class="sxs-lookup"><span data-stu-id="beabb-110">Because the address schema has a `targetNamespace` that is different from that of the customer schema, the `<xs:import />` element and therefore import semantics is used.</span></span>  
  
 <span data-ttu-id="beabb-111">El código de ejemplo incluye el esquema de direcciones en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="beabb-111">The code example includes the address schema in the following steps.</span></span>  
  
1. <span data-ttu-id="beabb-112">Agrega el esquema del cliente y el esquema de direcciones a un objeto <xref:System.Xml.Schema.XmlSchemaSet> nuevo y luego los compila.</span><span class="sxs-lookup"><span data-stu-id="beabb-112">Adds the customer schema and the address schema to a new <xref:System.Xml.Schema.XmlSchemaSet> object and then compiles them.</span></span> <span data-ttu-id="beabb-113">Cualquier error y advertencia de validación de esquemas que se encuentre durante la lectura o compilación de los esquemas se controla por medio del delegado <xref:System.Xml.Schema.ValidationEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="beabb-113">Any schema validation warnings and errors encountered reading or compiling the schemas are handled by the <xref:System.Xml.Schema.ValidationEventHandler> delegate.</span></span>  
  
2. <span data-ttu-id="beabb-114">Recupera los objetos <xref:System.Xml.Schema.XmlSchema> compilados para los esquemas del cliente y de direcciones desde <xref:System.Xml.Schema.XmlSchemaSet> iterando por la propiedad <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A>.</span><span class="sxs-lookup"><span data-stu-id="beabb-114">Retrieves the compiled <xref:System.Xml.Schema.XmlSchema> objects for both the customer and address schemas from the <xref:System.Xml.Schema.XmlSchemaSet> by iterating over the <xref:System.Xml.Schema.XmlSchemaSet.Schemas%2A> property.</span></span> <span data-ttu-id="beabb-115">Puesto que los esquemas se compilan, las propiedades del conjunto de información posterior a la compilación del esquema son accesibles.</span><span class="sxs-lookup"><span data-stu-id="beabb-115">Because the schemas are compiled, Post-Schema-Compilation-Infoset (PSCI) properties are accessible.</span></span>  
  
3. <span data-ttu-id="beabb-116">Crea un objeto <xref:System.Xml.Schema.XmlSchemaImport>, establece la propiedad <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> de la importación en el espacio de nombres del esquema de direcciones, establece la propiedad <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> de la importación en el objeto <xref:System.Xml.Schema.XmlSchema> del esquema de direcciones y agrega la importación a la propiedad <xref:System.Xml.Schema.XmlSchema.Includes%2A> del esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="beabb-116">Creates an <xref:System.Xml.Schema.XmlSchemaImport> object, sets the <xref:System.Xml.Schema.XmlSchemaImport.Namespace%2A> property of the import to the namespace of the address schema, sets the <xref:System.Xml.Schema.XmlSchemaExternal.Schema%2A> property of the import to the <xref:System.Xml.Schema.XmlSchema> object of the address schema, and adds the import to the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span>  
  
4. <span data-ttu-id="beabb-117">Vuelve a procesar y compilar el objeto <xref:System.Xml.Schema.XmlSchema> modificado del esquema del cliente utilizando los métodos <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> y <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> de la clase <xref:System.Xml.Schema.XmlSchemaSet> y lo escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="beabb-117">Reprocesses and compiles the modified <xref:System.Xml.Schema.XmlSchema> object of the customer schema using the <xref:System.Xml.Schema.XmlSchemaSet.Reprocess%2A> and <xref:System.Xml.Schema.XmlSchemaSet.Compile%2A> methods of the <xref:System.Xml.Schema.XmlSchemaSet> class and writes it to the console.</span></span>  
  
5. <span data-ttu-id="beabb-118">Por último, escribe de forma recursiva en la consola todos los esquemas importados al esquema del cliente utilizando la propiedad <xref:System.Xml.Schema.XmlSchema.Includes%2A> del esquema del cliente.</span><span class="sxs-lookup"><span data-stu-id="beabb-118">Finally, recursively writes all of the schemas imported into the customer schema to the console using the <xref:System.Xml.Schema.XmlSchema.Includes%2A> property of the customer schema.</span></span> <span data-ttu-id="beabb-119">La propiedad <xref:System.Xml.Schema.XmlSchema.Includes%2A> proporciona acceso a todas las inclusiones, importaciones o redefiniciones agregadas a un esquema.</span><span class="sxs-lookup"><span data-stu-id="beabb-119">The <xref:System.Xml.Schema.XmlSchema.Includes%2A> property provides access to all the includes, imports, or redefines added to a schema.</span></span>  
  
 <span data-ttu-id="beabb-120">A continuación se ofrece el código de ejemplo completo y los esquemas de direcciones y del cliente escritos en la consola.</span><span class="sxs-lookup"><span data-stu-id="beabb-120">The following is the complete code example and the customer and address schemas written to the console.</span></span>  
  
 [!code-cpp[XmlSchemaImportExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaImportExample/CPP/XmlSchemaImportExample.cpp#1)]
 [!code-csharp[XmlSchemaImportExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaImportExample/CS/XmlSchemaImportExample.cs#1)]
 [!code-vb[XmlSchemaImportExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaImportExample/VB/XmlSchemaImportExample.vb#1)]  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema xmlns:tns="http://www.tempuri.org" targetNamespace="http://www.tempuri.org" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:import namespace="http://www.example.com/IPO" />  
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
<schema targetNamespace="http://www.example.com/IPO" xmlns="http://www.w3.org/2001/XMLSchema" xmlns:ipo="http://www.example.com/IPO">  
  <annotation>  
    <documentation xml:lang="en">  
      Addresses for International Purchase order schema  
      Copyright 2000 Example.com. All rights reserved.  
    </documentation>  
  </annotation>  
  <complexType name="Address">  
    <sequence>  
      <element name="name"   type="string"/>  
      <element name="street" type="string"/>  
      <element name="city"   type="string"/>  
    </sequence>  
  </complexType>  
  <complexType name="USAddress">  
    <complexContent>  
      <extension base="ipo:Address">  
        <sequence>  
          <element name="state" type="ipo:USState"/>  
          <element name="zip"   type="positiveInteger"/>  
        </sequence>  
      </extension>  
    </complexContent>  
  </complexType>  
  <!-- other Address derivations for more countries or regions -->  
  <simpleType name="USState">  
    <restriction base="string">  
      <enumeration value="AK"/>  
      <enumeration value="AL"/>  
      <enumeration value="AR"/>  
      <!-- and so on ... -->  
    </restriction>  
  </simpleType>  
</schema>  
```  
  
 <span data-ttu-id="beabb-121">Para obtener más información sobre los elementos `<xs:import />`, `<xs:include />` y `<xs:redefine />`, y sobre las clases <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> y <xref:System.Xml.Schema.XmlSchemaRedefine>, vea [W3C XML Schema](https://www.w3.org/XML/Schema) y la documentación de referencia sobre las clases del espacio de nombres <xref:System.Xml.Schema?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="beabb-121">For more information about the `<xs:import />`, `<xs:include />`, and `<xs:redefine />` elements and the <xref:System.Xml.Schema.XmlSchemaImport>, <xref:System.Xml.Schema.XmlSchemaInclude> and <xref:System.Xml.Schema.XmlSchemaRedefine> classes, see the [W3C XML Schema](https://www.w3.org/XML/Schema) and the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace class reference documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beabb-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="beabb-122">See also</span></span>

- [<span data-ttu-id="beabb-123">Información general sobre el Modelo de objetos de esquema XML</span><span class="sxs-lookup"><span data-stu-id="beabb-123">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="beabb-124">Lectura y escritura de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="beabb-124">Reading and Writing XML Schemas</span></span>](reading-and-writing-xml-schemas.md)
- [<span data-ttu-id="beabb-125">Compilación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="beabb-125">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="beabb-126">Recorrido de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="beabb-126">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="beabb-127">Edición de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="beabb-127">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="beabb-128">XmlSchemaSet para compilación de esquemas</span><span class="sxs-lookup"><span data-stu-id="beabb-128">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
