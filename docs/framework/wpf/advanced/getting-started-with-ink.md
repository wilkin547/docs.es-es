---
title: Crear InkCanvas en Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: b8087d6db04f7024b9ee48f28002bee04045a14b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737887"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="13cf3-102">Introducción a la entrada manuscrita en WPF</span><span class="sxs-lookup"><span data-stu-id="13cf3-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="13cf3-103">Windows Presentation Foundation (WPF) tiene una característica de entrada manuscrita que facilita la incorporación de tinta digital a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="13cf3-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13cf3-104">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="13cf3-104">Prerequisites</span></span>

<span data-ttu-id="13cf3-105">Para usar los ejemplos siguientes, primero instale [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="13cf3-105">To use the following examples, first install [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span></span> <span data-ttu-id="13cf3-106">También ayuda a saber cómo escribir aplicaciones WPF básicas.</span><span class="sxs-lookup"><span data-stu-id="13cf3-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="13cf3-107">Para obtener ayuda para empezar a trabajar con WPF, vea [Tutorial: mi primera aplicación de escritorio WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="13cf3-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="13cf3-108">Inicio rápido</span><span class="sxs-lookup"><span data-stu-id="13cf3-108">Quick Start</span></span>

<span data-ttu-id="13cf3-109">Esta sección le ayuda a escribir una aplicación WPF sencilla que recopila entradas manuscritas.</span><span class="sxs-lookup"><span data-stu-id="13cf3-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="13cf3-110">¿Tiene tinta?</span><span class="sxs-lookup"><span data-stu-id="13cf3-110">Got Ink?</span></span>

<span data-ttu-id="13cf3-111">Para crear una aplicación de WPF que admita la entrada de lápiz:</span><span class="sxs-lookup"><span data-stu-id="13cf3-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="13cf3-112">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="13cf3-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="13cf3-113">Cree una nueva **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="13cf3-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="13cf3-114">En el cuadro de diálogo **nuevo proyecto** , expanda la categoría **instalado** > **Visual C#**  o **Visual Basic** > **escritorio de Windows** .</span><span class="sxs-lookup"><span data-stu-id="13cf3-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="13cf3-115">A continuación, seleccione la plantilla aplicación de **WPF (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="13cf3-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="13cf3-116">Escriba un nombre y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13cf3-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="13cf3-117">Visual Studio crea el proyecto y *MainWindow. Xaml* se abre en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="13cf3-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="13cf3-118">Escriba `<InkCanvas/>` entre las etiquetas de `<Grid>`.</span><span class="sxs-lookup"><span data-stu-id="13cf3-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Diseñador XAML con etiqueta InkCanvas](./media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="13cf3-120">Presione **F5** para iniciar la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="13cf3-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="13cf3-121">Con un lápiz o un mouse, escriba **Hello World** en la ventana.</span><span class="sxs-lookup"><span data-stu-id="13cf3-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="13cf3-122">Ha escrito el equivalente de tinta de una aplicación "Hola mundo" con solo 12 pulsaciones de teclas.</span><span class="sxs-lookup"><span data-stu-id="13cf3-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="13cf3-123">Enriquecer su aplicación</span><span class="sxs-lookup"><span data-stu-id="13cf3-123">Spice Up Your App</span></span>

<span data-ttu-id="13cf3-124">Vamos a aprovechar algunas características de WPF.</span><span class="sxs-lookup"><span data-stu-id="13cf3-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="13cf3-125">Reemplace todo el código entre las etiquetas de apertura y cierre \<> por el marcado siguiente:</span><span class="sxs-lookup"><span data-stu-id="13cf3-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

```xaml
<Page>
  <InkCanvas Name="myInkCanvas" MouseRightButtonUp="RightMouseUpHandler">
    <InkCanvas.Background>
      <LinearGradientBrush>
        <GradientStop Color="Yellow" Offset="0.0" />
          <GradientStop Color="Blue" Offset="0.5" />
            <GradientStop Color="HotPink" Offset="1.0" />
              </LinearGradientBrush>
    </InkCanvas.Background>
  </InkCanvas>
</Page>
```

<span data-ttu-id="13cf3-126">Este código XAML crea un fondo de pincel de degradado en la superficie de entrada manuscrita.</span><span class="sxs-lookup"><span data-stu-id="13cf3-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Colores de degradado en la superficie de entrada manuscrita en la aplicación WPF](./media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="13cf3-128">Agregar código detrás de XAML</span><span class="sxs-lookup"><span data-stu-id="13cf3-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="13cf3-129">Aunque XAML facilita enormemente el diseño de la interfaz de usuario, cualquier aplicación real necesita agregar código para controlar eventos.</span><span class="sxs-lookup"><span data-stu-id="13cf3-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="13cf3-130">Este es un ejemplo sencillo que acerca la tinta en respuesta a un clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="13cf3-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="13cf3-131">Establezca el controlador de `MouseRightButtonUp` en el código XAML:</span><span class="sxs-lookup"><span data-stu-id="13cf3-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="13cf3-132">En **Explorador de soluciones**, expanda MainWindow. XAML y abra el archivo de código subyacente (MainWindow.Xaml.cs o MainWindow. Xaml. VB).</span><span class="sxs-lookup"><span data-stu-id="13cf3-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="13cf3-133">Agregue el siguiente código de controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="13cf3-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="13cf3-134">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="13cf3-134">Run the application.</span></span> <span data-ttu-id="13cf3-135">Agregue una entrada de lápiz y, a continuación, haga clic con el botón secundario del mouse o realice un equivalente de mantener presionado con un lápiz.</span><span class="sxs-lookup"><span data-stu-id="13cf3-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="13cf3-136">La pantalla se acerca cada vez que se hace clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="13cf3-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="13cf3-137">Usar código de procedimientos en lugar de XAML</span><span class="sxs-lookup"><span data-stu-id="13cf3-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="13cf3-138">Puede tener acceso a todas las características de WPF desde código de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="13cf3-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="13cf3-139">Siga estos pasos para crear una aplicación "Hello Ink World" para WPF que no use ningún XAML.</span><span class="sxs-lookup"><span data-stu-id="13cf3-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="13cf3-140">Cree un nuevo proyecto de aplicación de consola en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="13cf3-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="13cf3-141">En el cuadro de diálogo **nuevo proyecto** , expanda la categoría **instalado** > **Visual C#**  o **Visual Basic** > **escritorio de Windows** .</span><span class="sxs-lookup"><span data-stu-id="13cf3-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="13cf3-142">A continuación, seleccione la plantilla aplicación de **consola (.NET Framework)** .</span><span class="sxs-lookup"><span data-stu-id="13cf3-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="13cf3-143">Escriba un nombre y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="13cf3-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="13cf3-144">Pegue el código siguiente en el archivo Program.cs o Program. VB:</span><span class="sxs-lookup"><span data-stu-id="13cf3-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="13cf3-145">Agregue referencias a los ensamblados PresentationCore, PresentationFramework y WindowsBase; para ello, haga clic con el botón derecho en **referencias** en **Explorador de soluciones** y elija **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="13cf3-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Administrador de referencias que muestra PresentationCore y PresentationFramework](./media/getting-started-with-ink/reference-manager-presentationcore-presentationframework.png)

1. <span data-ttu-id="13cf3-147">Para compilar la aplicación, presione **F5**.</span><span class="sxs-lookup"><span data-stu-id="13cf3-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="13cf3-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="13cf3-148">See also</span></span>

- [<span data-ttu-id="13cf3-149">Entrada de lápiz digital</span><span class="sxs-lookup"><span data-stu-id="13cf3-149">Digital Ink</span></span>](digital-ink.md)
- [<span data-ttu-id="13cf3-150">Recopilación de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="13cf3-150">Collecting Ink</span></span>](collecting-ink.md)
- [<span data-ttu-id="13cf3-151">Reconocimiento de escritura a mano</span><span class="sxs-lookup"><span data-stu-id="13cf3-151">Handwriting Recognition</span></span>](handwriting-recognition.md)
- [<span data-ttu-id="13cf3-152">Almacenamiento de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="13cf3-152">Storing Ink</span></span>](storing-ink.md)
