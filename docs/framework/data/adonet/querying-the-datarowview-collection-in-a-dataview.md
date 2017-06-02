---
title: "Consultar la colecci&#243;n DataRowView en un objeto DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Consultar la colecci&#243;n DataRowView en un objeto DataView
El objeto <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>.  <xref:System.Data.DataRowView> representa una vista personalizada de un objeto <xref:System.Data.DataRow> y muestra una versión concreta de dicho objeto <xref:System.Data.DataRow> en un control.  Solo se puede mostrar una versión de un objeto <xref:System.Data.DataRow> mediante un control, como por ejemplo, <xref:System.Windows.Forms.DataGridView>.  Se puede tener acceso al objeto <xref:System.Data.DataRow> que está expuesto por <xref:System.Data.DataRowView> mediante la propiedad <xref:System.Data.DataRowView.Row%2A> de <xref:System.Data.DataRowView>.  Cuando se ven valores mediante el uso de <xref:System.Data.DataRowView>, la propiedad <xref:System.Data.DataView.RowStateFilter%2A> determina qué versión de fila del objeto <xref:System.Data.DataRow> subyacente está expuesta.  Para obtener información sobre cómo tener acceso a las diferentes versiones de fila mediante <xref:System.Data.DataRow>, vea [Estados de fila y versiones de fila](../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  Dado que la colección de objetos <xref:System.Data.DataRowView> expuestos por <xref:System.Data.DataView> es enumerable, se puede usar [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] para realizar consultas en ella.  
  
 En el ejemplo siguiente se realiza una consulta en la tabla `Product` para los productos de color rojo y se crea una tabla a partir de dicha consulta.  Se crea un objeto <xref:System.Data.DataView> a partir de la tabla y se establece la propiedad <xref:System.Data.DataView.RowStateFilter%2A> para filtrar por filas modificadas o eliminadas.  <xref:System.Data.DataView> se utiliza después como origen en una consulta LINQ, y los objetos <xref:System.Data.DataRowView> que se han modificado y eliminado se enlazan a un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 En el ejemplo siguiente se crea una tabla de productos a partir de una vista que se enlaza a un control <xref:System.Windows.Forms.DataGridView>.  Se realiza una consulta en <xref:System.Data.DataView> para los productos de color rojo y los resultados ordenados se enlazan a un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## Vea también  
 [Enlace de datos y LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)