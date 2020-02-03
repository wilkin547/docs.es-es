---
title: Datos proporcionados por el usuario en una aplicación Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, user input
ms.assetid: 9d61fa96-70f7-4754-885a-49a4a6316bdb
ms.openlocfilehash: 8e82276f14519c4ef54948744c93014232bdff52
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734806"
---
# <a name="user-input-in-a-windows-forms-application"></a>Datos proporcionados por el usuario en una aplicación de Windows Forms
En Windows Forms, los datos proporcionados por el usuario se envían a las aplicaciones en forma de mensajes de Windows. Una serie de métodos reemplazables procesa estos mensajes en el nivel de aplicación, formulario y control. Cuando estos métodos reciben los mensajes del mouse y del teclado, generan eventos que se pueden controlar para obtener información sobre la entrada del mouse o del teclado. En muchos casos, las aplicaciones Windows Forms podrán procesar todos los datos proporcionados por el usuario mediante el control de estos eventos. En otros casos, es posible que una aplicación necesite reemplazar uno de los métodos que procesan los mensajes para interceptar un mensaje determinado antes de que lo reciba la aplicación, el formulario o el control.  
  
## <a name="mouse-and-keyboard-events"></a>Eventos del mouse y del teclado  
 Todos los controles de Windows Forms heredan un conjunto de eventos relacionados con la entrada de mouse y teclado. Por ejemplo, un control puede controlar el evento <xref:System.Windows.Forms.Control.KeyPress> para determinar el código de carácter de una tecla que se presionó, o un control puede controlar el evento <xref:System.Windows.Forms.Control.MouseClick> para determinar la ubicación de un clic del mouse. Para obtener más información sobre los eventos del mouse y del teclado, vea [usar eventos de teclado](using-keyboard-events.md) y [eventos del mouse en Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="methods-that-process-user-input-messages"></a>Métodos que procesan los mensajes de entrada del usuario  
 Los formularios y controles tienen acceso a la interfaz de <xref:System.Windows.Forms.IMessageFilter> y un conjunto de métodos reemplazables que procesan los mensajes de Windows en distintos puntos de la cola de mensajes. Todos estos métodos tienen un parámetro <xref:System.Windows.Forms.Message>, que encapsula los detalles de bajo nivel de los mensajes de Windows. Puede implementar o invalidar estos métodos para examinar el mensaje y, a continuación, utilizar el mensaje o pasarlo al siguiente consumidor en la cola de mensajes. En la tabla siguiente se presentan los métodos que procesan todos los mensajes de Windows en Windows Forms.  
  
|Método|Notas|  
|------------|-----------|  
|<xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A>|Este método intercepta mensajes de Windows en cola (también conocidos como publicados) en el nivel de aplicación.|  
|<xref:System.Windows.Forms.Control.PreProcessMessage%2A>|Este método intercepta los mensajes de Windows en el nivel de formulario y de control antes de que se hayan procesado.|  
|<xref:System.Windows.Forms.Control.WndProc%2A>|Este método procesa los mensajes de Windows en el nivel de formulario y de control.|  
|<xref:System.Windows.Forms.Control.DefWndProc%2A>|Este método realiza el procesamiento predeterminado de los mensajes de Windows en el nivel de formulario y de control. Esto proporciona la funcionalidad mínima de una ventana.|  
|<xref:System.Windows.Forms.Control.OnNotifyMessage%2A>|Este método intercepta los mensajes en el nivel de formulario y control, una vez que se han procesado. Se debe establecer el bit de estilo <xref:System.Windows.Forms.ControlStyles.EnableNotifyMessage> para que se llame a este método.|  
  
 Los mensajes del teclado y del mouse también se procesan mediante un conjunto adicional de métodos reemplazables que son específicos de esos tipos de mensajes. Para obtener más información, vea [Cómo funciona la entrada mediante teclado](how-keyboard-input-works.md) y [Cómo funciona la entrada del mouse en Windows Forms](how-mouse-input-works-in-windows-forms.md).  
  
## <a name="see-also"></a>Consulte también

- [Datos proporcionados por el usuario en Windows Forms](user-input-in-windows-forms.md)
- [Entradas mediante teclado en una aplicación de Windows Forms](keyboard-input-in-a-windows-forms-application.md)
- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
