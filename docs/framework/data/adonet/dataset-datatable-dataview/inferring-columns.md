---
title: "Deducir columnas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Deducir columnas
Una vez que ADO.NET determina a partir de un documento XML los elementos que se van a inferir como tablas para un <xref:System.Data.DataSet>, se deducen las columnas para dichas tablas.  ADO.NET 2.0 presenta un nuevo motor de inferencia de esquemas que deduce un tipo fuertemente tipado para cada elemento **simpleType**.  En versiones anteriores, el tipo de datos de un elemento **simpleType** deducido siempre era **xsd:string**.  
  
## Migración y compatibilidad con versiones anteriores  
 El método **ReadXml** acepta argumentos del tipo **InferSchema**.  Este argumento le permite especificar un comportamiento de inferencia compatible con versiones anteriores.  En la siguiente tabla se muestran los valores disponibles para la enumeración **InferSchema**.  
  
 <xref:System.Data.XmlReadMode>  
 Proporciona compatibilidad con versiones anteriores al deducir siempre un tipo simple como <xref:System.String>.  
  
 <xref:System.Data.XmlReadMode>  
 Infiere un tipo de datos fuertemente tipado.  Inicia una excepción si se utiliza con una <xref:System.Data.DataTable>.  
  
 <xref:System.Data.XmlReadMode>  
 Omite cualquier esquema alineado y lee los datos del esquema del <xref:System.Data.DataSet> existente.  
  
## Atributos  
 Como se ha definido en [Deducir tablas](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), un elemento que tenga atributos se deducirá como una tabla.  Los atributos de dicho elemento se deducirán como columnas de la tabla.  La propiedad **ColumnMapping** de las columnas se establecerá como **MappingType.Attribute** para asegurarse de que los nombres de columna se escribirán como atributos si se vuelve a escribir el esquema en XML.  Los valores de los atributos se almacenan en una fila de la tabla.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 El proceso de deducción crea la tabla **Element1** con dos columnas, **attr1** y **attr2**.  La propiedad **ColumnMapping** de ambas columnas se establecerá como **MappingType.Attribute**.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Elementos sin atributos o elementos secundarios  
 Si un elemento no tiene elementos secundarios o atributos, se deducirá como una columna.  La propiedad **ColumnMapping** de la columna se establecerá en **MappingType.Element**.  El texto de los elementos secundarios se almacena en una fila de la tabla.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia crea la tabla **Element1** con dos columnas, **ChildElement1** y **ChildElement2**.  La propiedad **ColumnMapping** de ambas columnas se establecerá como **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|ChildElement2|  
|-------------------|-------------------|  
|Text1|Text2|  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)