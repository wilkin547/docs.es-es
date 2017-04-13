---
title: "DataTableReaders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# DataTableReaders
El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Al crear un **DataTableReader** desde una **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, con excepción de las filas que se hayan marcado como eliminadas.  Las columnas aparecen en el mismo orden que en la **DataTable** original.  
  
 Un **DataTableReader** puede contener varios conjuntos de resultados si se ha creado llamando a <xref:System.Data.DataSet.CreateDataReader%2A>.  Los resultados se encuentran en el mismo orden que las **DataTables** de la colección <xref:System.Data.DataSet.Tables%2A> del objeto **DataSet**.  
  
## En esta sección  
 [Crear un DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Describe cómo crear un objeto **DataTableReader**.  
  
 [Navegar por DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Describe el uso del método **Read** para navegar por el contenido de un **DataTableReader**.  
  
## Vea también  
 [Recuperación y modificación de datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)