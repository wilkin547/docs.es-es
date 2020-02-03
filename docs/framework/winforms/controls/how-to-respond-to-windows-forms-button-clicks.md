---
title: para responder a clics de botón
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], responding to Click events
- events [Windows Forms], Click events
- Click event [Windows Forms], Button control
- MouseDown event
- Button control [Windows Forms], click response
- double-clicks
- examples [Windows Forms], controls
- Click event [Windows Forms], responding to
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
ms.openlocfilehash: dd6cf75a316257c86a23b44a818422336c12aa67
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735715"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Cómo: Responder a clics de botones en formularios Windows Forms
El uso más básico de un control de Windows Forms <xref:System.Windows.Forms.Button> es ejecutar código al hacer clic en el botón.  
  
 Al hacer clic en un control de <xref:System.Windows.Forms.Button> también se generan otros eventos, como los eventos <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>y <xref:System.Windows.Forms.Control.MouseUp>. Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entran en conflicto. Por ejemplo, si al hacer clic en el botón se borra la información que el usuario ha escrito en un cuadro de texto, al pausar el puntero del mouse sobre el botón, no se debería mostrar una información sobre herramientas que ahora no existe.  
  
 Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.Button>, cada clic se procesará por separado. es decir, el control no admite el evento de doble clic.  
  
### <a name="to-respond-to-a-button-click"></a>Para responder a un clic de botón  
  
- En el `Click` del botón <xref:System.EventHandler> escriba el código que se va a ejecutar. `Button1_Click` debe estar enlazado al control. Para obtener más información, vea [Cómo: crear controladores de eventos en tiempo de ejecución para Windows Forms](../how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       MessageBox.Show("Button1 was clicked")  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       MessageBox.Show("button1 was clicked");  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre el control Button](button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](ways-to-select-a-windows-forms-button-control.md)
- [Botón (control)](button-control-windows-forms.md)
