---
title: "How to: Determine Which Modifier Key Was Pressed | Microsoft Docs"
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
  - "keyboard input"
  - "shift keys"
  - "events [Windows Forms], mouse"
  - "Keys.ControlKey enumeration member"
  - "keys, control keys"
  - "user input, checking for keyboard"
  - "keys, determining last pressed"
  - "keys, shift keys"
  - "keys, modifier keys"
  - "control keys"
  - "keys, alt keys"
  - "alt keys"
  - "Keys.Shift enumeration member"
  - "events [Windows Forms], keyboard"
  - "keyboards, keyboard input"
  - "Keys.Alt enumeration member"
  - "modifier keys"
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Determine Which Modifier Key Was Pressed
Cuando cree una aplicación que acepte pulsaciones de teclas por parte del usuario, es posible que desee supervisar también teclas modificadoras tales como Mayús, Alt y Ctrl.  Cuando se presiona una tecla modificadora en combinación con otras teclas, o con clics del mouse, la aplicación puede responder adecuadamente.  Por ejemplo, si se presiona la letra S, esto puede hacer que simplemente aparezca una "s" en la pantalla, pero si presiona las teclas CTRL\+S, se puede guardar el documento actual.  Si controla el evento <xref:System.Windows.Forms.Control.KeyDown>, la propiedad <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> de <xref:System.Windows.Forms.KeyEventArgs> recibida por el controlador de eventos especifica qué teclas modificadoras se han presionado.  De forma alternativa, la propiedad <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> de <xref:System.Windows.Forms.KeyEventArgs> especifica el carácter que se presionó, así como cualquier tecla modificadora en combinación con una operación OR bit a bit.  Sin embargo, si está controlando el evento <xref:System.Windows.Forms.Control.KeyPress> o un evento del mouse, el controlador de eventos no recibe esta información.  En este caso, debe utilizar la propiedad <xref:System.Windows.Forms.Control.ModifierKeys%2A> de la clase <xref:System.Windows.Forms.Control>.  En cualquier caso, debe realizar una operación AND bit a bit del valor <xref:System.Windows.Forms.Keys> adecuado y el valor que está probando.  La enumeración <xref:System.Windows.Forms.Keys> proporciona variaciones de cada tecla modificadora, por lo que es importante que realice una operación AND bit a bit con el valor correcto.  Por ejemplo, <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys>, <xref:System.Windows.Forms.Keys> y <xref:System.Windows.Forms.Keys> representan la tecla MAYÚS y el valor correcto para probar la tecla MAYÚS como tecla modificadora es <xref:System.Windows.Forms.Keys>.  De forma similar, para probar las teclas CTLR y ALT como modificadores debería utilizar los valores <xref:System.Windows.Forms.Keys> y <xref:System.Windows.Forms.Keys> respectivamente.  
  
> [!NOTE]
>  Los programadores de Visual Basic también pueden obtener acceso a la información sobre las teclas a través de la propiedad <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A>.  
  
### Para determinar qué tecla modificadora se presionó  
  
-   Utilice el operador `AND` bit a bit con la propiedad <xref:System.Windows.Forms.Control.ModifierKeys%2A> y un valor de la enumeración <xref:System.Windows.Forms.Keys> para determinar si se presiona una tecla modificadora determinada.  El ejemplo de código siguiente muestra cómo determinar si la tecla MAYÚS se presiona dentro de un controlador de eventos <xref:System.Windows.Forms.Control.KeyPress>.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## Vea también  
 <xref:System.Windows.Forms.Keys>   
 <xref:System.Windows.Forms.Control.ModifierKeys%2A>   
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How to: Determine If CapsLock is On in Visual Basic](http://msdn.microsoft.com/es-es/91e60f5c-dd61-4222-ba5f-39af803afd8c)