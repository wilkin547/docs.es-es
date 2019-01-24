---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: bc3863bbe6fd7c290c25056e2420107ed2d8bff3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732809"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
El **keyref** elemento le permite establecer vínculos entre elementos dentro de un documento. Esto es similar a una relación de clave externa en una base de datos relacional. Si especifica un esquema de la **keyref** elemento, el elemento se convierte durante el proceso de asignación de esquema para una restricción de clave externa correspondiente en las columnas de las tablas de la <xref:System.Data.DataSet>. De forma predeterminada, el **keyref** elemento también genera una relación con el **ParentTable**, **ChildTable**, **ParentColumn**y  **ChildColumn** propiedades especificadas en la relación.  
  
 La siguiente tabla se describen los **msdata** atributos que puede especificar en el **keyref** elemento.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Si **ConstraintOnly = "true"** se especifica en el **keyref** elemento en el esquema, se crea una restricción, pero se crea ninguna relación. Si no se especifica este atributo (o se establece en **False**), la restricción y la relación se crean en el **DataSet**.|  
|**msdata:ConstraintName**|Si el **ConstraintName** atributo se especifica, su valor se utiliza como el nombre de la restricción. En caso contrario, el **nombre** atributo de la **keyref** elemento en el esquema proporciona el nombre de la restricción en el **DataSet**.|  
|**msdata:UpdateRule**|Si el **UpdateRule** atributo se especifica en el **keyref** elemento del esquema, su valor se asigna a la **UpdateRule** propiedad de restricción del  **Conjunto de datos**. En caso contrario, el **UpdateRule** propiedad está establecida en **Cascade**.|  
|**msdata:DeleteRule**|Si el **DeleteRule** atributo se especifica en el **keyref** elemento del esquema, su valor se asigna a la **DeleteRule** propiedad de restricción del  **Conjunto de datos**. En caso contrario, el **DeleteRule** propiedad está establecida en **Cascade**.|  
|**msdata:AcceptRejectRule**|Si el **AcceptRejectRule** atributo se especifica en el **keyref** elemento del esquema, su valor se asigna a la **AcceptRejectRule** el propiedadderestricción **Conjunto de datos**. En caso contrario, el **AcceptRejectRule** propiedad está establecida en **ninguno**.|  
  
 El ejemplo siguiente contiene un esquema que especifica el **clave** y **keyref** relaciones entre la **OrderNumber** elemento secundario de la **orden**  elemento y el **OrderNo** elemento secundario de la **OrderDetail** elemento.  
  
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
  
 El proceso de asignación de esquema de lenguaje (XSD) de esquema XML definición produce el siguiente **DataSet** con dos tablas:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Además, el **DataSet** define las restricciones siguientes:  
  
-   Una restricción unique en la **orden** tabla.  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
-   Una relación entre el **orden** y **OrderDetail** tablas. El **Nested** propiedad está establecida en **False** porque los dos elementos no están anidados en el esquema.  
  
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
  
-   Una restricción foreign key en el **OrderDetail** tabla.  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Vea también
- [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
