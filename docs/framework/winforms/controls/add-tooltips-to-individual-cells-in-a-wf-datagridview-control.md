---
title: Agregar información sobre herramientas a celdas individuales en el control DataGridView
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
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732179"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a>Cómo: Agregar información sobre herramientas a celdas individuales en un control DataGridView de formularios Windows Forms
De forma predeterminada, la información sobre herramientas se usa para mostrar los valores de <xref:System.Windows.Forms.DataGridView> celdas que son demasiado pequeñas para mostrar todo su contenido. Sin embargo, puede invalidar este comportamiento para establecer valores de texto de información sobre herramientas para celdas individuales. Esto resulta útil para mostrar a los usuarios información adicional sobre una celda o para proporcionar a los usuarios una descripción alternativa del contenido de la celda. Por ejemplo, si tiene una fila que muestra los iconos de estado, es posible que desee proporcionar explicaciones de texto mediante la información sobre herramientas.  
  
 También puede deshabilitar la visualización de la información sobre herramientas en el nivel de celda si establece la propiedad <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> en `false`.  
  
### <a name="to-add-a-tooltip-to-a-cell"></a>Para agregar una información sobre herramientas a una celda  
  
- Establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Para este ejemplo se necesita:  
  
- Un control de <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `Rating` para mostrar valores de cadena de uno a cuatro símbolos de asterisco ("*"). El evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del control debe estar asociado con el método de control de eventos que se muestra en el ejemplo.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Al enlazar el control de <xref:System.Windows.Forms.DataGridView> a un origen de datos externo o proporcionar su propio origen de datos mediante la implementación del modo virtual, pueden producirse problemas de rendimiento. Para evitar una reducción del rendimiento al trabajar con grandes cantidades de datos, controle el evento <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> en lugar de establecer la propiedad <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> de varias celdas. Al controlar este evento, al obtener el valor de una celda <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> propiedad, se genera el evento y se devuelve el valor de la propiedad <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> tal y como se especifica en el controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [Programar con celdas, filas y columnas en el control DataGridView de Windows Forms](programming-with-cells-rows-and-columns-in-the-datagrid.md)
