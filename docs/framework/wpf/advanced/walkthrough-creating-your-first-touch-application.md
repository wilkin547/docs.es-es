---
title: "Tutorial: Crear su primera aplicación táctil"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee85a5d8764fc27205cf09e1af43069b25096ef1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="cc396-102">Tutorial: Crear su primera aplicación táctil</span><span class="sxs-lookup"><span data-stu-id="cc396-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="cc396-103">permite que las aplicaciones responder a la entrada táctil.</span><span class="sxs-lookup"><span data-stu-id="cc396-103"> enables applications to respond to touch.</span></span> <span data-ttu-id="cc396-104">Por ejemplo, puede interactuar con una aplicación mediante el uso de uno o más dedos en un dispositivo táctil, como una pantalla táctil que este tutorial crea una aplicación que permite al usuario mover, cambiar el tamaño o girar un solo objeto usando el toque.</span><span class="sxs-lookup"><span data-stu-id="cc396-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc396-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="cc396-105">Prerequisites</span></span>  
 <span data-ttu-id="cc396-106">Necesita los componentes siguientes para completar este tutorial:</span><span class="sxs-lookup"><span data-stu-id="cc396-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]<span data-ttu-id="cc396-107">.</span><span class="sxs-lookup"><span data-stu-id="cc396-107">.</span></span>  
  
-   <span data-ttu-id="cc396-108">Windows 7.</span><span class="sxs-lookup"><span data-stu-id="cc396-108">Windows 7.</span></span>  
  
-   <span data-ttu-id="cc396-109">Un dispositivo que acepta la entrada táctil, como una pantalla táctil, que es compatible con Windows Touch.</span><span class="sxs-lookup"><span data-stu-id="cc396-109">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="cc396-110">Además, debe tener un conocimiento básico de cómo crear una aplicación en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especialmente cómo suscribirse a y controlar un evento.</span><span class="sxs-lookup"><span data-stu-id="cc396-110">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="cc396-111">Para obtener más información, consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="cc396-111">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="cc396-112">Crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="cc396-112">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="cc396-113">Para crear la aplicación</span><span class="sxs-lookup"><span data-stu-id="cc396-113">To create the application</span></span>  
  
