---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: e364efe0856a5291fc8157ef6ab185c2438a3347
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="80bd3-102">Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="80bd3-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="80bd3-103">El **keyref** elemento permite establecer vínculos entre elementos dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="80bd3-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="80bd3-104">Esto es similar a una relación de clave externa en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="80bd3-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="80bd3-105">Si un esquema especifica la **keyref** elemento, el elemento se convierte durante el proceso de asignación de esquema para una restricción de clave externa correspondiente en las columnas de las tablas de la <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="80bd3-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="80bd3-106">De forma predeterminada, el **keyref** elemento también genera una relación con la **ParentTable**, **ChildTable**, **ParentColumn**y  **ChildColumn** propiedades especificadas en la relación.</span><span class="sxs-lookup"><span data-stu-id="80bd3-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="80bd3-107">La siguiente tabla se describen los **msdata** atributos que puede especificar en el **keyref** elemento.</span><span class="sxs-lookup"><span data-stu-id="80bd3-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="80bd3-108">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="80bd3-108">Attribute name</span></span>|<span data-ttu-id="80bd3-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="80bd3-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="80bd3-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="80bd3-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="80bd3-111">Si **ConstraintOnly = "true"** se especifica en el **keyref** elemento en el esquema, se crea una restricción, pero se crea ninguna relación.</span><span class="sxs-lookup"><span data-stu-id="80bd3-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="80bd3-112">Si no se especifica este atributo (o se establece en **False**), tanto la restricción como la relación se crean en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="80bd3-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="80bd3-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="80bd3-114">Si el **ConstraintName** atributo se especifica, su valor se utiliza como el nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="80bd3-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="80bd3-115">En caso contrario, el **nombre** atributo de la **keyref** elemento en el esquema proporciona el nombre de restricción en la **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="80bd3-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="80bd3-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="80bd3-117">Si el **UpdateRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **UpdateRule** propiedad de restricción en la  **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="80bd3-118">En caso contrario, el **UpdateRule** propiedad está establecida en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="80bd3-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="80bd3-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="80bd3-120">Si el **DeleteRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **DeleteRule** propiedad de restricción en la  **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="80bd3-121">En caso contrario, el **DeleteRule** propiedad está establecida en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="80bd3-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="80bd3-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="80bd3-123">Si el **AcceptRejectRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **AcceptRejectRule** propiedad de restricción en la  **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="80bd3-124">En caso contrario, el **AcceptRejectRule** propiedad está establecida en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="80bd3-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="80bd3-125">El ejemplo siguiente contiene un esquema que especifica la **clave** y **keyref** las relaciones entre la **OrderNumber** elemento secundario de la **orden**  elemento y el **OrderNo** elemento secundario de la **OrderDetail** elemento.</span><span class="sxs-lookup"><span data-stu-id="80bd3-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="80bd3-126">En el ejemplo, el **OrderNumber** elemento secundario de la **OrderDetail** elemento hace referencia a la **OrderNo** elemento secundario de clave de la **orden**elemento.</span><span class="sxs-lookup"><span data-stu-id="80bd3-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="80bd3-127">El proceso de asignación de esquema de lenguaje (XSD) de esquema XML definición produce el siguiente **conjunto de datos** con dos tablas:</span><span class="sxs-lookup"><span data-stu-id="80bd3-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="80bd3-128">Además, el **conjunto de datos** define las restricciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="80bd3-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
-   <span data-ttu-id="80bd3-129">Una restricción unique en la **orden** tabla.</span><span class="sxs-lookup"><span data-stu-id="80bd3-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   <span data-ttu-id="80bd3-130">Una relación entre la **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="80bd3-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="80bd3-131">El **Nested** propiedad está establecida en **False** porque los dos elementos no están anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="80bd3-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
    ```  
              ParentTable: Order  
    ParentColumns: OrderNumber   
    ChildTable: OrderDetail  
    ChildColumns: OrderNo   
    ParentKeyConstraint: OrderNumberKey  
    ChildKeyConstraint: OrderNoRef  
    RelationName: OrderNoRef  
    Nested: False  
    ```  
  
-   <span data-ttu-id="80bd3-132">Una restricción foreign key en la **OrderDetail** tabla.</span><span class="sxs-lookup"><span data-stu-id="80bd3-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="80bd3-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="80bd3-133">See Also</span></span>  
 [<span data-ttu-id="80bd3-134">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="80bd3-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [<span data-ttu-id="80bd3-135">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="80bd3-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [<span data-ttu-id="80bd3-136">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="80bd3-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
