---
title: Consultar la colección de DataRowView en un objeto DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b9070a12-1094-44d6-bb87-a23b50bcb0af
ms.openlocfilehash: 5757079bbc0ef8c498ea1db1a88f6b356ab0409e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172754"
---
# <a name="querying-the-datarowview-collection-in-a-dataview"></a>Consultar la colección de DataRowView en un objeto DataView

El objeto <xref:System.Data.DataView> expone una colección enumerable de objetos <xref:System.Data.DataRowView>. <xref:System.Data.DataRowView> representa una vista personalizada de un objeto <xref:System.Data.DataRow> y muestra una versión concreta de dicho objeto <xref:System.Data.DataRow> en un control. Solo se puede mostrar una versión de un objeto <xref:System.Data.DataRow> mediante un control, como por ejemplo, <xref:System.Windows.Forms.DataGridView>. Se puede tener acceso al objeto <xref:System.Data.DataRow> que está expuesto por <xref:System.Data.DataRowView> mediante la propiedad <xref:System.Data.DataRowView.Row%2A> de <xref:System.Data.DataRowView>. Cuando se ven valores mediante el uso de <xref:System.Data.DataRowView>, la propiedad <xref:System.Data.DataView.RowStateFilter%2A> determina qué versión de fila del objeto <xref:System.Data.DataRow> subyacente está expuesta. Para obtener información sobre cómo obtener acceso a diferentes versiones de fila mediante <xref:System.Data.DataRow> , vea [Estados de fila y versiones de fila](./dataset-datatable-dataview/row-states-and-row-versions.md). Dado que la colección de <xref:System.Data.DataRowView> objetos expuesta por <xref:System.Data.DataView> es Enumerable, puede utilizar LINQ to DataSet para realizar consultas sobre él.  
  
 En el ejemplo siguiente se realiza una consulta en la tabla `Product` para los productos de color rojo y se crea una tabla a partir de dicha consulta. Se crea un objeto <xref:System.Data.DataView> a partir de la tabla y se establece la propiedad <xref:System.Data.DataView.RowStateFilter%2A> para filtrar por filas modificadas o eliminadas. <xref:System.Data.DataView> se utiliza después como origen en una consulta LINQ, y los objetos <xref:System.Data.DataRowView> que se han modificado y eliminado se enlazan a un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview2)]
 [!code-vb[DP DataView Samples#QueryDataView2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview2)]  
  
 En el ejemplo siguiente se crea una tabla de productos a partir de una vista que se enlaza a un control <xref:System.Windows.Forms.DataGridView>. Se realiza una consulta en <xref:System.Data.DataView> para los productos de color rojo y los resultados ordenados se enlazan a un control <xref:System.Windows.Forms.DataGridView>.  
  
 [!code-csharp[DP DataView Samples#QueryDataView1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#querydataview1)]
 [!code-vb[DP DataView Samples#QueryDataView1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#querydataview1)]  
  
## <a name="see-also"></a>Consulte también

- [Enlace de datos y LINQ to DataSet](data-binding-and-linq-to-dataset.md)
