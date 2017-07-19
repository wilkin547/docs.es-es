---
title: "Informaci&#243;n general sobre el componente NotifyIcon (Formularios Windows Forms) | Microsoft Docs"
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
  - "NotifyIcon"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "NotifyIcon (componente), acerca del componente NotifyIcon"
  - "iconos de la bandeja del sistema, acerca de los iconos de la bandeja del sistema"
  - "iconos de la bandeja del sistema, usar en Windows Forms"
ms.assetid: 5b9189fa-d4ae-41a6-9b97-eb1f44bb1a69
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general sobre el componente NotifyIcon (Formularios Windows Forms)
El componente <xref:System.Windows.Forms.NotifyIcon> de Windows Forms se usa normalmente para mostrar iconos para los procesos que se ejecutan en segundo plano y no muestran una interfaz de usuario gran parte del tiempo.  Un ejemplo sería un programa antivirus al que se puede acceder haciendo clic en un icono en el área de notificación de estado de la barra de tareas.  
  
## Propiedades clave de NotifyIcons  
 Cada componente <xref:System.Windows.Forms.NotifyIcon> muestra un solo icono en el área de estado.  Si tiene tres procesos en segundo plano y quiere mostrar un icono para cada uno, deberá agregar tres componentes <xref:System.Windows.Forms.NotifyIcon> al formulario.  Las propiedades clave del componente <xref:System.Windows.Forms.NotifyIcon> son <xref:System.Windows.Forms.NotifyIcon.Icon%2A> y <xref:System.Windows.Forms.NotifyIcon.Visible%2A>.  La propiedad <xref:System.Windows.Forms.NotifyIcon.Icon%2A> establece el icono que aparece en el área de estado.  Para que el icono aparezca, la propiedad <xref:System.Windows.Forms.NotifyIcon.Visible%2A> debe establecerse en `true`.  
  
 Si usa [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], tiene acceso a una gran biblioteca de imágenes estándar que puede usar con el control <xref:System.Windows.Forms.NotifyIcon>.  
  
## Opciones de NotifyIcons  
 Puede asociar globos de sugerencias, menús contextuales e información sobre herramientas a un <xref:System.Windows.Forms.NotifyIcon> para ayudar al usuario.  
  
 Para mostrar globos de sugerencias para un <xref:System.Windows.Forms.NotifyIcon>, llame al método <xref:System.Windows.Forms.NotifyIcon.ShowBalloonTip%2A> y especifique el intervalo de tiempo que quiere que el globo de sugerencias se muestre.  También puede especificar el texto, el icono y el título del globo de sugerencias con <xref:System.Windows.Forms.NotifyIcon.BalloonTipText%2A>, <xref:System.Windows.Forms.NotifyIcon.BalloonTipIcon%2A> y <xref:System.Windows.Forms.NotifyIcon.BalloonTipTitle%2A>, respectivamente.  Los componentes <xref:System.Windows.Forms.NotifyIcon> también pueden tener asociada información sobre herramientas y menús contextuales.  Para obtener más información, consulte [Información general sobre el componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md) e [Información general sobre ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md).  
  
## Vea también  
 <xref:System.Windows.Forms.NotifyIcon>   
 [NotifyIcon](../../../../docs/framework/winforms/controls/notifyicon-component-windows-forms.md)