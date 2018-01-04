---
title: "Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms"
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
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 577a8237c79f90ae717b75e8d6633bfbdba82f58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms
Para especificar la apariencia visual de las celdas dentro de un control <xref:System.Windows.Forms.DataGridView>, establezca las propiedades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>. Puede recuperar instancias de esta clase desde distintas propiedades de la clase <xref:System.Windows.Forms.DataGridView> y sus clases complementarias, o puede crear instancias de objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para la asignación de estas propiedades.  
  
 Los procedimientos siguientes muestran cómo realizar una personalización básica de la apariencia de las celdas mediante la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. Cada celda del control hereda los estilos especificados mediante esta propiedad, a menos que se invaliden en el nivel de celda, fila o columna. Para obtener un ejemplo de herencia de estilos, consulte [Cómo: establecer estilos de celda predeterminados para el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Para obtener información sobre otros adicionales de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, consulte los temas de la sección Consulte también.  
  
 Visual Studio es altamente compatible con esta tarea.  Consulte también [Cómo: establecer estilos de celda predeterminados y formatos de datos para el Control Windows Forms DataGridView mediante el diseñador](http://msdn.microsoft.com/library/95y5fz2x\(v=vs.110\)).  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>Para especificar la fuente que usan las celdas de DataGridView  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer la fuente para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>Para especificar los colores de primer plano y de fondo de las celdas de DataGridView  
  
-   Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>Para especificar los colores de primer plano y de fondo de las celdas seleccionadas de DataGridView  
  
-   Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>. El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado. Para obtener más información, consulte [procedimientos recomendados para ajustar la escala del DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
