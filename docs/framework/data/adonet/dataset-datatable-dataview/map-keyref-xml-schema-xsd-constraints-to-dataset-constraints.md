---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 4ca72292bd2c43fec6f3833d521ddb83c01c32c9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
El **keyref** elemento permite establecer vínculos entre elementos dentro de un documento. Esto es similar a una relación de clave externa en una base de datos relacional. Si un esquema especifica la **keyref** elemento, el elemento se convierte durante el proceso de asignación de esquema para una restricción de clave externa correspondiente en las columnas de las tablas de la <xref:System.Data.DataSet>. De forma predeterminada, el **keyref** elemento también genera una relación con la **ParentTable**, **ChildTable**, **ParentColumn**y  **ChildColumn** propiedades especificadas en la relación.  
  
 La siguiente tabla se describen los **msdata** atributos que puede especificar en el **keyref** elemento.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata: ConstraintOnly**|Si **ConstraintOnly = "true"** se especifica en el **keyref** elemento en el esquema, se crea una restricción, pero se crea ninguna relación. Si no se especifica este atributo (o se establece en **False**), tanto la restricción como la relación se crean en el **conjunto de datos**.|  
|**msdata: ConstraintName**|Si el **ConstraintName** atributo se especifica, su valor se utiliza como el nombre de la restricción. En caso contrario, el **nombre** atributo de la **keyref** elemento en el esquema proporciona el nombre de restricción en la **conjunto de datos**.|  
|**msdata:UpdateRule**|Si el **UpdateRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **UpdateRule** propiedad de restricción en la  **Conjunto de datos**. En caso contrario, el **UpdateRule** propiedad está establecida en **Cascade**.|  
|**msdata:DeleteRule**|Si el **DeleteRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **DeleteRule** propiedad de restricción en la  **Conjunto de datos**. En caso contrario, el **DeleteRule** propiedad está establecida en **Cascade**.|  
|**msdata:AcceptRejectRule**|Si el **AcceptRejectRule** atributo se especifica en el **keyref** elemento en el esquema, su valor se asigna a la **AcceptRejectRule** propiedad de restricción en la  **Conjunto de datos**. En caso contrario, el **AcceptRejectRule** propiedad está establecida en **ninguno**.|  
  
 El ejemplo siguiente contiene un esquema que especifica la **clave** y **keyref** las relaciones entre la **OrderNumber** elemento secundario de la **orden**  elemento y el **OrderNo** elemento secundario de la **OrderDetail** elemento.  
  
 En el ejemplo, el **OrderNumber** elemento secundario de la **OrderDetail** elemento hace referencia a la **OrderNo** elemento secundario de clave de la **orden**elemento.  
  
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
  
 El proceso de asignación de esquema de lenguaje (XSD) de esquema XML definición produce el siguiente **conjunto de datos** con dos tablas:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Además, el **conjunto de datos** define las restricciones siguientes:  
  
-   Una restricción unique en la **orden** tabla.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Una relación entre la **orden** y **OrderDetail** tablas. El **Nested** propiedad está establecida en **False** porque los dos elementos no están anidados en el esquema.  
  
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
  
-   Una restricción foreign key en la **OrderDetail** tabla.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Vea también  
 [Asignar restricciones de esquema (XSD) de XML a las restricciones de conjunto de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generar las relaciones de conjunto de datos desde un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
