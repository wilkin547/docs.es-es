---
title: Especificar el modo de edición para el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: c0318202a80f9a43f1b656201732ef032f430b5b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743767"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Cómo: Especificar el modo de edición del control DataGridView de formularios Windows Forms
De forma predeterminada, los usuarios pueden modificar el contenido de la celda <xref:System.Windows.Forms.DataGridView> cuadro de texto actual escribiendo o presionando F2. Esto coloca la celda en modo de edición si se cumplen todas las condiciones siguientes:  
  
- El origen de datos subyacente admite la edición.  
  
- El control de <xref:System.Windows.Forms.DataGridView> está habilitado.  
  
- El valor de propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A> no es <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
- El `ReadOnly` las propiedades de la celda, la fila, la columna y el control se establecen en `false`.  
  
 En el modo de edición, el usuario puede cambiar el valor de la celda y presionar entrar para confirmar el cambio o ESC para revertir la celda a su valor original.  
  
 Puede configurar un control de <xref:System.Windows.Forms.DataGridView> para que una celda entre en el modo de edición en cuanto se convierta en la celda actual. En este caso, el comportamiento de las teclas entrar y ESC no cambia, pero la celda permanece en modo de edición después de confirmar o revertir el valor. También puede configurar el control para que las celdas entren en modo de edición solo cuando los usuarios escriban la celda o solo cuando los usuarios presionen F2. Por último, puede evitar que las celdas entren en el modo de edición excepto cuando llame al método <xref:System.Windows.Forms.DataGridView.BeginEdit%2A>.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Para cambiar el modo de edición de un control DataGridView  
  
- Establezca la propiedad <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> en la enumeración <xref:System.Windows.Forms.DataGridViewEditMode> adecuada.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Referencias a los ensamblados <xref:System> y <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](data-entry-in-the-windows-forms-datagridview-control.md)
