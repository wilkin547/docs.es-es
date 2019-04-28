---
title: Datos introducidos por el usuario en una aplicación de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 0eb39f0ecd8fcd12918b38bd77fed2ff32cac1d8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800144"
---
# <a name="user-input-in-a-windows-forms-application"></a>Datos introducidos por el usuario en una aplicación de formularios Windows Forms
En Windows Forms, proporcionados por el usuario se envían a las aplicaciones en forma de mensajes de Windows. Una serie de métodos reemplazables procesan estos mensajes en la aplicación, el formulario y controlar el nivel. Cuando estos métodos reciben los mensajes del mouse y teclado, generan eventos que pueden administrarse para obtener información sobre el mouse o entrada del teclado. En muchos casos, las aplicaciones de Windows Forms será capaces de procesar todas las entradas de usuario controlando estos eventos. En otros casos, una aplicación puede necesitar reemplazar uno de los métodos que procesan mensajes para interceptar un mensaje concreto antes de ser recibido por la aplicación, formulario o control.  
  
## <a name="mouse-and-keyboard-events"></a>Eventos del mouse y teclado  
 Todos los controles de Windows Forms heredan un conjunto de eventos relacionados con el mouse y teclado. Por ejemplo, un control puede controlar el <xref:System.Windows.Forms.Control.KeyPress> puede controlar el evento para determinar el código de carácter de una clave que se presionó, o un control de la <xref:System.Windows.Forms.Control.MouseClick> evento para determinar la ubicación de un mouse, haga clic en. Para obtener más información sobre los eventos del mouse y teclado, consulte [mediante eventos de teclado](using-keyboard-events.md) y [eventos del Mouse en Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Métodos que procesan los mensajes de entrada de usuario  
 Formularios y controles tienen acceso a la <xref:System.Windows.Forms.IMessageFilter> interfaz y un conjunto de métodos reemplazables que procesan los mensajes de Windows en distintos puntos de la cola de mensajes. Estos métodos tienen un <xref:System.Windows.Forms.Message> parámetro, que encapsula los detalles de bajo nivel de mensajes de Windows. Puede implementar o invalidar estos métodos para examinar el mensaje y consumir el mensaje o la pasa al siguiente consumidor en la cola de mensajes. En la tabla siguiente presenta los métodos que procesan todos los mensajes de Windows en Windows Forms.  
  
|Método|Notas|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Este método intercepta los mensajes de Windows (también conocido como expuestos) en cola en el nivel de aplicación.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Este método intercepta los mensajes de Windows en el nivel de formulario y el control antes de que se han procesado.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Este método procesa mensajes de Windows en el nivel de formulario y control.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Este método realiza el procesamiento predeterminado de mensajes de Windows en el nivel de formulario y control. Esto proporciona la funcionalidad mínima de una ventana.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Este método intercepta los mensajes en el nivel de formulario y control, una vez que se han procesado. El <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> se debe establecer el bit de estilo para que se llama a este método.|  
  
 También se procesan los mensajes del teclado y mouse (ratón) por un conjunto adicional de métodos reemplazables que son específicos de esos tipos de mensajes. Para obtener más información, consulte [cómo funciona la entrada de teclado](how-keyboard-input-works.md) y [cómo funciona de entrada de mouse (ratón) en Windows Forms](how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Vea también

- [Datos proporcionados por el usuario en Windows Forms](user-input-in-windows-forms.md)
- [Entradas mediante teclado en una aplicación de Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
