---
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150849"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="07368-102">Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="07368-102">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="07368-103">En un esquema de lenguaje de definición de esquemas XML (XSD), el elemento **unique** especifica la restricción de unicidad en un elemento o atributo.</span><span class="sxs-lookup"><span data-stu-id="07368-103">In an XML Schema definition language (XSD) schema, the **unique** element specifies the uniqueness constraint on an element or attribute.</span></span> <span data-ttu-id="07368-104">En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.</span><span class="sxs-lookup"><span data-stu-id="07368-104">In the process of translating an XML Schema into a relational schema, the unique constraint specified on an element or attribute in the XML Schema is mapped to a unique constraint in the <xref:System.Data.DataTable> in the corresponding <xref:System.Data.DataSet> that is generated.</span></span>  
  
 <span data-ttu-id="07368-105">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **único.**</span><span class="sxs-lookup"><span data-stu-id="07368-105">The following table outlines the **msdata** attributes that you can specify in the **unique** element.</span></span>  
  
|<span data-ttu-id="07368-106">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="07368-106">Attribute name</span></span>|<span data-ttu-id="07368-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="07368-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="07368-108">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="07368-108">**msdata:ConstraintName**</span></span>|<span data-ttu-id="07368-109">Si se especifica este atributo, su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="07368-109">If this attribute is specified, its value is used as the constraint name.</span></span> <span data-ttu-id="07368-110">De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="07368-110">Otherwise, the **name** attribute provides the value of the constraint name.</span></span>|  
|<span data-ttu-id="07368-111">**msdata:PrimaryKey**</span><span class="sxs-lookup"><span data-stu-id="07368-111">**msdata:PrimaryKey**</span></span>|<span data-ttu-id="07368-112">Si `PrimaryKey="true"` está presente en el elemento **único,** se crea una restricción única con la propiedad **IsPrimaryKey** establecida en **true**.</span><span class="sxs-lookup"><span data-stu-id="07368-112">If `PrimaryKey="true"` is present in the **unique** element, a unique constraint is created with the **IsPrimaryKey** property set to **true**.</span></span>|  
  
 <span data-ttu-id="07368-113">En el ejemplo siguiente se muestra un esquema XML que utiliza el elemento **único** para especificar una restricción de unicidad.</span><span class="sxs-lookup"><span data-stu-id="07368-113">The following example shows an XML Schema that uses the **unique** element to specify a uniqueness constraint.</span></span>  
  
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
  
 <span data-ttu-id="07368-114">El elemento **único** del esquema especifica que para todos los elementos **Customers** de una instancia de documento, el valor del elemento secundario **CustomerID** debe ser único.</span><span class="sxs-lookup"><span data-stu-id="07368-114">The **unique** element in the schema specifies that for all **Customers** elements in a document instance, the value of the **CustomerID** child element must be unique.</span></span> <span data-ttu-id="07368-115">Al compilar el **conjunto de datos**, el proceso de asignación lee este esquema y genera la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="07368-115">In building the **DataSet**, the mapping process reads this schema and generates the following table:</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="07368-116">El proceso de asignación también crea una restricción única en la columna **CustomerID,** como se muestra en el siguiente **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="07368-116">The mapping process also creates a unique constraint on the **CustomerID** column, as shown in the following **DataSet**.</span></span> <span data-ttu-id="07368-117">Para simplificar, sólo se muestran las propiedades relevantes.</span><span class="sxs-lookup"><span data-stu-id="07368-117">(For simplicity, only relevant properties are shown.)</span></span>  
  
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
  
 <span data-ttu-id="07368-118">En el **DataSet** que se genera, el **IsPrimaryKey** propiedad está establecida en **False** para la restricción única.</span><span class="sxs-lookup"><span data-stu-id="07368-118">In the **DataSet** that is generated, the **IsPrimaryKey** property is set to **False** for the unique constraint.</span></span> <span data-ttu-id="07368-119">La propiedad **unique** de la columna indica que los valores de columna **CustomerID** deben ser únicos (pero pueden ser una referencia nula, tal como se especifica en la propiedad **AllowDBNull** de la columna).</span><span class="sxs-lookup"><span data-stu-id="07368-119">The **unique** property on the column indicates that the **CustomerID** column values must be unique (but they can be a null reference, as specified by the **AllowDBNull** property of the column).</span></span>  
  
 <span data-ttu-id="07368-120">Si modifica el esquema y establece el valor opcional del atributo **msdata:PrimaryKey** en **True**, se crea la restricción única en la tabla.</span><span class="sxs-lookup"><span data-stu-id="07368-120">If you modify the schema and set the optional **msdata:PrimaryKey** attribute value to **True**, the unique constraint is created on the table.</span></span> <span data-ttu-id="07368-121">La propiedad de columna **AllowDBNull** se establece en **False**y la propiedad **IsPrimaryKey** de la restricción establecida en **True**, por lo que la columna **CustomerID** es una columna de clave principal.</span><span class="sxs-lookup"><span data-stu-id="07368-121">The **AllowDBNull** column property is set to **False**, and the **IsPrimaryKey** property of the constraint set to **True**, thus making the **CustomerID** column a primary key column.</span></span>  
  
 <span data-ttu-id="07368-122">Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML.</span><span class="sxs-lookup"><span data-stu-id="07368-122">You can specify a unique constraint on a combination of elements or attributes in the XML Schema.</span></span> <span data-ttu-id="07368-123">En el ejemplo siguiente se muestra cómo especificar que una combinación de **CustomerID** y **CompanyName** valores deben ser únicos para todos los **clientes** en cualquier instancia, agregando otro **xs:field** elemento en el esquema.</span><span class="sxs-lookup"><span data-stu-id="07368-123">The following example demonstrates how to specify that a combination of **CustomerID** and **CompanyName** values must be unique for all **Customers** in any instance, by adding another **xs:field** element in the schema.</span></span>  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 <span data-ttu-id="07368-124">Esta es la restricción que se crea en el **conjunto de datos**resultante.</span><span class="sxs-lookup"><span data-stu-id="07368-124">This is the constraint that is created in the resulting **DataSet**.</span></span>  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a><span data-ttu-id="07368-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="07368-125">See also</span></span>

- [<span data-ttu-id="07368-126">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="07368-126">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="07368-127">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="07368-127">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="07368-128">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="07368-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
