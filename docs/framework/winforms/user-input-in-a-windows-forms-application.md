---
title: "User Input in a Windows Forms Application | Microsoft Docs"
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
  - "Windows Forms, user input"
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# User Input in a Windows Forms Application
En los formularios Windows Forms, los datos introducidos por el usuario se envían a las aplicaciones como mensajes de Windows.  Una serie de métodos reemplazables procesan estos mensajes en el nivel de la aplicación, formulario y control.  Cuando estos métodos reciben los mensajes del mouse y del teclado, provocan eventos que se pueden controlar para obtener información sobre las entradas del teclado y del mouse.  En muchos casos, al controlar estos eventos las aplicaciones de Windows Forms podrán procesar todos los datos introducidos por el usuario.  En otros casos, la aplicación puede tener que reemplazar uno de los métodos que procesan mensajes para interceptar un mensaje específico antes de que lo reciba la aplicación, el formulario o el control.  
  
## Eventos del mouse y del teclado  
 Todos los controles de los formularios Windows Forms heredan un conjunto de eventos relacionados con las entradas del teclado y del mouse.  Por ejemplo, un control puede controlar el evento <xref:System.Windows.Forms.Control.KeyPress> para determinar el código de carácter de una tecla que se ha presionado, o un control puede controlar el evento <xref:System.Windows.Forms.Control.MouseClick> para determinar la ubicación de un clic del mouse.  Para obtener más información sobre los eventos de teclado y de mouse, vea [Using Keyboard Events](../../../docs/framework/winforms/using-keyboard-events.md) y [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Métodos que procesan los mensajes de datos introducidos por el usuario  
 Los formularios y los controles tienen acceso a la interfaz <xref:System.Windows.Forms.IMessageFilter> y a un conjunto de métodos reemplazables que procesan mensajes de Windows en distintos puntos de la cola de mensajes.  Todos estos métodos tienen un parámetro <xref:System.Windows.Forms.Message>, que encapsula los detalles de bajo nivel de los mensajes de Windows.  Puede implementar o reemplazar estos métodos para examinar el mensaje y luego utilizar el mensaje o bien pasarlo al siguiente consumidor de la cola de mensajes.  En la tabla siguiente se presentan los métodos que procesan todos los mensajes de Windows en los formularios Windows Forms.  
  
|Método|Notas|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Este método intercepta mensajes de Windows puestos en cola \(o enviados\) en el nivel de la aplicación.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Este método intercepta los mensajes de Windows en el nivel del formulario y del control antes de que se hayan procesado.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Este método procesa mensajes de Windows en el nivel del formulario y del control.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Este método realiza el procesamiento predeterminado de los mensajes de Windows en el nivel del formulario y del control.  Este procedimiento proporciona la funcionalidad mínima de una ventana.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Este método intercepta los mensajes en el nivel del formulario y del control, después de que se hayan procesado.  Hay que establecer el bit de estilo <xref:System.Windows.Forms.ControlStyles> para que se llame a este método.|  
  
 Un conjunto adicional de métodos reemplazables que son específicos a esos tipos de mensajes también procesan los mensajes del mouse y del teclado.  Para obtener más información, vea [How Keyboard Input Works](../../../docs/framework/winforms/how-keyboard-input-works.md) y [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  
  
## Vea también  
 [User Input in Windows Forms](../../../docs/framework/winforms/user-input-in-windows-forms.md)   
 [Keyboard Input in a Windows Forms Application](../../../docs/framework/winforms/keyboard-input-in-a-windows-forms-application.md)   
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)