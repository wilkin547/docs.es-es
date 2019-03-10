---
title: Procedimiento Crear controladores de eventos en tiempo de ejecución para Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 7ebafd745290a40fa6f4f83910fb32d67cdcff75
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57705273"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Procedimiento Crear controladores de eventos en tiempo de ejecución para Windows Forms
Además de crear eventos mediante Diseñador de Windows Forms, también puede crear un controlador de eventos en tiempo de ejecución. Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando se inicia el programa.  
  
### <a name="to-create-an-event-handler-at-run-time"></a>Para crear un controlador de eventos en tiempo de ejecución  
  
1.  Abra el formulario en el editor de código al que desee agregar un controlador de eventos.  
  
2.  Agregue un método al formulario con la firma del método para el evento que desee controlar.  
  
     Por ejemplo, si desea controlar la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> control, debe crear un método como la siguiente:  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)  
       ' Add event handler code here.  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
    // Add event handler code here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,   
          System::EventArgs ^ e)  
       {  
          // Add event handler code here.  
       }  
    ```  
  
3.  Agregue el código al controlador de eventos según corresponda a su aplicación.  
  
4.  Determine el formulario o control para el que desea crear un controlador de eventos.  
  
5.  En un método de la clase del formulario, agregue código que especifique el controlador de eventos para controlar el evento. Por ejemplo, el código siguiente especifica el controlador de eventos `button1_Click` controla la <xref:System.Windows.Forms.Control.Click> eventos de un <xref:System.Windows.Forms.Button> control:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     El <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> método mostrado en el código de Visual Basic anterior establece un controlador de eventos click del botón.  
  
## <a name="see-also"></a>Vea también
- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
