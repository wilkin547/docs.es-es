---
title: Funcionamiento de la entrada del mouse (ratón) en los formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: c9193ffa9ef34f1e43a92feec230fa2282264147
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203020"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Funcionamiento de la entrada del mouse (ratón) en los formularios Windows Forms
Recibir y controlar la entrada del mouse es una parte importante de cada aplicación de Windows. Puede controlar los eventos del mouse para llevar a cabo una acción en la aplicación, o usar la información de ubicación del mouse para realizar la prueba de posicionamiento u otras acciones. Además, puede cambiar la manera en que los controles en la aplicación controlan la entrada de mouse. En este tema se describe estos eventos del mouse en detalle y cómo obtener y cambiar la configuración del sistema para el mouse. Para obtener más información acerca de los datos proporcionados con el mouse se producen los eventos y el orden en que el mouse, haga clic en eventos, vea [eventos del Mouse en Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Ubicación del mouse y la prueba de posicionamiento  
 Cuando el usuario mueve el mouse, el sistema operativo mueve el puntero del mouse. El puntero del mouse contiene un solo píxel, llama a la zona activa, que el sistema operativo se realiza un seguimiento y se reconoce como la posición del puntero. Cuando el usuario mueve el mouse o presiona un botón del mouse, el <xref:System.Windows.Forms.Control> que contiene el <xref:System.Windows.Forms.Cursor.HotSpot%2A> provoca el evento del mouse adecuado. Puede obtener la posición actual del mouse con el <xref:System.Windows.Forms.MouseEventArgs.Location%2A> propiedad de la <xref:System.Windows.Forms.MouseEventArgs> al controlar un evento del mouse o mediante el <xref:System.Windows.Forms.Cursor.Position%2A> propiedad de la <xref:System.Windows.Forms.Cursor> clase. Puede posteriormente, usar información de ubicación del mouse para realizar la prueba de posicionamiento y, a continuación, realizar una acción basada en la ubicación del puntero del mouse. Capacidad de prueba de posicionamiento se halla integrado en varios controles en formularios de Windows, como el <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> y <xref:System.Windows.Forms.DataGridView> controles. Puede usar con el evento del mouse adecuado, <xref:System.Windows.Forms.Control.MouseHover> por ejemplo, la prueba de posicionamiento es muy útil para determinar cuándo la aplicación debe realizar una acción específica.  
  
## <a name="mouse-events"></a>Eventos del mouse  
 La manera principal para responder a la entrada del mouse es controlar los eventos del mouse. En la tabla siguiente muestra los eventos de mouse y describe cuándo se generan.  
  
|Evento del mouse|Descripción|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Este evento se produce cuando se suelta el botón del mouse, normalmente antes el <xref:System.Windows.Forms.Control.MouseUp> eventos. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>. Controle este evento cuando solo necesite determinar cuándo se produce un clic.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Este evento se produce cuando el usuario hace clic en el control con el mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Controle este evento cuando necesite obtener información sobre el mouse cuando se produce un clic.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Este evento se produce cuando se hace doble clic en el control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>. Controle este evento cuando solo necesite determinar cuándo se produce un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Este evento se produce cuando el usuario hace doble clic en el control con el mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Controle este evento cuando se necesita obtener información sobre el mouse cuando se produce un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Este evento se produce cuando el puntero del mouse está encima del control y el usuario presiona un botón del mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Este evento se produce cuando el puntero del mouse entra en el área de cliente o el borde del control, según el tipo de control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Este evento se produce cuando el puntero del mouse se detenga y se sitúa sobre el control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Este evento se produce cuando el puntero del mouse abandona el área de cliente o el borde del control, según el tipo del control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Este evento se produce cuando el puntero del mouse se mueve mientras está sobre un control. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Este evento se produce cuando el puntero del mouse está encima del control y el usuario suelta un botón del mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Este evento se produce cuando el usuario gira la rueda del mouse mientras el control tiene el foco. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Puede usar el <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> propiedad de <xref:System.Windows.Forms.MouseEventArgs> para determinar hasta qué punto se ha desplazado el mouse.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Cambiar la entrada del Mouse y para detectar la configuración del sistema  
 Puede detectar y cambiar la forma en que un control controla la entrada de mouse derivando desde el control y utilizando el <xref:System.Windows.Forms.Control.GetStyle%2A> y <xref:System.Windows.Forms.Control.SetStyle%2A> métodos. El <xref:System.Windows.Forms.Control.SetStyle%2A> método toma una combinación bit a bit de <xref:System.Windows.Forms.ControlStyles> valores para determinar si el control tendrá estándar, haga clic en o haga doble clic en el comportamiento o si el control controlará su propio procesamiento de mouse. Además, el <xref:System.Windows.Forms.SystemInformation> clase incluye propiedades que describen las capacidades del mouse y especifican cómo interactúa el mouse con el sistema operativo. En la tabla siguiente se resume estas propiedades.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Obtiene las dimensiones, en píxeles, del área en la que el usuario debe hacer clic dos veces para que el sistema operativo considere los dos clics como un doble clic.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Obtiene el número máximo de milisegundos que pueden pasar entre un primer clic y un segundo clic para que el sistema operativo, considere la acción del mouse en un doble clic.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Obtiene el número de botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Obtiene un valor que indica si se intercambiaron las funciones de los botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Obtiene las dimensiones, en píxeles, del rectángulo en el que el puntero del mouse debe permanecer un tiempo de desplazamiento para que se genere un mensaje de desplazamiento.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Obtiene el tiempo, en milisegundos, que el puntero del mouse tiene que permanecer en el rectángulo seleccionado mediante movimiento del mouse hasta que se genera un mensaje de movimiento del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Obtiene un valor que indica si está instalado un mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Obtiene un valor que indica la velocidad del mouse actual, de 1 a 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Obtiene un valor que indica si se instaló la rueda del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Obtiene la cantidad del valor de incremento del incremento de un giro de la rueda del mouse único.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Obtiene el número de líneas de desplazamiento al girar la rueda del mouse.|  
  
## <a name="see-also"></a>Vea también

- [Entradas mediante el mouse (ratón) en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Captura del mouse (ratón) en formularios Windows Forms](mouse-capture-in-windows-forms.md)
- [Punteros del mouse (ratón) en formularios Windows Forms](mouse-pointers-in-windows-forms.md)
