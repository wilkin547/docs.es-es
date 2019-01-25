---
title: Procedimiento Especificar el modo de edición para el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
ms.openlocfilehash: fcb2014cc92a8a3e4afe7c3ed0365fd5947c70f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54628271"
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>Procedimiento Especificar el modo de edición para el Control DataGridView de Windows Forms
De forma predeterminada, los usuarios pueden editar el contenido del elemento actual <xref:System.Windows.Forms.DataGridView> celda de cuadro de texto al escribir en él o presione F2. Esto coloca la celda en modo de edición si se cumplen todas las condiciones siguientes:  
  
-   El origen de datos subyacente admite la edición.  
  
-   El <xref:System.Windows.Forms.DataGridView> control está habilitado.  
  
-   El <xref:System.Windows.Forms.DataGridView.EditMode%2A> no es el valor de propiedad <xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>.  
  
-   El `ReadOnly` propiedades de la celda, fila, columna y control están establecidos en `false`.  
  
 En modo de edición, el usuario puede cambiar el valor de celda y presione ENTRAR para confirmar el cambio o la tecla ESC para revertir la celda a su valor original.  
  
 Puede configurar un <xref:System.Windows.Forms.DataGridView> controlar de manera que una celda entra en modo de edición, en cuanto se convierte en la celda actual. El comportamiento de las teclas ENTRAR y ESC se modifica en este caso, pero sigue siendo la celda en modo de edición después de confirmar o revertir el valor. También puede configurar el control para que las celdas entrar en modo de edición solo cuando los usuarios escriben en la celda o solo cuando los usuarios presionar F2. Por último, puede impedir que las celdas entrando en modo de edición, excepto cuando se llama a la <xref:System.Windows.Forms.DataGridView.BeginEdit%2A> método.  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>Para cambiar el modo de edición de un control DataGridView  
  
-   Establecer el <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType> propiedad correspondientes <xref:System.Windows.Forms.DataGridViewEditMode> enumeración.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System> y <xref:System.Windows.Forms>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>
- [Entrada de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
