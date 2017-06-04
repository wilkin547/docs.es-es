---
title: "C&#243;mo: Crear un formulario MDI con combinaci&#243;n de men&#250;s y controles ToolStrip | Microsoft Docs"
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
  - "MenuStrip (control) [Windows Forms]"
  - "barras de herramientas [Windows Forms]"
  - "ToolStrip (control) [Windows Forms]"
  - "ToolStripPanel (control) [Windows Forms]"
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Crear un formulario MDI con combinaci&#243;n de men&#250;s y controles ToolStrip
El espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> es compatible con aplicaciones de interfaces de múltiples documentos \(MDI\) y el control <xref:System.Windows.Forms.MenuStrip> admite la combinación de menús.  Los formularios MDI también pueden ser compatibles con los controles <xref:System.Windows.Forms.ToolStrip>.  
  
 Hay una amplia compatibilidad para esta característica en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Consulte también [Tutorial: Crear un formulario MDI con combinación de menús y controles ToolStrip](http://msdn.microsoft.com/library/ms233676\(v=vs.110\)).  
  
## Ejemplo  
 En el siguiente ejemplo de código, se muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStripPanel> con un formulario MDI.  El formulario también admite la combinación de menús con menús secundarios.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo de código se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)