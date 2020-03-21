---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: 5ebf333b065157fa9497cc1471a45698663638e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150940"
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante el elemento **key.** El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.  
  
 La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.  
  
 En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **key.**  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente, la propiedad de restricción **IsPrimaryKey** se establece en **true,** lo que la convierte en una clave principal. La propiedad de columna **AllowDBNull** se establece en **false**, porque las claves principales no pueden tener valores NULL.|  
  
 Al convertir el esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción única en la tabla con la propiedad de columna **AllowDBNull** establecida en **false** para cada columna de la restricción. La propiedad **IsPrimaryKey** de la restricción unique también `msdata:PrimaryKey="true"` se establece en **false** a menos que haya especificado en el elemento **de clave.** Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.  
  
 En el ejemplo de esquema siguiente, el elemento **key** especifica la restricción key en el elemento **CustomerID.**  
  
```xml  
<xs:schema id="cod"  
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
        <xs:element name="CompanyName" type="xs:string" minOccurs="0" />  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
<xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:key  msdata:PrimaryKey="true"  
       msdata:ConstraintName="KeyCustID"  
          name="KeyConstCustomerID" >  
     <xs:selector xpath=".//Customers" />  
     <xs:field xpath="CustomerID" />  
    </xs:key>  
 </xs:element>  
</xs:schema>
```  
  
 El elemento **key** especifica que los valores del elemento secundario **CustomerID** del elemento **Customers** deben tener valores únicos y no pueden tener valores null. Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:  
  
```text  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 La asignación de esquema XML también crea un **UniqueConstraint** <xref:System.Data.DataSet>en la columna **CustomerID,** como se muestra en el siguiente archivo . Para simplificar, sólo se muestran las propiedades relevantes.  
  
```text  
      DataSetName: MyDataSet  
TableName: customers  
  ColumnName: CustomerID  
      AllowDBNull: False  
      Unique: True  
  ConstraintName: KeyCustID  
      Table: customers  
      Columns: CustomerID
      IsPrimaryKey: True  
```  
  
 En el **DataSet** que se genera, el **IsPrimaryKey** propiedad de la **UniqueConstraint** se establece `msdata:PrimaryKey="true"` en **true** porque el esquema especifica en el elemento **de clave.**  
  
 El valor de la **Propiedad ConstraintName** de **UniqueConstraint** en el **DataSet** es el valor del atributo **msdata:ConstraintName** especificado en el elemento **clave** del esquema.  
  
## <a name="see-also"></a>Consulte también

- [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
