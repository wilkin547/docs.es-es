---
title: "Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET Framework], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET Framework], asynchronous features
- components [.NET Framework], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 49e03a8d886ccd4ed6e4b2a19692c1874f5928ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos
Muchos componentes le ofrecen la opción de realizar su trabajo de forma asincrónica. El <xref:System.Media.SoundPlayer> y <xref:System.Windows.Forms.PictureBox> componentes, por ejemplo, habilitar cargar sonidos e imágenes "en segundo plano", mientras que el subproceso principal continúa ejecutándose sin interrupción.  
  
 Usar métodos asincrónicos en una clase que admita la [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) puede ser tan simple como asociar un controlador de eventos para el componente *MethodName* `Completed` eventos, tal y como lo haría con cualquier otro evento. Cuando se llama a la *MethodName* `Async` método, la aplicación seguirá ejecutándose sin interrupción hasta que el *MethodName* `Completed` evento se desencadena. En el controlador de eventos, puede examinar el <xref:System.ComponentModel.AsyncCompletedEventArgs> parámetro para determinar si la operación asincrónica se completó correctamente o si se canceló.  
  
 Para obtener más información sobre el uso de controladores de eventos, vea [información general sobre controladores de eventos](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
 El siguiente procedimiento muestra cómo utilizar la capacidad de carga de imagen asincrónica de un <xref:System.Windows.Forms.PictureBox> control.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Para activar un control PictureBox cargar una imagen de forma asincrónica  
  
1.  Cree una instancia de la <xref:System.Windows.Forms.PictureBox> componente en el formulario.  
  
2.  Asignar un controlador de eventos para el <xref:System.Windows.Forms.PictureBox.LoadCompleted> eventos.  
  
     Compruebe si hay errores que puedan haberse producido durante la descarga asincrónica aquí. También es donde puede comprobar posibles cancelaciones.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  Agregue dos botones, denominados `loadButton` y `cancelLoadButton`, al formulario. Agregar <xref:System.Windows.Forms.Control.Click> controladores de eventos para iniciar y cancelar la descarga.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  Ejecute la aplicación.  
  
     Mientras se realiza la descarga de la imagen, puede mover libremente el formulario, minimizarlo y maximizarlo.  
  
## <a name="see-also"></a>Vea también  
 [Ejecutar una operación en segundo plano](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)  
 [NO está en la compilación: Multithreading en Visual Basic](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
