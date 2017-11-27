---
title: "Cómo: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aada475af0ccac03dfa6ef9248b0fb07fd86b3ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Cómo: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms
Puede obtener las celdas seleccionadas, filas o columnas de una <xref:System.Windows.Forms.DataGridView> control mediante las propiedades correspondientes: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. En los procedimientos siguientes, obtendrá las celdas seleccionadas y mostrar sus índices de fila y columna en un <xref:System.Windows.Forms.MessageBox>.  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Para obtener las celdas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    >  Use la <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método para evitar que se muestre un número potencialmente grande de celdas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Para obtener las filas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Para permitir a los usuarios seleccionar las filas, debe establecer el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Para obtener las columnas seleccionadas en un control DataGridView  
  
-   Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Para habilitar a los usuarios seleccionar las columnas, debe establecer el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   <xref:System.Windows.Forms.Button>controles denominados `selectedCellsButton`, `selectedRowsButton`, y `selectedColumnsButton`, cada uno con controladores para la <xref:System.Windows.Forms.Control.Click> evento adjunto.  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las colecciones que se describe en este tema no realizan eficazmente cuando se selecciona gran número de celdas, filas o columnas. Para obtener más información acerca del uso de estas colecciones con grandes cantidades de datos, vea [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [Selección y uso del Portapapeles con el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
