---
title: "Asignar restricciones keyref de esquema XML (XSD) a las restricciones de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar restricciones keyref de esquema XML (XSD) a las restricciones de DataSet
El elemento **keyref** permite establecer vínculos entre elementos dentro de un documento.  Esto es similar a una relación de clave externa en una base de datos relacional.  Si un esquema especifica el elemento **keyref**, durante el proceso de asignación del esquema el elemento se convertirá en una restricción de clave externa correspondiente en las columnas de las tablas del <xref:System.Data.DataSet>.  De manera predeterminada, el elemento **keyref** genera también una relación donde se especifican las propiedades **ParentTable**, **ChildTable**, **ParentColumn** y **ChildColumn**.  
  
 En la siguiente tabla se describen los atributos **msdata** que puede especificar en el elemento **keyref**.  
  
|Nombre del atributo|Descripción|  
|-------------------------|-----------------|  
|**msdata:ConstraintOnly**|Si se especifica **ConstraintOnly\="true"** en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación.  Si no se especifica este atributo \(o si se establece como **False**\), tanto la restricción como la relación se crearán en el **DataSet**.|  
|**msdata:ConstraintName**|Si se especifica el atributo **ConstraintName**, su valor se utiliza como nombre de la restricción.  De lo contrario, el atributo **name** del elemento **keyref** del esquema proporciona el nombre de restricción del **DataSet**.|  
|**msdata:UpdateRule**|Si se especifica el atributo **UpdateRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** del **DataSet**.  De lo contrario, la propiedad **UpdateRule** se establece como **Cascade**.|  
|**msdata:DeleteRule**|Si se especifica el atributo **DeleteRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** del **DataSet**.  De lo contrario, la propiedad **DeleteRule** se establece como **Cascade**.|  
|**msdata:AcceptRejectRule**|Si se especifica el atributo **AcceptRejectRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **AcceptRejectRule** del **DataSet**.  De lo contrario, la propiedad **AcceptRejectRule** se establece como **None**.|  
  
 El ejemplo siguiente contiene un esquema que especifica las relaciones **key** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** del elemento **OrderDetail**.  
  
 En el ejemplo, el elemento secundario **OrderNumber** del elemento **OrderDetail** hace referencia al elemento secundario de clave **OrderNo** del elemento **Order**.  
  
```  
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
  
 El proceso de asignación del esquema del lenguaje de definición de esquemas XML \(XSD\) crea el siguiente **DataSet** con dos tablas:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Además, el **DataSet** define las restricciones siguientes:  
  
-   Una restricción única en la tabla **Order**.  
  
    ```  
  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Una relación entre las tablas **Order** y **OrderDetail**.  La propiedad **Nested** se establece como **False** porque los dos elementos no están anidados en el esquema.  
  
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
  
-   Una restricción de clave externa en la tabla **OrderDetail**.  
  
    ```  
  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## Vea también  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)