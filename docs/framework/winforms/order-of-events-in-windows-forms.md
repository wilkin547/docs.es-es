---
title: Orden de eventos
description: Obtenga información detallada sobre el orden de los eventos en Windows Forms durante varias fases importantes en la duración de las aplicaciones y los controles.
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: b16d544d11500b2c684e87a915fc4b8eec071faa
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904343"
---
# <a name="order-of-events-in-windows-forms"></a>Orden de eventos en los formularios Windows Forms
El orden en que se producen los eventos en las aplicaciones de Windows Forms es de particular interés para los programadores a los que les preocupa controlar cada uno de estos eventos uno por uno. Cuando una situación requiere un control minucioso de los eventos, por ejemplo, cuando se vuelven a dibujar partes del formulario, es necesario conocer el orden exacto en que los eventos se producen en tiempo de ejecución. En este tema se proporcionan algunos detalles sobre el orden de los eventos en varias fases importantes de la duración de las aplicaciones y los controles. Para obtener detalles específicos sobre el orden de los eventos de entrada del mouse, consulte [eventos del mouse en Windows Forms](mouse-events-in-windows-forms.md). Para obtener información general sobre los eventos de Windows Forms, consulte [información general sobre eventos](events-overview-windows-forms.md). Para obtener más información sobre la composición de los controladores de eventos, vea [información general](event-handlers-overview-windows-forms.md)sobre los controladores de eventos.  
  
## <a name="application-startup-and-shutdown-events"></a>Eventos de inicio y cierre de la aplicación  
 Las clases <xref:System.Windows.Forms.Form> y <xref:System.Windows.Forms.Control> exponen un conjunto de eventos relacionados con el inicio y el cierre de la aplicación. Cuando se inicia una aplicación de Windows Forms, se generan los eventos de inicio del formulario principal en el orden siguiente:  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 Cuando se cierra una aplicación, se generan los eventos de cierre del formulario principal en el orden siguiente:  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 El evento <xref:System.Windows.Forms.Application.ApplicationExit> de la clase <xref:System.Windows.Forms.Application> se genera después de los eventos de cierre del formulario principal.  
  
> [!NOTE]
> Visual Basic 2005 incluye eventos de aplicación adicionales, como <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> y <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.  
  
## <a name="focus-and-validation-events"></a>Eventos de foco y validación  
 Al cambiar el foco mediante el teclado (TAB, MAYÚS+TAB, etc.) mediante una llamada a los métodos <xref:System.Windows.Forms.Control.Select%2A> o <xref:System.Windows.Forms.Control.SelectNextControl%2A>, o estableciendo la propiedad <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> en el formulario actual, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 Al cambiar el foco mediante el mouse o mediante una llamada al método <xref:System.Windows.Forms.Control.Focus%2A>, los eventos de foco de la clase <xref:System.Windows.Forms.Control> se generan en el orden siguiente:  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a>Consulte también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
