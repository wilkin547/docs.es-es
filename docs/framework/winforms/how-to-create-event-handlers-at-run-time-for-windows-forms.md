---
title: 'Cómo: crear controladores de eventos en tiempo de ejecución'
description: Obtenga información sobre cómo crear un controlador de eventos en tiempo de ejecución con la Diseñador de Windows Forms en Visual Studio. Esta acción le permite conectar controladores de eventos en tiempo de ejecución.
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
ms.openlocfilehash: 857076c46377b3276154d9b193d4bbe51841828f
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325803"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>Procedimiento para crear controladores de eventos en tiempo de ejecución para formularios Windows Forms

Además de crear eventos mediante el Diseñador de Windows Forms en Visual Studio, también puede crear un controlador de eventos en tiempo de ejecución. Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando se inicia el programa.

## <a name="create-an-event-handler-at-run-time"></a>Crear un controlador de eventos en tiempo de ejecución

1. Abra el formulario al que desea agregar un controlador de eventos.

2. Agregue un método al formulario con la firma del método para el evento que desee controlar.

     Por ejemplo, si controla el <xref:System.Windows.Forms.Control.Click> evento de un <xref:System.Windows.Forms.Button> control, debe crear un método como el siguiente:

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

5. En un método de la clase del formulario, agregue código que especifique el controlador de eventos para controlar el evento. Por ejemplo, el código siguiente especifica que el controlador `button1_Click` de eventos controla el <xref:System.Windows.Forms.Control.Click> evento de un <xref:System.Windows.Forms.Button> control:

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     El <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> método que se muestra en el código Visual Basic anterior establece un controlador de eventos click para el botón.

## <a name="see-also"></a>Vea también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)
- [Solucionar problemas de controladores de eventos heredados en Visual Basic](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
