---
title: "Cómo: Implementar un control ToolStripRenderer personalizado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ecd8953d6fe2e4a22e6c3b5fcc294855ef3a1c8a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a>Cómo: Implementar un control ToolStripRenderer personalizado
Puede personalizar la apariencia de un control <xref:System.Windows.Forms.ToolStrip> implementando una clase que deriva de <xref:System.Windows.Forms.ToolStripRenderer>. Esta opción le da flexibilidad para crear un aspecto diferente al que proporcionan las clases <xref:System.Windows.Forms.ToolStripProfessionalRenderer> y <xref:System.Windows.Forms.ToolStripSystemRenderer>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo implementar una clase <xref:System.Windows.Forms.ToolStripRenderer> personalizada. En este ejemplo, el control `GridStrip` implementa un rompecabezas de mosaicos deslizantes que permite al usuario trasladar mosaicos en un diseño de tabla para formar una imagen. Un control <xref:System.Windows.Forms.ToolStrip> personalizado organiza sus controles <xref:System.Windows.Forms.ToolStripButton> en un diseño de cuadrícula. El diseño contiene una celda vacía en la que el usuario puede deslizar un mosaico adyacente mediante una operación de arrastrar y colocar. Se resaltan los mosaicos que el usuario puede mover.  
  
 La clase `GridStripRenderer` personaliza tres aspectos del aspecto del control `GridStrip`:  
  
-   Borde `GridStrip`  
  
-   Borde <xref:System.Windows.Forms.ToolStripButton>  
  
-   Imagen <xref:System.Windows.Forms.ToolStripButton>  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
 Para información sobre cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilación desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Compilar desde la línea de comandos con csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Vea también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
