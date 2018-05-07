---
title: 'Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StatusStrip control [Windows Forms]
- ToolStrip control [Windows Forms]
- status bars [Windows Forms], examples
- Spring property [Windows Forms]
ms.assetid: 18bde842-a93c-48dd-9db3-15738a1775ce
ms.openlocfilehash: e3818beb96a7c005ea02bc04e9ea740b28a54707
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip
Puede utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>. La propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina si el control <xref:System.Windows.Forms.ToolStripStatusLabel> rellena automáticamente el espacio disponible en el control <xref:System.Windows.Forms.StatusStrip>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>. El controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> realiza una operación OR exclusiva (XOR) para cambiar el valor de la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
 Para usar este ejemplo de código, compile y ejecute la aplicación y, a continuación, haga clic en **Middle (Spring)** en el <xref:System.Windows.Forms.StatusStrip> control para cambiar el valor de la <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> propiedad.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
