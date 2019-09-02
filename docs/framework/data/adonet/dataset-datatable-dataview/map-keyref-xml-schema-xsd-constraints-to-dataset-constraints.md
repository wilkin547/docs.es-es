---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: 611322065a4df53d1a3149ef4e1ca5592f149081
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203440"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
El elemento **keyref** permite establecer vínculos entre los elementos de un documento. Esto es similar a una relación de clave externa en una base de datos relacional. Si un esquema especifica el elemento **keyref** , el elemento se convierte durante el proceso de asignación de esquemas en una restricción de clave externa correspondiente en las columnas de <xref:System.Data.DataSet>las tablas de. De forma predeterminada, el elemento **keyref** genera también una relación, con las propiedades **ParentTable**, **ChildTable**, **ParentColumn**y **ChildColumn** especificadas en la relación.  
  
 En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **keyref** .  
  
|Nombre del atributo|DESCRIPCIÓN|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Si **ConstraintOnly = "true"** se especifica en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación. Si no se especifica este atributo (o se establece en **false**), tanto la restricción como la relación se crean en el **conjunto de DataSet**.|  
|**msdata:ConstraintName**|Si se especifica el atributo **ConstraintName** , su valor se utiliza como nombre de la restricción. De lo contrario, el atributo **Name** del elemento **keyref** del esquema proporciona el nombre de la restricción en el **conjunto**de elementos.|  
|**msdata:UpdateRule**|Si el atributo **UpdateRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** del **conjunto**de elementos. En caso contrario, la propiedad **UpdateRule** está establecida en **Cascade**.|  
|**msdata:DeleteRule**|Si el atributo **DeleteRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** del **conjunto**de elementos. De lo contrario, la propiedad **DeleteRule** se establece como **Cascade**.|  
|**msdata:AcceptRejectRule**|Si se especifica el atributo **AcceptRejectRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **AcceptRejectRule** en el **conjunto**de elementos. En caso contrario, la propiedad **AcceptRejectRule** está establecida en **None**.|  
  
 El ejemplo siguiente contiene un esquema que especifica las relaciones de **clave** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** de **OrderDetail** . Element.  
  
 En el ejemplo, el elemento secundario **OrderNumber** del elemento **OrderDetail** hace referencia al elemento secundario **OrderNo** Key del elemento **Order** .  
  
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
  
 El proceso de asignación del esquema del lenguaje de definición de esquemas XML (XSD) genera el siguiente **conjunto** de elementos con dos tablas:  
  
```  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Además, el **conjunto** de elementos define las siguientes restricciones:  
  
- Una restricción UNIQUE en la tabla **Order** .  
  
    ```  
              Table: Order  
    Columns: OrderNumber   
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Una relación entre las tablas **Order** y **OrderDetail** . La propiedad Nested se establece en **false** porque los dos elementos no están anidados en el esquema.  
  
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
  
- Una restricción FOREIGN KEY en la tabla **OrderDetail** .  
  
    ```  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo   
    RelatedTable: Order  
    RelatedColumns: OrderNumber   
    ```  
  
## <a name="see-also"></a>Vea también

- [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
