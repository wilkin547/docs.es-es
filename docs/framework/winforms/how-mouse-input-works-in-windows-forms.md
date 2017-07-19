---
title: "How Mouse Input Works in Windows Forms | Microsoft Docs"
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
  - "Windows Forms, mouse input"
  - "mouse, input"
ms.assetid: 48fc5240-75a6-44bf-9fce-6aa21b49705a
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# How Mouse Input Works in Windows Forms
Recibir y controlar la entrada del mouse es un aspecto importante de cada aplicación para Windows.  Se pueden controlar los eventos del mouse para realizar una acción en la aplicación o utilizar la información de ubicación del mouse para realizar comprobaciones de visitas u otras acciones.  Además, puede cambiar el modo en que los controles de la aplicación controlan la entrada del mouse.  Este tema describe con detalle estos eventos del mouse y cómo obtener y cambiar la configuración del sistema para el mouse.  Para obtener más información sobre los datos proporcionados mediante los eventos del mouse y el orden en que se producen los eventos clic del mouse, vea [Mouse Events in Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md).  
  
## Ubicación del mouse y comprobación de visitas  
 Cuando el usuario mueve el mouse, el sistema operativo mueve el puntero.  El puntero del mouse contiene un único píxel, denominado punto activo que el sistema operativo sigue y reconoce como la posición del puntero.  Cuando el usuario mueve el mouse o presiona un botón del mismo, <xref:System.Windows.Forms.Control> que contiene <xref:System.Windows.Forms.Cursor.HotSpot%2A> provoca el evento correspondiente del mouse.  Puede obtener la posición actual del mouse con la propiedad <xref:System.Windows.Forms.MouseEventArgs.Location%2A> de <xref:System.Windows.Forms.MouseEventArgs> controlando un evento del mouse o utilizando la propiedad <xref:System.Windows.Forms.Cursor.Position%2A> de la clase <xref:System.Windows.Forms.Cursor>.  Posteriormente puede utilizar la información de ubicación del mouse para realizar la comprobación de visitas y, a continuación, realiza una acción basada en la ubicación del mouse.  La función de comprobación de visitas está integrada en varios controles de Windows Forms como <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.MonthCalendar> y los controles <xref:System.Windows.Forms.DataGridView>.  Si se utiliza con el evento del mouse adecuado, por ejemplo <xref:System.Windows.Forms.Control.MouseHover>, la comprobación de visitas es muy útil para determinar cuando debería realizar la aplicación una acción concreta.  
  
## Eventos del mouse  
 El modo principal para responder a la entrada del mouse es controlar los eventos del mouse.  La tabla siguiente muestra los eventos del mouse y describe cuando se producen.  
  
|Eventos del mouse|Descripción|  
|-----------------------|-----------------|  
|<xref:System.Windows.Forms.Control.Click>|Se produce cuando se suelta el botón del mouse, normalmente antes del evento <xref:System.Windows.Forms.Control.MouseUp>.  El controlador de este evento recibe un argumento de tipo <xref:System.EventArgs>.  Controle este evento cuando sólo necesite determinar cuando se debe producir un clic.|  
|<xref:System.Windows.Forms.Control.MouseClick>|Se produce cuando el usuario hace clic en el control.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.  Controle este evento cuando necesite obtener información sobre el mouse cuando se produce un clic.|  
|<xref:System.Windows.Forms.Control.DoubleClick>|Se produce cuando se hace doble clic en el control.  El controlador de este evento recibe un argumento de tipo <xref:System.EventArgs>.  Controle este evento cuando sólo necesite determinar cuando se debe producir un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDoubleClick>|Se produce cuando el usuario hace doble clic en el control.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.  Controle este evento cuando necesite obtener información sobre el mouse cuando se produce un doble clic.|  
|<xref:System.Windows.Forms.Control.MouseDown>|Se produce cuando el puntero del mouse se sitúa encima del control y el usuario presiona un botón del mouse.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseEnter>|Se produce cuando el puntero del mouse entra en el borde o área de cliente del control dependiendo del tipo de control.  El controlador de este evento recibe un argumento de tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseHover>|Se produce cuando el puntero del mouse se detiene y permanece sobre el control.  El controlador de este evento recibe un argumento de tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseLeave>|Se produce cuando el puntero del mouse deja el borde o área de cliente del control dependiendo del tipo de control.  El controlador de este evento recibe un argumento de tipo <xref:System.EventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseMove>|Se produce cuando el puntero del mouse se mantiene mientras se encuentra sobre un control.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseUp>|Se produce cuando el puntero del mouse se sitúa encima del control y el usuario suelta un botón del mouse.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.|  
|<xref:System.Windows.Forms.Control.MouseWheel>|Se produce cuando el usuario gira la rueda del mouse mientras el control tiene el foco.  El controlador de este evento recibe un argumento de tipo <xref:System.Windows.Forms.MouseEventArgs>.  Puede utilizar la propiedad <xref:System.Windows.Forms.MouseEventArgs.Delta%2A> de <xref:System.Windows.Forms.MouseEventArgs> para determinar el recorrido de desplazamiento del mouse.|  
  
