---
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8bcf705ce4415929e685be79f813846bbb40bb36
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150849"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
En un esquema de lenguaje de definición de esquemas XML (XSD), el elemento **unique** especifica la restricción de unicidad en un elemento o atributo. En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.  
  
 En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **único.**  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente en el elemento **único,** se crea una restricción única con la propiedad **IsPrimaryKey** establecida en **true**.|  
  
 En el ejemplo siguiente se muestra un esquema XML que utiliza el elemento **único** para especificar una restricción de unicidad.  
  
```xml  
<xs:schema id="SampleDataSet"
            xmlns:xs="http://www.w3.org/2001/XMLSchema"
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="Customers">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="CustomerID" type="xs:integer"
           minOccurs="0"/>  
        <xs:element name="CompanyName" type="xs:string"
           minOccurs="0"/>  
       <xs:element name="Phone" type="xs:string" />  
     </xs:sequence>  
   </xs:complexType>  
 </xs:element>  
  
 <xs:element name="SampleDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element ref="Customers" />  
    </xs:choice>  
  </xs:complexType>  
   <xs:unique     msdata:ConstraintName="UCustID"     name="UniqueCustIDConstr" >       <xs:selector xpath=".//Customers" />       <xs:field xpath="CustomerID" />     </xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 El elemento **único** del esquema especifica que para todos los elementos **Customers** de una instancia de documento, el valor del elemento secundario **CustomerID** debe ser único. Al compilar el **conjunto de datos**, el proceso de asignación lee este esquema y genera la tabla siguiente:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 El proceso de asignación también crea una restricción única en la columna **CustomerID,** como se muestra en el siguiente **DataSet**. Para simplificar, sólo se muestran las propiedades relevantes.  
  
```text  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID       Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID
      IsPrimaryKey: False  
```  
  
 En el **DataSet** que se genera, el **IsPrimaryKey** propiedad está establecida en **False** para la restricción única. La propiedad **unique** de la columna indica que los valores de columna **CustomerID** deben ser únicos (pero pueden ser una referencia nula, tal como se especifica en la propiedad **AllowDBNull** de la columna).  
  
 Si modifica el esquema y establece el valor opcional del atributo **msdata:PrimaryKey** en **True**, se crea la restricción única en la tabla. La propiedad de columna **AllowDBNull** se establece en **False**y la propiedad **IsPrimaryKey** de la restricción establecida en **True**, por lo que la columna **CustomerID** es una columna de clave principal.  
  
 Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML. En el ejemplo siguiente se muestra cómo especificar que una combinación de **CustomerID** y **CompanyName** valores deben ser únicos para todos los **clientes** en cualquier instancia, agregando otro **xs:field** elemento en el esquema.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 Esta es la restricción que se crea en el **conjunto de datos**resultante.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Consulte también

- [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
