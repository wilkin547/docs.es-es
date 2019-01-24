---
title: Procedimiento Conectar varios eventos con un único controlador de eventos en Windows Forms
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- events [Windows Forms], connecting multiple to single event handler
- event handlers [Windows Forms], connecting events to
- menus [Windows Forms], event-handling methods for multiple menu items
- Windows Forms controls, events
- menu items [Windows Forms], multicasting event-handling methods
ms.assetid: 5a20749a-41b5-4acc-8eb1-9e5040b0a2c4
ms.openlocfilehash: 527e2c594f236f94ce23e4fd21238b8605af308c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54502448"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Procedimiento Conectar varios eventos con un único controlador de eventos en Windows Forms
En el diseño de aplicaciones, puede que sea necesario para usar un único controlador de eventos para varios eventos o tener varios eventos de realizar el mismo procedimiento. Por ejemplo, a menudo es ahorrar mucho tiempo si un comando de menú producen el mismo evento que un botón en el formulario si expone la misma funcionalidad. Puede hacerlo mediante el uso de la vista eventos de la ventana Propiedades de C# o mediante el `Handles` palabra clave y el **nombre de la clase** y **nombre del método** listas desplegables en el Editor de código de Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Para conectar varios eventos con un único controlador de eventos en Visual Basic  
  
1.  Haga clic en el formulario y elija **ver código**.  
  
2.  Desde el **nombre de la clase** cuadro de lista desplegable, seleccione uno de los controles que desea agregar el controlador de eventos.  
  
3.  Desde el **nombre del método** cuadro de lista desplegable, seleccione uno de los eventos que desea que el controlador de eventos.  
  
4.  El Editor de código se inserta el controlador de eventos adecuado y coloca el punto de inserción dentro del método. En el ejemplo siguiente, es el <xref:System.Windows.Forms.Control.Click> eventos para el <xref:System.Windows.Forms.Button> control.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5.  Agregue los otros eventos que desea que administran el `Handles` cláusula.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6.  Agregue el código adecuado para el controlador de eventos.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Para conectar varios eventos con un único controlador de eventos enC#  
  
1.  Seleccione el control al que desea conectarse a un controlador de eventos.  
  
2.  En la ventana Propiedades, haga clic en el **eventos** botón (![botón eventos](../../../docs/framework/winforms/media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3.  Haga clic en el nombre del evento que desea controlar.  
  
4.  En la sección de valor junto al nombre del evento, haga clic en el botón de lista desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.  
  
5.  Seleccione el controlador de eventos apropiado en la lista.  
  
     Se agregará código al formulario para enlazar el evento al controlador de eventos existente.  
  
## <a name="see-also"></a>Vea también
- [Crear controladores de eventos en Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)
