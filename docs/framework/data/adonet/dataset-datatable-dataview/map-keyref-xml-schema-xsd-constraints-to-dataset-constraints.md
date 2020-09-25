---
title: Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 5b634fea-cc1e-4f6b-9454-10858105b1c8
ms.openlocfilehash: fe53232b6818b5bb28b433c4a473b6381b8e9083
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198566"
---
# <a name="map-keyref-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEYREF de un esquema XML (XSD) a restricciones de conjuntos de datos

El elemento **keyref** permite establecer vínculos entre los elementos de un documento. Esto es similar a una relación de clave externa en una base de datos relacional. Si un esquema especifica el elemento **keyref** , el elemento se convierte durante el proceso de asignación de esquemas en una restricción de clave externa correspondiente en las columnas de las tablas de <xref:System.Data.DataSet> . De forma predeterminada, el elemento **keyref** genera también una relación, con las propiedades **ParentTable**, **ChildTable**, **ParentColumn**y **ChildColumn** especificadas en la relación.  
  
 En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **keyref** .  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintOnly**|Si **ConstraintOnly = "true"** se especifica en el elemento **keyref** del esquema, se crea una restricción, pero no se crea ninguna relación. Si no se especifica este atributo (o se establece en **false**), tanto la restricción como la relación se crean en el **conjunto de DataSet**.|  
|**msdata:ConstraintName**|Si se especifica el atributo **ConstraintName** , su valor se utiliza como nombre de la restricción. De lo contrario, el atributo **Name** del elemento **keyref** del esquema proporciona el nombre de la restricción en el **conjunto**de elementos.|  
|**msdata:UpdateRule**|Si el atributo **UpdateRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **UpdateRule** del **conjunto**de elementos. En caso contrario, la propiedad **UpdateRule** está establecida en **Cascade**.|  
|**msdata:DeleteRule**|Si el atributo **DeleteRule** se especifica en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **DeleteRule** del **conjunto**de elementos. De lo contrario, la propiedad **DeleteRule** se establece como **Cascade**.|  
|**msdata:AcceptRejectRule**|Si se especifica el atributo **AcceptRejectRule** en el elemento **keyref** del esquema, su valor se asigna a la propiedad de restricción **AcceptRejectRule** en el **conjunto**de elementos. En caso contrario, la propiedad **AcceptRejectRule** está establecida en **None**.|  
  
 El ejemplo siguiente contiene un esquema que especifica las relaciones de **clave** y **keyref** entre el elemento secundario **OrderNumber** del elemento **Order** y el elemento secundario **OrderNo** del elemento **OrderDetail** .  
  
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
  
```text  
OrderDetail(OrderNo, ItemNo) and  
Order(OrderNumber, EmpNumber)  
```  
  
 Además, el **conjunto** de elementos define las siguientes restricciones:  
  
- Una restricción UNIQUE en la tabla **Order** .  
  
    ```text
              Table: Order  
    Columns: OrderNumber
    ConstraintName: OrderNumberKey  
    Type: UniqueConstraint  
    IsPrimaryKey: False  
    ```  
  
- Una relación entre las tablas **Order** y **OrderDetail** . La propiedad **Nested** se establece en **false** porque los dos elementos no están anidados en el esquema.  
  
    ```text
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
  
    ```text  
              ConstraintName: OrderNoRef  
    Type: ForeignKeyConstraint  
    Table: OrderDetail  
    Columns: OrderNo
    RelatedTable: Order  
    RelatedColumns: OrderNumber
    ```  
  
## <a name="see-also"></a>Consulte también

- [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generar relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
