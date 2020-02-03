---
title: Funcionamiento de la entrada del mouse
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, mouse input
- mouse [Windows Forms], input
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
ms.openlocfilehash: 1164974e65ca1e96c0650569626ad4140baf004e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739625"
---
# <a name="how-mouse-input-works-in-windows-forms"></a>Funcionamiento de la entrada del mouse (ratón) en los formularios Windows Forms
Recibir y controlar la entrada del mouse es una parte importante de cada aplicación de Windows. Puede controlar los eventos del mouse para realizar una acción en la aplicación o usar la información de la ubicación del mouse para realizar pruebas de posicionamiento u otras acciones. Además, puede cambiar la forma en que los controles de la aplicación controlan la entrada del mouse. En este tema se describen los eventos del mouse en detalle y cómo obtener y cambiar la configuración del sistema para el mouse. Para obtener más información sobre los datos proporcionados con los eventos del mouse y el orden en que se producen los eventos de clic del mouse, consulte [eventos del mouse en Windows Forms](mouse-events-in-windows-forms.md).  
  
## <a name="mouse-location-and-hit-testing"></a>Ubicación del mouse y prueba de aciertos  
 Cuando el usuario mueve el mouse, el sistema operativo mueve el puntero del mouse. El puntero del mouse contiene un solo píxel, denominado zona activa, que el sistema operativo realiza un seguimiento y reconoce como la posición del puntero. Cuando el usuario mueve el mouse o presiona un botón del mouse, el <xref:System.Windows.Forms.Control> que contiene el <xref:System.Windows.Forms.Cursor.HotSpot%2A> provoca el evento del mouse adecuado. Puede obtener la posición actual del mouse con la propiedad <xref:System.Windows.Forms.MouseEventArgs.Location%2A> del <xref:System.Windows.Forms.MouseEventArgs> al controlar un evento del mouse o mediante la propiedad <xref:System.Windows.Forms.Cursor.Position%2A> de la clase <xref:System.Windows.Forms.Cursor>. Posteriormente, puede usar la información de ubicación del mouse para realizar pruebas de posicionamiento y, a continuación, realizar una acción en función de la ubicación del mouse. La funcionalidad de la prueba de posicionamiento está integrada en varios controles de Windows Forms como los controles <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> y <xref:System.Windows.Forms.DataGridView>. Si se usa con el evento del mouse adecuado, <xref:System.Windows.Forms.Control.MouseHover> por ejemplo, la prueba de posicionamiento es muy útil para determinar cuándo la aplicación debe realizar una acción específica.  
  
## <a name="mouse-events"></a>Eventos del mouse  
 La forma principal de responder a la entrada del mouse es controlar los eventos del mouse. En la tabla siguiente se muestran los eventos del mouse y se describe cuándo se generan.  
  
|Evento del mouse|Descripción|  
|-----------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Este evento se produce cuando se suelta el botón del mouse, normalmente antes del evento <xref:System.Windows.Forms.Control.MouseUp>. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>. Controle este evento cuando solo necesite determinar cuándo se produce un clic.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Este evento se produce cuando el usuario hace clic en el control con el mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Controle este evento cuando necesite obtener información sobre el mouse cuando se produce un clic.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Este evento se produce cuando se hace doble clic en el control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>. Controle este evento cuando solo necesite determinar cuándo se produce un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Este evento se produce cuando el usuario hace doble clic en el control con el mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Controle este evento cuando necesite obtener información sobre el mouse cuando se produce un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Este evento se produce cuando el puntero del mouse se sitúa sobre el control y el usuario presiona un botón del mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Este evento se produce cuando el puntero del Mouse entra en el área de borde o cliente del control, dependiendo del tipo de control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Este evento se produce cuando el puntero del mouse se detiene y se sitúa sobre el control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Este evento se produce cuando el puntero del mouse sale del área de borde o cliente del control, dependiendo del tipo de control. El controlador de este evento recibe un argumento del tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Este evento se produce cuando se mueve el puntero del mouse mientras se encuentra sobre un control. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Este evento se produce cuando el puntero del mouse se sitúa sobre el control y el usuario suelta un botón del mouse. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Este evento se produce cuando el usuario gira la rueda del mouse mientras el control tiene el foco. El controlador de este evento recibe un argumento del tipo <xref:System.Windows.Forms.MouseEventArgs>. Puede usar la propiedad <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> de <xref:System.Windows.Forms.MouseEventArgs> para determinar hasta qué punto se ha desplazado el mouse.|  
  
## <a name="changing-mouse-input-and-detecting-system-settings"></a>Cambiar la entrada del mouse y detectar la configuración del sistema  
 Puede detectar y cambiar la manera en que un control controla la entrada del mouse derivando del control y usando los métodos <xref:System.Windows.Forms.Control.GetStyle%2A> y <xref:System.Windows.Forms.Control.SetStyle%2A>. El método <xref:System.Windows.Forms.Control.SetStyle%2A> toma una combinación bit a bit de los valores de <xref:System.Windows.Forms.ControlStyles> para determinar si el control tendrá un comportamiento de clic o doble clic estándar, o si el control controlará su propio procesamiento del mouse. Además, la clase <xref:System.Windows.Forms.SystemInformation> incluye propiedades que describen las capacidades del mouse y especifican cómo interactúa el mouse con el sistema operativo. En la tabla siguiente se resumen estas propiedades.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Obtiene las dimensiones, en píxeles, del área en la que el usuario debe hacer clic dos veces para que el sistema operativo considere los dos clics como un doble clic.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Obtiene el número máximo de milisegundos que pueden transcurrir entre un primer clic y un segundo clic para que el sistema operativo considere que la acción del mouse es un doble clic.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Obtiene el número de botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Obtiene un valor que indica si se intercambiaron las funciones de los botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Obtiene las dimensiones, en píxeles, del rectángulo en el que el puntero del mouse debe permanecer un tiempo de desplazamiento para que se genere un mensaje de desplazamiento.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Obtiene el tiempo, en milisegundos, que el puntero del mouse tiene que permanecer en el rectángulo seleccionado mediante movimiento del mouse hasta que se genera un mensaje de movimiento del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Obtiene un valor que indica si hay un mouse instalado.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Obtiene un valor que indica la velocidad actual del mouse, de 1 a 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Obtiene un valor que indica si se instaló la rueda del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Obtiene la cantidad del valor Delta del incremento de un único giro de la rueda del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Obtiene el número de líneas de desplazamiento al girar la rueda del mouse.|  
  
## <a name="see-also"></a>Consulte también

- [Entradas mediante el mouse en una aplicación de Windows Forms](mouse-input-in-a-windows-forms-application.md)
- [Captura del mouse en Windows Forms](mouse-capture-in-windows-forms.md)
- [Punteros del mouse en Windows Forms](mouse-pointers-in-windows-forms.md)
