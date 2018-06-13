---
title: Generar relaciones de objetos DataSet en un esquema XML (XSD)
ms.date: 03/30/2017
ms.assetid: 1c9a1413-c0d2-4447-88ba-9a2b0cbc0aa8
ms.openlocfilehash: fdf22c311ef7b4267f4a4da8566e4ea59504b103
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32758443"
---
# <a name="generating-dataset-relations-from-xml-schema-xsd"></a><span data-ttu-id="1375b-102">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="1375b-102">Generating DataSet Relations from XML Schema (XSD)</span></span>
<span data-ttu-id="1375b-103">En un <xref:System.Data.DataSet>, para formar una asociación entre dos o más columnas se debe crear una relación primaria-secundaria.</span><span class="sxs-lookup"><span data-stu-id="1375b-103">In a <xref:System.Data.DataSet>, you form an association between two or more columns by creating a parent-child relation.</span></span> <span data-ttu-id="1375b-104">Hay tres formas de representar un **conjunto de datos** relación dentro de un esquema de lenguaje (XSD) de definición de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="1375b-104">There are three ways to represent a **DataSet** relation within an XML Schema definition language (XSD) schema:</span></span>  
  
-   <span data-ttu-id="1375b-105">Especificar tipos complejos anidados.</span><span class="sxs-lookup"><span data-stu-id="1375b-105">Specify nested complex types.</span></span>  
  
-   <span data-ttu-id="1375b-106">Use la **msdata: Relationship** anotación.</span><span class="sxs-lookup"><span data-stu-id="1375b-106">Use the **msdata:Relationship** annotation.</span></span>  
  
-   <span data-ttu-id="1375b-107">Especifique un **xs: keyref** sin el **msdata: ConstraintOnly** anotación.</span><span class="sxs-lookup"><span data-stu-id="1375b-107">Specify an **xs:keyref** without the **msdata:ConstraintOnly** annotation.</span></span>  
  
## <a name="nested-complex-types"></a><span data-ttu-id="1375b-108">Tipos complejos anidados</span><span class="sxs-lookup"><span data-stu-id="1375b-108">Nested Complex Types</span></span>  
 <span data-ttu-id="1375b-109">Las definiciones de tipos complejos anidados de un esquema indican las relaciones primaria-secundaria de los elementos.</span><span class="sxs-lookup"><span data-stu-id="1375b-109">Nested complex type definitions in a schema indicate the parent-child relationships of the elements.</span></span> <span data-ttu-id="1375b-110">El siguiente fragmento de esquema XML muestra que **OrderDetail** es un elemento secundario de la **orden** elemento.</span><span class="sxs-lookup"><span data-stu-id="1375b-110">The following XML Schema fragment shows that **OrderDetail** is a child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="1375b-111">El proceso de asignación de esquema XML crea tablas en la **conjunto de datos** que corresponden a los tipos complejos anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="1375b-111">The XML Schema mapping process creates tables in the **DataSet** that correspond to the nested complex types in the schema.</span></span> <span data-ttu-id="1375b-112">También crea columnas adicionales que se usan como primario**-** columnas primaria-secundaria para las tablas generadas.</span><span class="sxs-lookup"><span data-stu-id="1375b-112">It also creates additional columns that are used as parent**-** child columns for the generated tables.</span></span> <span data-ttu-id="1375b-113">Tenga en cuenta que estos primario**-** columnas primaria-secundaria especifican relaciones, que no es lo mismo que especificar restricciones de clave externa y clave principal.</span><span class="sxs-lookup"><span data-stu-id="1375b-113">Note that these parent**-** child columns specify relationships, which is not the same as specifying primary key/foreign key constraints.</span></span>  
  
## <a name="msdatarelationship-annotation"></a><span data-ttu-id="1375b-114">Anotación msdata:Relationship</span><span class="sxs-lookup"><span data-stu-id="1375b-114">msdata:Relationship Annotation</span></span>  
 <span data-ttu-id="1375b-115">El **msdata: Relationship** anotación permite especificar explícitamente relaciones primaria-secundaria entre los elementos del esquema que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="1375b-115">The **msdata:Relationship** annotation allows you to explicitly specify parent-child relationships between elements in the schema that are not nested.</span></span> <span data-ttu-id="1375b-116">En el ejemplo siguiente se muestra la estructura de la **relación** elemento.</span><span class="sxs-lookup"><span data-stu-id="1375b-116">The following example shows the structure of the **Relationship** element.</span></span>  
  
