---
title: "Asignar relaciones implícitas entre elementos de esquema anidados"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 740d45c47f46c311ed703fa11ec86a9739930944
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="map-implicit-relations-between-nested-schema-elements"></a>Asignar relaciones implícitas entre elementos de esquema anidados
Un esquema del lenguaje de definición de esquema XML (XSD) puede tener tipos complejos anidados dentro de otros. En este caso, el proceso de asignación aplica la asignación predeterminada y crea lo siguiente en el <xref:System.Data.DataSet>:  
  
-   Una tabla para cada uno de los tipos complejos (primario y secundario).  
  
-   Si no existe ninguna restricción única en el elemento primario, una columna de clave principal adicional por cada definición de tabla denominada *TableName*_Id donde *TableName* es el nombre de la tabla primaria.  
  
-   Una restricción primary key en la tabla primaria que identifica la columna adicional como clave principal (estableciendo la **IsPrimaryKey** propiedad **True**). La restricción recibe el nombre Constraint *#*  donde  *#*  es 1, 2, 3 y así sucesivamente. Por ejemplo, el nombre predeterminado de la primera restricción es Constraint1.  
  
-   Una restricción de clave externa en la tabla secundaria que identifica la columna adicional como clave externa que hace referencia a la clave principal de la tabla primaria. La restricción recibe el nombre *ParentTable_ChildTable* donde *ParentTable* es el nombre de la tabla primaria y *ChildTable* es el nombre de la tabla secundaria.  
  
-   Una relación de datos entre las tablas primaria y secundaria.  
  
 En el ejemplo siguiente se muestra un esquema donde **OrderDetail** es un elemento secundario de **orden**.  
  
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
  
 El proceso de asignación de esquema XML crea lo siguiente en el **conjunto de datos**:  
  
-   Un **orden** y **OrderDetail** tabla.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Una restricción unique en la **orden** tabla. Tenga en cuenta que la **IsPrimaryKey** propiedad está establecida en **True**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Una restricción foreign key en la **OrderDetail** tabla.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Una relación entre la **orden** y **OrderDetail** tablas. El **Nested** propiedad para esta relación se establece en **True** porque el **orden** y **OrderDetail** elementos están anidados en el esquema .  
  
    ```  
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
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
