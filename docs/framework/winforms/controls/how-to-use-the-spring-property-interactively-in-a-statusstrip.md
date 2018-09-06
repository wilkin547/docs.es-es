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
ms.openlocfilehash: 3319771cfcf671f5457bd3e95d264a694f9fa1c6
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744195"
---
# <a name="how-to-use-the-spring-property-interactively-in-a-statusstrip"></a>Cómo: Utilizar la propiedad Spring de manera interactiva en un control StatusStrip
Puede utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>. La propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> determina si el control <xref:System.Windows.Forms.ToolStripStatusLabel> rellena automáticamente el espacio disponible en el control <xref:System.Windows.Forms.StatusStrip>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> para colocar un control <xref:System.Windows.Forms.ToolStripStatusLabel> en un control <xref:System.Windows.Forms.StatusStrip>. El controlador de eventos <xref:System.Windows.Forms.ToolStripItem.Click> realiza una operación OR exclusiva (XOR) para cambiar el valor de la propiedad <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A>.  
  
 Para usar este ejemplo de código, compilar y ejecutar la aplicación y, a continuación, haga clic en **Middle (Spring)** en el <xref:System.Windows.Forms.StatusStrip> control para cambiar el valor de la <xref:System.Windows.Forms.ToolStripStatusLabel.Spring%2A> propiedad.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#50)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#50)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripStatusLabel>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