```xml  
<msdata:Relationship name="CustOrderRelationship"    
msdata:parent=""    
msdata:child=""    
msdata:parentkey=""    
msdata:childkey="" />  
```  
  
 <span data-ttu-id="1375b-117">Los atributos de la **msdata: Relationship** anotación identifican los elementos implicados en la relación de elementos primarios y secundarios, así como el **parentkey** y **childkey** elementos y atributos implicados en la relación.</span><span class="sxs-lookup"><span data-stu-id="1375b-117">The attributes of the **msdata:Relationship** annotation identify the elements involved in the parent-child relationship, as well as the **parentkey** and **childkey** elements and attributes involved in the relationship.</span></span> <span data-ttu-id="1375b-118">El proceso de asignación utiliza esta información para generar tablas en el **conjunto de datos** y para crear la relación de clave principal/clave externa entre estas tablas.</span><span class="sxs-lookup"><span data-stu-id="1375b-118">The mapping process uses this information to generate tables in the **DataSet** and to create the primary key/foreign key relationship between these tables.</span></span>  
  
 <span data-ttu-id="1375b-119">Por ejemplo, el siguiente fragmento de esquema especifica **orden** y **OrderDetail** elementos del mismo nivel (no están anidados).</span><span class="sxs-lookup"><span data-stu-id="1375b-119">For example, the following schema fragment specifies **Order** and **OrderDetail** elements at the same level (not nested).</span></span> <span data-ttu-id="1375b-120">El esquema especifica un **msdata: Relationship** anotación, que especifica la relación de elementos primarios y secundarios entre estos dos elementos.</span><span class="sxs-lookup"><span data-stu-id="1375b-120">The schema specifies an **msdata:Relationship** annotation, which specifies the parent-child relationship between these two elements.</span></span> <span data-ttu-id="1375b-121">En este caso, se debe especificar una relación explícita mediante la **msdata: Relationship** anotación.</span><span class="sxs-lookup"><span data-stu-id="1375b-121">In this case, an explicit relationship must be specified using the **msdata:Relationship** annotation.</span></span>  
  
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
  
 <span data-ttu-id="1375b-122">El proceso de asignación utiliza el **relación** elemento que se va a crear una relación de elementos primarios y secundarios entre el **OrderNumber** columna en el **orden** tabla y la **OrderNo** columna en el **OrderDetail** tabla el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="1375b-122">The mapping process uses the **Relationship** element to create a parent-child relationship between the **OrderNumber** column in the **Order** table and the **OrderNo** column in the **OrderDetail** table in the **DataSet**.</span></span> <span data-ttu-id="1375b-123">El proceso de asignación sólo especifica la relación; no especifica automáticamente ninguna restricción para los valores de estas columnas, como ocurre en las restricciones de clave principal y clave externa de las bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="1375b-123">The mapping process only specifies the relationship; it does not automatically specify any constraints on the values in these columns, as do the primary key/foreign key constraints in relational databases.</span></span>  
  
### <a name="in-this-section"></a><span data-ttu-id="1375b-124">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1375b-124">In This Section</span></span>  
 [<span data-ttu-id="1375b-125">Asignación de relaciones implícitas entre elementos de esquema anidados</span><span class="sxs-lookup"><span data-stu-id="1375b-125">Map Implicit Relations Between Nested Schema Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md)  
 <span data-ttu-id="1375b-126">Describe las restricciones y relaciones que se crean implícitamente en un **conjunto de datos** cuando se encuentran elementos anidados en el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="1375b-126">Describes the constraints and relations that are implicitly created in a **DataSet** when nested elements are encountered in XML Schema.</span></span>  
  
 [<span data-ttu-id="1375b-127">Asignación de relaciones especificadas para elementos anidados</span><span class="sxs-lookup"><span data-stu-id="1375b-127">Map Relations Specified for Nested Elements</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-relations-specified-for-nested-elements.md)  
 <span data-ttu-id="1375b-128">Describe cómo establecer explícitamente relaciones en un **conjunto de datos** para los elementos anidados del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="1375b-128">Describes how to explicitly set relations in a **DataSet** for nested elements in XML Schema.</span></span>  
  
 [<span data-ttu-id="1375b-129">Definición de relaciones entre elementos sin anidamiento</span><span class="sxs-lookup"><span data-stu-id="1375b-129">Specify Relations Between Elements with No Nesting</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/specify-relations-between-elements-with-no-nesting.md)  
 <span data-ttu-id="1375b-130">Describe cómo crear relaciones en un **conjunto de datos** entre elementos de esquema XML que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="1375b-130">Describes how to create relations in a **DataSet** between XML Schema elements that are not nested.</span></span>  
  
### <a name="related-sections"></a><span data-ttu-id="1375b-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="1375b-131">Related Sections</span></span>  
 [<span data-ttu-id="1375b-132">Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="1375b-132">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="1375b-133">Describe la estructura relacional, o esquema, de un **conjunto de datos** creado a partir de esquema XML Schema definition language (XSD).</span><span class="sxs-lookup"><span data-stu-id="1375b-133">Describes the relational structure, or schema, of a **DataSet** that is created from XML Schema definition language (XSD) schema.</span></span>  
  
 [<span data-ttu-id="1375b-134">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="1375b-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="1375b-135">Describe los elementos de esquema XML utilizados para crear restricciones de clave únicas y externas en un **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="1375b-135">Describes the XML Schema elements used to create unique and foreign key constraints in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1375b-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="1375b-136">See Also</span></span>  
 [<span data-ttu-id="1375b-137">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="1375b-137">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
