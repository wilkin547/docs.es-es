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
# <a name="xml-schema-constraints-and-relationships"></a>Restricciones y relaciones del esquema XML

En un esquema del lenguaje de definición de esquemas XML (XSD), puede especificar las restricciones (Unique, Key y keyref) y las relaciones (mediante la anotación **msdata: Relationship** ). En este tema se explica cómo se interpretan las restricciones y relaciones especificadas en un esquema XML para generar el <xref:System.Data.DataSet>.  
  
 En general, en un esquema XML, se especifica la anotación **msdata: Relationship** si se desea generar solo relaciones en el **DataSet**. Para obtener más información, vea [generar relaciones de conjunto de datos a partir de un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Puede especificar restricciones (Unique, Key y keyref) Si desea generar restricciones en el **conjunto de DataSet**. Tenga en cuenta que las restricciones key y keyref también se utilizan para generar relaciones, como se explica más adelante en este tema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generar una relación a partir de restricciones key y keyref  

 En lugar de especificar la anotación **msdata: Relationship** , puede especificar las restricciones Key y keyref, que se utilizan durante el proceso de asignación del esquema XML para generar no solo las restricciones, sino también la relación en el **DataSet**. Sin embargo, si especifica `msdata:ConstraintOnly="true"` en el elemento **keyref** , el **conjunto** de elementos solo incluirá las restricciones y no incluirá la relación.  
  
 En el ejemplo siguiente se muestra un esquema XML que incluye los elementos **Order** y **OrderDetail** , que no están anidados. El esquema también especifica restricciones key y keyref.  
  
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
  
 El **DataSet** que se genera durante el proceso de asignación del esquema XML incluye las tablas **Order** y **OrderDetail** . Además, el **conjunto** de elementos incluye relaciones y restricciones. En el siguiente ejemplo se muestran estas relaciones y restricciones. Tenga en cuenta que el esquema no especifica la anotación **msdata: Relationship** ; en su lugar, se usan las restricciones Key y keyref para generar la relación.  
  
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
  
 En el ejemplo de esquema anterior, los elementos **Order** y **OrderDetail** no están anidados. En el siguiente ejemplo de esquema, estos elementos están anidados. Sin embargo, no se especifica ninguna anotación **msdata: Relationship** ; por lo tanto, se supone una relación implícita. Para obtener más información, vea [asignar relaciones implícitas entre elementos de esquema anidados](map-implicit-relations-between-nested-schema-elements.md). El esquema también especifica restricciones key y keyref.  
  
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
  
 El **conjunto** de resultados resultante del proceso de asignación de esquemas XML incluye dos tablas:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 El **DataSet** también incluye las dos relaciones (una basada en la anotación **msdata: Relationship** y la otra basándose en las restricciones Key y keyref) y varias restricciones. En el siguiente ejemplo se muestran las relaciones y restricciones.  
  
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
  
 Si una restricción keyref que hace referencia a una tabla anidada contiene la anotación **msdata: IsNested = "true"** , el **conjunto de DataSet** creará una única relación anidada basada en la restricción keyref y en la restricción UNIQUE/Key relacionada.  
  
## <a name="see-also"></a>Vea también

- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
