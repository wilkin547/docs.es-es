---
title: "Asignar restricciones de esquema XML (XSD) a las restricciones de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 22664196-f270-4ebc-a169-70e16a83dfa1
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Asignar restricciones de esquema XML (XSD) a las restricciones de DataSet
En un esquema puede especificar una restricción de clave para un elemento o un atributo mediante el elemento **key**.  El elemento o el atributo para el que se especifica una restricción de clave debe tener valores únicos en cualquier instancia del esquema y no puede tener valores nulos.  
  
 La restricción de clave es similar a la restricción única, excepto en que la columna sobre la que se define una restricción de clave no puede tener valores nulos.  
  
 En la siguiente tabla se describen los atributos **msdata** que puede especificar en el elemento **key**.  
  
|Nombre del atributo|Descripción|  
|-------------------------|-----------------|  
|**msdata:ConstraintName**|Si se especifica este atributo, su valor se utiliza como nombre de la restricción.  De lo contrario, el atributo **name** proporciona el valor del nombre de la restricción.|  
|**msdata:PrimaryKey**|Si `PrimaryKey="true"` está presente, la propiedad **IsPrimaryKey** de la restricción se establece como **true**, lo que la convierte en una clave principal.  La propiedad de columna **AllowDBNull** se establece como **false** porque las claves principales no pueden tener valores nulos.|  
  
 Al convertir un esquema en el que se ha especificado una restricción de clave, el proceso de asignación crea una restricción única en la tabla, donde la propiedad de columna **AllowDBNull** se ha establecido como **false** para cada columna de la restricción.  La propiedad **IsPrimaryKey** de la restricción única también se establece como **false** a menos que haya especificado `msdata:PrimaryKey="true"` en el elemento **key**.  Esto es idéntico a una restricción única del esquema donde `PrimaryKey="true"`.  
  
 En el siguiente ejemplo de esquema, el elemento **key** especifica la restricción de clave del elemento **CustomerID**.  
  
```  
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
  
 El elemento **key** especifica que los valores del elemento secundario **CustomerID** del elemento **Customers** deben tener valores únicos y no pueden tener valores nulos.  Al traducir el esquema del lenguaje de definición de esquema XML \(XSD\), el proceso de asignación crea la tabla siguiente:  
  
```  
Customers(CustomerID, CompanyName, Phone)  
```  
  
 La asignación de esquema XML crea también una **UniqueConstraint** en la columna **CustomerID**, como se muestra en el siguiente <xref:System.Data.DataSet>.  Para simplificar, sólo se muestran las propiedades relevantes.  
  
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
  
 En el **DataSet** que se genera, la propiedad **IsPrimaryKey** de la **UniqueConstraint** se establece como **true** porque el esquema contiene `msdata:PrimaryKey="true"` en el elemento **key**.  
  
 El valor de la propiedad **ConstraintName** de la **UniqueConstraint** del **DataSet** es el valor del atributo **msdata:ConstraintName** especificado en el elemento **key** del esquema.  
  
## Vea también  
 [Asignar restricciones de esquema XML \(XSD\) a las restricciones de DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)   
 [Generar las relaciones de DataSet desde la definición de esquemas XML \(XSD\)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)