---
title: Procedimiento para agregar un control ToolStripContainer a un formulario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStrip control [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], adding to Windows Forms
ms.assetid: d0f55095-a833-453e-be5a-644906d75d54
ms.openlocfilehash: 3d69bc6ed0cf23da8315ae95565300d151069d51
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582582"
---
# <a name="how-to-add-a-toolstripcontainer-to-a-form"></a>Procedimiento para agregar un control ToolStripContainer a un formulario
Puede agregar mediante programación un <xref:System.Windows.Forms.ToolStripContainer> a Windows Forms y rellenarlo con controles.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo agregar un panel <xref:System.Windows.Forms.ToolStripContainer> y un control <xref:System.Windows.Forms.ToolStrip> a Windows Forms, cómo agregar elementos al control <xref:System.Windows.Forms.ToolStrip> y cómo agregar el control <xref:System.Windows.Forms.ToolStrip> a la propiedad <xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A> del panel <xref:System.Windows.Forms.ToolStripContainer>.  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/cs/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer2#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.toolstripcontainer2/vb/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo de código se necesita:  
  
- Referencias a los ensamblados System.Drawing, System.Text y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStripContainer (control)](toolstripcontainer-control.md)
- [Control ToolStrip](toolstrip-control-windows-forms.md)
