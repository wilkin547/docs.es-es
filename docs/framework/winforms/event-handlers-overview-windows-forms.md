---
title: "Event Handlers Overview (Windows Forms) | Microsoft Docs"
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
  - "event handling, Windows Forms"
  - "event handlers, about event handlers"
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Event Handlers Overview (Windows Forms)
Un controlador de eventos es un método enlazado a un evento.  Cuando se produce el evento, se ejecuta el código del controlador de eventos.  Cada controlador de eventos proporciona dos parámetros que permiten controlar correctamente el evento.  En el siguiente ejemplo se muestra un controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> del control <xref:System.Windows.Forms.Button>.  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 El primer parámetro, `sender`, proporciona una referencia al objeto que provocó el evento.  El segundo parámetro, `e` en el ejemplo anterior, pasa un objeto específico del evento que se está controlando.  Al hacer referencia a las propiedades del objeto \(y, a veces, a sus métodos\), puede obtener información tal como la posición del mouse para los eventos del mouse o los datos que se están transfiriendo en los eventos de arrastrar y colocar.  
  
 Habitualmente, cada evento produce un controlador de eventos con un tipo de objeto de evento diferente para el segundo parámetro.  Algunos controladores de evento, tales como los de los eventos <xref:System.Windows.Forms.Control.MouseDown> y <xref:System.Windows.Forms.Control.MouseUp>, tienen el mismo tipo de objeto para el segundo parámetro.  Para estos tipos de eventos, se puede utilizar el mismo controlador de eventos para controlar ambos eventos.  
  
 También puede utilizar el mismo controlador de eventos para controlar el mismo evento de diferentes controles.  Por ejemplo, si tiene un grupo de controles <xref:System.Windows.Forms.RadioButton> en un formulario, puede crear un único controlador de eventos para el evento <xref:System.Windows.Forms.Control.Click> y hacer que el evento <xref:System.Windows.Forms.Control.Click> de cada control se enlace a ese controlador de eventos único.  Para obtener más información, vea [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](../../../docs/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).  
  
## Vea también  
 [Creating Event Handlers in Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)   
 [Events Overview](../../../docs/framework/winforms/events-overview-windows-forms.md)