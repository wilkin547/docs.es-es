---
title: Procedimiento Obtener y establecer la celda actual en el Control DataGridView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], getting current cell
- DataGridView control [Windows Forms], setting current cell
- cells [Windows Forms], getting and setting current
ms.assetid: b0e41e57-493a-4bd0-9376-a6f76723540c
ms.openlocfilehash: 712340e6fbc081cbac9ecfb516bffb7a58bf0c12
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724029"
---
# <a name="how-to-get-and-set-the-current-cell-in-the-windows-forms-datagridview-control"></a>Filtrar Obtener y establecer la celda actual en el Control DataGridView de formularios de Windows
Interacción con el <xref:System.Windows.Forms.DataGridView> a menudo requiere que detectar mediante programación la celda que está actualmente activa. También es posible que deba cambiar la celda actual. Puede realizar estas tareas con el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.  
  
> [!NOTE]
>  No se puede establecer la celda actual en una fila o columna que tiene su <xref:System.Windows.Forms.DataGridViewBand.Visible%2A> propiedad establecida en `false`.  
  
 En función de la <xref:System.Windows.Forms.DataGridView> modo de selección del control, cambiar la celda actual puede cambiar la selección. Para obtener más información, consulte [modos de selección en el DataGridView Control de Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md).  
  
### <a name="to-get-the-current-cell-programmatically"></a>Para obtener la celda actual mediante programación  
  
-   Use la <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#080)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#080](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#080)]  
  
### <a name="to-set-the-current-cell-programmatically"></a>Para establecer la celda actual mediante programación  
  
-   Establecer el <xref:System.Windows.Forms.DataGridView.CurrentCell%2A> propiedad de la <xref:System.Windows.Forms.DataGridView> control. En el ejemplo de código siguiente, se establece la celda actual en la fila 0, columna 1.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#085)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#085](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#085)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   <xref:System.Windows.Forms.Button> controles denominados `getCurrentCellButton` y `setCurrentCellButton`. En Visual C#, debe asociar el <xref:System.Windows.Forms.Control.Click> eventos para cada botón al controlador de eventos asociados en el código de ejemplo.  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.CurrentCell%2A?displayProperty=nameWithType>
- [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Modos de selección en el control DataGridView de formularios Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
