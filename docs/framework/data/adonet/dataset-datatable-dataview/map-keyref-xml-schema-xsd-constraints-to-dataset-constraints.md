---
description: Obtener más información acerca de cómo asignar restricciones keyref de esquema XML (XSD) a restricciones de conjunto de código
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: f9925cf68e0c8fd1258eeeb509664e0527e58526
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651982"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="7de4c-103">Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="7de4c-103">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>

<span data-ttu-id="7de4c-104">El elemento **keyref** permite establecer vínculos entre los elementos de un documento.</span><span class="sxs-lookup"><span data-stu-id="7de4c-104">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="7de4c-105">Esto es similar a una relación de clave externa en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="7de4c-105">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="7de4c-106">Si un esquema especifica el elemento **keyref** , el elemento se convierte durante el proceso de asignación de esquemas en una restricción de clave externa correspondiente en las columnas de las tablas de <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="7de4c-106">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="7de4c-107">De forma predeterminada, el elemento **keyref** genera también una relación, con las propiedades **ParentTable**, **ChildTable**, **ParentColumn** y **ChildColumn** especificadas en la relación.</span><span class="sxs-lookup"><span data-stu-id="7de4c-107">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="7de4c-108">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **keyref** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-108">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="7de4c-109">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="7de4c-109">Attribute name</span></span>|<span data-ttu-id="7de4c-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="7de4c-110">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7de4c-111">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="7de4c-111">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="7de4c-112">Si **ConstraintOnly = "true"** se especifica en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación.</span><span class="sxs-lookup"><span data-stu-id="7de4c-112">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="7de4c-113">Si no se especifica este atributo (o se establece en **false**), tanto la restricción como la relación se crean en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="7de4c-113">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="7de4c-114">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="7de4c-114">**msdata:ConstraintName**</span></span>|<span data-ttu-id="7de4c-115">Si se especifica el atributo **ConstraintName** , su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="7de4c-115">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="7de4c-116">De lo contrario, el atributo **Name** del elemento **keyref** del esquema proporciona el nombre de la restricción en el **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="7de4c-116">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="7de4c-117">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="7de4c-117">**msdata:UpdateRule**</span></span>|<span data-ttu-id="7de4c-118">Si el atributo **UpdateRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** del **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="7de4c-118">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7de4c-119">En caso contrario, la propiedad **UpdateRule** está establecida en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="7de4c-119">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7de4c-120">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="7de4c-120">**msdata:DeleteRule**</span></span>|<span data-ttu-id="7de4c-121">Si el atributo **DeleteRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** del **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="7de4c-121">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7de4c-122">De lo contrario, la propiedad **DeleteRule** se establece como **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="7de4c-122">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="7de4c-123">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="7de4c-123">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="7de4c-124">Si se especifica el atributo **AcceptRejectRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **AcceptRejectRule** en el **conjunto** de elementos.</span><span class="sxs-lookup"><span data-stu-id="7de4c-124">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="7de4c-125">En caso contrario, la propiedad **AcceptRejectRule** está establecida en **None**.</span><span class="sxs-lookup"><span data-stu-id="7de4c-125">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="7de4c-126">El ejemplo siguiente contiene un esquema que especifica las relaciones de **clave** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** del elemento **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-126">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="7de4c-127">En el ejemplo, el elemento secundario **OrderNumber** del elemento **OrderDetail** hace referencia al elemento secundario **OrderNo** Key del elemento **Order** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-127">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:integer" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:key name="OrderNumberKey"  >  
    <xs:selector xpath=".//Order" />  
    <xs:field xpath="OrderNumber" />  
  </xs:key>  
  
  <xs:keyref name="OrderNoRef" refer="OrderNumberKey">  
    <xs:selector xpath=".//OrderDetail" />  
    <xs:field xpath="OrderNo" />  
  </xs:keyref>  
 </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="7de4c-128">El proceso de asignación del esquema del lenguaje de definición de esquemas XML (XSD) genera el siguiente **conjunto** de elementos con dos tablas:</span><span class="sxs-lookup"><span data-stu-id="7de4c-128">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="7de4c-129">Además, el **conjunto** de elementos define las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="7de4c-129">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="7de4c-130">Una restricción UNIQUE en la tabla **Order** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-130">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="7de4c-131">Una relación entre las tablas **Order** y **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-131">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="7de4c-132">La propiedad **Nested** se establece en **false** porque los dos elementos no están anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="7de4c-132">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```text
              ParentTable: Order  
    ParentColumns: OrderNumber
    ChildTable: OrderDetail  
    ChildColumns: OrderNo
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
- <span data-ttu-id="7de4c-133">Una restricción FOREIGN KEY en la tabla **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="7de4c-133">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7de4c-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="7de4c-134">See also</span></span>

- [<span data-ttu-id="7de4c-135">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="7de4c-135">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="7de4c-136">Generar relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="7de4c-136">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="7de4c-137">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7de4c-137">ADO.NET Overview</span></span>](../ado-net-overview.md)
