---
title: Filtrar para llevar a cabo una acción personalizada en función de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], detecting changes
- DataGridView control [Windows Forms], detecting changes in cells
- data grids [Windows Forms], detecting changes in cells
ms.assetid: 7fa44d01-97f4-4ccb-a149-bc72628d2c36
ms.openlocfilehash: 0573199e9afb7e52c7542d36a2f3e39730dacdc4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59229165"
---
# <a name="how-to-perform-a-custom-action-based-on-changes-in-a-cell-of-a-windows-forms-datagridview-control"></a>Filtrar para llevar a cabo una acción personalizada en función de los cambios que se realicen en una celda de un control DataGridView de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control tiene un número de eventos que puede usar para detectar cambios en el estado de <xref:System.Windows.Forms.DataGridView> celdas. Dos de los más usados son el <xref:System.Windows.Forms.DataGridView.CellValueChanged> y <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventos.  
  
### <a name="to-detect-changes-in-the-values-of-datagridview-cells"></a>Para detectar cambios en los valores de las celdas de DataGridView  
  
-   Escribir un controlador para el <xref:System.Windows.Forms.DataGridView.CellValueChanged> eventos.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#130)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#130)]  
  
### <a name="to-detect-changes-in-the-states-of-datagridview-cells"></a>Para detectar cambios en los Estados de las celdas de DataGridView  
  
-   Escribir un controlador para el <xref:System.Windows.Forms.DataGridView.CellStateChanged> eventos.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#135)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#135](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#135)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`. Para C#, los controladores de eventos deben estar conectados a los eventos correspondientes.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellValueChanged?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellStateChanged?displayProperty=nameWithType>
- [Programar con celdas, filas y columnas en el control DataGridView de formularios Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
- [Tutorial: Validar datos en el control DataGridView de formularios Windows Forms](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
