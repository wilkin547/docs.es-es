---
title: Procedimiento para obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 670708f342e1cd1ac495c215b7508093349ac2e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933701"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Procedimiento para obtener y establecer la celda actual en el control DataGridView de formularios Windows Forms
La <xref:System.Windows.Forms.DataGridView> interacción con suele requerir que se detecte mediante programación qué celda está activa actualmente. También puede que necesite cambiar la celda actual. Puede realizar estas tareas con la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.  
  
> [!NOTE]
> No se puede establecer la celda actual en una fila o columna que tenga <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> su propiedad establecida `false`en.  
  
 Dependiendo del <xref:System.Windows.Forms.DataGridView> modo de selección del control, cambiar la celda actual puede cambiar la selección. Para obtener más información, vea [modos de selección en el control DataGridView Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Para obtener la celda actual mediante programación  
  
- Use la <xref:System.Windows.Forms.DataGridView> propiedad del <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Para establecer la celda actual mediante programación  
  
- Establezca la <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad <xref:System.Windows.Forms.DataGridView> del control. En el ejemplo de código siguiente, la celda actual se establece en la fila 0, columna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- <xref:System.Windows.Forms.Button>controles `getCurrentCellButton` denominados `setCurrentCellButton`y. En Visual C#, debe adjuntar <xref:System.Windows.Forms.Control.Click> los eventos de cada botón al controlador de eventos asociado en el código de ejemplo.  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modos de selección en el control DataGridView de formularios Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
