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
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="bd1fe-102">Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="bd1fe-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="bd1fe-103">Muchos componentes le ofrecen la opción de realizar su trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="bd1fe-104">El <xref:System.Media.SoundPlayer> y <xref:System.Windows.Forms.PictureBox> componentes, por ejemplo, habilitar cargar sonidos e imágenes "en segundo plano", mientras que el subproceso principal continúa ejecutándose sin interrupción.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="bd1fe-105">Usar métodos asincrónicos en una clase que admita la [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) puede ser tan simple como asociar un controlador de eventos para el componente *MethodName* `Completed` eventos, tal y como lo haría con cualquier otro evento.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's *MethodName*`Completed` event, just as you would for any other event.</span></span> <span data-ttu-id="bd1fe-106">Cuando se llama a la *MethodName* `Async` método, la aplicación seguirá ejecutándose sin interrupción hasta que el *MethodName* `Completed` evento se desencadena.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-106">When you call the *MethodName*`Async` method, your application will continue running without interruption until the *MethodName*`Completed` event is raised.</span></span> <span data-ttu-id="bd1fe-107">En el controlador de eventos, puede examinar el <xref:System.ComponentModel.AsyncCompletedEventArgs> parámetro para determinar si la operación asincrónica se completó correctamente o si se canceló.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="bd1fe-108">Para obtener más información sobre el uso de controladores de eventos, vea [información general sobre controladores de eventos](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bd1fe-108">For more information about using event handlers, see [Event Handlers Overview](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="bd1fe-109">El siguiente procedimiento muestra cómo utilizar la capacidad de carga de imagen asincrónica de un <xref:System.Windows.Forms.PictureBox> control.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="bd1fe-110">Para activar un control PictureBox cargar una imagen de forma asincrónica</span><span class="sxs-lookup"><span data-stu-id="bd1fe-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1.  <span data-ttu-id="bd1fe-111">Cree una instancia de la <xref:System.Windows.Forms.PictureBox> componente en el formulario.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2.  <span data-ttu-id="bd1fe-112">Asignar un controlador de eventos para el <xref:System.Windows.Forms.PictureBox.LoadCompleted> eventos.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="bd1fe-113">Compruebe si hay errores que puedan haberse producido durante la descarga asincrónica aquí.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="bd1fe-114">También es donde puede comprobar posibles cancelaciones.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#5)]  
  
3.  <span data-ttu-id="bd1fe-115">Agregue dos botones, denominados `loadButton` y `cancelLoadButton`, al formulario.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="bd1fe-116">Agregar <xref:System.Windows.Forms.Control.Click> controladores de eventos para iniciar y cancelar la descarga.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.PictureBox.LoadAsync/VB/Form1.vb#4)]  
  
4.  <span data-ttu-id="bd1fe-117">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-117">Run your application.</span></span>  
  
     <span data-ttu-id="bd1fe-118">Mientras se realiza la descarga de la imagen, puede mover libremente el formulario, minimizarlo y maximizarlo.</span><span class="sxs-lookup"><span data-stu-id="bd1fe-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1fe-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd1fe-119">See Also</span></span>  
 [<span data-ttu-id="bd1fe-120">Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="bd1fe-120">How to: Run an Operation in the Background</span></span>](../../../docs/framework/winforms/controls/how-to-run-an-operation-in-the-background.md)  
 <span data-ttu-id="bd1fe-121">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="bd1fe-121">[Event-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)</span></span>  
 [<span data-ttu-id="bd1fe-122">NO está en la compilación: Multithreading en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bd1fe-122">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/en-us/c731a50c-09c1-4468-9646-54c86b75d269)
