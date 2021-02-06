---
description: Más información acerca de cómo asignar relaciones implícitas entre elementos de esquema anidados
title: Asignar relaciones implícitas entre elementos de esquema anidados
ms.date: 03/30/2017
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
ms.openlocfilehash: 418dd1210674b2c592cf96c6d369bc43f8dcab9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652021"
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Asignar relaciones implícitas entre elementos de esquema anidados

Un esquema del lenguaje de definición de esquema XML (XSD) puede tener tipos complejos anidados dentro de otros. En este caso, el proceso de asignación aplica la asignación predeterminada y crea lo siguiente en el <xref:System.Data.DataSet>:  
  
- Una tabla para cada uno de los tipos complejos (primario y secundario).  
  
- Si no existe ninguna restricción UNIQUE en el elemento principal, una columna de clave principal adicional por cada definición de tabla denominada *tablename* _Id donde *TableName* es el nombre de la tabla primaria.  
  
- Una restricción primary key en la tabla primaria que identifica la columna adicional como clave principal (estableciendo la propiedad **IsPrimaryKey** en **true**). La restricción recibe el nombre Constraint\#, donde \# es 1, 2, 3, etc. Por ejemplo, el nombre predeterminado de la primera restricción es Constraint1.  
  
- Una restricción de clave externa en la tabla secundaria que identifica la columna adicional como clave externa que hace referencia a la clave principal de la tabla primaria. La restricción se denomina *ParentTable_ChildTable* donde *ParentTable* es el nombre de la tabla primaria y *ChildTable* es el nombre de la tabla secundaria.  
  
- Una relación de datos entre las tablas primaria y secundaria.  
  
 En el ejemplo siguiente se muestra un esquema en el que **OrderDetail** es un elemento secundario de **Order**.  
  
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
            <xs:element name="OrderNumber" type="xs:string" />  
            <xs:element name="EmpNumber" type="xs:string" />  
            <xs:element name="OrderDetail">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="OrderNo" type="xs:string" />  
                  <xs:element name="ItemNo" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
          </xs:sequence>  
         </xs:complexType>  
       </xs:element>  
     </xs:choice>  
   </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 El proceso de asignación del esquema XML crea lo siguiente en el **conjunto** de elementos:  
  
- Un **pedido** y una tabla **OrderDetail** .  
  
    ```text  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
- Una restricción UNIQUE en la tabla **Order** . Tenga en cuenta que la propiedad **IsPrimaryKey** está establecida en **true**.  
  
    ```text  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id
    IsPrimaryKey: True  
    ```  
  
- Una restricción FOREIGN KEY en la tabla **OrderDetail** .  
  
    ```text  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id
    RelatedTable: Order  
    RelatedColumns: Order_Id
    ```  
  
- Una relación entre las tablas **Order** y **OrderDetail** . La propiedad **Nested** de esta relación está establecida en **true** porque los elementos **Order** y **OrderDetail** están anidados en el esquema.  
  
    ```text  
    ParentTable: Order  
    ParentColumns: Order_Id
    ChildTable: OrderDetail  
    ChildColumns: Order_Id
    ParentKeyConstraint: Constraint1  
    ChildKeyConstraint: Order_OrderDetail  
    RelationName: Order_OrderDetail  
    Nested: True  
    ```  
  
## <a name="see-also"></a>Vea también

- [Generar relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Información general de ADO.NET](../ado-net-overview.md)
