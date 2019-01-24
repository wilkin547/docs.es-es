---
title: Crear un objeto InkCanvas en una aplicación WPF en Visual Studio
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- procedural code in lieu of XAML [WPF]
- XAML [WPF], procedural code in lieu of
- InkCanvas (WPF)
ms.assetid: 760332dd-594a-475d-865b-01659db8cab7
ms.openlocfilehash: eaaa8ad5273331941bc6915231460100e8ac24b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646245"
---
# <a name="get-started-with-ink-in-wpf"></a><span data-ttu-id="5b510-102">Empezar a trabajar con entradas manuscritas en WPF</span><span class="sxs-lookup"><span data-stu-id="5b510-102">Get Started with Ink in WPF</span></span>

<span data-ttu-id="5b510-103">Windows Presentation Foundation (WPF) tiene una característica de tinta que facilita la tarea incorporar la entrada de lápiz digital en su aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b510-103">Windows Presentation Foundation (WPF) has an ink feature that makes it easy to incorporate digital ink into your app.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5b510-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5b510-104">Prerequisites</span></span>

<span data-ttu-id="5b510-105">Para usar los ejemplos siguientes, primero [instalar Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span><span class="sxs-lookup"><span data-stu-id="5b510-105">To use the following examples, first [install Microsoft Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).</span></span> <span data-ttu-id="5b510-106">También ayuda a saber cómo escribir aplicaciones básicas de WPF.</span><span class="sxs-lookup"><span data-stu-id="5b510-106">It also helps to know how to write basic WPF apps.</span></span> <span data-ttu-id="5b510-107">Para obtener ayuda de introducción a WPF, consulte [Tutorial: Mi primera aplicación de escritorio de WPF](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span><span class="sxs-lookup"><span data-stu-id="5b510-107">For help getting started with WPF, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>

## <a name="quick-start"></a><span data-ttu-id="5b510-108">Guía de inicio rápido</span><span class="sxs-lookup"><span data-stu-id="5b510-108">Quick Start</span></span>

<span data-ttu-id="5b510-109">En esta sección le ayuda a escribir una aplicación WPF sencilla que recopila entradas de lápiz.</span><span class="sxs-lookup"><span data-stu-id="5b510-109">This section helps you write a simple WPF application that collects ink.</span></span>

### <a name="got-ink"></a><span data-ttu-id="5b510-110">¿Tiene la entrada de lápiz?</span><span class="sxs-lookup"><span data-stu-id="5b510-110">Got Ink?</span></span>

<span data-ttu-id="5b510-111">Para crear una aplicación WPF que admite la entrada de lápiz:</span><span class="sxs-lookup"><span data-stu-id="5b510-111">To create a WPF app that supports ink:</span></span>

1. <span data-ttu-id="5b510-112">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b510-112">Open Visual Studio.</span></span>

2. <span data-ttu-id="5b510-113">Cree un nuevo **aplicación WPF**.</span><span class="sxs-lookup"><span data-stu-id="5b510-113">Create a new **WPF App**.</span></span>

   <span data-ttu-id="5b510-114">En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** o **Visual Basic**  >   **Windows Desktop** categoría.</span><span class="sxs-lookup"><span data-stu-id="5b510-114">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="5b510-115">A continuación, seleccione el **aplicación de WPF (.NET Framework)** plantilla de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b510-115">Then, select the **WPF App (.NET Framework)** app template.</span></span> <span data-ttu-id="5b510-116">Escriba un nombre y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b510-116">Enter a name, and then select **OK**.</span></span>

   <span data-ttu-id="5b510-117">Visual Studio crea el proyecto, y *MainWindow.xaml* se abre en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="5b510-117">Visual Studio creates the project, and *MainWindow.xaml* opens in the designer.</span></span>

3. <span data-ttu-id="5b510-118">Tipo `<InkCanvas/>` entre el `<Grid>` etiquetas.</span><span class="sxs-lookup"><span data-stu-id="5b510-118">Type `<InkCanvas/>` between the `<Grid>` tags.</span></span>

   ![Diseñador XAML con la etiqueta a InkCanvas](media/getting-started-with-ink/inkcanvas-xaml.png)

4. <span data-ttu-id="5b510-120">Presione **F5** para iniciar la aplicación en el depurador.</span><span class="sxs-lookup"><span data-stu-id="5b510-120">Press **F5** to launch your application in the debugger.</span></span>

5. <span data-ttu-id="5b510-121">Con un lápiz o un mouse, escribir **Hola mundo** en la ventana.</span><span class="sxs-lookup"><span data-stu-id="5b510-121">Using a stylus or mouse, write **hello world** in the window.</span></span>

<span data-ttu-id="5b510-122">Ha escrito el equivalente de tinta de una aplicación "hello world" con tan sólo 12 pulsaciones de teclas.</span><span class="sxs-lookup"><span data-stu-id="5b510-122">You've written the ink equivalent of a "hello world" application with only 12 keystrokes!</span></span>

### <a name="spice-up-your-app"></a><span data-ttu-id="5b510-123">Anime la aplicación</span><span class="sxs-lookup"><span data-stu-id="5b510-123">Spice Up Your App</span></span>

<span data-ttu-id="5b510-124">Vamos a sacar partido de algunas características de WPF.</span><span class="sxs-lookup"><span data-stu-id="5b510-124">Let’s take advantage of some features of the WPF.</span></span> <span data-ttu-id="5b510-125">Reemplace todo entre la apertura y cierre \<Ventana > etiquetas con el marcado siguiente:</span><span class="sxs-lookup"><span data-stu-id="5b510-125">Replace everything between the opening and closing \<Window> tags with the following markup:</span></span>

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

<span data-ttu-id="5b510-126">Este XAML crea un fondo de pincel de degradado en la superficie de escritura a mano.</span><span class="sxs-lookup"><span data-stu-id="5b510-126">This XAML creates a gradient brush background on your inking surface.</span></span>

![Colores de degradado en la superficie de la aplicación WPF de tinta](media/getting-started-with-ink/gradient-colors.png)

### <a name="add-some-code-behind-the-xaml"></a><span data-ttu-id="5b510-128">Agregar código detrás del XAML</span><span class="sxs-lookup"><span data-stu-id="5b510-128">Add Some Code Behind the XAML</span></span>

<span data-ttu-id="5b510-129">Aunque XAML hace muy fácil de diseñar la interfaz de usuario, debe agregar código para controlar los eventos de cualquier aplicación del mundo real.</span><span class="sxs-lookup"><span data-stu-id="5b510-129">While XAML makes it very easy to design the user interface, any real-world application needs to add code to handle events.</span></span> <span data-ttu-id="5b510-130">Este es un ejemplo sencillo que amplía la tinta en respuesta a un secundario de un mouse.</span><span class="sxs-lookup"><span data-stu-id="5b510-130">Here is a simple example that zooms in on the ink in response to a right-click from a mouse.</span></span>

1. <span data-ttu-id="5b510-131">Establecer el `MouseRightButtonUp` controlador en el XAML:</span><span class="sxs-lookup"><span data-stu-id="5b510-131">Set the `MouseRightButtonUp` handler in your XAML:</span></span>

   [!code-xaml[DigitalInkTopics#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#3)]

1. <span data-ttu-id="5b510-132">En **el Explorador de soluciones**, expanda MainWindow.xaml y abra el archivo de código subyacente (MainWindow.xaml.cs o MainWindow.xaml.vb).</span><span class="sxs-lookup"><span data-stu-id="5b510-132">In **Solution Explorer**, expand MainWindow.xaml and open the code-behind file (MainWindow.xaml.cs or MainWindow.xaml.vb).</span></span> <span data-ttu-id="5b510-133">Agregue el siguiente código de controlador de eventos:</span><span class="sxs-lookup"><span data-stu-id="5b510-133">Add the following event handler code:</span></span>

   [!code-csharp[DigitalInkTopics#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml.cs#4)]
   [!code-vb[DigitalInkTopics#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window2.xaml.vb#4)]

1. <span data-ttu-id="5b510-134">Ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b510-134">Run the application.</span></span> <span data-ttu-id="5b510-135">Agregar algo de tinta y, a continuación, haga doble clic con el mouse o presione y mantenga equivalente de hacer con un lápiz óptico.</span><span class="sxs-lookup"><span data-stu-id="5b510-135">Add some ink, and then right-click with the mouse or perform a press-and-hold equivalent with a stylus.</span></span>

   <span data-ttu-id="5b510-136">La presentación acerca cada vez que haga clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="5b510-136">The display zooms in each time you click with the right mouse button.</span></span>

### <a name="use-procedural-code-instead-of-xaml"></a><span data-ttu-id="5b510-137">Usar código de procedimientos en lugar de XAML</span><span class="sxs-lookup"><span data-stu-id="5b510-137">Use Procedural Code Instead of XAML</span></span>

<span data-ttu-id="5b510-138">Puede tener acceso a todas las características WPF del código de procedimientos.</span><span class="sxs-lookup"><span data-stu-id="5b510-138">You can access all WPF features from procedural code.</span></span> <span data-ttu-id="5b510-139">Siga estos pasos para crear una aplicación "Hello Ink World" para WPF que no usa ningún XAML en absoluto.</span><span class="sxs-lookup"><span data-stu-id="5b510-139">Follow these steps to create a "Hello Ink World" application for WPF that doesn’t use any XAML at all.</span></span>

1. <span data-ttu-id="5b510-140">Crear un nuevo proyecto de aplicación de consola en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5b510-140">Create a new console application project in Visual Studio.</span></span>

   <span data-ttu-id="5b510-141">En el **nuevo proyecto** cuadro de diálogo, expanda el **instalado** > **Visual C#** o **Visual Basic**  >   **Windows Desktop** categoría.</span><span class="sxs-lookup"><span data-stu-id="5b510-141">In the **New Project** dialog, expand the **Installed** > **Visual C#** or **Visual Basic** > **Windows Desktop** category.</span></span> <span data-ttu-id="5b510-142">A continuación, seleccione el **aplicación de consola (.NET Framework)** plantilla de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5b510-142">Then, select the **Console App (.NET Framework)** app template.</span></span> <span data-ttu-id="5b510-143">Escriba un nombre y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b510-143">Enter a name, and then select **OK**.</span></span>

1. <span data-ttu-id="5b510-144">Pegue el código siguiente en el archivo Program.cs o Program.vb:</span><span class="sxs-lookup"><span data-stu-id="5b510-144">Paste the following code into the Program.cs or Program.vb file:</span></span>

   [!code-csharp[InkCanvasConsoleApp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasConsoleApp/CSharp/Program.cs#1)]
   [!code-vb[InkCanvasConsoleApp#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkCanvasConsoleApp/VisualBasic/Module1.vb#1)]

1. <span data-ttu-id="5b510-145">Agregue referencias a los ensamblados PresentationCore, PresentationFramework y WindowsBase haciendo clic en **referencias** en **el Explorador de soluciones** y eligiendo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="5b510-145">Add references to the PresentationCore, PresentationFramework, and WindowsBase assemblies by right-clicking on **References** in **Solution Explorer** and choosing **Add Reference**.</span></span>

   ![Administrador de referencias que muestra PresentationCore y PresentationFramework](media/getting-started-with-ink/references.png)

1. <span data-ttu-id="5b510-147">Compile la aplicación presionando **F5**.</span><span class="sxs-lookup"><span data-stu-id="5b510-147">Build the application by pressing **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b510-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b510-148">See also</span></span>

- [<span data-ttu-id="5b510-149">Entrada de lápiz digital</span><span class="sxs-lookup"><span data-stu-id="5b510-149">Digital Ink</span></span>](../../../../docs/framework/wpf/advanced/digital-ink.md)
- [<span data-ttu-id="5b510-150">Recopilación de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="5b510-150">Collecting Ink</span></span>](../../../../docs/framework/wpf/advanced/collecting-ink.md)
- [<span data-ttu-id="5b510-151">Reconocimiento de escritura a mano</span><span class="sxs-lookup"><span data-stu-id="5b510-151">Handwriting Recognition</span></span>](../../../../docs/framework/wpf/advanced/handwriting-recognition.md)
- [<span data-ttu-id="5b510-152">Almacenamiento de entradas de lápiz</span><span class="sxs-lookup"><span data-stu-id="5b510-152">Storing Ink</span></span>](../../../../docs/framework/wpf/advanced/storing-ink.md)
