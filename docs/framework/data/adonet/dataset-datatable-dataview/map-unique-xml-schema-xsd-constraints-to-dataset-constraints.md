---
description: Obtener más información acerca de cómo asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjunto de los conjuntos de los mismos
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 41a6e5424d67b092e57ac61d6e34a1f285fb8d0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651930"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="b8a7e-103">Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="b8a7e-103">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="b8a7e-104">En un esquema del lenguaje de definición de esquemas XML (XSD), el elemento **Unique** especifica la restricción de unicidad en un elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-104">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="b8a7e-105">En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-105">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="b8a7e-106">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **Unique** .</span><span class="sxs-lookup"><span data-stu-id="b8a7e-106">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="b8a7e-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="b8a7e-107">Attribute name</span></span>|<span data-ttu-id="b8a7e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b8a7e-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="b8a7e-109">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="b8a7e-109">**msdata:ConstraintName**</span></span>|<span data-ttu-id="b8a7e-110">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-110">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="b8a7e-111">De lo contrario, el atributo **Name** proporciona el valor del nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-111">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="b8a7e-112">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="b8a7e-112">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="b8a7e-113">Si `PrimaryKey="true"` está presente en el elemento **Unique** , se crea una restricción UNIQUE con la propiedad **IsPrimaryKey** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-113">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="b8a7e-114">En el ejemplo siguiente se muestra un esquema XML que utiliza el elemento **Unique** para especificar una restricción de unicidad.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-114">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="b8a7e-115">El elemento **Unique** del esquema especifica que, para todos los elementos de los **clientes** de una instancia de documento, el valor del elemento secundario **CustomerID** debe ser único.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-115">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="b8a7e-116">Al compilar el **conjunto** de elementos, el proceso de asignación Lee este esquema y genera la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="b8a7e-116">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="b8a7e-117">El proceso de asignación también crea una restricción UNIQUE en la columna **CustomerID** , como se muestra en el siguiente **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-117">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="b8a7e-118">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-118">(For simplicity, only relevant properties are shown.)</span></span>  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 <span data-ttu-id="b8a7e-119">En el **conjunto de DataSet** que se genera, la propiedad **IsPrimaryKey** está establecida en **false** para la restricción UNIQUE.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-119">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="b8a7e-120">La propiedad **Unique** de la columna indica que los valores de la columna **CustomerID** deben ser únicos (pero pueden ser una referencia nula, tal y como se especifica en la propiedad **AllowDBNull** de la columna).</span><span class="sxs-lookup"><span data-stu-id="b8a7e-120">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="b8a7e-121">Si modifica el esquema y establece el valor del atributo **msdata: PrimaryKey** opcional en **true**, se creará la restricción UNIQUE en la tabla.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-121">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="b8a7e-122">La propiedad de columna **AllowDBNull** está establecida en **false** y la propiedad **IsPrimaryKey** de la restricción se establece en **true**, lo que convierte la columna **CustomerID** en una columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-122">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="b8a7e-123">Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-123">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="b8a7e-124">En el ejemplo siguiente se muestra cómo especificar que una combinación de valores **CustomerID** y **CompanyName** debe ser única para todos los **clientes** de cualquier instancia, agregando otro elemento **xs: Field** en el esquema.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-124">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="b8a7e-125">Esta es la restricción que se crea en el **conjunto** de resultados.</span><span class="sxs-lookup"><span data-stu-id="b8a7e-125">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8a7e-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b8a7e-126">See also</span></span>

- [<span data-ttu-id="b8a7e-127">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="b8a7e-127">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="b8a7e-128">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="b8a7e-128">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="b8a7e-129">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b8a7e-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
