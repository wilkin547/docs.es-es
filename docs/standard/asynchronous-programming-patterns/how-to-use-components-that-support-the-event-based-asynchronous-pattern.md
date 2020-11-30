---
title: 'Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Event-based Asynchronous Pattern
- ProgressChangedEventArgs class
- BackgroundWorker component
- events [.NET], asynchronous
- Asynchronous Pattern
- AsyncOperationManager class
- threading [.NET], asynchronous features
- components [.NET], asynchronous
- AsyncOperation class
- threading [Windows Forms], asynchronous features
- AsyncCompletedEventArgs class
ms.assetid: 35e9549c-1568-4768-ad07-17cc6dff11e1
ms.openlocfilehash: 36fe8015187833e03c4cc3fc1609ec647daf7278
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678004"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a>Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos

Muchos componentes le ofrecen la opción de realizar su trabajo de forma asincrónica. Por ejemplo, los componentes <xref:System.Media.SoundPlayer> y <xref:System.Windows.Forms.PictureBox> permiten cargas sonidos e imágenes "en segundo plano" mientras el subproceso principal continúa ejecutándose sin interrupción.  
  
 Usar métodos asincrónicos en una clase que admite la [Información general sobre el modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md) puede ser tan sencillo como adjuntar un controlador de eventos al evento _MethodName_**Completed** del componente, como lo haría para cualquier otro evento. Cuando se llama al método _MethodName_**Async**, la aplicación continuará ejecutándose sin interrupción hasta que se genere el evento _MethodName_**Completed**. En el controlador de eventos, puede examinar el parámetro <xref:System.ComponentModel.AsyncCompletedEventArgs> para determinar si la operación asincrónica se completó correctamente o si se canceló.  
  
 Para más información sobre el uso de los controladores de eventos, vea [Información general sobre controladores de eventos](/dotnet/desktop/winforms/event-handlers-overview-windows-forms).  
  
 En el siguiente procedimiento se explica cómo usar la funcionalidad de carga de imágenes asincrónica de un control <xref:System.Windows.Forms.PictureBox>.  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a>Para permitir que un control PictureBox cargue una imagen de manera asincrónica  
  
1. Cree una instancia del componente <xref:System.Windows.Forms.PictureBox> en el formulario.  
  
2. Asigne un controlador de eventos al evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.  
  
     Compruebe si hay errores que puedan haberse producido durante la descarga asincrónica aquí. También es donde puede comprobar posibles cancelaciones.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. Agregue dos botones, denominados `loadButton` y `cancelLoadButton`, al formulario. Agregue los controladores de eventos <xref:System.Windows.Forms.Control.Click> para iniciar y cancelar la descarga.  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. Ejecute la aplicación.  
  
     Mientras se realiza la descarga de la imagen, puede mover libremente el formulario, minimizarlo y maximizarlo.  
  
## <a name="see-also"></a>Vea también

- [Ejecutar una operación en segundo plano](/dotnet/desktop/winforms/controls/how-to-run-an-operation-in-the-background)
- [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)
