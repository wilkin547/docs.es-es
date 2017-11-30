---
title: "Introducción a las entradas manuscritas"
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
- procedural code in lieu of XAML [WPF]
- gradient brush [WPF], animating colors of
- XAML [WPF], procedural code in lieu of
- animation [WPF], gradient brush colors
- brushes [WPF], animating colors of
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dc8ffe9ad68060d9dfbcafe99133a736237a2bb3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="getting-started-with-ink"></a><span data-ttu-id="0f185-102">Introducción a las entradas manuscritas</span><span class="sxs-lookup"><span data-stu-id="0f185-102">Getting Started with Ink</span></span>
<span data-ttu-id="0f185-103">La incorporación de entrada de lápiz digital en sus aplicaciones es más fácil que nunca.</span><span class="sxs-lookup"><span data-stu-id="0f185-103">Incorporating digital ink into your applications is easier than ever.</span></span> <span data-ttu-id="0f185-104">Tinta ha evolucionado ante un corolario al método COM y formularios Windows Forms de la programación para lograr una integración completa en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-104">Ink has evolved from being a corollary to the COM and Windows Forms method of programming to achieving full integration into the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="0f185-105">No es necesario instalar ningún SDK independiente ni bibliotecas en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f185-105">You do not need to install separate SDKs or runtime libraries.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f185-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="0f185-106">Prerequisites</span></span>  
 <span data-ttu-id="0f185-107">Para usar los ejemplos siguientes, primero debe instalar Microsoft Visual Studio 2005 y [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-107">To use the following examples, you must first install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)].</span></span> <span data-ttu-id="0f185-108">También debe saber cómo escribir aplicaciones para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-108">You should also understand how to write applications for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="0f185-109">Para obtener más información acerca de cómo empezar a usar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="0f185-109">For more information about getting started with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="quick-start"></a><span data-ttu-id="0f185-110">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="0f185-110">Quick Start</span></span>  
 <span data-ttu-id="0f185-111">Esta sección le ayudará a escribir una sencilla [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación que recopila tinta.</span><span class="sxs-lookup"><span data-stu-id="0f185-111">This section helps you write a simple [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that collects ink.</span></span>  
  
 <span data-ttu-id="0f185-112">Si aún no lo ha hecho, instale Microsoft Visual Studio 2005 y [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-112">If you haven't already done so, install Microsoft Visual Studio 2005 and the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)].</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="0f185-113">las aplicaciones normalmente deben compilarse antes de verlos, aunque estas constan únicamente de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-113"> applications usually must be compiled before you can view them, even if they consist entirely of [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="0f185-114">Sin embargo, el [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] incluye una aplicación, XamlPad, diseñada para acelerar el proceso de implementar un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-según la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="0f185-114">However, the [!INCLUDE[TLA#tla_winfxsdk](../../../../includes/tlasharptla-winfxsdk-md.md)] includes an application, XamlPad, designed to speed up the process of implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-based UI.</span></span> <span data-ttu-id="0f185-115">Puede utilizar esa aplicación para ver y aprovechar los primeros ejemplos de este documento.</span><span class="sxs-lookup"><span data-stu-id="0f185-115">You can use that application to view and tinker with the first few samples in this document.</span></span> <span data-ttu-id="0f185-116">El proceso de creación de compila aplicaciones de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] se trata más adelante en este documento.</span><span class="sxs-lookup"><span data-stu-id="0f185-116">The process of creating compiled applications from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] is covered later in this document.</span></span>  
  
 <span data-ttu-id="0f185-117">Para iniciar XAMLPad, haga clic en el **iniciar** menú, elija **todos los programas**, seleccione **Microsoft Winndows SDK**, seleccione **herramientas**y haga clic en **XAMLPad**.</span><span class="sxs-lookup"><span data-stu-id="0f185-117">To launch XAMLPad, click the **Start** menu, point to **All Programs**, point to **Microsoft Winndows SDK**, point to **Tools**, and click **XAMLPad**.</span></span> <span data-ttu-id="0f185-118">En el panel de representación, XAMLPad representa el código XAML escrito en el panel de código.</span><span class="sxs-lookup"><span data-stu-id="0f185-118">In the rendering pane, XAMLPad renders the XAML code written in the code pane.</span></span> <span data-ttu-id="0f185-119">Puede editar el código XAML y los cambios aparecen inmediatamente en el panel de representación.</span><span class="sxs-lookup"><span data-stu-id="0f185-119">You can edit the XAML code, and the changes immediately appear in the rendering pane.</span></span>  
  
#### <a name="got-ink"></a><span data-ttu-id="0f185-120">¿Se obtuvo tinta?</span><span class="sxs-lookup"><span data-stu-id="0f185-120">Got Ink?</span></span>  
 <span data-ttu-id="0f185-121">Para iniciar su primer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicación que admita tinta:</span><span class="sxs-lookup"><span data-stu-id="0f185-121">To start your first [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application that supports ink:</span></span>  
  
1.  <span data-ttu-id="0f185-122">Abra Microsoft Visual Studio 2005</span><span class="sxs-lookup"><span data-stu-id="0f185-122">Open Microsoft Visual Studio 2005</span></span>  
  
2.  <span data-ttu-id="0f185-123">Crear un nuevo **aplicación de Windows (WPF)**</span><span class="sxs-lookup"><span data-stu-id="0f185-123">Create a new **Windows Application (WPF)**</span></span>  
  
3.  <span data-ttu-id="0f185-124">Tipo de `<InkCanvas/>` entre el `<Grid>` etiquetas</span><span class="sxs-lookup"><span data-stu-id="0f185-124">Type `<InkCanvas/>` between the `<Grid>` tags</span></span>  
  
4.  <span data-ttu-id="0f185-125">Presione **F5** para iniciar la aplicación en el depurador</span><span class="sxs-lookup"><span data-stu-id="0f185-125">Press **F5** to launch your application in the debugger</span></span>  
  
5.  <span data-ttu-id="0f185-126">Con un lápiz o un mouse, escribir **Hola a todos** en la ventana</span><span class="sxs-lookup"><span data-stu-id="0f185-126">Using a stylus or mouse, write **hello world** in the window</span></span>  
  
 <span data-ttu-id="0f185-127">Ha escrito el equivalente de tinta de una aplicación "hello world" con tan sólo 12 pulsaciones de teclas.</span><span class="sxs-lookup"><span data-stu-id="0f185-127">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>  
  
#### <a name="spice-up-your-application"></a><span data-ttu-id="0f185-128">Animar la aplicación</span><span class="sxs-lookup"><span data-stu-id="0f185-128">Spice Up Your Application</span></span>  
 <span data-ttu-id="0f185-129">Vamos a aprovechar las ventajas de algunas características de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0f185-129">Let’s take advantage of some features of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  <span data-ttu-id="0f185-130">Reemplace todo entre la apertura \<Ventana > y cerrar \</Window > etiquetas con el código siguiente para obtener un fondo de pincel de degradado en la superficie de escritura a mano.</span><span class="sxs-lookup"><span data-stu-id="0f185-130">Replace everything between the opening \<Window> and closing \</Window> tags with the following markup to get a gradient brush background on your inking surface.</span></span>  
  
 [!code-xaml[DigitalInkTopics#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1)]  
[!code-xaml[DigitalInkTopics#1a](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#1a)]  
  
#### <a name="using-animation"></a><span data-ttu-id="0f185-131">Uso de animación</span><span class="sxs-lookup"><span data-stu-id="0f185-131">Using Animation</span></span>  
 <span data-ttu-id="0f185-132">Para divertirse, vamos a animar los colores del pincel de degradado.</span><span class="sxs-lookup"><span data-stu-id="0f185-132">For fun, let's animate the colors of the gradient brush.</span></span> <span data-ttu-id="0f185-133">Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] después del cierre `</InkCanvas>` etiqueta pero antes del cierre `</Page>` etiqueta.</span><span class="sxs-lookup"><span data-stu-id="0f185-133">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] after the closing `</InkCanvas>` tag but before the closing `</Page>` tag.</span></span>  
  
 [!code-xaml[DigitalInkTopics#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml#2)]  
  
#### <a name="adding-some-code-behind-the-xaml"></a><span data-ttu-id="0f185-134">Agrega un código detrás de XAML</span><span class="sxs-lookup"><span data-stu-id="0f185-134">Adding Some Code Behind the XAML</span></span>  
 <span data-ttu-id="0f185-135">Aunque XAML facilita diseñar la interfaz de usuario, cualquier aplicación del mundo real debe agregar código para controlar los eventos.</span><span class="sxs-lookup"><span data-stu-id="0f185-135">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="0f185-136">Este es un ejemplo sencillo que para acercar la tinta en respuesta a un menú contextual de un mouse:</span><span class="sxs-lookup"><span data-stu-id="0f185-136">Here is a simple example that zooms in on the ink in response to a right-click from a mouse:</span></span>  
  
 <span data-ttu-id="0f185-137">Establecer el `MouseRightButtonUp` controlador en su [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="0f185-137">Set the `MouseRightButtonUp` handler in your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]:</span></span>  
  
 [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]  
  
 <span data-ttu-id="0f185-138">En el Explorador de soluciones de Visual Studio, expanda Windows1.xaml y abra el archivo de código subyacente, Window1.xaml.cs o Window1.xaml.vb si está utilizando Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0f185-138">In Visual Studio’s Solution Explorer, expand Windows1.xaml and open the code-behind file, Window1.xaml.cs or Window1.xaml.vb if you are using Visual Basic.</span></span> <span data-ttu-id="0f185-139">Agregue el siguiente código de controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="0f185-139">Add the following event handler code:</span></span>  
  
 [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
 [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]  
  
 <span data-ttu-id="0f185-140">Ahora, ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0f185-140">Now, run your application.</span></span> <span data-ttu-id="0f185-141">Agregar algunas entradas manuscritas y, a continuación, haga clic en con el mouse o realizar un equivalente de presionar y mantener presionado con un lápiz.</span><span class="sxs-lookup"><span data-stu-id="0f185-141">Add some ink and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>  
  
#### <a name="using-procedural-code-instead-of-xaml"></a><span data-ttu-id="0f185-142">Usando código de procedimiento en lugar de XAML</span><span class="sxs-lookup"><span data-stu-id="0f185-142">Using Procedural Code Instead of XAML</span></span>  
 <span data-ttu-id="0f185-143">Puede tener acceso a todas las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] características del código de procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0f185-143">You can access all [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] features from procedural code.</span></span> <span data-ttu-id="0f185-144">Este es una "tinta aplicación Hola a todos" para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que no usa ningún [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en absoluto.</span><span class="sxs-lookup"><span data-stu-id="0f185-144">Here is a "Hello Ink World" application for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] that doesn’t use any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] at all.</span></span> <span data-ttu-id="0f185-145">Pegue el código siguiente en una aplicación de consola vacía en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="0f185-145">Paste the code below into an empty Console Application in Visual Studio.</span></span> <span data-ttu-id="0f185-146">Agregue referencias a los ensamblados de WindowsBase, PresentationCore y PresentationFramework y compile la aplicación presionando **F5**:</span><span class="sxs-lookup"><span data-stu-id="0f185-146">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies, and build the application by pressing **F5**:</span></span>  
  
 [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
 [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="0f185-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f185-147">See Also</span></span>  
 [<span data-ttu-id="0f185-148">Entrada de lápiz digital</span><span class="sxs-lookup"><span data-stu-id="0f185-148">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)  
 [<span data-ttu-id="0f185-149">Recopilación de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="0f185-149">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)  
 [<span data-ttu-id="0f185-150">Reconocimiento de escritura a mano</span><span class="sxs-lookup"><span data-stu-id="0f185-150">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)  
 [<span data-ttu-id="0f185-151">Almacenamiento de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="0f185-151">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
