---
title: 'Cómo: conectar varios eventos a un solo controlador de eventos'
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
ms.openlocfilehash: 0591291522ab1da04fef90bf1c0a73cf33ba0518
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739610"
---
# <a name="how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms"></a>Cómo: Conectar varios eventos con un único controlador de eventos en Windows Forms
En el diseño de la aplicación, es posible que sea necesario usar un solo controlador de eventos para varios eventos o que varios eventos realicen el mismo procedimiento. Por ejemplo, a menudo es un eficaz ahorro de tiempo para que un comando de menú genere el mismo evento que un botón en el formulario, si expone la misma funcionalidad. Para ello, puede usar la vista eventos del ventana Propiedades en C# o utilizar la palabra clave `Handles` y los cuadros de lista desplegable nombre de **clase** y nombre de **método** en el editor de código Visual Basic.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-visual-basic"></a>Para conectar varios eventos a un solo controlador de eventos en Visual Basic  
  
1. Haga clic con el botón secundario en el formulario y elija **Ver código**.  
  
2. En el cuadro de lista desplegable **nombre de clase** , seleccione uno de los controles que desea que tengan el identificador de controlador de eventos.  
  
3. En el cuadro de lista desplegable **nombre de método** , seleccione uno de los eventos que desea que controle el controlador de eventos.  
  
4. El editor de código inserta el controlador de eventos adecuado y coloca el punto de inserción en el método. En el ejemplo siguiente, es el evento <xref:System.Windows.Forms.Control.Click> para el control <xref:System.Windows.Forms.Button>.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
5. Anexe los otros eventos que desea que se controlen a la cláusula `Handles`.  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click, Button2.Click  
    ' Add event-handler code here.  
    End Sub  
    ```  
  
6. Agregue el código adecuado al controlador de eventos.  
  
### <a name="to-connect-multiple-events-to-a-single-event-handler-in-c"></a>Para conectar varios eventos a un solo controlador de eventos en C\#
  
1. Seleccione el control al que desea conectar un controlador de eventos.  
  
2. En el ventana Propiedades, haga clic en el botón **eventos** (![botón eventos](./media/vxeventsbutton-propertieswindow.png "vxEventsButton_PropertiesWindow")).  
  
3. Haga clic en el nombre del evento que desea controlar.  
  
4. En la sección valor junto al nombre del evento, haga clic en el botón desplegable para mostrar una lista de controladores de eventos existentes que coincidan con la firma del método del evento que desea controlar.  
  
5. Seleccione en la lista el controlador de eventos adecuado.  
  
     Se agregará código al formulario para enlazar el evento al controlador de eventos existente.  
  
## <a name="see-also"></a>Consulte también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)
