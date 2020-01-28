---
title: Funcionalidad de arrastrar y colocar
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.assetid: 65cd2c03-8782-474e-b958-cbe43eeb902c
ms.openlocfilehash: 603dc158719c0b11def4386eb24a33f235cf3a42
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732752"
---
# <a name="drag-and-drop-functionality-in-windows-forms"></a>Funcionalidad de arrastrar y colocar en Windows Forms
Windows Forms incluye un conjunto de métodos, eventos y clases que implementan el comportamiento de arrastrar y colocar. En este tema se proporciona una introducción a la compatibilidad para arrastrar y colocar en Windows Forms.  Vea también [operaciones de arrastrar y colocar y soporte del portapapeles](./advanced/drag-and-drop-operations-and-clipboard-support.md).  
  
## <a name="performing-drag-and-drop-operations"></a>Realizar operaciones de arrastrar y colocar  
 Para realizar una operación de arrastrar y colocar, use el método <xref:System.Windows.Forms.Control.DoDragDrop%2A> de la clase <xref:System.Windows.Forms.Control>. Para obtener más información acerca de cómo se realiza una operación de arrastrar y colocar, consulte <xref:System.Windows.Forms.Control.DoDragDrop%2A>. Para obtener el rectángulo sobre el cual debe arrastrarse el puntero del mouse antes de que comience una operación de arrastrar y colocar, use la propiedad <xref:System.Windows.Forms.SystemInformation.DragSize%2A> de la clase <xref:System.Windows.Forms.SystemInformation>.  
  
## <a name="events-related-to-drag-and-drop-operations"></a>Eventos relacionados con las operaciones de arrastrar y colocar  
 Hay dos categorías de eventos en una operación de arrastrar y colocar: eventos que se producen en el destino actual de la operación de arrastrar y colocar, y eventos que se producen en el origen de la operación de arrastrar y colocar.  
  
### <a name="events-on-the-current-target"></a>Eventos en el destino actual  
 En la tabla siguiente se muestran los eventos que se producen en el destino actual de una operación de arrastrar y colocar.  
  
|Evento del mouse|Descripción|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.DragEnter>|Este evento se produce cuando se arrastra un objeto dentro de los límites del control. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragOver>|Este evento se produce cuando se arrastra un objeto mientras el puntero del mouse está dentro de los límites del control. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragDrop>|Este evento se produce cuando se completa una operación de arrastrar y colocar. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.DragEventArgs>.|  
|<xref:System.Windows.Forms.Control.DragLeave>|Este evento se produce cuando se arrastra un objeto fuera de los límites del control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
  
 La clase <xref:System.Windows.Forms.DragEventArgs> proporciona la ubicación del puntero del mouse, el estado actual de los botones del mouse y las teclas modificadoras del teclado, los datos que se están arrastrando y valores <xref:System.Windows.Forms.DragDropEffects> que especifican las operaciones permitidas por el origen del evento de arrastrar y el efecto de colocar en el destino de la operación.  
  
### <a name="events-on-the-source"></a>Eventos en el origen  
 En la tabla siguiente se muestran los eventos que se producen en el origen de la operación de arrastrar y colocar.  
  
|Evento del mouse|Descripción|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.GiveFeedback>|Este evento se produce durante una operación de arrastre. Ofrece la oportunidad de dar una indicación visual al usuario de que se está produciendo la operación de arrastrar y colocar, por ejemplo, cambiar el puntero del mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.GiveFeedbackEventArgs>.|  
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|Este evento se produce durante una operación de arrastrar y colocar, y permite al origen de arrastre determinar si la operación de arrastrar y colocar tiene que cancelarse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.QueryContinueDragEventArgs>.|  
  
 La clase <xref:System.Windows.Forms.QueryContinueDragEventArgs> proporciona el estado actual de los botones del mouse y las teclas modificadoras del teclado, un valor que especifica si se presionó la tecla ESC y un valor <xref:System.Windows.Forms.DragAction> que se puede establecer para especificar si la operación de arrastrar y colocar debe continuar.  
  
## <a name="see-also"></a>Vea también

- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
