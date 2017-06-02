---
title: "Using Keyboard Events | Microsoft Docs"
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
  - "KeyPress event"
  - "keyboards, keyboard events"
  - "KeyUp event"
  - "KeyDown event"
  - "keyboard events"
  - "events [Windows Forms], keyboard"
ms.assetid: d3f3e14b-a459-4ee6-9875-8957e34f8ee9
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Using Keyboard Events
La mayoría de los programas de Windows Forms procesan la entrada de teclado controlando los eventos de teclado.  Este ofrece una introducción a los eventos de teclado, incluidos detalles sobre cuándo usar cada evento y los datos que se proporcionan para cada evento.  Consulte también [Información general sobre controladores de eventos \(Windows Forms\)](http://msdn.microsoft.com/library/be6fx1bb%20\(v=vs.110\)), [Información general sobre eventos \(Windows Forms\)](http://msdn.microsoft.com/library/1h12f09z%20\(v=vs.110\))  
  
## Eventos de teclado  
 Windows Forms proporciona dos eventos que se producen cuando el usuario presiona una tecla del teclado y un evento cuando el usuario suelta una tecla del teclado:  
  
-   El evento <xref:System.Windows.Forms.Control.KeyDown>, que se produce una vez.  
  
-   El evento <xref:System.Windows.Forms.Control.KeyPress>, que se puede producir varias veces cuando un usuario mantiene presionada la misma tecla.  
  
-   El evento <xref:System.Windows.Forms.Control.KeyUp> se produce una vez cuando el usuario suelta una tecla.  
  
 Cuando un usuario presiona una tecla, Windows Forms determina qué evento se genera en función de si el mensaje del teclado especifica una tecla de carácter o una tecla física.  Para obtener más información sobre las teclas de carácter y físicas, consulte [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md).  
  
 En la tabla siguiente se describen los tres eventos de teclado.  
  
|Evento de teclado|Descripción|Resultados|  
|-----------------------|-----------------|----------------|  
|<xref:System.Windows.Forms.Control.KeyDown>|Este evento se genera cuando el usuario presiona una tecla física.|El controlador de <xref:System.Windows.Forms.Control.KeyDown> recibe:<br /><br /> <ul><li>Un parámetro <xref:System.Windows.Forms.KeyEventArgs> que proporciona la propiedad <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> \(que especifica un botón de teclado físico\).</li><li>La propiedad <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> \(MAYÚS, CTRL o ALT\).</li><li>La propiedad <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> \(que combina el código de tecla y el modificador\).  El parámetro <xref:System.Windows.Forms.KeyEventArgs> también proporciona:<br /><br /> <ul><li>La propiedad <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>, que se pueden establecer para evitar que el control subyacente reciba la tecla.</li><li>La propiedad <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>, que puede usarse para suprimir los eventos <xref:System.Windows.Forms.Control.KeyPress> y <xref:System.Windows.Forms.Control.KeyUp> para esa pulsación de tecla.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyPress>|Este evento se genera cuando las teclas presionadas dan como resultado un carácter.  Por ejemplo, un usuario presiona las teclas MAYÚS y "a" minúscula, que producirá un carácter "A" mayúscula.|<xref:System.Windows.Forms.Control.KeyPress> se genera después de <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>El controlador de <xref:System.Windows.Forms.Control.KeyPress> recibe:</li><li>Un parámetro <xref:System.Windows.Forms.KeyPressEventArgs>, que contiene el código de carácter de la tecla que se presionó.  Este código de carácter es único para cada combinación de una tecla de carácter y una tecla modificadora.<br /><br />     Por ejemplo, la tecla "A" generará:<br /><br /> <ul><li>El código de carácter 65, si se presiona con la tecla MAYÚS</li><li>O la tecla BLOQ MAYÚS, 97 si se presiona sola</li><li>Y 1, si se presiona con la tecla CTRL.</li></ul></li></ul>|  
|<xref:System.Windows.Forms.Control.KeyUp>|Este evento se genera cuando el usuario suelta una tecla física.|El controlador de <xref:System.Windows.Forms.Control.KeyUp> recibe:<br /><br /> <ul><li>Un parámetro <xref:System.Windows.Forms.KeyEventArgs>:<br /><br /> <ul><li>Que proporciona la propiedad <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> \(que especifica un botón de teclado físico\).</li><li>La propiedad <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> \(MAYÚS, CTRL o ALT\).</li><li>La propiedad <xref:System.Globalization.SortKey.KeyData%2A> \(que combina el código de tecla y el modificador\).</li></ul></li></ul>|  
  
## Vea también  
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md)   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)