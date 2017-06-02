---
title: "Asignar restricciones unique de esquema XML (XSD) a las restricciones de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 56da90bf-21d3-4d1a-8bb8-de908866b78d
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar restricciones unique de esquema XML (XSD) a las restricciones de DataSet
En un esquema del lenguaje de definición de esquema XML \(XSD\), el elemento **unique** especifica la restricción de unicidad de un elemento o un atributo.  En el proceso de traducción de un esquema XML a un esquema relacional, la restricción única especificada para un elemento o un atributo del esquema XML se asigna a una restricción única de la <xref:System.Data.DataTable> en el <xref:System.Data.DataSet> correspondiente que se genera.  
  
 En la siguiente tabla se describen los atributos **msdata** que puede especificar en el elemento **unique**.  
  
|Nombre del atributo|Descripción|  
|-------------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción.  De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente en el elemento **unique**, se creará una restricción única donde la propiedad **IsPrimaryKey** tiene el valor **true**.|  
  
 En el siguiente ejemplo se muestra un esquema XML que utiliza el elemento **unique** para especificar una restricción de unicidad.  
  
```  
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
   <xs:unique      
msdata:ConstraintName="UCustID"      
name="UniqueCustIDConstr" >        
<xs:selector xpath=".//Customers" />        
<xs:field xpath="CustomerID" />      
</xs:unique>  
</xs:element>  
</xs:schema>  
```  
  
 El elemento **unique** del esquema especifica que para todos los elementos **Customers** de una instancia del documento, el valor del elemento secundario **CustomerID** debe ser único.  Al crear el **DataSet**, el proceso de asignación lee este esquema y crea la tabla siguiente:  
  
```  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 El proceso de asignación crea también una restricción única para la columna **CustomerID**, como se muestra en el siguiente **DataSet**.  Para simplificar, sólo se muestran las propiedades relevantes.  
  
```  
  
      DataSetName: MyDataSet  
TableName: Customers  
  ColumnName: CustomerID  
      AllowDBNull: True  
      Unique: True  
  ConstraintName: UcustID  
      Type: UniqueConstraint  
      Table: Customers  
      Columns: CustomerID   
      IsPrimaryKey: False  
```  
  
 En el **DataSet** que se genera, la propiedad **IsPrimaryKey** se establece como **False** para la restricción única.  La propiedad **unique** de la columna indica que los valores de la columna **CustomerID** deben ser únicos \(pero pueden ser una referencia nula, según especifica la propiedad **AllowDBNull** de la columna\).  
  
 Si se modifica el esquema y se establece el valor del atributo opcional **msdata:PrimaryKey** como **True**, se crea la restricción única en la tabla.  La propiedad de la columna **AllowDBNull** se establece como **False** y la propiedad **IsPrimaryKey** de la restricción se establece como **True**, lo que hace que **CustomerID** sea una columna de clave principal.  
  
 Puede especificar una restricción única en una combinación de elementos o atributos del esquema XML.  En el siguiente ejemplo se muestra cómo especificar que una combinación de valores **CustomerID** y **CompanyName** debe ser única para todos los **Customers** de cualquier instancia; para ello, se agrega otro elemento **xs:field** al esquema.  
  
```  
  
      <xs:unique     
         msdata:ConstraintName="SomeName"    
         name="UniqueCustIDConstr" >   
  <xs:selector xpath=".//Customers" />   
  <xs:field xpath="CustomerID" />   
  <xs:field xpath="CompanyName" />   
</xs:unique>  
```  
  
 Esta es la restricción creada en el **DataSet** resultante.  
  
```  
ConstraintName: SomeName  
  Table: Customers  
  Columns: CustomerID CompanyName   
  IsPrimaryKey: False  
```  
  
## Vea también  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)