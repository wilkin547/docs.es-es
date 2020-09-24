---
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 3b2dad44176e52adcf32e2e3ccff3d82ba23f6ed
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153240"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos

En un esquema del lenguaje de definición de esquemas XML (XSD), el elemento **Unique** especifica la restricción de unicidad en un elemento o atributo. En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.  
  
 En la tabla siguiente se describen los atributos **msdata** que puede especificar en el elemento **Unique** .  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. De lo contrario, el atributo **Name** proporciona el valor del nombre de la restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente en el elemento **Unique** , se crea una restricción UNIQUE con la propiedad **IsPrimaryKey** establecida en **true**.|  
  
 En el ejemplo siguiente se muestra un esquema XML que utiliza el elemento **Unique** para especificar una restricción de unicidad.  
  
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
  
 El elemento **Unique** del esquema especifica que, para todos los elementos de los **clientes** de una instancia de documento, el valor del elemento secundario **CustomerID** debe ser único. Al compilar el **conjunto**de elementos, el proceso de asignación Lee este esquema y genera la tabla siguiente:  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 El proceso de asignación también crea una restricción UNIQUE en la columna **CustomerID** , como se muestra en el siguiente **conjunto**de elementos. Para simplificar, sólo se muestran las propiedades relevantes.  
  
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
  
 En el **conjunto de DataSet** que se genera, la propiedad **IsPrimaryKey** está establecida en **false** para la restricción UNIQUE. La propiedad **Unique** de la columna indica que los valores de la columna **CustomerID** deben ser únicos (pero pueden ser una referencia nula, tal y como se especifica en la propiedad **AllowDBNull** de la columna).  
  
 Si modifica el esquema y establece el valor del atributo **msdata: PrimaryKey** opcional en **true**, se creará la restricción UNIQUE en la tabla. La propiedad de columna **AllowDBNull** está establecida en **false**y la propiedad **IsPrimaryKey** de la restricción se establece en **true**, lo que convierte la columna **CustomerID** en una columna de clave principal.  
  
 Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML. En el ejemplo siguiente se muestra cómo especificar que una combinación de valores **CustomerID** y **CompanyName** debe ser única para todos los **clientes** de cualquier instancia, agregando otro elemento **xs: Field** en el esquema.  
  
```xml  
      <xs:unique
         msdata:ConstraintName="SomeName"
         name="UniqueCustIDConstr" >
  <xs:selector xpath=".//Customers" />
  <xs:field xpath="CustomerID" />
  <xs:field xpath="CompanyName" />
</xs:unique>  
```  
  
 Esta es la restricción que se crea en el **conjunto**de resultados.  
  
```text  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Vea también

- [Asignar restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)
- [Generar relaciones de objetos DataSet en un esquema XML (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)
- [Información general de ADO.NET](../ado-net-overview.md)
