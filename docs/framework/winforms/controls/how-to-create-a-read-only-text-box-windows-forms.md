---
title: "C&#243;mo: Crear un cuadro de texto de s&#243;lo lectura (formularios Windows Forms) | Microsoft Docs"
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
  - "cuadros de texto de sólo lectura"
  - "cuadros de texto, solo lectura"
  - "TextBox (control) [Windows Forms], solo lectura"
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un cuadro de texto de s&#243;lo lectura (formularios Windows Forms)
Puede transformar un cuadro de texto editable de formularios Windows Forms en un control de sólo lectura.  Por ejemplo, el cuadro de texto podría mostrar un valor que normalmente se edita pero que no se puede modificar en este caso debido al estado de la aplicación.  
  
### Para crear un cuadro de texto de sólo lectura  
  
1.  Establezca la propiedad <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> del control <xref:System.Windows.Forms.TextBox> en `true`.  Con la propiedad establecida en `true`, los usuarios pueden continuar desplazándose por el texto del cuadro de texto y resaltándolo, pero no pueden hacer cambios.  En un cuadro de texto se puede utilizar el comando **Copiar**; en cambio, no se pueden utilizar los comandos **Cortar** y **Pegar**.  
  
    > [!NOTE]
    >  La propiedad <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> sólo afecta a la interacción del usuario con el programa en tiempo de ejecución.  Podrá seguir modificando el contenido del cuadro de texto mediante programación en tiempo de ejecución; para ello, cambie la propiedad <xref:System.Windows.Forms.TextBox.Text%2A> del cuadro de texto.  
  
## Vea también  
 <xref:System.Windows.Forms.TextBox>   
 [Información general sobre el control TextBox](../../../../docs/framework/winforms/controls/textbox-control-overview-windows-forms.md)   
 [Cómo: Controlar el punto de inserción en un control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)   
 [Cómo: Crear un cuadro de texto de contraseña con el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)   
 [Cómo: Insertar comillas en una cadena](../../../../docs/framework/winforms/controls/how-to-put-quotation-marks-in-a-string-windows-forms.md)   
 [Cómo: Seleccionar texto en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-select-text-in-the-windows-forms-textbox-control.md)   
 [Cómo: Ver múltiples líneas en el control TextBox de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)   
 [TextBox \(Control\)](../../../../docs/framework/winforms/controls/textbox-control-windows-forms.md)