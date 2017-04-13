---
title: "C&#243;mo: Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario | Microsoft Docs"
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
  - "ToolStrip (control) [Windows Forms], asignar como primario a formularios"
  - "Windows Forms, asignar controles ToolStrip como primarios"
ms.assetid: a1c94a7f-6fc5-4e4c-84cf-ff11dc573d33
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Mover un objeto ToolStrip de un contenedor ToolStripContainer a un formulario
Utilice el procedimiento siguiente para mover un <xref:System.Windows.Forms.ToolStrip> de <xref:System.Windows.Forms.ToolStripContainer> a un formulario.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para mover un objeto ToolStrip de ToolStripContainer a un formulario  
  
1.  Seleccione <xref:System.Windows.Forms.ToolStrip>.  
  
2.  Corte el <xref:System.Windows.Forms.ToolStrip> presionando CTRL\+X o haga clic con el botón secundario del mouse en <xref:System.Windows.Forms.ToolStrip> y elija **Cortar** en el menú contextual.  
  
3.  Seleccione el formulario.  
  
4.  Pegue el <xref:System.Windows.Forms.ToolStrip> presionando CTRL\+V o elija **Pegar** en el menú **Editar**.  
  
5.  Establezca la propiedad <xref:System.Windows.Forms.ToolStrip.Dock%2A> del <xref:System.Windows.Forms.ToolStrip> en **Top**.  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripContainer>   
 [Información sobre el control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)