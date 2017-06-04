---
title: "DataSets con establecimiento de tipos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataSets con establecimiento de tipos
Además del acceso en tiempo de ejecución a valores mediante variables débilmente tipadas, el <xref:System.Data.DataSet> proporciona acceso a los datos mediante una metáfora fuertemente tipada.  Se puede tener acceso a las tablas y columnas que forman parte del **DataSet** mediante nombres descriptivos y variables fuertemente tipadas.  
  
 Un **DataSet** con información de tipos es una clase que se deriva de un **DataSet**.  Como tal, hereda todos los métodos, eventos y propiedades de un **DataSet**.  Además, un **DataSet** con información de tipos proporciona métodos, eventos y propiedades fuertemente tipadas.  Esto significa que se puede tener acceso a tablas y columnas por su nombre, en lugar de utilizar métodos de una colección.  Además de la mayor legibilidad del código, un **DataSet** con información de tipos también permite que el editor de código Visual Studio .NET complete automáticamente las líneas mientras escribe.  
  
 Asimismo, el **DataSet** fuertemente tipado proporciona acceso a valores del tipo correcto en el momento de la compilación.  Con un **DataSet** fuertemente tipado, los errores por no coincidencia de tipos se interceptan cuando se compila el código, no en tiempo de ejecución.  
  
## En esta sección  
 [Generar DataSets fuertemente tipados](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Describe cómo se crea y utiliza un **DataSet** fuertemente tipado.  
  
 [Anotar DataSets con tipos](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Describe cómo se anota el esquema del lenguaje de definición de esquemas XML \(XSD\) utilizado para generar un **DataSet** fuertemente tipado con el fin de asignar nombres descriptivos a los elementos del **DataSet** sin modificar el esquema subyacente.  
  
## Vea también  
 [DataSets, DataTables y DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)