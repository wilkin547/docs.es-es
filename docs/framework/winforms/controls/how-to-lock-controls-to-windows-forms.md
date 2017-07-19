---
title: "C&#243;mo: Bloquear controles en formularios Windows Forms | Microsoft Docs"
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
  - "controles [Windows Forms], bloquear"
  - "controles de Windows Forms, bloquear"
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Bloquear controles en formularios Windows Forms
Cuando diseñe la interfaz de usuario de una aplicación para Windows, puede bloquear los controles, una vez ubicados correctamente, para no moverlos ni cambiar su tamaño inadvertidamente al establecer otras propiedades.  
  
 Además, puede bloquear y desbloquear todos los controles del formulario a la vez, lo que resulta útil para formularios con muchos controles, o bien desbloquear controles individuales.  Una vez que haya ubicado todos los controles donde desea en el formulario, bloquéelos todos en su lugar para evitar movimientos erróneos.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para bloquear un control  
  
1.  En la ventana **Propiedades**, haga clic en la propiedad **Locked** y seleccione `true`.  \(Al hacer doble clic en el nombre cambiará la configuración de la propiedad.\)  
  
     Alternativamente, haga clic con el botón secundario en el control y elija **Bloquear controles**.  
  
    > [!NOTE]
    >  El bloqueo de controles impide arrastrarlos para cambiar su tamaño o su posición en la superficie de diseño.  Sin embargo, todavía puede cambiar el tamaño o la ubicación de los controles por medio de la ventana **Propiedades** o en el código.  
  
### Para bloquear todos los controles de un formulario  
  
1.  Desde el menú **Formato**, elija **Bloquear controles**.  
  
    > [!NOTE]
    >  Este comando bloquea también el tamaño del formulario, puesto que el formulario es también un control.  
  
### Para desbloquear todos los controles bloqueados de un formulario  
  
1.  Desde el menú **Formato**, elija **Bloquear controles**.  
  
     Todos los controles que estaban antes bloqueados en el formulario ahora están desbloqueados.  
  
### Para desbloquear individualmente los controles bloqueados  
  
1.  En la ventana **Propiedades**, haga clic en la propiedad **Locked** y seleccione `false`.  \(Al hacer doble clic en el nombre cambiará la configuración de la propiedad.\)  
  
## Vea también  
 [Controles de Windows Forms](../../../../docs/framework/winforms/controls/index.md)   
 [Organizar controles en formularios Windows Forms](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)   
 [Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)   
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Controles de formularios Windows Forms por función](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)