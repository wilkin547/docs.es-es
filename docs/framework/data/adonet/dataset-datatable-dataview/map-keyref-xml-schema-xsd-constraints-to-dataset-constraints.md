---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 902b79b73f494ced0f54b29babff1b2e767bd47a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150888"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a03bc-102">Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="a03bc-102">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a03bc-103">El elemento **keyref** permite establecer vínculos entre elementos dentro de un documento.</span><span class="sxs-lookup"><span data-stu-id="a03bc-103">The **keyref** element allows you to establish links between elements within a document.</span></span> <span data-ttu-id="a03bc-104">Esto es similar a una relación de clave externa en una base de datos relacional.</span><span class="sxs-lookup"><span data-stu-id="a03bc-104">This is similar to a foreign key relationship in a relational database.</span></span> <span data-ttu-id="a03bc-105">Si un esquema especifica el elemento **keyref,** el elemento se convierte durante el proceso de asignación de esquema en una restricción de clave externa correspondiente en las columnas de las <xref:System.Data.DataSet>tablas del archivo .</span><span class="sxs-lookup"><span data-stu-id="a03bc-105">If a schema specifies the **keyref** element, the element is converted during the schema mapping process to a corresponding foreign key constraint on the columns in the tables of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a03bc-106">De forma predeterminada, el elemento **keyref** también genera una relación, con las propiedades **ParentTable**, **ChildTable**, **ParentColumn**y **ChildColumn** especificadas en la relación.</span><span class="sxs-lookup"><span data-stu-id="a03bc-106">By default, the **keyref** element also generates a relation, with the **ParentTable**, **ChildTable**, **ParentColumn**, and **ChildColumn** properties specified on the relation.</span></span>  
  
 <span data-ttu-id="a03bc-107">En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **keyref.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-107">The following table outlines the **msdata** attributes you can specify in the **keyref** element.</span></span>  
  
|<span data-ttu-id="a03bc-108">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="a03bc-108">Attribute name</span></span>|<span data-ttu-id="a03bc-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="a03bc-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="a03bc-110">**msdata:ConstraintOnly**</span><span class="sxs-lookup"><span data-stu-id="a03bc-110">**msdata:ConstraintOnly**</span></span>|<span data-ttu-id="a03bc-111">Si se especifica **ConstraintOnly"true"** en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación.</span><span class="sxs-lookup"><span data-stu-id="a03bc-111">If **ConstraintOnly="true"** is specified on the **keyref** element in the schema, a constraint is created, but no relation is created.</span></span> <span data-ttu-id="a03bc-112">Si no se especifica este atributo (o se establece en **False**), tanto la restricción como la relación se crean en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-112">If this attribute is not specified (or is set to **False**), both the constraint and the relation are created in the **DataSet**.</span></span>|  
|<span data-ttu-id="a03bc-113">**msdata:ConstraintName**</span><span class="sxs-lookup"><span data-stu-id="a03bc-113">**msdata:ConstraintName**</span></span>|<span data-ttu-id="a03bc-114">Si se especifica el atributo **ConstraintName,** su valor se utiliza como nombre de la restricción.</span><span class="sxs-lookup"><span data-stu-id="a03bc-114">If the **ConstraintName** attribute is specified, its value is used as the name of the constraint.</span></span> <span data-ttu-id="a03bc-115">De lo contrario, el atributo **name** del elemento **keyref** del esquema proporciona el nombre de restricción en **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-115">Otherwise, the **name** attribute of the **keyref** element in the schema provides the constraint name in the **DataSet**.</span></span>|  
|<span data-ttu-id="a03bc-116">**msdata:UpdateRule**</span><span class="sxs-lookup"><span data-stu-id="a03bc-116">**msdata:UpdateRule**</span></span>|<span data-ttu-id="a03bc-117">Si el atributo **UpdateRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-117">If the **UpdateRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **UpdateRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="a03bc-118">De lo contrario, la propiedad **UpdateRule** se establece en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-118">Otherwise the **UpdateRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="a03bc-119">**msdata:DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="a03bc-119">**msdata:DeleteRule**</span></span>|<span data-ttu-id="a03bc-120">Si el atributo **DeleteRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** en el **conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-120">If the **DeleteRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **DeleteRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="a03bc-121">De lo contrario, la propiedad **DeleteRule** se establece en **Cascade**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-121">Otherwise the **DeleteRule** property is set to **Cascade**.</span></span>|  
|<span data-ttu-id="a03bc-122">**msdata:AcceptRejectRule**</span><span class="sxs-lookup"><span data-stu-id="a03bc-122">**msdata:AcceptRejectRule**</span></span>|<span data-ttu-id="a03bc-123">Si el **acceptRejectRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **AcceptRejectRule** propiedad de restricción en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-123">If the **AcceptRejectRule** attribute is specified in the **keyref** element in the schema, its value is assigned to the **AcceptRejectRule** constraint property in the **DataSet**.</span></span> <span data-ttu-id="a03bc-124">De lo contrario, la propiedad **AcceptRejectRule** se establece en **None**.</span><span class="sxs-lookup"><span data-stu-id="a03bc-124">Otherwise the **AcceptRejectRule** property is set to **None**.</span></span>|  
  
 <span data-ttu-id="a03bc-125">El ejemplo siguiente contiene un esquema que especifica las relaciones **key** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** del elemento **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-125">The following example contains a schema that specifies the **key** and **keyref** relationships between the **OrderNumber** child element of the **Order** element and the **OrderNo** child element of the **OrderDetail** element.</span></span>  
  
 <span data-ttu-id="a03bc-126">En el ejemplo, el elemento secundario **OrderNumber** del elemento **OrderDetail** hace referencia al elemento secundario de clave **OrderNo** del elemento **Order.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-126">In the example, the **OrderNumber** child element of the **OrderDetail** element refers to the **OrderNo** key child element of the **Order** element.</span></span>  
  
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
  
 <span data-ttu-id="a03bc-127">El proceso de asignación de esquemas del lenguaje de definición de esquemas XML (XSD) genera el siguiente **DataSet** con dos tablas:</span><span class="sxs-lookup"><span data-stu-id="a03bc-127">The XML Schema definition language (XSD) schema mapping process produces the following **DataSet** with two tables:</span></span>  
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 <span data-ttu-id="a03bc-128">Además, el **DataSet** define las siguientes restricciones:</span><span class="sxs-lookup"><span data-stu-id="a03bc-128">In addition, the **DataSet** defines the following constraints:</span></span>  
  
- <span data-ttu-id="a03bc-129">Una restricción única en la tabla **Order.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-129">A unique constraint on the **Order** table.</span></span>  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- <span data-ttu-id="a03bc-130">Relación entre las tablas **Order** y **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-130">A relationship between the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="a03bc-131">La propiedad **Nested** se establece en **False** porque los dos elementos no están anidados en el esquema.</span><span class="sxs-lookup"><span data-stu-id="a03bc-131">The **Nested** property is set to **False** because the two elements are not nested in the schema.</span></span>  
  
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
  
- <span data-ttu-id="a03bc-132">Restricción de clave externa en la tabla **OrderDetail.**</span><span class="sxs-lookup"><span data-stu-id="a03bc-132">A foreign key constraint on the **OrderDetail** table.</span></span>  
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a03bc-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a03bc-133">See also</span></span>

- [<span data-ttu-id="a03bc-134">Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="a03bc-134">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [<span data-ttu-id="a03bc-135">Generación de relaciones de objetos DataSet en un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="a03bc-135">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)
- [<span data-ttu-id="a03bc-136">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a03bc-136">ADO.NET Overview</span></span>](../ado-net-overview.md)
