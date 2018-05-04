---
title: Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
ms.openlocfilehash: ad39fd75a3f8872ed2c24a65481209e3c772a638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="map-key-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones KEY de un esquema XML (XSD) a restricciones de conjuntos de datos
En un esquema, puede especificar una restricción de clave en un elemento o atributo mediante la **clave** elemento. El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.  
  
 La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.  
  
 La siguiente tabla se describen los **msdata** atributos que se pueden especificar en el **clave** elemento.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. En caso contrario, el **nombre** atributo proporciona el valor del nombre de restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente, el **IsPrimaryKey** propiedad de restricción se establece en **true**, lo que una clave principal. El **AllowDBNull** propiedad de columna se establece en **false**, porque las claves principales no pueden tener valores nulos.|  
  
 Convertir un esquema en el que se especifica una restricción de clave, el proceso de asignación crea una restricción unique en la tabla con el **AllowDBNull** propiedad column establecida en **false** para cada columna de la restricción. El **IsPrimaryKey** propiedad de la restricción única también se establece en **false** a menos que haya especificado `msdata:PrimaryKey="true"` en el **clave** elemento. Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.  
  
 En el siguiente ejemplo de esquema, el **clave** elemento especifica la restricción de clave en el **CustomerID** elemento.  
  
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
  
 El **clave** elemento especifica que los valores de la **CustomerID** elemento secundario de la **clientes** elemento debe tener valores únicos y no pueden tener valores nulos. Al traducir el esquema del lenguaje de definición de esquema XML (XSD), el proceso de asignación crea la tabla siguiente:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 La asignación de esquema XML crea también un **UniqueConstraint** en el **CustomerID** columna, tal y como se muestra en la siguiente <xref:System.Data.DataSet>. Para simplificar, sólo se muestran las propiedades relevantes.  
  
```  
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
  
 En el **conjunto de datos** que se genera, la **IsPrimaryKey** propiedad de la **UniqueConstraint** está establecido en **true** porque el esquema especifica `msdata:PrimaryKey="true"` en el **clave** elemento.  
  
 El valor de la **ConstraintName** propiedad de la **UniqueConstraint** en el **conjunto de datos** es el valor de la **msdata: ConstraintName** el atributo especificado en el **clave** elemento en el esquema.  
  
## <a name="see-also"></a>Vea también  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