## Cambiar la entrada del mouse y detectar la configuración del sistema  
 Puede detectar y cambiar la manera en que un control controla la entrada del mouse derivando del control y utilizando los métodos <xref:System.Windows.Forms.Control.GetStyle%2A> y <xref:System.Windows.Forms.Control.SetStyle%2A>.  El método <xref:System.Windows.Forms.Control.SetStyle%2A> utiliza una combinación bit a bit de los valores <xref:System.Windows.Forms.ControlStyles> para determinar si el control tendrá un comportamiento de clic o de doble clic estándar o si el control controlará su propio procesamiento del mouse.  Además, la clase <xref:System.Windows.Forms.SystemInformation> incluye propiedades que describen las funciones del mouse y especifican cómo interactúa el mouse con el sistema operativo.  La siguiente tabla proporciona un resumen de estas propiedades.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>|Obtiene las dimensiones, en píxeles, del área donde el usuario debe hacer clic dos veces para que el sistema operativo tenga en cuenta los dos clics.|  
|<xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A>|Obtiene el número máximo de milisegundos que pueden pasar entre el primer clic y el segundo para que el sistema operativo tenga en cuenta la acción del doble clic.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtons%2A>|Obtiene el número de botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseButtonsSwapped%2A>|Obtiene un valor que indica si se han intercambiado las funciones de los botones del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverSize%2A>|Obtiene las dimensiones, en píxeles, del rectángulo en el que el puntero del mouse debe permanecer un tiempo de desplazamiento para que se genere un mensaje de desplazamiento.|  
|<xref:System.Windows.Forms.SystemInformation.MouseHoverTime%2A>|Obtiene el tiempo, en milisegundos, que el puntero del mouse tiene que permanecer en el rectángulo seleccionado mediante movimiento del mouse hasta que se genera un mensaje de movimiento del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MousePresent%2A>|Obtiene un valor que indica si se ha instalado un mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseSpeed%2A>|Obtiene un valor que indica la velocidad actual del mouse, de 1 a 20.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelPresent%2A>|Obtiene un valor que indica si se ha instalado la rueda del mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollDelta%2A>|Obtiene la cantidad del valor delta del incremento de un único giro de la rueda de mouse.|  
|<xref:System.Windows.Forms.SystemInformation.MouseWheelScrollLines%2A>|Obtiene el número de líneas de desplazamiento al girar la rueda del mouse.|  
  
## Vea también  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)   
 [Mouse Capture in Windows Forms](../../../docs/framework/winforms/mouse-capture-in-windows-forms.md)   
 [Mouse Pointers in Windows Forms](../../../docs/framework/winforms/mouse-pointers-in-windows-forms.md)