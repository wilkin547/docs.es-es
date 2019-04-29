---
title: Procedimiento para agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: 3307c92a13e5730de6dce0fe45b924e44b7af554
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61640301"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Procedimiento para agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
De forma predeterminada, la información sobre herramientas se usa para mostrar los valores de <xref:System.Windows.Forms.DataGridView> celdas que son demasiado pequeñas para mostrar todo su contenido. Puede invalidar este comportamiento, sin embargo, para establecer los valores de texto de información sobre herramientas de celdas individuales. Esto es útil para mostrar a los usuarios información adicional sobre una celda o para proporcionar a los usuarios una descripción alternativa del contenido de la celda. Por ejemplo, si tiene una fila que muestra los iconos de estado, es posible que desee proporcionar explicaciones de texto mediante información sobre herramientas.  
  
 También puede deshabilitar la presentación de información sobre herramientas de nivel de celda estableciendo el <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> propiedad `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Para agregar una información sobre herramientas a una celda  
  
- Establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Para este ejemplo se necesita:  
  
- Un <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar los valores de cadena de uno a cuatro asterisco ("*") los símbolos. El <xref:System.Windows.Forms.DataGridView.CellFormatting> evento del control debe estar asociada con el método de controlador de eventos que se muestra en el ejemplo.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Al enlazar la <xref:System.Windows.Forms.DataGridView> el control a un origen de datos externo o proporcionar su propio origen de datos al implementar el modo virtual, podría encontrar problemas de rendimiento. Para evitar una reducción del rendimiento cuando se trabaja con grandes cantidades de datos, controlar el <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> evento en lugar de la configuración de la <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad de varias celdas. Cuando controle este evento, obtener el valor de una celda <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad provoca el evento y devuelve el valor de la <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> la propiedad especificados en el evento de controlador.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Programar con celdas, filas y columnas en el control DataGridView de Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
