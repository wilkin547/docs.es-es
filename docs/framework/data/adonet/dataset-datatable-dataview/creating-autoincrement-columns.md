---
title: "Crear columnas AutoIncrement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cf09732a-ab54-4d98-89e2-4d0a1f28fbce
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Crear columnas AutoIncrement
Para garantizar que los valores de una columna son únicos, éstos se pueden establecer de manera que se incrementen automáticamente cuando se agregan filas a la tabla.  Para crear una <xref:System.Data.DataColumn> que se incrementa automáticamente, establezca la propiedad <xref:System.Data.DataColumn.AutoIncrement%2A> de la columna en **true**.  La <xref:System.Data.DataColumn> comienza entonces con el valor definido en la propiedad <xref:System.Data.DataColumn.AutoIncrementSeed%2A> y, con cada fila agregada, el valor de la columna **AutoIncrement** aumenta en función del valor definido en la propiedad <xref:System.Data.DataColumn.AutoIncrementStep%2A> de la columna.  
  
 En el caso de las columnas **AutoIncrement**, se recomienda que la propiedad <xref:System.Data.DataColumn.ReadOnly%2A> de la **DataColumn** se establezca en **true**.  
  
 En el ejemplo siguiente se muestra cómo se crea una columna que comienza con un valor de 200 y va aumentando de tres en tres.  
  
```vb  
Dim workColumn As DataColumn = workTable.Columns.Add( _  
    "CustomerID", typeof(Int32))  
workColumn.AutoIncrement = true  
workColumn.AutoIncrementSeed = 200  
workColumn.AutoIncrementStep = 3  
  
```  
  
```csharp  
DataColumn workColumn = workTable.Columns.Add(  
    "CustomerID", typeof(Int32));  
workColumn.AutoIncrement = true;  
workColumn.AutoIncrementSeed = 200;  
workColumn.AutoIncrementStep = 3;  
```  
  
## Vea también  
 <xref:System.Data.DataColumn>   
 [Definición de esquema de DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Proveedores administrados de ADO.NET y centro de desarrolladores de conjuntos de datos](http://go.microsoft.com/fwlink/?LinkId=217917)