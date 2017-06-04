---
title: "Informaci&#243;n general sobre StatusBar (Control, formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "StatusBar"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "barras de estado"
  - "StatusBar (control) [Windows Forms], acerca del control StatusBar"
ms.assetid: b7b9852c-633d-4416-bb2e-94852b989c6c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Informaci&#243;n general sobre StatusBar (Control, formularios Windows Forms)
> [!IMPORTANT]
>  Los controles <xref:System.Windows.Forms.StatusStrip> y <xref:System.Windows.Forms.ToolStripStatusLabel> reemplazan a los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel>, y les agregan funcionalidad; sin embargo, los controles <xref:System.Windows.Forms.StatusBar> y <xref:System.Windows.Forms.StatusBarPanel> se conservan para obtener la compatibilidad con versiones anteriores y para su uso futuro, si se desea.  
  
 [StatusBar](../../../../docs/framework/winforms/controls/statusbar-control-windows-forms.md) de Windows Forms se utiliza en los formularios como un área, normalmente en la parte inferior de una ventana, donde una aplicación puede mostrar varios tipos de información de estado.  Los controles <xref:System.Windows.Forms.StatusBar> pueden contener paneles de barra de estado que muestren iconos de texto para indicar el estado. También pueden contener una serie de iconos animados que indiquen que un proceso está funcionando; por ejemplo, [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] indica que el documento se está guardando.  
  
## Utilizar el control StatusBar  
 Internet Explorer utiliza una barra de estado que indica la dirección URL de una página cuando el mouse pasa sobre el hipervínculo; [!INCLUDE[ofprword](../../../../includes/ofprword-md.md)] ofrece información sobre la ubicación de página, la ubicación de sección y los modos de edición, tales como el seguimiento de sobrescrituras y revisiones; por último, [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] utiliza la barra de estado para ofrecer información contextual, por ejemplo, indicaciones de cómo manipular las ventanas acoplables, ya sea acopladas o flotantes.  
  
 Para mostrar un único mensaje en la barra de estado, establezca la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `false` \(el valor predeterminado\) y la propiedad <xref:System.Windows.Forms.StatusBar.Text%2A> de la barra de estado en el texto que desee que aparezca en la barra de estado.  Puede dividir la barra de estado en varios paneles para mostrar más de un tipo de información; para ello, establezca la propiedad <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> en `true` y utilice el método <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection.Add%2A> de <xref:System.Windows.Forms.StatusBar.StatusBarPanelCollection>.  
  
## Vea también  
 <xref:System.Windows.Forms.StatusBar>   
 <xref:System.Windows.Forms.ToolStripStatusLabel>   
 [Cómo: Determinar en qué panel del control StatusBar de formularios Windows Forms se hizo clic](../../../../docs/framework/winforms/controls/determine-which-panel-wf-statusbar-control-was-clicked.md)