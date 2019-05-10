---
title: Procedimiento para usar controles ToolStripPanel para MDI
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], using ToolStripPanels [Windows Forms]
- ToolStripPanel control [Windows Forms], using for MDI
- toolbars [Windows Forms], using for MDI
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
ms.openlocfilehash: 2dfab5bb6e31454f97407502971f305794e01d7a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622354"
---
# <a name="how-to-use-toolstrippanels-for-mdi"></a>Procedimiento para usar controles ToolStripPanel para MDI
<xref:System.Windows.Forms.ToolStripPanel> proporciona flexibilidad para las aplicaciones de interfaz de múltiples documentos (MDI) mediante el método <xref:System.Windows.Forms.ToolStripPanel.Join%2A>.  
  
## <a name="example"></a>Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> para MDI.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStripPanel>
- [Cómo: Unir ToolStripPanels](how-to-join-toolstrippanels.md)
