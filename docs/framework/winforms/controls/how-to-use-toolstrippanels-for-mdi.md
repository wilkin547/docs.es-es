---
title: "C&#243;mo: Utilizar controles ToolStripPanel para MDI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI, utilizar controles ToolStripPanel [Windows Forms]"
  - "barras de herramientas [Windows Forms], utilizar para MDI"
  - "ToolStripPanel (control) [Windows Forms], utilizar para MDI"
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Utilizar controles ToolStripPanel para MDI
<xref:System.Windows.Forms.ToolStripPanel> proporciona flexibilidad para las aplicaciones de interfaz de múltiples documentos \(MDI\) mediante el método <xref:System.Windows.Forms.ToolStripPanel.Join%2A>.  
  
## Ejemplo  
 El siguiente ejemplo de código muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> para MDI.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripPanel>   
 [Cómo: Unir ToolStripPanels](../../../../docs/framework/winforms/controls/how-to-join-toolstrippanels.md)