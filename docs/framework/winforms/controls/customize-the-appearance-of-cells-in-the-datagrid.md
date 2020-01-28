---
title: Personalizar la apariencia de las celdas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
ms.openlocfilehash: 754932427a365a7b032c1ac9627d3237d1f7d0c6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744057"
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms
Puede personalizar la apariencia de cualquier celda controlando el evento de <xref:System.Windows.Forms.DataGridView.CellPainting> del control <xref:System.Windows.Forms.DataGridView>. Puede extraer el <xref:System.Drawing.Graphics> del control <xref:System.Windows.Forms.DataGridView> de la propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Con esta <xref:System.Drawing.Graphics>, puede afectar a la apariencia del control de <xref:System.Windows.Forms.DataGridView> completo, pero normalmente solo querrá afectar a la apariencia de la celda que se está dibujando actualmente. La propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> del <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir las operaciones de dibujo a la celda que se está dibujando actualmente.  
  
 En el ejemplo de código siguiente, dibujará todas las celdas de una `ContactName` columna mediante la combinación de colores del control <xref:System.Windows.Forms.DataGridView>. El contenido de texto de cada celda se dibuja en <xref:System.Drawing.Color.Crimson%2A>y un rectángulo de bajorrelieve se dibuja en el mismo color que la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A> del control <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna `ContactName` como la de la tabla Customers de la base de datos de ejemplo Northwind.  
  
- Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CellPainting>
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
