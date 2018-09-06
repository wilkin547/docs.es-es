---
title: 'Cómo: Establecer la representación de ToolStrip para una aplicación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: b86724bda83c701ad5c5872ae8d97bb490158e76
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43773032"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>Cómo: Establecer la representación de ToolStrip para una aplicación
Puede personalizar la apariencia de sus controles <xref:System.Windows.Forms.ToolStrip> de forma individual o para todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo aplicar de forma selectiva un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> y un control <xref:System.Windows.Forms.MenuStrip>.  
  
 Para utilizar este ejemplo de código, compile y ejecute la aplicación y, a continuación, seleccione el ámbito de la representación personalizada desde el <xref:System.Windows.Forms.ComboBox> control. Haga clic en **Aplicar** para establecer el representador.  
  
 Para ver la representación del elemento de menú personalizado, seleccione el <xref:System.Windows.Forms.MenuStrip> opción desde el <xref:System.Windows.Forms.ComboBox> de control, haga clic en **aplicar**y, a continuación, abra el **archivo** elemento de menú.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Establezca la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> para aplicar un representador personalizado a todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.  
  
 Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> para aplicar un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> individual.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStripManager>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
