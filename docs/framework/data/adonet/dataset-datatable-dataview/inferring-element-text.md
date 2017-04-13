---
title: "Deducir texto de elemento | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Deducir texto de elemento
Si un elemento contiene texto y no tiene elementos secundarios que se vayan a deducir como tablas \(como elementos con atributos o elementos repetidos\), se agregará una nueva columna denominada **TableName\_Text** a la tabla que se deduzca para el elemento.  El texto contenido en el elemento se agregará a una fila de la tabla y se almacenará en la nueva columna.  La propiedad **ColumnMapping** de la nueva columna se establecerá como **MappingType.SimpleContent**.  
  
 Por ejemplo, tomemos el siguiente código XML.  
  
```  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá una tabla denominada **Element1** con dos columnas: **attr1** y **Element1\_Text**.  La propiedad **ColumnMapping** de la columna **attr1** se establecerá en **MappingType.Attribute**.  La propiedad **ColumnMapping** de la columna **Element1\_Text** se establecerá en **MappingType.SimpleContent**.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|attr1|Element1\_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 Si un elemento contiene texto, pero también tiene elementos secundarios que contienen texto, no se agregará una columna a la tabla para almacenar el texto contenido en el elemento.  El texto contenido en el elemento se pasará por alto, mientras que el texto de los elementos secundarios se incluirá en una fila de la tabla.  Por ejemplo, tomemos el siguiente código XML.  
  
```  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 El proceso de inferencia producirá una tabla llamada **Element1** con una columna denominada **ChildElement1**.  El texto del elemento **ChildElement1** se incluirá en una fila de la tabla.  El otro texto se pasará por alto.  La propiedad **ColumnMapping** de la columna **ChildElement1** se establecerá en **MappingType.Element**.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)