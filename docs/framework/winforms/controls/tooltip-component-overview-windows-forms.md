---
title: "Informaci&#243;n general sobre el componente ToolTip (formularios Windows Forms) | Microsoft Docs"
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
  - "ToolTip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "ToolTip (componente) [Windows Forms], acerca del componente ToolTip"
  - "información sobre herramientas [Windows Forms], acerca de la información sobre herramientas"
ms.assetid: 3fbc6f08-c882-4acd-a960-a08efe3c7e6e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Informaci&#243;n general sobre el componente ToolTip (formularios Windows Forms)
El componente <xref:System.Windows.Forms.ToolTip> de los formularios Windows Forms muestra texto cuando el usuario apunta a otros controles.  Un ToolTip puede asociarse a cualquier otro control.  Un ejemplo del uso de este componente es ahorrar espacio en un formulario. Por ejemplo, puede mostrar un pequeño icono en un botón y utilizar un control ToolTip para explicar la función del botón.  
  
## Trabajar con el componente ToolTip  
 El componente <xref:System.Windows.Forms.ToolTip> proporciona una propiedad `ToolTip` a distintos controles en un Windows Form u otro contenedor.  Por ejemplo, si se coloca un componente <xref:System.Windows.Forms.ToolTip> en un formulario, se puede mostrar "Escriba aquí su nombre" en un control <xref:System.Windows.Forms.TextBox> y "Haga clic aquí para guardar los cambios" en un control <xref:System.Windows.Forms.Button>.  
  
 Los métodos principales del componente <xref:System.Windows.Forms.ToolTip> son <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> y <xref:System.Windows.Forms.ToolTip.GetToolTip%2A>.  Puede utilizar el método <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> para establecer el componente ToolTips mostrado en los controles.  Para obtener más información, vea [Cómo: Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md).  Las propiedades principales son <xref:System.Windows.Forms.ToolTip.Active%2A>, que debe establecerse en `true` para que aparezca el componente ToolTip, y <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>, que establece el tiempo que debe mostrarse el componente, cuánto tiempo debe apuntar el usuario en el control para que aparezca el componente y cuánto tarda en aparecer la ventana del componente ToolTip siguiente.  Para obtener más información, vea [Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md).  
  
## Vea también  
 <xref:System.Windows.Forms.ToolTip>   
 [Cómo: Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)   
 [Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)