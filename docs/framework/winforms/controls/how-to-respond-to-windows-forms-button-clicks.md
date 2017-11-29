---
title: "Cómo: Responder a clics de botones en formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 923eb7d1b1b5b442ce897619253a958019b239a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-respond-to-windows-forms-button-clicks"></a>Cómo: Responder a clics de botones en formularios Windows Forms
El uso más básico de Windows Forms <xref:System.Windows.Forms.Button> control consiste en ejecutar código cuando se hace clic en el botón.  
  
 Al hacer clic en un <xref:System.Windows.Forms.Button> control también genera un número de otros eventos, como el <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown>, y <xref:System.Windows.Forms.Control.MouseUp> eventos. Si desea adjuntar controladores de eventos para estos eventos relacionados, asegúrese de que sus acciones no entren en conflicto. Por ejemplo, si hace clic en el botón se borra la información escrita por el usuario en un cuadro de texto, el al situar el puntero del mouse sobre el botón debería mostrar no una información sobre herramientas con esa información ahora inexistente.  
  
 Si el usuario intenta hacer doble clic en el <xref:System.Windows.Forms.Button> control, cada clic se procesará por separado; es decir, el control no admite el evento doble clic.  
  
### <a name="to-respond-to-a-button-click"></a>Para responder a un clic del botón  
  
-   En el botón `Click` <xref:System.EventHandler> escribir el código que se ejecuta. `Button1_Click`se debe enlazar al control. Para obtener más información, consulte [Cómo: crear controladores de eventos en tiempo de ejecución para formularios Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)  
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)  
 [Botón (control)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)
