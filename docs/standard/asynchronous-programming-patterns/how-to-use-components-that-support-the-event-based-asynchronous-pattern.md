---
title: 'Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: e23a9b28cff9428cbc8896515ce71db85c832243
ms.sourcegitcommit: b78018c850590dfc0348301e1748b779c28604cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "89379153"
---
# <a name="how-to-use-components-that-support-the-event-based-asynchronous-pattern"></a><span data-ttu-id="39a46-102">Cómo: Utilizar componentes que admitan el modelo asincrónico basado en eventos</span><span class="sxs-lookup"><span data-stu-id="39a46-102">How to: Use Components That Support the Event-based Asynchronous Pattern</span></span>
<span data-ttu-id="39a46-103">Muchos componentes le ofrecen la opción de realizar su trabajo de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="39a46-103">Many components provide you with the option of performing their work asynchronously.</span></span> <span data-ttu-id="39a46-104">Por ejemplo, los componentes <xref:System.Media.SoundPlayer> y <xref:System.Windows.Forms.PictureBox> permiten cargas sonidos e imágenes "en segundo plano" mientras el subproceso principal continúa ejecutándose sin interrupción.</span><span class="sxs-lookup"><span data-stu-id="39a46-104">The <xref:System.Media.SoundPlayer> and <xref:System.Windows.Forms.PictureBox> components, for example, enable you to load sounds and images "in the background" while your main thread continues running without interruption.</span></span>  
  
 <span data-ttu-id="39a46-105">Usar métodos asincrónicos en una clase que admite la [Información general sobre el modelo asincrónico basado en eventos](event-based-asynchronous-pattern-overview.md) puede ser tan sencillo como adjuntar un controlador de eventos al evento _MethodName_**Completed** del componente, como lo haría para cualquier otro evento.</span><span class="sxs-lookup"><span data-stu-id="39a46-105">Using asynchronous methods on a class that supports the [Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) can be as simple as attaching an event handler to the component's _MethodName_**Completed** event, just as you would for any other event.</span></span> <span data-ttu-id="39a46-106">Cuando se llama al método _MethodName_**Async**, la aplicación continuará ejecutándose sin interrupción hasta que se genere el evento _MethodName_**Completed**.</span><span class="sxs-lookup"><span data-stu-id="39a46-106">When you call the _MethodName_**Async** method, your application will continue running without interruption until the _MethodName_**Completed** event is raised.</span></span> <span data-ttu-id="39a46-107">En el controlador de eventos, puede examinar el parámetro <xref:System.ComponentModel.AsyncCompletedEventArgs> para determinar si la operación asincrónica se completó correctamente o si se canceló.</span><span class="sxs-lookup"><span data-stu-id="39a46-107">In your event handler, you can examine the <xref:System.ComponentModel.AsyncCompletedEventArgs> parameter to determine if the asynchronous operation successfully completed or if it was canceled.</span></span>  
  
 <span data-ttu-id="39a46-108">Para más información sobre el uso de los controladores de eventos, vea [Información general sobre controladores de eventos](../../framework/winforms/event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="39a46-108">For more information about using event handlers, see [Event Handlers Overview](../../framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="39a46-109">En el siguiente procedimiento se explica cómo usar la funcionalidad de carga de imágenes asincrónica de un control <xref:System.Windows.Forms.PictureBox>.</span><span class="sxs-lookup"><span data-stu-id="39a46-109">The following procedure shows how to use the asynchronous image-loading capability of a <xref:System.Windows.Forms.PictureBox> control.</span></span>  
  
### <a name="to-enable-a-picturebox-control-to-asynchronously-load-an-image"></a><span data-ttu-id="39a46-110">Para permitir que un control PictureBox cargue una imagen de manera asincrónica</span><span class="sxs-lookup"><span data-stu-id="39a46-110">To enable a PictureBox control to asynchronously load an image</span></span>  
  
1. <span data-ttu-id="39a46-111">Cree una instancia del componente <xref:System.Windows.Forms.PictureBox> en el formulario.</span><span class="sxs-lookup"><span data-stu-id="39a46-111">Create an instance of the <xref:System.Windows.Forms.PictureBox> component in your form.</span></span>  
  
2. <span data-ttu-id="39a46-112">Asigne un controlador de eventos al evento <xref:System.Windows.Forms.PictureBox.LoadCompleted>.</span><span class="sxs-lookup"><span data-stu-id="39a46-112">Assign an event handler to the <xref:System.Windows.Forms.PictureBox.LoadCompleted> event.</span></span>  
  
     <span data-ttu-id="39a46-113">Compruebe si hay errores que puedan haberse producido durante la descarga asincrónica aquí.</span><span class="sxs-lookup"><span data-stu-id="39a46-113">Check for any errors that may have occurred during the asynchronous download here.</span></span> <span data-ttu-id="39a46-114">También es donde puede comprobar posibles cancelaciones.</span><span class="sxs-lookup"><span data-stu-id="39a46-114">This is also where you check for cancellation.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#2](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#2)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#5)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#5](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#5)]  
  
3. <span data-ttu-id="39a46-115">Agregue dos botones, denominados `loadButton` y `cancelLoadButton`, al formulario.</span><span class="sxs-lookup"><span data-stu-id="39a46-115">Add two buttons, called `loadButton` and `cancelLoadButton`, to your form.</span></span> <span data-ttu-id="39a46-116">Agregue los controladores de eventos <xref:System.Windows.Forms.Control.Click> para iniciar y cancelar la descarga.</span><span class="sxs-lookup"><span data-stu-id="39a46-116">Add <xref:System.Windows.Forms.Control.Click> event handlers to start and cancel the download.</span></span>  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#3](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/csharp/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.PictureBox.LoadAsync#4](snippets/component-that-supports-the-event-based-asynchronous-pattern/vb/Form1.vb#4)]  
  
4. <span data-ttu-id="39a46-117">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="39a46-117">Run your application.</span></span>  
  
     <span data-ttu-id="39a46-118">Mientras se realiza la descarga de la imagen, puede mover libremente el formulario, minimizarlo y maximizarlo.</span><span class="sxs-lookup"><span data-stu-id="39a46-118">As the image download proceeds, you can move the form freely, minimize it, and maximize it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39a46-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a46-119">See also</span></span>

- [<span data-ttu-id="39a46-120">Ejecutar una operación en segundo plano</span><span class="sxs-lookup"><span data-stu-id="39a46-120">How to: Run an Operation in the Background</span></span>](../../framework/winforms/controls/how-to-run-an-operation-in-the-background.md)
- <span data-ttu-id="39a46-121">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md) (Información general sobre el modelo asincrónico basado en eventos)</span><span class="sxs-lookup"><span data-stu-id="39a46-121">[Event-based Asynchronous Pattern Overview](event-based-asynchronous-pattern-overview.md)</span></span>
