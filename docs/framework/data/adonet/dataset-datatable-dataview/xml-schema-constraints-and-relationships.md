---
description: Más información acerca de las restricciones y relaciones del esquema XML
title: Restricciones y relaciones del esquema XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: c7847691537c4b754abcbacdeb367b1d92365ef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651319"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="9cd5c-103">Restricciones y relaciones del esquema XML</span><span class="sxs-lookup"><span data-stu-id="9cd5c-103">XML Schema Constraints and Relationships</span></span>

<span data-ttu-id="9cd5c-104">En un esquema del lenguaje de definición de esquemas XML (XSD), puede especificar las restricciones (Unique, Key y keyref) y las relaciones (mediante la anotación **msdata: Relationship** ).</span><span class="sxs-lookup"><span data-stu-id="9cd5c-104">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="9cd5c-105">En este tema se explica cómo se interpretan las restricciones y relaciones especificadas en un esquema XML para generar el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-105">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="9cd5c-106">En general, en un esquema XML, se especifica la anotación **msdata: Relationship** si se desea generar solo relaciones en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-106">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="9cd5c-107">Para obtener más información, vea [generar relaciones de conjunto de datos a partir de un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="9cd5c-107">For more information, see [Generating DataSet Relations from XML Schema (XSD)](generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="9cd5c-108">Puede especificar restricciones (Unique, Key y keyref) Si desea generar restricciones en el **conjunto de DataSet**.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-108">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="9cd5c-109">Tenga en cuenta que las restricciones key y keyref también se utilizan para generar relaciones, como se explica más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-109">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="9cd5c-110">Generar una relación a partir de restricciones key y keyref</span><span class="sxs-lookup"><span data-stu-id="9cd5c-110">Generating a Relationship from key and keyref Constraints</span></span>  

 <span data-ttu-id="9cd5c-111">En lugar de especificar la anotación **msdata: Relationship** , puede especificar las restricciones Key y keyref, que se utilizan durante el proceso de asignación del esquema XML para generar no solo las restricciones, sino también la relación en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-111">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="9cd5c-112">Sin embargo, si especifica `msdata:ConstraintOnly="true"` en el elemento **keyref** , el **conjunto** de elementos solo incluirá las restricciones y no incluirá la relación.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-112">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="9cd5c-113">En el ejemplo siguiente se muestra un esquema XML que incluye los elementos **Order** y **OrderDetail** , que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-113">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="9cd5c-114">El esquema también especifica restricciones key y keyref.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-114">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="9cd5c-115">El **DataSet** que se genera durante el proceso de asignación del esquema XML incluye las tablas **Order** y **OrderDetail** .</span><span class="sxs-lookup"><span data-stu-id="9cd5c-115">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="9cd5c-116">Además, el **conjunto** de elementos incluye relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-116">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="9cd5c-117">En el siguiente ejemplo se muestran estas relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-117">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="9cd5c-118">Tenga en cuenta que el esquema no especifica la anotación **msdata: Relationship** ; en su lugar, se usan las restricciones Key y keyref para generar la relación.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-118">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```text
....ConstraintName: OrderNumberKey  
....Type: UniqueConstraint  
....Table: Order  
....Columns: OrderNumber  
....IsPrimaryKey: False  
  
....ConstraintName: OrderNoRef  
....Type: ForeignKeyConstraint  
....Table: OrderDetail  
....Columns: OrderNo  
....RelatedTable: Order  
....RelatedColumns: OrderNumber  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
```  
  
 <span data-ttu-id="9cd5c-119">En el ejemplo de esquema anterior, los elementos **Order** y **OrderDetail** no están anidados.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-119">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="9cd5c-120">En el siguiente ejemplo de esquema, estos elementos están anidados.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-120">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="9cd5c-121">Sin embargo, no se especifica ninguna anotación **msdata: Relationship** ; por lo tanto, se supone una relación implícita.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-121">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="9cd5c-122">Para obtener más información, vea [asignar relaciones implícitas entre elementos de esquema anidados](map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="9cd5c-122">For more information, see [Map Implicit Relations Between Nested Schema Elements](map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="9cd5c-123">El esquema también especifica restricciones key y keyref.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-123">The schema also specifies key and keyref constraints.</span></span>  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
  
      <xs:element name="Order">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="OrderNumber" type="xs:integer" />  
            <xs:element name="EmpNumber" type="xs:integer" />  
  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:integer" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
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
  
 <span data-ttu-id="9cd5c-124">El **conjunto** de resultados resultante del proceso de asignación de esquemas XML incluye dos tablas:</span><span class="sxs-lookup"><span data-stu-id="9cd5c-124">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="9cd5c-125">El **DataSet** también incluye las dos relaciones (una basada en la anotación **msdata: Relationship** y la otra basándose en las restricciones Key y keyref) y varias restricciones.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-125">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="9cd5c-126">En el siguiente ejemplo se muestran las relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-126">The following example shows the relations and constraints.</span></span>  
  
```text
..RelationName: Order_OrderDetail  
..ParentTable: Order  
..ParentColumns: Order_Id  
..ChildTable: OrderDetail  
..ChildColumns: Order_Id  
..ParentKeyConstraint: Constraint1  
..ChildKeyConstraint: Order_OrderDetail  
..Nested: True  
  
..RelationName: OrderNoRef  
..ParentTable: Order  
..ParentColumns: OrderNumber  
..ChildTable: OrderDetail  
..ChildColumns: OrderNo  
..ParentKeyConstraint: OrderNumberKey  
..ChildKeyConstraint: OrderNoRef  
..Nested: False  
  
..ConstraintName: OrderNumberKey  
..Type: UniqueConstraint  
..Table: Order  
..Columns: OrderNumber  
..IsPrimaryKey: False  
  
..ConstraintName: Constraint1  
..Type: UniqueConstraint  
..Table: Order  
..Columns: Order_Id  
..IsPrimaryKey: True  
  
..ConstraintName: Order_OrderDetail  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: Order_Id  
..RelatedTable: Order  
..RelatedColumns: Order_Id  
  
..ConstraintName: OrderNoRef  
..Type: ForeignKeyConstraint  
..Table: OrderDetail  
..Columns: OrderNo  
..RelatedTable: Order  
..RelatedColumns: OrderNumber  
```  
  
 <span data-ttu-id="9cd5c-127">Si una restricción keyref que hace referencia a una tabla anidada contiene la anotación **msdata: IsNested = "true"** , el **conjunto de DataSet** creará una única relación anidada basada en la restricción keyref y en la restricción UNIQUE/Key relacionada.</span><span class="sxs-lookup"><span data-stu-id="9cd5c-127">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cd5c-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cd5c-128">See also</span></span>

- [<span data-ttu-id="9cd5c-129">Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="9cd5c-129">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="9cd5c-130">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9cd5c-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
