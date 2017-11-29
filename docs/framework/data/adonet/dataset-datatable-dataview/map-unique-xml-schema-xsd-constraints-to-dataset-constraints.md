---
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66183768b5b48608dc69a4021b27816595c43b4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a5ecd-102">Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="a5ecd-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a5ecd-103">En un esquema (XSD) de lenguaje de definición de esquemas XML, el **único** elemento especifica la restricción de unicidad en un elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="a5ecd-104">En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="a5ecd-105">La siguiente tabla se describen los **msdata** atributos que se pueden especificar en el **único** elemento.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="a5ecd-106">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="a5ecd-106">Attribute name</span></span>|<span data-ttu-id="a5ecd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5ecd-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a5ecd-108">**msdata: ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="a5ecd-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="a5ecd-109">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="a5ecd-110">En caso contrario, el **nombre** atributo proporciona el valor del nombre de restricción.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="a5ecd-111">**msdata: PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="a5ecd-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="a5ecd-112">Si `PrimaryKey="true"` está presente en el **único** elemento, se crea una restricción unique con la **IsPrimaryKey** propiedad establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="a5ecd-113">En el ejemplo siguiente se muestra un esquema XML que usa el **único** elemento para especificar una restricción de unicidad.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="a5ecd-114">El **único** elemento en el esquema especifica que para todos los **clientes** elementos en un documento de instancia, el valor de la **CustomerID** elemento secundario debe ser único.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="a5ecd-115">En el edificio del **conjunto de datos**, el proceso de asignación lee este esquema y genera la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5ecd-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="a5ecd-116">El proceso de asignación crea también una restricción unique en la **CustomerID** columna, tal y como se muestra en la siguiente **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="a5ecd-117">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
```  
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
  
 <span data-ttu-id="a5ecd-118">En el **conjunto de datos** que se genera, la **IsPrimaryKey** propiedad está establecida en **False** para la restricción única.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="a5ecd-119">El **único** propiedad en la columna indica que la **CustomerID** valores de columna deben ser únicos (pero pueden ser una referencia nula, según lo especificado por el **AllowDBNull** propiedad de la columna).</span><span class="sxs-lookup"><span data-stu-id="a5ecd-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="a5ecd-120">Si modifica el esquema y establezca el encabezado opcional **msdata: PrimaryKey** valor al atributo **True**, se crea la restricción unique en la tabla.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="a5ecd-121">El **AllowDBNull** propiedad de columna se establece en **False**y el **IsPrimaryKey** propiedad de la restricción se establece como **True**, lo que hace que el **CustomerID** una columna de clave principal de la columna.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="a5ecd-122">Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="a5ecd-123">En el ejemplo siguiente se muestra cómo especificar que una combinación de **CustomerID** y **CompanyName** valores deben ser únicos para todos los **clientes** en cualquier instancia por agregar otro **xs: Field** elemento en el esquema.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 <span data-ttu-id="a5ecd-124">Se trata de la restricción que se crea en el cuadro **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a5ecd-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5ecd-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a5ecd-125">See Also</span></span>  
 [<span data-ttu-id="a5ecd-126">Asignar restricciones de esquema (XSD) de XML a las restricciones de conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a5ecd-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="a5ecd-127">Generar las relaciones de conjunto de datos desde un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="a5ecd-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="a5ecd-128">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="a5ecd-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
