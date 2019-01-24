---
title: Procedimiento Responder a clics de botón de Windows Forms
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
ms.openlocfilehash: 98b52e914a891baec0b52dcc7b38d4f9f2198c90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539557"
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Procedimiento Responder a clics de botón de Windows Forms
El uso más básico de un formulario Windows Forms <xref:System.Windows.Forms.Button> control consiste en ejecutar código cuando se hace clic en el botón.  
  
 Al hacer clic en un <xref:System.Windows.Forms.Button> control también genera un número de otros eventos, como el <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, y <xref:System.Windows.Forms.Control.MouseUp> eventos. Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entren en conflicto. Por ejemplo, si hace clic en el botón se borra la información que el usuario ha escrito en un cuadro de texto, el pausando el puntero del mouse por encima del botón debe mostrar no herramientas con esa información ahora inexistente.  
  
 Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.Button> control, cada clic se procesará por separado; es decir, el control no admite el evento de doble clic.  
  
### <a name="to-respond-to-a-button-click"></a>Para responder a un clic de botón  
  
-   En el botón `Click` <xref:System.EventHandler> escribir el código que se ejecutará. `Button1_Click` se debe enlazar al control. Para obtener más información, vea [Cómo: Crear controladores de eventos en tiempo de ejecución para Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
  
## <a name="see-also"></a>Vea también
- [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)
- [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)
- [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
