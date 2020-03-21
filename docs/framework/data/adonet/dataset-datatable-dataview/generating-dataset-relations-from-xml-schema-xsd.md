---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: feb0be7f66bf0f407e54ef0830c13f0c4a8a6418
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151135"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="e95f9-102">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="e95f9-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="e95f9-103">En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria.</span><span class="sxs-lookup"><span data-stu-id="e95f9-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="e95f9-104">Hay tres maneras de representar una relación **DataSet** dentro de un esquema de lenguaje de definición de esquemas XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="e95f9-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
- <span data-ttu-id="e95f9-105">Especificar tipos complejos anidados.</span><span class="sxs-lookup"><span data-stu-id="e95f9-105">Specify nested complex types.</span></span>  
  
- <span data-ttu-id="e95f9-106">Utilice la anotación **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="e95f9-106">Use the **msdata:Relationship** annotation.</span></span>  
  
- <span data-ttu-id="e95f9-107">Especifique un **xs:keyref** sin la anotación **msdata:ConstraintOnly.**</span><span class="sxs-lookup"><span data-stu-id="e95f9-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="e95f9-108">Tipos complejos anidados</span><span class="sxs-lookup"><span data-stu-id="e95f9-108">Nested Complex Types</span></span>  
 <span data-ttu-id="e95f9-109">Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria-secundaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="e95f9-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="e95f9-110">El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario de la **Order** elemento.</span><span class="sxs-lookup"><span data-stu-id="e95f9-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
```xml  
<xs:element name="Order">  
  <xs:complexType>  
     <xs:sequence>
       <xs:element name="OrderDetail" />  
           <xs:complexType>
           </xs:complexType>  
     </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="e95f9-111">El proceso de asignación de esquemas XML crea tablas en el **conjunto** de datos que corresponden a los tipos complejos anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="e95f9-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="e95f9-112">También crea columnas adicionales que**-** se usan como columnas primarias secundarias para las tablas generadas.</span><span class="sxs-lookup"><span data-stu-id="e95f9-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="e95f9-113">Tenga en**-** cuenta que estas columnas primarias secundarias especifican relaciones, que no es lo mismo que especificar restricciones de clave principal/clave externa.</span><span class="sxs-lookup"><span data-stu-id="e95f9-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="e95f9-114">Anotación msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="e95f9-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="e95f9-115">La anotación **msdata:Relationship** permite especificar explícitamente las relaciones primario-secundario entre los elementos del esquema que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="e95f9-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="e95f9-116">En el ejemplo siguiente se muestra la estructura del elemento **Relationship.**</span><span class="sxs-lookup"><span data-stu-id="e95f9-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"
msdata:parent=""
msdata:child=""
msdata:parentkey=""
msdata:childkey="" />  
```  
  
 <span data-ttu-id="e95f9-117">Los atributos de la anotación **msdata:Relationship** identifican los elementos implicados en la relación primario-secundario, así como los elementos y atributos **parentkey** y **childkey** implicados en la relación.</span><span class="sxs-lookup"><span data-stu-id="e95f9-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="e95f9-118">El proceso de asignación utiliza esta información para generar tablas en el **conjunto** de datos y para crear la relación clave principal/clave externa entre estas tablas.</span><span class="sxs-lookup"><span data-stu-id="e95f9-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="e95f9-119">Por ejemplo, el siguiente fragmento de esquema especifica **Order** y **OrderDetail** elementos en el mismo nivel (no anidado).</span><span class="sxs-lookup"><span data-stu-id="e95f9-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="e95f9-120">El esquema especifica una anotación **msdata:Relationship,** que especifica la relación primario-secundario entre estos dos elementos.</span><span class="sxs-lookup"><span data-stu-id="e95f9-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="e95f9-121">En este caso, se debe especificar una relación explícita mediante la anotación **msdata:Relationship.**</span><span class="sxs-lookup"><span data-stu-id="e95f9-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
```xml  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
        <xs:element name="OrderDetail">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
       <xs:element name="Order">  
          <xs:complexType>  
  
          </xs:complexType>  
       </xs:element>  
    </xs:choice>  
  </xs:complexType>  
</xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrdDetailRelation"  
          msdata:parent="Order"  
          msdata:child="OrderDetail"
          msdata:parentkey="OrderNumber"  
          msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
```  
  
 <span data-ttu-id="e95f9-122">El proceso de asignación utiliza el elemento **Relationship** para crear una relación primario-secundario entre la columna **OrderNumber** de la tabla **Order** y la columna **OrderNo** de la tabla **OrderDetail** del **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="e95f9-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="e95f9-123">El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="e95f9-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="e95f9-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e95f9-124">In This Section</span></span>  
 [<span data-ttu-id="e95f9-125">Asignar relaciones implícitas entre elementos de esquema anidados</span><span class="sxs-lookup"><span data-stu-id="e95f9-125">Map Implicit Relations Between Nested Schema Elements</span></span>](map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="e95f9-126">Describe las restricciones y relaciones que se crean implícitamente en un **DataSet** cuando se encuentran elementos anidados en el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e95f9-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="e95f9-127">Asignar relaciones especificadas para elementos anidados</span><span class="sxs-lookup"><span data-stu-id="e95f9-127">Map Relations Specified for Nested Elements</span></span>](map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="e95f9-128">Describe cómo establecer explícitamente relaciones en un **DataSet** para elementos anidados en el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="e95f9-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="e95f9-129">Especificar relaciones entre elementos sin anidamiento</span><span class="sxs-lookup"><span data-stu-id="e95f9-129">Specify Relations Between Elements with No Nesting</span></span>](specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="e95f9-130">Describe cómo crear relaciones en un **DataSet** entre elementos de esquema XML que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="e95f9-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="e95f9-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="e95f9-131">Related Sections</span></span>  
 [<span data-ttu-id="e95f9-132">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="e95f9-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="e95f9-133">Describe la estructura relacional, o esquema, de un **DataSet** que se crea a partir del esquema del lenguaje de definición de esquemas XML (XSD).</span><span class="sxs-lookup"><span data-stu-id="e95f9-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="e95f9-134">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="e95f9-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="e95f9-135">Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un **dataset**.</span><span class="sxs-lookup"><span data-stu-id="e95f9-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e95f9-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e95f9-136">See also</span></span>

- [<span data-ttu-id="e95f9-137">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e95f9-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
