---
title: 'Cómo: Agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms'
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
ms.openlocfilehash: 50eb02a8f6e9a987fad074c173ab6711fa91143f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527705"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Cómo: Agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
De forma predeterminada, la información sobre herramientas se utiliza para mostrar los valores de <xref:System.Windows.Forms.DataGridView> celdas que son demasiado pequeñas para mostrar todo su contenido. Puede invalidar este comportamiento, sin embargo, para establecer los valores de texto de información sobre herramientas para celdas individuales. Esto es útil para mostrar a los usuarios información adicional sobre una celda o para proporcionar a los usuarios una descripción alternativa del contenido de la celda. Por ejemplo, si tiene una fila que muestra los iconos de estado, puede que desee proporcionar explicaciones de texto mediante información sobre herramientas.  
  
 También puede deshabilitar la presentación de información sobre herramientas de nivel de celda estableciendo la <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> propiedad `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Para agregar una información sobre herramientas a una celda  
  
-   Establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para este ejemplo se necesita:  
  
-   A <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar los valores de cadena de uno a cuatro asterisco ("*") símbolos. El <xref:System.Windows.Forms.DataGridView.CellFormatting> eventos del control deben estar asociado con el método de controlador de eventos que se muestra en el ejemplo.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Cuando se enlaza el <xref:System.Windows.Forms.DataGridView> el control a un origen de datos externo o proporcione su propio origen de datos implementando el modo virtual, pueden surgir problemas de rendimiento. Para evitar una reducción del rendimiento cuando se trabaja con grandes cantidades de datos, controlar el <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> eventos en lugar de establecer el <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad de varias celdas. Al controlar este evento, obtener el valor de una celda <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad provoca el evento y devuelve el valor de la <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> propiedad como especificados en el evento de controlador.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [Programar con celdas, filas y columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
