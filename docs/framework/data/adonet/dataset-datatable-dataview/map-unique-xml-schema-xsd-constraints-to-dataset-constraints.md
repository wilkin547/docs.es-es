---
title: Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
ms.date: 03/30/2017
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
ms.openlocfilehash: 8aed9830d613eeb7d49d2339a8ac1892c0e28e93
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761173"
---
# <a name="map-unique-xml-schema-xsd-constraints-to-dataset-constraints"></a>Asignar restricciones UNIQUE de un esquema XML (XSD) a restricciones de conjuntos de datos
En un esquema (XSD) de lenguaje de definición de esquemas XML, el **único** elemento especifica la restricción de unicidad en un elemento o atributo. En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.  
  
 La siguiente tabla se describen los **msdata** atributos que se pueden especificar en el **único** elemento.  
  
|Nombre del atributo|Descripción|  
|--------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción. En caso contrario, el **nombre** atributo proporciona el valor del nombre de restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente en el **único** elemento, se crea una restricción unique con la **IsPrimaryKey** propiedad establecida en **true**.|  
  
 En el ejemplo siguiente se muestra un esquema XML que usa el **único** elemento para especificar una restricción de unicidad.  
  
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
  
 El **único** elemento en el esquema especifica que para todos los **clientes** elementos en un documento de instancia, el valor de la **CustomerID** elemento secundario debe ser único. En el edificio del **conjunto de datos**, el proceso de asignación lee este esquema y genera la tabla siguiente:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 El proceso de asignación crea también una restricción unique en la **CustomerID** columna, tal y como se muestra en la siguiente **conjunto de datos**. Para simplificar, sólo se muestran las propiedades relevantes.  
  
```  
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
  
 En el **conjunto de datos** que se genera, la **IsPrimaryKey** propiedad está establecida en **False** para la restricción única. El **único** propiedad en la columna indica que la **CustomerID** valores de columna deben ser únicos (pero pueden ser una referencia nula, según lo especificado por el **AllowDBNull** propiedad de la columna).  
  
 Si modifica el esquema y establezca el encabezado opcional **msdata: PrimaryKey** valor al atributo **True**, se crea la restricción unique en la tabla. El **AllowDBNull** propiedad de columna se establece en **False**y el **IsPrimaryKey** propiedad de la restricción se establece como **True**, lo que hace que el **CustomerID** una columna de clave principal de la columna.  
  
 Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML. En el ejemplo siguiente se muestra cómo especificar que una combinación de **CustomerID** y **CompanyName** valores deben ser únicos para todos los **clientes** en cualquier instancia por agregar otro **xs: Field** elemento en el esquema.  
  
```xml  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Se trata de la restricción que se crea en el cuadro **conjunto de datos**.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## <a name="see-also"></a>Vea también  
 [Asignación de restricciones de un esquema XML (XSD) a restricciones de conjuntos de datos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [Generación de relaciones de objetos DataSet en un esquema XML (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
