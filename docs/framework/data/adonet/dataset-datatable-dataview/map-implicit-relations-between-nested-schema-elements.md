---
title: "Asignar relaciones impl&#237;citas entre elementos de esquema anidados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6b25002a-352e-4d9b-bae3-15129458a355
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar relaciones impl&#237;citas entre elementos de esquema anidados
Un esquema del lenguaje de definición de esquema XML \(XSD\) puede tener tipos complejos anidados dentro de otros.  En este caso, el proceso de asignación aplica la asignación predeterminada y crea lo siguiente en el <xref:System.Data.DataSet>:  
  
-   Una tabla para cada uno de los tipos complejos \(primario y secundario\).  
  
-   Si no existe una restricción única en el primario, crea una columna clave principal adicional llamada *TableName*\_Id, donde *TableName* es el nombre de la tabla primaria.  
  
-   Una restricción de clave principal en la tabla primaria que identifica la columna adicional como clave primaria \(la propiedad **IsPrimaryKey** se establece como **True**\).  La restricción recibe el nombre Constraint*\#*, donde *\#* es 1, 2, 3, etc.  Por ejemplo, el nombre predeterminado de la primera restricción es Constraint1.  
  
-   Una restricción de clave externa en la tabla secundaria que identifica la columna adicional como clave externa que hace referencia a la clave principal de la tabla primaria.  La restricción recibe el nombre *ParentTable\_ChildTable*, donde *ParentTable* es el nombre de la tabla primaria y *ChildTable* es el nombre de la tabla secundaria.  
  
-   Una relación de datos entre las tablas primaria y secundaria.  
  
 En el siguiente ejemplo se muestra un esquema donde **OrderDetail** es un elemento secundario de **Order**.  
  
```  
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
  
 El proceso de asignación del esquema XML crea lo siguiente en el **DataSet**:  
  
-   Una tabla **Order** y una tabla **OrderDetail**.  
  
    ```  
    Order(OrderNumber, EmpNumber, Order_Id)  
    OrderDetail(OrderNo, ItemNo, Order_Id)  
    ```  
  
-   Una restricción única en la tabla **Order**.  Tenga en cuenta que la propiedad **IsPrimaryKey** tiene el valor **True**.  
  
    ```  
    ConstraintName: Constraint1  
    Type: UniqueConstraint  
    Table: Order  
    Columns: Order_Id   
    IsPrimaryKey: True  
    ```  
  
-   Una restricción de clave externa en la tabla **OrderDetail**.  
  
    ```  
    ConstraintName: Order_OrderDetail  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: Order_Id   
    RelatedTable: Order  
    RelatedColumns: Order_Id   
    ```  
  
-   Una relación entre las tablas **Order** y **OrderDetail**.  La propiedad **Nested** de esta relación tiene el valor **True**, ya que los elementos **Order** y **OrderDetail** están anidados en el esquema.  
  
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
  
## Vea también  
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)