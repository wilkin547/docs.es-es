---
title: Establecer estilos de colores y fuentes en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: f1ee9131cfc0b28a5f6263dcd6254d27a092cc62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746756"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms
Para especificar la apariencia visual de las celdas dentro de un control <xref:System.Windows.Forms.DataGridView>, establezca las propiedades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>. Puede recuperar instancias de esta clase desde distintas propiedades de la clase <xref:System.Windows.Forms.DataGridView> y sus clases complementarias, o puede crear instancias de objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para la asignación de estas propiedades.  
  
 Los procedimientos siguientes muestran cómo realizar una personalización básica de la apariencia de las celdas mediante la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Cada celda del control hereda los estilos especificados mediante esta propiedad, a menos que se invaliden en el nivel de celda, fila o columna. Para obtener un ejemplo de herencia de estilo, vea [Cómo: establecer estilos de celda predeterminados para el control DataGridView de Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Para obtener información sobre otros adicionales de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, consulte los temas de la sección Consulte también.  
  
 Visual Studio es altamente compatible con esta tarea.  Consulte también [Cómo: establecer estilos de celda y formatos de datos predeterminados para el control DataGridView Windows Forms mediante el diseñador](default-cell-styles-datagridview.md).  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>Para especificar la fuente que usan las celdas de DataGridView  
  
- Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer la fuente para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>Para especificar los colores de primer plano y de fondo de las celdas de DataGridView  
  
- Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>Para especificar los colores de primer plano y de fondo de las celdas seleccionadas de DataGridView  
  
- Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado. Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
