---
title: "Deducir tablas | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Deducir tablas
Al deducir un esquema para un <xref:System.Data.DataSet> desde un documento XML, ADO.NET determina en primer lugar qué elementos XML representan tablas.  Las siguientes estructuras XML darán como resultado una tabla para el esquema de **DataSet**:  
  
-   Elementos con atributos  
  
-   Elementos con elementos secundarios  
  
-   Elementos que se repiten  
  
## Elementos con atributos  
 Los elementos para los que se han especificado atributos se deducen como tablas.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1||  
|value2|Text1|  
  
## Elementos con elementos secundarios  
 Los elementos que tienen elementos secundarios se deducen como tablas.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text1|  
  
 El elemento de documento, o raíz, se deduce como una tabla si tiene atributos o elementos secundarios que se deducen como columnas.  Si el elemento de documento no tiene atributos y ningún elemento secundario que se deduzca como una columna, el elemento se deduce como un **DataSet**.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "DocumentElement".  
  
 **DataSet:** NewDataSet  
  
 **Tabla:** DocumentElement  
  
|Element1|Element2|  
|--------------|--------------|  
|Text1|Text2|  
  
 Por otra parte, considere el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce un **DataSet** denominado "DocumentElement" que contiene una tabla denominada "Element1”.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|attr2|  
|-----------|-----------|  
|value1|value2|  
  
## Elementos que se repiten  
 Los elementos que se repiten se deducen como una única tabla.  Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia produce una tabla denominada "Element1".  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1\_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)