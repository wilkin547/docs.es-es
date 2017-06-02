---
title: "Informaci&#243;n general sobre el control Button (formularios Windows Forms) | Microsoft Docs"
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
  - "Button"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "control de botón [Windows Forms], acerca del control Button"
  - "botones, acerca de los botones"
ms.assetid: 255b291b-51a9-4a92-a1a4-2400cd82443f
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Informaci&#243;n general sobre el control Button (formularios Windows Forms)
El control <xref:System.Windows.Forms.Button> de Windows Forms permite al usuario hacer clic en él para ejecutar una acción.  Cuando se hace clic en el botón, da la sensación de que se ha presionado y soltado.  Cada vez que el usuario hace clic en un botón, se invoca al controlador del evento <xref:System.Windows.Forms.Control.Click>.  El código se ubica en el controlador del evento <xref:System.Windows.Forms.Control.Click> para ejecutar la acción deseada.  
  
 El texto que se muestra en el botón se almacena en la propiedad <xref:System.Windows.Forms.Control.Text%2A>.  Si este texto supera el ancho del botón, se ajustará en la línea siguiente.  No obstante, si el control no dispone del alto suficiente, el texto aparecerá cortado.  Para obtener más información, vea [Cómo: Establecer el texto mostrado por un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md).  La propiedad <xref:System.Windows.Forms.Control.Text%2A> puede contener una tecla de acceso, que permite al usuario presionar la tecla ALT junto con la tecla de acceso para "hacer clic" en el control.  Para obtener información detallada, vea [Cómo: Crear teclas de acceso para controles de Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-for-windows-forms-controls.md).  Las propiedades <xref:System.Windows.Forms.Control.Font%2A> y <xref:System.Windows.Forms.ButtonBase.TextAlign%2A> controlan la apariencia del texto.  
  
 El control <xref:System.Windows.Forms.Button> también muestra imágenes mediante las propiedades <xref:System.Windows.Forms.ButtonBase.Image%2A> y <xref:System.Windows.Forms.ButtonBase.ImageList%2A>.  Para obtener más información, vea [Cómo: Establecer la imagen que muestra un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-the-image-displayed-by-a-windows-forms-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.Button>   
 [Cómo: Responder a clics de botones en formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-respond-to-windows-forms-button-clicks.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Cómo: Designar un botón de formularios Windows Forms como botón para aceptar mediante el Diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-accept-button-using-the-designer.md)   
 [Cómo: Designar un botón de formularios Windows Forms como botón para cancelar mediante el Diseñador](../../../../docs/framework/winforms/controls/designate-a-wf-button-as-the-cancel-button-using-the-designer.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)