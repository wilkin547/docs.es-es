---
title: "How to: Create Event Handlers at Run Time for Windows Forms | Microsoft Docs"
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
  - "Windows Forms, event handling"
  - "event handlers, creating"
  - "run time, creating event handlers at"
  - "examples [Windows Forms], event handling"
  - "Button control [Windows Forms], event handlers"
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Create Event Handlers at Run Time for Windows Forms
Además de crear eventos con el Diseñador de Windows Forms, también puede crear un controlador de eventos en tiempo de ejecución.  Esta acción le permite conectar controladores de eventos basándose en las condiciones del código en tiempo de ejecución en lugar de conectarlos cuando el programa se inicia.  
  
### Para crear un controlador de eventos en tiempo de ejecución  
  
1.  Abra en el Editor de código el formulario al que desea agregar un controlador de eventos.  
  
2.  Agregue un método al formulario con la firma de método del evento que desee controlar.  
  
     Por ejemplo, si desea controlar el evento <xref:System.Windows.Forms.Control.Click> de un control <xref:System.Windows.Forms.Button>, deberá crear un método como el siguiente:  
  
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
  
3.  Agregue al controlador de eventos el código adecuado para la aplicación.  
  
4.  Determine el formulario o control para el que desea crear un controlador de eventos.  
  
5.  En un método de la clase del formulario, agregue código que especifique el controlador de eventos que va a controlar el evento.  Por ejemplo, en el código siguiente se especifica que el controlador de eventos `button1_Click` controla el evento <xref:System.Windows.Forms.Control.Click> de un control <xref:System.Windows.Forms.Button>:  
  
    ```vb  
    AddHandler Button1.Click, AddressOf Button1_Click  
  
    ```  
  
    ```csharp  
    button1.Click += new EventHandler(button1_Click);  
  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
     El método <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> mostrado anteriormente en el código de Visual Basic establece un controlador de evento clic para el botón.  
  
## Vea también  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)   
 [Solucionar problemas de controladores de eventos heredados en Visual Basic](../Topic/Troubleshooting%20Inherited%20Event%20Handlers%20in%20Visual%20Basic.md)