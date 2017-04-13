---
title: "C&#243;mo: Responder a clics de botones en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "control de botón [Windows Forms], respuesta a un clic de botón"
  - "botones, responder a eventos Click"
  - "Click (evento), Button (control)"
  - "Click (evento), responder a"
  - "hacer doble clic"
  - "eventos [Windows Forms], Click (eventos)"
  - "ejemplos [Windows Forms], controles"
  - "MouseDown (evento)"
ms.assetid: 7a4951bd-369c-4662-b246-28ad83eda484
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Responder a clics de botones en formularios Windows Forms
El uso más básico de un control <xref:System.Windows.Forms.Button> de formularios Windows Forms consiste en ejecutar código cuando se hace clic en el botón.  
  
 Al hacer clic en un control <xref:System.Windows.Forms.Button> se generan también otros eventos, como <xref:System.Windows.Forms.Control.MouseEnter>, <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp>.  Si desea asociar controladores de eventos a estos eventos relacionados, asegúrese de que sus correspondientes acciones no entren en conflicto.  Por ejemplo, si al hacer clic en el botón se borra la información escrita por el usuario en un cuadro de texto, al situar el puntero del mouse sobre el botón no debería aparecer una información sobre herramientas con ese texto ahora inexistente.  
  
 Si el usuario intenta hacer doble clic en el control <xref:System.Windows.Forms.Button>, cada clic se procesará por separado; es decir, el control no admite el evento doble clic.  
  
### Para responder a un clic en el botón  
  
-   En el control <xref:System.EventHandler> de `Click` , escriba el código que se va a ejecutar.  `Button1_Click` se debe enlazar al control.  Para obtener más información, vea [How to: Create Event Handlers at Run Time for Windows Forms](../../../../docs/framework/winforms/how-to-create-event-handlers-at-run-time-for-windows-forms.md).  
  
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
  
    ```cpp#  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          MessageBox::Show("button1 was clicked");  
       }  
    ```  
  
## Vea también  
 [Información general sobre el control Button](../../../../docs/framework/winforms/controls/button-control-overview-windows-forms.md)   
 [Maneras de seleccionar un control Button de formularios Windows Forms](../../../../docs/framework/winforms/controls/ways-to-select-a-windows-forms-button-control.md)   
 [Button \(Control\)](../../../../docs/framework/winforms/controls/button-control-windows-forms.md)