---
title: "C&#243;mo: Establecer la representaci&#243;n de ToolStrip para una aplicaci&#243;n | Microsoft Docs"
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
  - "Renderer (propiedad) [Windows Forms]"
  - "barras de herramientas [Windows Forms], personalizar"
  - "ToolStrip (control) [Windows Forms]"
  - "ToolStripProfessionalRenderer (clase) [Windows Forms]"
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Establecer la representaci&#243;n de ToolStrip para una aplicaci&#243;n
Puede personalizar la apariencia de sus controles <xref:System.Windows.Forms.ToolStrip> de forma individual o para todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.  
  
## Ejemplo  
 En el ejemplo de código siguiente, se muestra cómo aplicar de forma selectiva un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> y un control <xref:System.Windows.Forms.MenuStrip>.  
  
 Para utilizar este ejemplo de código, compile y ejecute la aplicación y, a continuación, seleccione el ámbito de la representación personalizada desde el <xref:System.Windows.Forms.ComboBox> control.  Haga clic en **Aplicar** para establecer el representador.  
  
 Para ver la representación del elemento de menú personalizado, seleccione la opción <xref:System.Windows.Forms.MenuStrip> desde el control <xref:System.Windows.Forms.ComboBox>, haga clic en **Aplicar** y, a continuación, abra el elemento de menú **Archivo**.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Establezca la propiedad <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=fullName> para aplicar un representador personalizado a todos los controles <xref:System.Windows.Forms.ToolStrip> de la aplicación.  
  
 Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=fullName> para aplicar un representador personalizado a un control <xref:System.Windows.Forms.ToolStrip> individual.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System.Design, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripManager>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>   
 [ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)