---
title: "Informaci&#243;n general sobre el control RadioButton (formularios Windows Forms) | Microsoft Docs"
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
  - "RadioButton"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "botones de opción, acerca de los botones de opción"
  - "botones de opción, determinar el estado"
  - "RadioButton (control) [Windows Forms], acerca del control RadioButton"
  - "RadioButton (control) [Windows Forms], determinar el estado"
ms.assetid: cd11f0c2-d098-4022-adf9-1455bc166a13
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el control RadioButton (formularios Windows Forms)
Los controles <xref:System.Windows.Forms.RadioButton> de Windows Forms presentan al usuario un conjunto de dos o más opciones excluyentes entre sí.  Aunque puede parecer que los botones de radio y las casillas funcionan de forma parecida, existe una diferencia importante: cuando un usuario selecciona un botón de radio, no puede seleccionar ninguno de los otros botones de radio del mismo grupo sin perder la selección de este botón.  En cambio, es posible activar tantas casillas como se desee.  Al definir un grupo de botones de radio, se indica al usuario que "tiene este conjunto de opciones entre las que puede elegir una y solamente una".  
  
## Utilizar el control  
 Cuando se hace clic en un control <xref:System.Windows.Forms.RadioButton>, su propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A> se establece en `true` y se llama al controlador de eventos <xref:System.Windows.Forms.Control.Click>.  El evento <xref:System.Windows.Forms.RadioButton.CheckedChanged> se produce cuando cambia el valor de la propiedad <xref:System.Windows.Forms.RadioButton.Checked%2A>.  Si la propiedad <xref:System.Windows.Forms.RadioButton.AutoCheck%2A> se establece en `true` \(la opción predeterminada\), al seleccionar el botón de radio se desactivarán automáticamente los demás botones de radio del grupo.  Normalmente, esta propiedad sólo se establece en `false` cuando se utiliza código de validación para comprobar que el botón de radio seleccionado corresponde a una opción válida.  El texto que se muestra dentro del control se establece con la propiedad <xref:System.Windows.Forms.Control.Text%2A>, que puede contener teclas de acceso directo.  Una tecla de acceso permite al usuario "hacer clic" en el otro control si presiona simultáneamente la tecla ALT y la tecla de acceso.  Para obtener más información, vea [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md) y [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  
  
 Si se establece la propiedad <xref:System.Windows.Forms.RadioButton.Appearance%2A> en <xref:System.Windows.Forms.Appearance>, el control <xref:System.Windows.Forms.RadioButton> puede tener la apariencia de un botón de comando, que parece estar presionado cuando está seleccionado.  Los botones de radio también muestran imágenes mediante las propiedades <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A>.  Para obtener más información, vea [Cómo: Establecer la imagen que muestra un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.RadioButton>   
 [Información general del control Panel](../../../../docs/framework/winforms/controls/panel-control-overview-windows-forms.md)   
 [Información general sobre el control GroupBox](../../../../docs/framework/winforms/controls/groupbox-control-overview-windows-forms.md)   
 [Información general sobre el control CheckBox](../../../../docs/framework/winforms/controls/checkbox-control-overview-windows-forms.md)   
 [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md)   
 [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)   
 [Cómo: Agrupar controles RadioButton de formularios Windows Forms para que funcionen como un conjunto](../../../../docs/framework/winforms/controls/how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md)   
 [RadioButton \(Control\)](../../../../docs/framework/winforms/controls/radiobutton-control-windows-forms.md)