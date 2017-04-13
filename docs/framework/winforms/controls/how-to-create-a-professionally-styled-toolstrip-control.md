---
title: "C&#243;mo: Crear un control ToolStrip de estilo profesional | Microsoft Docs"
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
  - "barras de herramientas [Windows Forms]"
  - "ToolStrip (control) [Windows Forms]"
  - "ToolStripProfessionalRenderer (clase) [Windows Forms]"
  - "ToolStripRenderer (clase) [Windows Forms]"
ms.assetid: c208b2f6-8105-474b-9075-d582e1792870
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un control ToolStrip de estilo profesional
Puede dar a los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación un aspecto y comportamiento profesional escribiendo su propia clase derivada del tipo <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
 Hay una amplia compatibilidad para esta característica en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Consulte [Tutorial: Crear un control ToolStrip de estilo profesional](../../../../docs/framework/winforms/controls/walkthrough-creating-a-professionally-styled-toolstrip-control.md).  
  
## Ejemplo  
 El ejemplo de código siguiente muestra cómo utilizar los controles <xref:System.Windows.Forms.ToolStrip> para crear un control compuesto que imite el **Panel de navegación** de Microsoft® Outlook®.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/CS/StackView.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.StackView#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.StackView/VB/StackView.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Tutorial: Crear un control ToolStrip de estilo profesional](http://msdn.microsoft.com/library/ms233664\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)   
 [Cómo: Proporcionar elementos de menú estándar a un formulario](../../../../docs/framework/winforms/controls/how-to-provide-standard-menu-items-to-a-form.md)