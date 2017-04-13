---
title: "How to: Perform Drag-and-Drop Operations Between Applications | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "drag and drop, between applications"
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Drag-and-Drop Operations Between Applications
Realizar operaciones de arrastrar y colocar entre aplicaciones es similar a habilitar esta acción dentro de una aplicación, siempre que ambas aplicaciones implicadas se comporten según el "contrato" establecido entre las propiedades <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> y <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.  
  
 En el siguiente procedimiento, usará una aplicación basada en Windows que cree y el procesador de textos WordPad que se incluye con el sistema operativo Windows para realizar operaciones de arrastrar y colocar entre aplicaciones.  WordPad tiene un determinado conjunto de efectos permitidos para el texto que se va a arrastrar y colocar; la aplicación basada en Windows para la que escribirá el código trabajará con estos efectos para que las operaciones de arrastrar y colocar puedan completarse correctamente.  
  
### Para realizar un procedimiento de arrastrar y colocar entre aplicaciones  
  
1.  Cree una nueva aplicación de Windows Forms.  
  
2.  Agregue un control <xref:System.Windows.Forms.TextBox> al formulario.  
  
3.  Configure el control <xref:System.Windows.Forms.TextBox> para recibir datos colocados.  
  
     Para obtener más información, consulte [Tutorial: Llevar a cabo una operación de arrastrar y colocar en Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Ejecute la aplicación basada en Windows y, mientras la aplicación se está ejecutando, ejecute WordPad.  
  
     WordPad es un editor de texto instalado por Windows que permite operaciones de arrastrar y colocar.  Para acceder a él, presione el botón **Inicio**, seleccione **Ejecutar**; después, escriba `WordPad` en el cuadro de texto del cuadro de diálogo **Ejecutar** y haga clic en **Aceptar**.  
  
5.  Una vez abierto WordPad, escriba una cadena de texto en él.  
  
6.  Use el mouse para seleccionar el texto y, después, arrastre el texto seleccionado al control <xref:System.Windows.Forms.TextBox> de la aplicación basada en Windows.  
  
     Observe que, cuando el mouse se desplaza sobre el control <xref:System.Windows.Forms.TextBox> \(y, por lo tanto, se genera el evento <xref:System.Windows.Forms.Control.DragEnter>\), el cursor cambia y puede colocar el texto seleccionado en el control <xref:System.Windows.Forms.TextBox>.  
  
     También puede configurar su control <xref:System.Windows.Forms.TextBox> para poder arrastrar y colocar cadenas de texto en WordPad.  Para obtener más información, consulte [Walkthrough: Performing a Drag\-and\-Drop Operation in Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## Vea también  
 [How to: Add Data to the Clipboard](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)   
 [How to: Retrieve Data from the Clipboard](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)   
 [Drag\-and\-Drop Operations and Clipboard Support](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)