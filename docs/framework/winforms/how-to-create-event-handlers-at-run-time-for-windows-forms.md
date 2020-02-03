---
title: 'Cómo: crear controladores de eventos en tiempo de ejecución'
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
ms.openlocfilehash: 0b496a3da77c5bcf7a08c435edba468a7c5809cb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739496"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms

Además de crear eventos mediante el Diseñador de Windows Forms en Visual Studio, también puede crear un controlador de eventos en tiempo de ejecución. Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando se inicia el programa.

## <a name="create-an-event-handler-at-run-time"></a>Crear un controlador de eventos en tiempo de ejecución

1. Abra el formulario al que desea agregar un controlador de eventos.

2. Agregue un método al formulario con la firma del método para el evento que desee controlar.

     Por ejemplo, si controla el evento <xref:System.Windows.Forms.Control.Click> de un control <xref:System.Windows.Forms.Button>, debe crear un método como el siguiente:

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

3. Agregue el código al controlador de eventos según corresponda a su aplicación.

4. Determine el formulario o control para el que desea crear un controlador de eventos.

5. En un método de la clase del formulario, agregue código que especifique el controlador de eventos para controlar el evento. Por ejemplo, el código siguiente especifica el controlador de eventos `button1_Click` controla el evento de <xref:System.Windows.Forms.Control.Click> de un control <xref:System.Windows.Forms.Button>:

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     El método <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> mostrado en el código de Visual Basic anterior establece un controlador de eventos click para el botón.

## <a name="see-also"></a>Consulte también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
