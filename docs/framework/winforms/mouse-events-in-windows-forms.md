---
title: "Mouse Events in Windows Forms | Microsoft Docs"
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
  - "MouseLeave event"
  - "events [Windows Forms], mouse"
  - "Click event, raising order"
  - "Windows Forms controls, click events"
  - "MouseDoubleClick event"
  - "MouseEnter event"
  - "MouseHover event"
  - "MouseDown event"
  - "MouseClick event"
  - "MouseMove event"
  - "mouse, events"
  - "MouseUp event"
ms.assetid: 8cf0070d-793b-4876-b09e-d20d28280fab
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Mouse Events in Windows Forms
Cuando se controla la entrada de mouse, normalmente desea conocer la ubicación del puntero del mouse y el estado de los botones del mismo.  En este tema se describe cómo obtener esta información de los eventos del mouse y explica el orden en que se generan los eventos de clic del mouse en los controles de Windows Forms.  Para obtener una lista y una descripción de todos los eventos del mouse, consulte [How Mouse Input Works in Windows Forms](../../../docs/framework/winforms/how-mouse-input-works-in-windows-forms.md).  Consulte también [Información general sobre controladores de eventos \(Windows Forms\)](http://msdn.microsoft.com/library/be6fx1bb%20\(v=vs.110\)), [Información general sobre eventos \(Windows Forms\)](http://msdn.microsoft.com/library/1h12f09z%20\(v=vs.110\))  
  
## Información del mouse  
 Se envía un <xref:System.Windows.Forms.MouseEventArgs> a los controladores de eventos del mouse relacionados con hacer clic en un botón del mouse y el seguimiento de los movimientos del mouse.  <xref:System.Windows.Forms.MouseEventArgs> proporciona información sobre el estado actual del mouse, incluida la ubicación del puntero del mouse en coordenadas de cliente, qué botones del mouse se presionan y si se ha desplazado la rueda del mouse.  Algunos eventos del mouse, como aquellos que simplemente notifican cuando el puntero del mouse entra o sale de los límites de un control, envían un <xref:System.EventArgs> al controlador de eventos sin más información.  
  
 Si quiere conocer el estado actual de los botones del mouse o la ubicación del puntero del mouse y no desea controlar un evento del mouse, también puede usar las propiedades <xref:System.Windows.Forms.Control.MouseButtons%2A> y <xref:System.Windows.Forms.Control.MousePosition%2A> de la clase <xref:System.Windows.Forms.Control>.  <xref:System.Windows.Forms.Control.MouseButtons%2A> devuelve información acerca de qué botones del mouse están presionados actualmente.  <xref:System.Windows.Forms.Control.MousePosition%2A> devuelve las coordenadas de pantalla del puntero del mouse y equivale al valor devuelto por <xref:System.Windows.Forms.Cursor.Position%2A>.  
  
## Conversión de coordenadas de pantalla y de cliente  
 Como alguna información de ubicación del mouse está en coordenadas de cliente y otra está en coordenadas de pantalla, puede que necesite convertir un punto de un sistema de coordenadas a otro.  Puede hacerlo fácilmente con los métodos <xref:System.Windows.Forms.Control.PointToClient%2A> y <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibles en la clase <xref:System.Windows.Forms.Control>.  
  
## Comportamiento estándar del evento de clic  
 Si quiere controlar los eventos de clic del mouse en el orden correcto, necesita saber el orden en que se generan los eventos de clic en los controles de Windows Forms.  Todos los controles de Windows Forms generan los eventos de clic en el mismo orden cuando se presiona y se suelta un botón del mouse \(independientemente de qué botón sea\), excepto cuando se indique otra cosa para cada control en la lista siguiente.  La siguiente lista muestra el orden de los eventos generados para un único clic del botón del mouse:  
  
1.  Evento <xref:System.Windows.Forms.Control.MouseDown>.  
  
2.  Evento <xref:System.Windows.Forms.Control.Click>.  
  
3.  Evento <xref:System.Windows.Forms.Control.MouseClick>.  
  
4.  Evento <xref:System.Windows.Forms.Control.MouseUp>.  
  
 El siguiente es el orden de los eventos generados para un doble clic del botón del mouse:  
  
1.  Evento <xref:System.Windows.Forms.Control.MouseDown>.  
  
2.  Evento <xref:System.Windows.Forms.Control.Click>.  
  
3.  Evento <xref:System.Windows.Forms.Control.MouseClick>.  
  
4.  Evento <xref:System.Windows.Forms.Control.MouseUp>.  
  
5.  Evento <xref:System.Windows.Forms.Control.MouseDown>.  
  
6.  Evento <xref:System.Windows.Forms.Control.DoubleClick>.  \(Esto puede variar según si el control en cuestión tiene el bit de estilo <xref:System.Windows.Forms.ControlStyles> establecido en `true` o no.  Para obtener más información sobre cómo establecer un bit <xref:System.Windows.Forms.ControlStyles>, consulte el método <xref:System.Windows.Forms.Control.SetStyle%2A>\).  
  
7.  Evento <xref:System.Windows.Forms.Control.MouseDoubleClick>.  
  
8.  Evento <xref:System.Windows.Forms.Control.MouseUp>.  
  
 Para ver un ejemplo de código que muestra el orden de los eventos de clic del mouse, consulte [How to: Handle User Input Events in Windows Forms Controls](../../../docs/framework/winforms/how-to-handle-user-input-events-in-windows-forms-controls.md).  
  
### Controles individuales  
 Los controles siguientes no siguen el comportamiento estándar de los eventos de clic del mouse:  
  
-   Controles <xref:System.Windows.Forms.Button>, <xref:System.Windows.Forms.CheckBox>, <xref:System.Windows.Forms.ComboBox> y <xref:System.Windows.Forms.RadioButton>  
  
    > [!NOTE]
    >  Para el control <xref:System.Windows.Forms.ComboBox>, se produce el comportamiento de eventos que se describe a continuación si el usuario hace clic en el campo de edición, en el botón o en un elemento de la lista.  
  
    -   Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Clic con el botón secundario: no se generan eventos  
  
    -   Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doble clic con el botón secundario: no se generan eventos  
  
-   Controles <xref:System.Windows.Forms.TextBox>, <xref:System.Windows.Forms.RichTextBox>, <xref:System.Windows.Forms.ListBox>, <xref:System.Windows.Forms.MaskedTextBox> y <xref:System.Windows.Forms.CheckedListBox>  
  
    > [!NOTE]
    >  Se produce el comportamiento de eventos que se describe a continuación cuando el usuario hace clic en cualquier parte dentro de estos controles.  
  
    -   Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Clic con el botón secundario: no se generan eventos  
  
    -   Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>, <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doble clic con el botón secundario: no se generan eventos  
  
-   Control <xref:System.Windows.Forms.ListView>  
  
    > [!NOTE]
    >  Se produce el comportamiento de eventos que se describe a continuación solo cuando el usuario hace clic en los elementos del control <xref:System.Windows.Forms.ListView>.  No se genera ningún evento para los clics que se realizan en cualquier otro lugar del control.  Además de los eventos que se describen más adelante, están los eventos <xref:System.Windows.Forms.ListView.BeforeLabelEdit> y <xref:System.Windows.Forms.ListView.AfterLabelEdit>, que pueden resultarle de interés si quiere usar la validación con el control <xref:System.Windows.Forms.ListView>.  
  
    -   Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doble clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
-   Control <xref:System.Windows.Forms.TreeView>  
  
    > [!NOTE]
    >  El comportamiento de eventos que se describe a continuación se produce solo cuando el usuario hace clic en los propios elementos o a la derecha de los elementos en el control <xref:System.Windows.Forms.TreeView>.  No se genera ningún evento para los clics que se realizan en cualquier otro lugar del control.  Además de los eventos que se describen más adelante, están los eventos <xref:System.Windows.Forms.TreeView.BeforeCheck>, <xref:System.Windows.Forms.TreeView.BeforeSelect>, <xref:System.Windows.Forms.TreeView.BeforeLabelEdit>, <xref:System.Windows.Forms.TreeView.AfterSelect>, <xref:System.Windows.Forms.TreeView.AfterCheck> y <xref:System.Windows.Forms.TreeView.AfterLabelEdit>, que pueden resultarle de interés si quiere usar la validación con el control <xref:System.Windows.Forms.TreeView>.  
  
    -   Clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>  
  
    -   Doble clic con el botón primario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
    -   Doble clic con el botón secundario: <xref:System.Windows.Forms.Control.Click>, <xref:System.Windows.Forms.Control.MouseClick>; <xref:System.Windows.Forms.Control.DoubleClick>, <xref:System.Windows.Forms.Control.MouseDoubleClick>  
  
### Comportamiento de dibujo de los controles de alternancia  
 Los controles de alternancia, como los controles que derivan de la clase <xref:System.Windows.Forms.ButtonBase>, tienen el siguiente comportamiento de dibujo particular en combinación con los eventos de clic del mouse:  
  
1.  El usuario presiona el botón del mouse.  
  
2.  El control se dibuja en estado presionado.  
  
3.  Se genera el evento <xref:System.Windows.Forms.Control.MouseDown>.  
  
4.  El usuario suelta el botón del mouse.  
  
5.  El control se dibuja en estado no presionado.  
  
6.  Se genera el evento <xref:System.Windows.Forms.Control.Click>.  
  
7.  Se genera el evento <xref:System.Windows.Forms.Control.MouseClick>.  
  
8.  Se genera el evento <xref:System.Windows.Forms.Control.MouseUp>.  
  
    > [!NOTE]
    >  Si el usuario mueve el puntero fuera del control de alternancia mientras el botón del mouse está presionado \(sacar el mouse del control <xref:System.Windows.Forms.Button> mientras está presionado\), el control de alternancia se dibujará en estado no presionado y solo se produce el evento <xref:System.Windows.Forms.Control.MouseUp>.  En este caso no se producen los eventos <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick>.  
  
## Vea también  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)