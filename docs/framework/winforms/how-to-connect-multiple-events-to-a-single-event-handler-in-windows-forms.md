---
title: "How to: Connect Multiple Events to a Single Event Handler in Windows Forms | Microsoft Docs"
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
  - "events [Windows Forms], connecting multiple to single event handler"
  - "event handlers [Windows Forms], connecting events to"
  - "menus, event-handling methods for multiple menu items"
  - "Windows Forms controls, events"
  - "menu items, multicasting event-handling methods"
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# How to: Connect Multiple Events to a Single Event Handler in Windows Forms
En el diseño de la aplicación, quizá encuentre necesario disponer de un único controlador de eventos que se utilice para múltiples eventos o bien que múltiples eventos realicen el mismo procedimiento.  Por ejemplo, se suele ahorrar mucho tiempo si un comando de menú activa el mismo evento que un botón del formulario, en el caso de que ambos ofrezcan la misma funcionalidad.  Para ello se puede utilizar la vista Eventos de la ventana Propiedades de C\#, o la palabra clave `Handles` y las listas desplegables **Nombre de clase** y **Nombre de método** en el Editor de código de Visual Basic.  
  
### Para conectar varios eventos a un único controlador de eventos en Visual Basic  
  
1.  Haga clic con el botón secundario del mouse en el formulario y elija **Ver código**.  
  
2.  En el cuadro de diálogo **Nombre de clase**, seleccione uno de los controles al que desea agregar un controlador de eventos.  
  
3.  En el cuadro de diálogo **Nombre de método**, seleccione uno de los eventos al que desea agregar un controlador de eventos.  
  
4.  El Editor de código inserta el controlador de eventos apropiado y sitúa el punto de inserción dentro del método.  En el siguiente ejemplo, se trata del evento <xref:System.Windows.Forms.Control.Click> para el control <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Agregue los otros eventos que desea controlar en la cláusula `Handles` .  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Agregue el código correspondiente al controlador de eventos.  
  
### Para conectar varios eventos a un único controlador de eventos en C\#  
  
1.  Seleccione el control al que desea conectar un controlador de eventos.  
  
2.  En la ventana Propiedades, haga clic en el botón **Eventos** \(![Botón de eventos](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton\_PropertiesWindow")\).  
  
3.  Haga clic en el nombre del evento que desea controlar.  
  
4.  En la sección de valor, junto al nombre del evento, haga clic en el botón de lista desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.  
  
5.  Seleccione en la lista el controlador de eventos adecuado.  
  
     Se agregará código al formulario para enlazar el evento al controlador de eventos existente.  
  
## Vea también  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)