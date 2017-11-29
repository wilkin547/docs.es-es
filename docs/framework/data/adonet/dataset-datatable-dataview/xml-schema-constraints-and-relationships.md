---
title: Restricciones y relaciones del esquema XML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 165bc2bc-60a1-40e0-9b89-7c68ef979079
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a324c3b7f24d3395382067ea5581313af58e13f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xml-schema-constraints-and-relationships"></a>Restricciones y relaciones del esquema XML
En un esquema (XSD) de lenguaje de definición de esquemas XML, puede especificar restricciones (unique, restricciones key y keyref) y relaciones (mediante la **msdata: Relationship** anotación). En este tema se explica cómo se interpretan las restricciones y relaciones especificadas en un esquema XML para generar el <xref:System.Data.DataSet>.  
  
 En general, en un esquema XML, especifique la **msdata: Relationship** anotación si desea generar únicamente relaciones en el **conjunto de datos**. Para obtener más información, consulte [relaciones de conjunto de datos de generación de esquemas XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md). Especificar restricciones (unique, key y keyref) si desea generar restricciones en el **conjunto de datos**. Tenga en cuenta que las restricciones key y keyref también se utilizan para generar relaciones, como se explica más adelante en este tema.  
  
## <a name="generating-a-relationship-from-key-and-keyref-constraints"></a>Generar una relación a partir de restricciones key y keyref  
 En lugar de especificar el **msdata: Relationship** anotación, puede especificar restricciones key y keyref que se utilizarán durante el proceso de asignación de esquema XML para generar no sólo las restricciones, sino también la relación en la  **Conjunto de datos**. Sin embargo, si especifica `msdata:ConstraintOnly="true"` en el **keyref** elemento, el **conjunto de datos** sólo incluirá las restricciones y no incluirá la relación.  
  
 En el ejemplo siguiente se muestra un esquema XML que incluye **orden** y **OrderDetail** elementos, que no están anidados. El esquema también especifica restricciones key y keyref.  
  
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
  
 El **conjunto de datos** que se genera durante el esquema XML del proceso de asignación incluye la **orden** y **OrderDetail** tablas. Además, el **conjunto de datos** incluye relaciones y restricciones. En el siguiente ejemplo se muestran estas relaciones y restricciones. Tenga en cuenta que el esquema no especifica la **msdata: Relationship** anotación; en su lugar, se utilizan las restricciones key y keyref para generar la relación.  
  
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
  
 En el ejemplo de esquema anterior, el **orden** y **OrderDetail** elementos no están anidados. En el siguiente ejemplo de esquema, estos elementos están anidados. Sin embargo, no **msdata: Relationship** anotación se especifica; por lo tanto, se supone una relación implícita. Para obtener más información, consulte [asignación implícita relaciones entre elementos de esquema anidados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-implicit-relations-between-nested-schema-elements.md). El esquema también especifica restricciones key y keyref.  
  
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
  
 El **conjunto de datos** resultante del proceso de asignación del esquema XML incluye dos tablas:  
  
```  
Order(OrderNumber, EmpNumber, Order_Id)  
OrderDetail(OrderNumber, ItemNumber, Order_Id)  
```  
  
 El **conjunto de datos** incluye también las dos relaciones (una basada en la **msdata: Relationship** anotación y otra basada en las restricciones key y keyref) y varias restricciones. En el siguiente ejemplo se muestran las relaciones y restricciones.  
  
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
  
 Si una restricción keyref que hace referencia a una tabla anidada contiene el **msdata: IsNested = "true"** anotación, la **conjunto de datos** creará una única relación anidada basada en la restricción keyref y relacionados con la restricción unique/key.  
  
## <a name="see-also"></a>Vea también  
 [Derivar la estructura relacional de un conjunto de datos de esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
