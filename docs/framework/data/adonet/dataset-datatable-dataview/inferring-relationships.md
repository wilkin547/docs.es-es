---
title: "Deducir relaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Deducir relaciones
Si un elemento que se deduce como una tabla tiene un elemento secundario que también se deduce como una tabla, se creará una <xref:System.Data.DataRelation> entre las dos tablas.  Se agregará una nueva columna denominada **ParentTableName\_Id** tanto a la tabla creada para el elemento primario como a la tabla creada para el elemento secundario.  La propiedad **ColumnMapping** de esta columna de identidad se establecerá en **MappingType.Hidden**.  La columna será una clave principal de incremento automático para la tabla primaria y se utilizará para la **DataRelation** entre las dos tablas.  El tipo de datos de la columna de identidad agregada será **System.Int32**, a diferencia del tipo de datos de todas las demás columnas deducidas, que es **System.String**.  También se creará una <xref:System.Data.ForeignKeyConstraint> con **DeleteRule** \= **Cascade** utilizando la nueva columna tanto en la tabla primaria como en la tabla secundaria.  
  
 Por ejemplo, tomemos el siguiente código XML:  
  
```  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 El proceso de inferencia producirá dos tablas: **Element1** y **ChildElement1**.  
  
 La tabla **Element1** tendrá dos columnas: **Element1\_Id** y **ChildElement2**.  La propiedad **ColumnMapping** de la columna **Element1\_Id** se establecerá en **MappingType.Hidden**.  La propiedad **ColumnMapping** de la columna **ChildElement2** se establecerá en **MappingType.Element**.  La columna **Element1\_Id** se establecerá como clave principal de la tabla **Element1**.  
  
 La tabla **ChildElement1** tendrá tres columnas: **attr1**, **attr2** y **Element1\_Id**.  La propiedad **ColumnMapping** de las columnas **attr1** y **attr2** se establecerá en **MappingType.Attribute**.  La propiedad **ColumnMapping** de la columna **Element1\_Id** se establecerá en **MappingType.Hidden**.  
  
 Se creará una **DataRelation** y una **ForeignKeyConstraint** utilizando las columnas **Element1\_Id** de ambas tablas.  
  
 **DataSet:** DocumentElement  
  
 **Tabla:** Element1  
  
|Element1\_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabla:** ChildElement1  
  
|attr1|attr2|Element1\_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1\_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1\_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1\_Id  
  
 **Nested:** True  
  
 **ForeignKeyConstraint:** Element1\_ChildElement1  
  
 **Column:** Element1\_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** None  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Anidar DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)