---
title: "Crear un DataReader | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Crear un DataReader
Las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet> tienen un método <xref:System.Data.DataTable.CreateDataReader%2A> que devuelve el contenido de la <xref:System.Data.DataTable> o el contenido de la colección <xref:System.Data.DataSet.Tables%2A> del objeto <xref:System.Data.DataSet> como uno o más conjuntos de resultados de solo lectura y solo avance.  
  
## Ejemplo  
 La siguiente aplicación de consola crea una instancia de <xref:System.Data.DataTable>.  A continuación, en el ejemplo se pasa la <xref:System.Data.DataTable> ``  rellenada a un procedimiento que llama al método <xref:System.Data.DataTable.CreateDataReader%2A>, que repite los resultados que se encuentran en el <xref:System.Data.DataTableReader>.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 En el ejemplo se muestra el siguiente resultado en la ventana de consola:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## Vea también  
 <xref:System.Data.DataTable.CreateDataReader%2A>   
 <xref:System.Data.DataSet.CreateDataReader%2A>   
 [DataTableReaders](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)