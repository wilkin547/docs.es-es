---
title: "How to: Use Components That Support the Event-based Asynchronous Pattern | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# How to: Use Components That Support the Event-based Asynchronous Pattern
Muchos componentes le ofrecen la opción de realizar tareas de forma asincrónica.  Los componentes <xref:System.Media.SoundPlayer> y <xref:System.Windows.Forms.PictureBox>, por ejemplo, le permiten cargar sonidos e imágenes "en segundo plano", mientras el subproceso principal continúa ejecutándose sin interrupciones.  
  
 Utilizando métodos asincrónicos en una clase que admite [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) puede reducirse a asociar un controlador de eventos al evento de *MethodName*`Completed` del componente, como lo haría con cualquier otro evento.  Cuando se llama al método de *MethodName*`Async` , la aplicación seguirá ejecutándose sin interrupciones hasta que se produzca el evento de *MethodName*`Completed` .  Puede examinar el parámetro <xref:System.ComponentModel.AsyncCompletedEventArgs> del controlador de eventos para determinar si la operación asincrónica ha finalizado correctamente o se ha cancelado.  
  
 Para obtener información sobre la forma de utilizar controladores de eventos, vea [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 El siguiente procedimiento muestra cómo utilizar la función de carga de imágenes asincrónica de un control <xref:System.Windows.Forms.PictureBox>.  
  
### Para permitir que un control PictureBox cargue una imagen de forma asincrónica  
  
1.  Cree una instancia del componente <xref:System.Windows.Forms.PictureBox> en el formulario.  
  
2.  Asigne un controlador de eventos al evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Compruebe aquí que no se haya producido ningún error durante la descarga asincrónica.  Aquí también puede comprobar posibles cancelaciones.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Agregue dos botones al formulario, los botones denominados `loadButton` y `cancelLoadButton`.  Agregue controladores de eventos <xref:System.Windows.Forms.Control.Click> para iniciar y cancelar la descarga.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Ejecute la aplicación.  
  
     A medida que vaya descargándose la imagen, podrá mover libremente el formulario, minimizarlo y maximizarlo.  
  
## Vea también  
 [Cómo: Ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)   
 [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)   
 [NOT IN BUILD: Multithreading in Visual Basic](http://msdn.microsoft.com/es-es/c731a50c-09c1-4468-9646-54c86b75d269)