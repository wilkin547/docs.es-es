---
title: Restricciones y relaciones del esquema XML
ms.date: 03/30/2017
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
ms.openlocfilehash: 2388d7c277ba1f01bea8d419e5aedf487b843ed7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150719"
---
# <a name="xml-schema-constraints-and-relationships"></a>Restricciones y relaciones del esquema XML
En un esquema de lenguaje de definición de esquemas XML (XSD), puede especificar restricciones (restricciones únicas, clave y keyref) y relaciones (mediante la anotación **msdata:Relationship).** En este tema se explica cómo se interpretan las restricciones y relaciones especificadas en un esquema XML para generar el <xref:System.Data.DataSet>.  
  
 En general, en un esquema XML, especifique la anotación **msdata:Relationship** si desea generar solo relaciones en el **conjunto de datos**. Para obtener más información, vea Generar relaciones de [conjunto de datos a partir de esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md). Especifique restricciones (únicas, clave y keyref) si desea generar restricciones en el **conjunto de datos**. Tenga en cuenta que las restricciones key y keyref también se utilizan para generar relaciones, como se explica más adelante en este tema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generar una relación a partir de restricciones key y keyref  
 En lugar de especificar la anotación **msdata:Relationship,** puede especificar restricciones key y keyref, que se utilizan durante el proceso de asignación de esquemas XML para generar no solo las restricciones, sino también la relación en el **conjunto**de datos . Sin embargo, `msdata:ConstraintOnly="true"` si especifica en el elemento **keyref,** el **DataSet** incluirá solo las restricciones y no incluirá la relación.  
  
 En el ejemplo siguiente se muestra un esquema XML que incluye **Order** y **OrderDetail** elementos, que no están anidados. El esquema también especifica restricciones key y keyref.  
  
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
  
 El **DataSet** que se genera durante el proceso de asignación de esquema XML incluye el **Order** y **OrderDetail** tablas. Además, el **DataSet** incluye relaciones y restricciones. En el siguiente ejemplo se muestran estas relaciones y restricciones. Tenga en cuenta que el esquema no especifica la anotación **msdata:Relationship;** en su lugar, las restricciones key y keyref se utilizan para generar la relación.  
  
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
  
 En el ejemplo de esquema anterior, los elementos **Order** y **OrderDetail** no están anidados. En el siguiente ejemplo de esquema, estos elementos están anidados. Sin embargo, no se especifica ninguna anotación **msdata:Relationship;** por lo tanto, se asume una relación implícita. Para obtener más información, vea [Asignar relaciones implícitas entre elementos](map-implicit-relations-between-nested-schema-elements.md)de esquema anidados . El esquema también especifica restricciones key y keyref.  
  
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
  
 El **DataSet** resultante del proceso de asignación de esquemas XML incluye dos tablas:  
  
```text  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 El **DataSet** también incluye las dos relaciones (una basada en la anotación **msdata:relationship** y la otra basada en las restricciones key y keyref) y varias restricciones. En el siguiente ejemplo se muestran las relaciones y restricciones.  
  
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
  
 Si una restricción keyref que hace referencia a una tabla anidada contiene la anotación **msdata:IsNested-"true",** el **DataSet** creará una única relación anidada que se basa en la restricción keyref y la restricción única/clave relacionada.  
  
## <a name="see-also"></a>Consulte también

- [Derivar una estructura relacional de un conjunto de datos a partir de un esquema XML (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
