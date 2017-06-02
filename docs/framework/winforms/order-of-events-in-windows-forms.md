---
title: "Order of Events in Windows Forms | Microsoft Docs"
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
  - "events [Windows Forms], order of"
  - "focus event order"
  - "application shutdown event order"
  - "sequence, of events"
  - "validation events, order of"
  - "application startup event order"
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Order of Events in Windows Forms
El orden en que se producen los eventos en las aplicaciones de Windows Forms es de particular interés para los programadores a los que les preocupa controlar cada uno de estos eventos uno por uno.  Cuando una situación requiere un control minucioso de los eventos, por ejemplo, cuando se vuelven a dibujar partes del formulario, es necesario conocer el orden exacto en que los eventos se producen en tiempo de ejecución.  En este tema se proporcionan algunos detalles sobre el orden de los eventos en varias fases importantes de la duración de las aplicaciones y los controles.  Para obtener detalles específicos sobre el orden de los eventos de entrada del mouse, consulte [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  Para obtener información general sobre los eventos en Windows Forms, consulte [Events Overview](../../../docs/framework/winforms/events-overview-windows-forms.md).  Para obtener más información sobre la creación de controladores de eventos, consulte [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
## Eventos de inicio y cierre de la aplicación  
 Las clases <xref:System.Windows.Forms.Form> y <xref:System.Windows.Forms.Control> exponen un conjunto de eventos relacionados con el inicio y el cierre de la aplicación.  Cuando se inicia una aplicación de Windows Forms, se generan los eventos de inicio del formulario principal en el orden siguiente:  
  
-   <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.Load?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.Activated?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.Shown?displayProperty=fullName>  
  
 Cuando se cierra una aplicación, se generan los eventos de cierre del formulario principal en el orden siguiente:  
  
-   <xref:System.Windows.Forms.Form.Closing?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.FormClosing?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.Closed?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.FormClosed?displayProperty=fullName>  
  
-   <xref:System.Windows.Forms.Form.Deactivate?displayProperty=fullName>  
  
 El evento <xref:System.Windows.Forms.Application.ApplicationExit> de la clase <xref:System.Windows.Forms.Application> se genera después de los eventos de cierre del formulario principal.  
  
> [!NOTE]
>  Visual Basic 2005 incluye eventos de aplicación adicionales, como <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=fullName> y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=fullName>.  
  
## Eventos de foco y validación  
 Al cambiar el foco mediante el teclado \(TAB, MAYÚS\+TAB, etc.\) mediante una llamada a los métodos <xref:System.Windows.Forms.Control.Select%2A> o <xref:System.Windows.Forms.Control.SelectNextControl%2A>, o estableciendo la propiedad <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> en el formulario actual, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
 Al cambiar el foco mediante el mouse o mediante una llamada al método <xref:System.Windows.Forms.Control.Focus%2A>, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
## Vea también  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)