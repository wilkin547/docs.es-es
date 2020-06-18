---
title: Obtener las celdas, filas y columnas seleccionadas en el control DataGridView
description: Obtenga información sobre cómo obtener las celdas, filas o columnas seleccionadas desde un control DataGridView usando las propiedades correspondientes.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
ms.openlocfilehash: 32ddae34104d23b8e5fbc0cce7da79f33fcce1d2
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904174"
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a>Procedimiento para obtener las celdas, filas y columnas seleccionadas en el control DataGridView de formularios Windows Forms
Puede obtener las celdas, filas o columnas seleccionadas de un control mediante <xref:System.Windows.Forms.DataGridView> las propiedades correspondientes: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> , <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> . En los procedimientos siguientes, obtendrá las celdas seleccionadas y mostrará los índices de fila y columna en <xref:System.Windows.Forms.MessageBox> .  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a>Para obtener las celdas seleccionadas en un control DataGridView  
  
- Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>.  
  
    > [!NOTE]
    > Use el <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método para evitar que se muestre un número potencialmente grande de celdas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a>Para obtener las filas seleccionadas en un control DataGridView  
  
- Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>. Para permitir que los usuarios seleccionen filas, debe establecer la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a>Para obtener las columnas seleccionadas en un control DataGridView  
  
- Utilice la propiedad <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>. Para permitir que los usuarios seleccionen columnas, debe establecer la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> propiedad en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> o <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect> .  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- <xref:System.Windows.Forms.Button>controles denominados `selectedCellsButton` , `selectedRowsButton` y `selectedColumnsButton` , cada uno con controladores para el <xref:System.Windows.Forms.Control.Click> evento asociado.  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Text?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Las colecciones descritas en este tema no funcionan de forma eficaz cuando se selecciona un gran número de celdas, filas o columnas. Para obtener más información sobre el uso de estas colecciones con grandes cantidades de datos, vea [prácticas recomendadas para escalar el control DataGridView Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>
- <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>
- <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>
- [Selección y uso del Portapapeles con el control DataGridView de formularios Windows Forms](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)
