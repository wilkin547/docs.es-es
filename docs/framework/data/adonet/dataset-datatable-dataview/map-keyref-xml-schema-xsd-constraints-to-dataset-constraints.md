---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 611322065a4df53d1a3149ef4e1ca5592f149081
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203440"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="8f527-102">Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="8f527-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="8f527-103">El elemento **keyref** permite establecer vínculos entre los elementos de un documento.</span><span class="sxs-lookup"><span data-stu-id="8f527-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="8f527-104">Esto es similar a una relación de clave externa en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="8f527-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="8f527-105">Si un esquema especifica el elemento **keyref** , el elemento se convierte durante el proceso de asignación de esquemas en una restricción de clave externa correspondiente en las columnas de <xref:System.Data.DataSet>las tablas de.</span><span class="sxs-lookup"><span data-stu-id="8f527-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="8f527-106">De forma predeterminada, el elemento **keyref** genera también una relación, con las propiedades **ParentTable**, **ChildTable**, **ParentColumn**y **ChildColumn** especificadas en la relación.</span><span class="sxs-lookup"><span data-stu-id="8f527-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="8f527-107">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **keyref** .</span><span class="sxs-lookup"><span data-stu-id="8f527-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="8f527-108">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="8f527-108">Attribute name</span></span>|<span data-ttu-id="8f527-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8f527-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="8f527-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="8f527-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="8f527-111">Si **ConstraintOnly = "true"** se especifica en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación.</span><span class="sxs-lookup"><span data-stu-id="8f527-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="8f527-112">Si no se especifica este atributo (o se establece en **false**), tanto la restricción como la relación se crean en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="8f527-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="8f527-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="8f527-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="8f527-114">Si se especifica el atributo **ConstraintName** , su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="8f527-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="8f527-115">De lo contrario, el atributo **Name** del elemento **keyref** del esquema proporciona el nombre de la restricción en el **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="8f527-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="8f527-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="8f527-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="8f527-117">Si el atributo **UpdateRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** del **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="8f527-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8f527-118">En caso contrario, la propiedad **UpdateRule** está establecida en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="8f527-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="8f527-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="8f527-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="8f527-120">Si el atributo **DeleteRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** del **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="8f527-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8f527-121">De lo contrario, la propiedad **DeleteRule** se establece como **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="8f527-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="8f527-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="8f527-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="8f527-123">Si se especifica el atributo **AcceptRejectRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **AcceptRejectRule** en el **conjunto**de elementos.</span><span class="sxs-lookup"><span data-stu-id="8f527-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="8f527-124">En caso contrario, la propiedad **AcceptRejectRule** está establecida en **None**.</span><span class="sxs-lookup"><span data-stu-id="8f527-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="8f527-125">El ejemplo siguiente contiene un esquema que especifica las relaciones de **clave** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** de **OrderDetail** . Element.</span><span class="sxs-lookup"><span data-stu-id="8f527-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="8f527-126">En el ejemplo, el elemento secundario **OrderNumber** del elemento **OrderDetail** hace referencia al elemento secundario **OrderNo** Key del elemento **Order** .</span><span class="sxs-lookup"><span data-stu-id="8f527-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="8f527-127">El proceso de asignación del esquema del lenguaje de definición de esquemas XML (XSD) genera el siguiente **conjunto** de elementos con dos tablas:</span><span class="sxs-lookup"><span data-stu-id="8f527-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="8f527-128">Además, el **conjunto** de elementos define las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="8f527-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="8f527-129">Una restricción UNIQUE en la tabla **Order** .</span><span class="sxs-lookup"><span data-stu-id="8f527-129">A unique constraint on the **Order** table.</span></span>  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="8f527-130">Una relación entre las tablas **Order** y **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="8f527-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="8f527-131">La propiedad Nested se establece en **false** porque los dos elementos no están anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="8f527-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="8f527-132">Una restricción FOREIGN KEY en la tabla **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="8f527-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8f527-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f527-133">See also</span></span>

- [<span data-ttu-id="8f527-134">Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="8f527-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="8f527-135">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="8f527-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="8f527-136">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8f527-136">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
