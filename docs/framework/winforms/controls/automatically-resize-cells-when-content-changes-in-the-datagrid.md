---
title: Procedimiento para cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], resizing cells automatically
- cells [Windows Forms], resizing automatically
- DataGridView control [Windows Forms], resizing cells
ms.assetid: 1d68934d-a04c-4b12-9e66-c856c6828131
ms.openlocfilehash: 3411b68b4dcc64dba86cd9fa8804e0a487cec76d
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65586633"
---
# <a name="how-to-automatically-resize-cells-when-content-changes-in-the-windows-forms-datagridview-control"></a>Procedimiento para cambiar automáticamente el tamaño de las celdas cuando se modifica el contenido en un control DataGridView de formularios Windows Forms
Puede configurar el control <xref:System.Windows.Forms.DataGridView> para que ajuste el tamaño de sus filas, columnas y encabezados automáticamente siempre que cambie el contenido, para que las celdas sean siempre lo suficientemente grandes para mostrar los valores sin recortarlos.  
  
 Tiene muchas opciones para restringir qué celdas se usan para determinar los nuevos tamaños. Por ejemplo, puede configurar el control para ajustar automáticamente el ancho de sus columnas basándose solo en los valores de las filas que se muestran actualmente. De esta forma evita la falta de eficiencia al trabajar con grandes cantidades de filas, aunque en este caso quizás quiera usar métodos de ajuste de tamaño como <xref:System.Windows.Forms.DataGridView.AutoResizeColumns%2A> para ajustar el tamaño en el momento que elija.  
  
 Para obtener más información sobre el cambio de tamaño automático, consulte [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
 El ejemplo de código siguiente muestra las opciones disponibles para el ajuste de tamaño automático.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CPP/autosizing.cpp#0)]
 [!code-csharp[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/CS/autosizing.cs#0)]
 [!code-vb[System.Windows.Forms.DataGridView.AutoSizing#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.AutoSizing/VB/autosizing.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ColumnHeadersHeightSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowHeadersWidthSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.AutoSizeRowsMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.InheritedAutoSizeMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>
- <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>
- <xref:System.Windows.Forms.DataGridViewColumnHeadersHeightSizeMode>
- <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>
- [Cambiar el tamaño de columnas y filas en el control DataGridView de Windows Forms](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Cómo: Cambiar el tamaño de las celdas para ajustar el contenido en el Control DataGridView de Windows Forms mediante programación](programmatically-resize-cells-to-fit-content-in-the-datagrid.md)
