---
title: 'Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: badbf316c769f60001b2ca2a4cacbf268f600e8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33530606"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>Cómo: Crear un formulario MDI con combinación de menús y controles ToolStrip
El espacio de nombres <xref:System.Windows.Forms?displayProperty=nameWithType> es compatible con aplicaciones de interfaces de múltiples documentos (MDI) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús. Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.  
  
 Hay una amplia compatibilidad para esta característica en Visual Studio.  
  
 Vea también [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).  
  
## <a name="example"></a>Ejemplo  
 En el siguiente ejemplo de código, se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI. El formulario también admite la combinación de menús con menús secundarios.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo de código se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