1.  <span data-ttu-id="cc396-114">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `BasicManipulation`.</span><span class="sxs-lookup"><span data-stu-id="cc396-114">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="cc396-115">Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="cc396-115">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="cc396-116">Reemplace el contenido de MainWindow.xaml por el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="cc396-116">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="cc396-117">Este marcado crea una aplicación simple que contiene un rojo <xref:System.Windows.Shapes.Rectangle> en un <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="cc396-117">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="cc396-118">El <xref:System.Windows.UIElement.IsManipulationEnabled%2A> propiedad de la <xref:System.Windows.Shapes.Rectangle> se establece en true para que recibirá los eventos de manipulación.</span><span class="sxs-lookup"><span data-stu-id="cc396-118">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="cc396-119">La aplicación se suscribe a la <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, y <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos.</span><span class="sxs-lookup"><span data-stu-id="cc396-119">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="cc396-120">Estos eventos contienen la lógica para mover el <xref:System.Windows.Shapes.Rectangle> cuando el usuario lo manipule.</span><span class="sxs-lookup"><span data-stu-id="cc396-120">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="cc396-121">Si utiliza Visual Basic, en la primera línea de MainWindow.xaml, reemplace `x:Class="BasicManipulation.MainWindow"` con `x:Class="MainWindow"`.</span><span class="sxs-lookup"><span data-stu-id="cc396-121">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="cc396-122">En el `MainWindow` de clases, agregue las siguientes <xref:System.Windows.UIElement.ManipulationStarting> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cc396-122">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="cc396-123">El <xref:System.Windows.UIElement.ManipulationStarting> evento tiene lugar cuando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detecta ese táctil entrada empieza a manipular un objeto.</span><span class="sxs-lookup"><span data-stu-id="cc396-123">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="cc396-124">El código especifica que la posición de la manipulación debe ser relativa a la <xref:System.Windows.Window> estableciendo el <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="cc396-124">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  <span data-ttu-id="cc396-125">En el `MainWindow` de clases, agregue las siguientes <xref:System.Windows.Input.ManipulationDelta> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cc396-125">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>  
  
     <span data-ttu-id="cc396-126">El <xref:System.Windows.Input.ManipulationDelta> evento tiene lugar cuando cambia la posición de entrada de la entrada táctil y puede aparecer varias veces durante una manipulación.</span><span class="sxs-lookup"><span data-stu-id="cc396-126">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="cc396-127">El evento también puede producirse después de que se produzca un dedo.</span><span class="sxs-lookup"><span data-stu-id="cc396-127">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="cc396-128">Por ejemplo, si el usuario arrastra un dedo en una pantalla, la <xref:System.Windows.Input.ManipulationDelta> evento aparece varias veces como se mueve el dedo.</span><span class="sxs-lookup"><span data-stu-id="cc396-128">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="cc396-129">Cuando el usuario levanta un dedo en la pantalla, la <xref:System.Windows.Input.ManipulationDelta> evento sigue produciéndose para simular la inercia.</span><span class="sxs-lookup"><span data-stu-id="cc396-129">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>  
  
     <span data-ttu-id="cc396-130">El código se aplica el <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> a la <xref:System.Windows.UIElement.RenderTransform%2A> de la <xref:System.Windows.Shapes.Rectangle> moverlo a medida que el usuario mueve la entrada táctil de entrada.</span><span class="sxs-lookup"><span data-stu-id="cc396-130">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="cc396-131">También comprueba si el <xref:System.Windows.Shapes.Rectangle> está fuera de los límites de la <xref:System.Windows.Window> cuando el evento tiene lugar durante la inercia.</span><span class="sxs-lookup"><span data-stu-id="cc396-131">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="cc396-132">Si es así, la aplicación llama a la <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> método para finalizar la manipulación.</span><span class="sxs-lookup"><span data-stu-id="cc396-132">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  <span data-ttu-id="cc396-133">En el `MainWindow` de clases, agregue las siguientes <xref:System.Windows.UIElement.ManipulationInertiaStarting> controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="cc396-133">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>  
  
     <span data-ttu-id="cc396-134">El <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento tiene lugar cuando el usuario levanta todos los dedos de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="cc396-134">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="cc396-135">El código establece la velocidad inicial y desaceleración para el movimiento, expansión y giro del rectángulo.</span><span class="sxs-lookup"><span data-stu-id="cc396-135">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  <span data-ttu-id="cc396-136">Compile y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc396-136">Build and run the project.</span></span>  
  
     <span data-ttu-id="cc396-137">Debería ver un cuadrado rojo aparecen en la ventana.</span><span class="sxs-lookup"><span data-stu-id="cc396-137">You should see a red square appear in the window.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="cc396-138">Probar la aplicación</span><span class="sxs-lookup"><span data-stu-id="cc396-138">Testing the Application</span></span>  
 <span data-ttu-id="cc396-139">Para probar la aplicación, pruebe a las manipulaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="cc396-139">To test the application, try the following manipulations.</span></span> <span data-ttu-id="cc396-140">Tenga en cuenta que puede hacer más de uno de los siguientes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="cc396-140">Note that you can do more than one of the following at the same time.</span></span>  
  
-   <span data-ttu-id="cc396-141">Para mover el <xref:System.Windows.Shapes.Rectangle>, coloque un dedo en el <xref:System.Windows.Shapes.Rectangle> y mueva el dedo por la pantalla.</span><span class="sxs-lookup"><span data-stu-id="cc396-141">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>  
  
-   <span data-ttu-id="cc396-142">Para cambiar el tamaño de la <xref:System.Windows.Shapes.Rectangle>, coloque dos dedos en la <xref:System.Windows.Shapes.Rectangle> y mover los dedos acerque o alejados entre sí.</span><span class="sxs-lookup"><span data-stu-id="cc396-142">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>  
  
-   <span data-ttu-id="cc396-143">Para girar el <xref:System.Windows.Shapes.Rectangle>, coloque dos dedos en la <xref:System.Windows.Shapes.Rectangle> y rote los dedos entre sí.</span><span class="sxs-lookup"><span data-stu-id="cc396-143">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>  
  
 <span data-ttu-id="cc396-144">Para producir inercia, levante rápidamente los dedos en la pantalla de medida que realiza las manipulaciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="cc396-144">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="cc396-145">El <xref:System.Windows.Shapes.Rectangle> continuarán mover, cambiar el tamaño o girar durante unos segundos antes de que se detenga.</span><span class="sxs-lookup"><span data-stu-id="cc396-145">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc396-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc396-146">See Also</span></span>  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
