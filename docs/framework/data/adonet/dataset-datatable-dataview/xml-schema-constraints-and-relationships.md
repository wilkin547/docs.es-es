---
title: Restricciones y relaciones del esquema XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: bcb6e257a40040701612b73768a98e056bccd6c5
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785617"
---
# <a name="xml-schema-constraints-and-relationships"></a><span data-ttu-id="199f3-102">Restricciones y relaciones del esquema XML</span><span class="sxs-lookup"><span data-stu-id="199f3-102">XML Schema Constraints and Relationships</span></span>
<span data-ttu-id="199f3-103">En un esquema (XSD) del lenguaje de definición de esquemas XML, puede especificar restricciones (unique, key y keyref) y relaciones (mediante la **msdata: Relationship** anotación).</span><span class="sxs-lookup"><span data-stu-id="199f3-103">In an XML Schema definition language (XSD) schema, you can specify constraints (unique, key, and keyref constraints) and relationships (using the **msdata:Relationship** annotation).</span></span> <span data-ttu-id="199f3-104">En este tema se explica cómo se interpretan las restricciones y relaciones especificadas en un esquema XML para generar el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="199f3-104">This topic explains how the constraints and relationships specified in an XML Schema are interpreted to generate the <xref:System.Data.DataSet>.</span></span>  
  
 <span data-ttu-id="199f3-105">En general, en un esquema XML, especifique el **msdata: Relationship** anotación si desea generar únicamente relaciones en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="199f3-105">In general, in an XML Schema, you specify the **msdata:Relationship** annotation if you want to generate only relationships in the **DataSet**.</span></span> <span data-ttu-id="199f3-106">Para obtener más información, consulte [relaciones de conjunto de datos de generación de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="199f3-106">For more information, see [Generating DataSet Relations from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md).</span></span> <span data-ttu-id="199f3-107">Especificar restricciones (unique, key y keyref) si desea generar restricciones en el **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="199f3-107">You specify constraints (unique, key, and keyref) if you want to generate constraints in the **DataSet**.</span></span> <span data-ttu-id="199f3-108">Tenga en cuenta que las restricciones key y keyref también se utilizan para generar relaciones, como se explica más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="199f3-108">Note that the key and keyref constraints are also used to generate relationships, as explained later in this topic.</span></span>  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a><span data-ttu-id="199f3-109">Generar una relación a partir de restricciones key y keyref</span><span class="sxs-lookup"><span data-stu-id="199f3-109">Generating a Relationship from key and keyref Constraints</span></span>  
 <span data-ttu-id="199f3-110">En lugar de especificar el **msdata: Relationship** anotación, puede especificar restricciones key y keyref, que se usan durante el proceso de asignación de esquema XML para generar no sólo las restricciones, sino también la relación en el  **Conjunto de datos**.</span><span class="sxs-lookup"><span data-stu-id="199f3-110">Instead of specifying the **msdata:Relationship** annotation, you can specify key and keyref constraints, which are used during the XML Schema mapping process to generate not only the constraints but also the relationship in the **DataSet**.</span></span> <span data-ttu-id="199f3-111">Sin embargo, si especifica `msdata:ConstraintOnly="true"` en el **keyref** elemento, el **DataSet** sólo incluirá las restricciones y no incluirá la relación.</span><span class="sxs-lookup"><span data-stu-id="199f3-111">However, if you specify `msdata:ConstraintOnly="true"` in the **keyref** element, the **DataSet** will include only the constraints and will not include the relationship.</span></span>  
  
 <span data-ttu-id="199f3-112">En el ejemplo siguiente se muestra un esquema XML que incluye **orden** y **OrderDetail** elementos, que no están anidados.</span><span class="sxs-lookup"><span data-stu-id="199f3-112">The following example shows an XML Schema that includes **Order** and **OrderDetail** elements, which are not nested.</span></span> <span data-ttu-id="199f3-113">El esquema también especifica restricciones key y keyref.</span><span class="sxs-lookup"><span data-stu-id="199f3-113">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="199f3-114">El **DataSet** que se genera durante el esquema XML incluye el proceso de asignación del **orden** y **OrderDetail** tablas.</span><span class="sxs-lookup"><span data-stu-id="199f3-114">The **DataSet** that is generated during the XML Schema mapping process includes the **Order** and **OrderDetail** tables.</span></span> <span data-ttu-id="199f3-115">Además, el **DataSet** incluye relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="199f3-115">In addition, the **DataSet** includes relationships and constraints.</span></span> <span data-ttu-id="199f3-116">En el siguiente ejemplo se muestran estas relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="199f3-116">The following example shows these relationships and constraints.</span></span> <span data-ttu-id="199f3-117">Tenga en cuenta que el esquema no especifica la **msdata: Relationship** anotación; en su lugar, las restricciones key y keyref se utilizan para generar la relación.</span><span class="sxs-lookup"><span data-stu-id="199f3-117">Note that the schema does not specify the **msdata:Relationship** annotation; instead, the key and keyref constraints are used to generate the relation.</span></span>  
  
```  
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
  
 <span data-ttu-id="199f3-118">En el ejemplo de esquema anterior, el **orden** y **OrderDetail** elementos no están anidados.</span><span class="sxs-lookup"><span data-stu-id="199f3-118">In the previous schema example, the **Order** and **OrderDetail** elements are not nested.</span></span> <span data-ttu-id="199f3-119">En el siguiente ejemplo de esquema, estos elementos están anidados.</span><span class="sxs-lookup"><span data-stu-id="199f3-119">In the following schema example, these elements are nested.</span></span> <span data-ttu-id="199f3-120">Sin embargo, no hay **msdata: Relationship** anotación se especifica; por lo tanto, se supone una relación implícita.</span><span class="sxs-lookup"><span data-stu-id="199f3-120">However, no **msdata:Relationship** annotation is specified; therefore, an implicit relation is assumed.</span></span> <span data-ttu-id="199f3-121">Para obtener más información, consulte [asignación implícita relaciones entre elementos de esquema anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span><span class="sxs-lookup"><span data-stu-id="199f3-121">For more information, see [Map Implicit Relations Between Nested Schema Elements](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md).</span></span> <span data-ttu-id="199f3-122">El esquema también especifica restricciones key y keyref.</span><span class="sxs-lookup"><span data-stu-id="199f3-122">The schema also specifies key and keyref constraints.</span></span>  
  
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
  
 <span data-ttu-id="199f3-123">El **DataSet** resultante del proceso de asignación del esquema XML incluye dos tablas:</span><span class="sxs-lookup"><span data-stu-id="199f3-123">The **DataSet** resulting from the XML Schema mapping process includes two tables:</span></span>  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 <span data-ttu-id="199f3-124">El **DataSet** también incluye las dos relaciones (uno basado en la **msdata: Relationship** anotación y otro en función de las restricciones key y keyref) y varias restricciones.</span><span class="sxs-lookup"><span data-stu-id="199f3-124">The **DataSet** also includes the two relationships (one based on the **msdata:relationship** annotation and the other based on the key and keyref constraints) and various constraints.</span></span> <span data-ttu-id="199f3-125">En el siguiente ejemplo se muestran las relaciones y restricciones.</span><span class="sxs-lookup"><span data-stu-id="199f3-125">The following example shows the relations and constraints.</span></span>  
  
```  
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
  
 <span data-ttu-id="199f3-126">Si una restricción keyref que hace referencia a una tabla anidada contiene el **msdata: IsNested = "true"** anotación, la **DataSet** creará una única relación anidada basada en la restricción keyref y relacionados con la restricción unique/key.</span><span class="sxs-lookup"><span data-stu-id="199f3-126">If a keyref constraint referring to a nested table contains the **msdata:IsNested="true"** annotation, the **DataSet** will create a single nested relationship that is based on the keyref constraint and the related unique/key constraint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199f3-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="199f3-127">See Also</span></span>  
 [<span data-ttu-id="199f3-128">Derivación de una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)</span><span class="sxs-lookup"><span data-stu-id="199f3-128">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="199f3-129">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="199f3-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
