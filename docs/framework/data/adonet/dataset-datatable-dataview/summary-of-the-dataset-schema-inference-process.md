---
title: "Resumen del proceso de inferencia de esquemas de DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Resumen del proceso de inferencia de esquemas de DataSet
El proceso de inferencia determina en primer lugar, a partir del documento XML, qué elementos se inferirán como tablas.  A partir del XML restante, el proceso de inferencia determina las columnas para dichas tablas.  En el caso de las tablas anidadas, el proceso de inferencia genera objetos <xref:System.Data.DataRelation> y <xref:System.Data.ForeignKeyConstraint> anidados.  
  
 A continuación se resumen brevemente las reglas de inferencia:  
  
-   Los elementos que tienen atributos se deducen como tablas.  
  
-   Los elementos que tienen elementos secundarios se deducen como tablas.  
  
-   Los elementos que se repiten se deducen como una única tabla.  
  
-   Si el elemento de documento, o raíz, no tiene atributos y no se deduciría ningún elemento secundario como una columna, se deduce como un <xref:System.Data.DataSet>.  De lo contrario, el elemento de documento se deducirá como una tabla.  
  
-   Los atributos se deducen como columnas.  
  
-   Los elementos que no tienen atributos o elementos secundarios, y que no se repiten, se deducen como columnas.  
  
-   Para los elementos que se deducen como tablas anidadas dentro de otros elementos que también se deducen como tablas, se crea una **DataRelation** anidada entre las dos tablas.  Se agrega a ambas tablas una nueva columna de clave principal denominada **TableName\_Id** que la **DataRelation** utiliza.  Se crea una **ForeignKeyConstraint** entre las dos tablas mediante la columna **TableName\_Id**.  
  
-   Para los elementos que se deducen como tablas y que contienen texto pero que no tienen elementos secundarios, se crea una columna nueva denominada **TableName\_Text** para el texto de cada uno de los elementos.  Si un elemento se deduce como una tabla y tiene texto, pero también tiene elementos secundarios, se pasa por alto el texto.  
  
## Vea también  
 [Deducir la estructura relacional de DataSet de XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)   
 [Cargar DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)   
 [Cargar la información de esquema de DataSet desde XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)   
 [Utilizar XML en un DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)   
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)