---
title: Cree su primera aplicación de WPF en Visual Studio 2019-.NET Framework
titleSuffix: ''
description: Desarrolle una aplicación de escritorio Windows Presentation Foundation (WPF) que incluya elementos comunes a la mayoría de las aplicaciones de WPF.
ms.date: 09/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
ms.topic: tutorial
ms.custom: mvc,vs-dotnet
ms.openlocfilehash: c9af988bcf291325b11df4fd22827b47090c0b48
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853886"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="98bcb-103">Tutorial: crear su primera aplicación de WPF en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="98bcb-103">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="98bcb-104">En este artículo se muestra cómo desarrollar una aplicación de escritorio Windows Presentation Foundation (WPF) que incluya los elementos que son comunes a la mayoría de las aplicaciones de WPF: marcado de lenguaje XAML (XAML), código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-104">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="98bcb-105">Para desarrollar la aplicación, usará Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98bcb-105">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="98bcb-106">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="98bcb-106">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="98bcb-107">Cree un proyecto de WPF.</span><span class="sxs-lookup"><span data-stu-id="98bcb-107">Create a WPF project.</span></span>
> - <span data-ttu-id="98bcb-108">Use XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-108">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="98bcb-109">Escriba código para compilar el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-109">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="98bcb-110">Cree una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-110">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="98bcb-111">Agregue controles y cree el diseño para crear la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-111">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="98bcb-112">Cree estilos para un aspecto coherente en la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-112">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="98bcb-113">Enlace la interfaz de usuario a los datos, para rellenar la interfaz de usuario a partir de los datos y para mantener sincronizados los datos y la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-113">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="98bcb-114">Al final del tutorial, habrá creado una aplicación de Windows independiente que permite a los usuarios ver informes de gastos para personas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-114">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="98bcb-115">La aplicación se compone de varias páginas de WPF que se hospedan en una ventana de estilo de explorador.</span><span class="sxs-lookup"><span data-stu-id="98bcb-115">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="98bcb-116">El código de ejemplo que se usa en este tutorial está disponible para Visual Basic y C# en el [tutorial ejemplo de aplicación WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="98bcb-116">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="98bcb-117">Puede alternar el lenguaje de código del código de ejemplo entre C# y Visual Basic mediante el selector de idioma situado en la parte superior de esta página.</span><span class="sxs-lookup"><span data-stu-id="98bcb-117">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98bcb-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="98bcb-118">Prerequisites</span></span>

- <span data-ttu-id="98bcb-119">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo de **desarrollo de escritorio de .net** instalada.</span><span class="sxs-lookup"><span data-stu-id="98bcb-119">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="98bcb-120">Para obtener más información sobre cómo instalar la versión más reciente de Visual Studio, vea [instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="98bcb-120">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="98bcb-121">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="98bcb-121">Create the application project</span></span>

<span data-ttu-id="98bcb-122">El primer paso es crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="98bcb-122">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="98bcb-123">Cree un nuevo proyecto de aplicación de WPF en Visual Basic o Visual C# llamado **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="98bcb-123">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="98bcb-124">Abra Visual Studio y seleccione **crear un nuevo proyecto** **en el menú introducción.**</span><span class="sxs-lookup"><span data-stu-id="98bcb-124">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="98bcb-125">Se abre el cuadro de diálogo **crear nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-125">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="98bcb-126">En la lista desplegable **lenguaje** , seleccione **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-126">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="98bcb-127">Seleccione la plantilla **aplicación WPF (.NET Framework)** y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-127">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Cuadro de diálogo Crear un proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="98bcb-129">Se abre el cuadro de diálogo **configurar el nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-129">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="98bcb-130">Escriba el nombre del proyecto **`ExpenseIt`** y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-130">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Cuadro de diálogo Configurar un nuevo proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="98bcb-132">Visual Studio crea el proyecto y abre el diseñador de la ventana de la aplicación predeterminada denominada **MainWindow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-132">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="98bcb-133">Abra *Application. Xaml* (Visual Basic) o *app. Xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="98bcb-133">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="98bcb-134">Este archivo XAML define una aplicación WPF y los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-134">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="98bcb-135">También se usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow. Xaml*, que se muestra automáticamente cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-135">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="98bcb-136">El código XAML debe tener un aspecto similar al siguiente en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="98bcb-136">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="98bcb-137">Y similar al siguiente en C#:</span><span class="sxs-lookup"><span data-stu-id="98bcb-137">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="98bcb-138">Abra *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-138">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="98bcb-139">Este archivo XAML es la ventana principal de la aplicación y muestra el contenido creado en las páginas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-139">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="98bcb-140">La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono, y controla los eventos, como cerrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="98bcb-140">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="98bcb-141">Cambie el <xref:System.Windows.Window> elemento a <xref:System.Windows.Navigation.NavigationWindow> , como se muestra en el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="98bcb-141">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="98bcb-142">Esta aplicación navega a contenido diferente en función de los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-142">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="98bcb-143">Este es el motivo por el que el principal <xref:System.Windows.Window> debe cambiarse a <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-143">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="98bcb-144"><xref:System.Windows.Navigation.NavigationWindow>hereda todas las propiedades de <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-144"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="98bcb-145">El <xref:System.Windows.Navigation.NavigationWindow> elemento del archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase.</span><span class="sxs-lookup"><span data-stu-id="98bcb-145">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="98bcb-146">Para obtener más información, vea [información general sobre navegación](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-146">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="98bcb-147">Quite los <xref:System.Windows.Controls.Grid> elementos de entre las <xref:System.Windows.Navigation.NavigationWindow> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-147">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="98bcb-148">Cambie las siguientes propiedades en el código XAML para el <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="98bcb-148">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="98bcb-149">Establezca la <xref:System.Windows.Window.Title%2A> propiedad en " `ExpenseIt` ".</span><span class="sxs-lookup"><span data-stu-id="98bcb-149">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="98bcb-150">Establezca la <xref:System.Windows.FrameworkElement.Height%2A> propiedad en 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-150">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="98bcb-151">Establezca la <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-151">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="98bcb-152">El código XAML debe tener un aspecto similar al siguiente para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="98bcb-152">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="98bcb-153">Y similar a lo siguiente para C#:</span><span class="sxs-lookup"><span data-stu-id="98bcb-153">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="98bcb-154">Abra *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-154">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="98bcb-155">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-155">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="98bcb-156">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="98bcb-156">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="98bcb-157">Si usa C#, cambie la `MainWindow` clase para que se derive de <xref:System.Windows.Navigation.NavigationWindow> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-157">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="98bcb-158">(En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML). El código de C# debería tener ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="98bcb-158">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="98bcb-159">Agregar archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="98bcb-159">Add files to the application</span></span>

<span data-ttu-id="98bcb-160">En esta sección, agregará dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-160">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="98bcb-161">Agregue una nueva página al proyecto y asígnele el nombre *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="98bcb-161">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="98bcb-162">En **Explorador de soluciones**, haga clic con el botón secundario en el **`ExpenseIt`** nodo del proyecto y elija **Agregar**  >  **Página**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-162">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="98bcb-163">En el cuadro de diálogo **Agregar nuevo elemento** , la plantilla **página (WPF)** ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98bcb-163">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="98bcb-164">Escriba el nombre **`ExpenseItHome`** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-164">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="98bcb-165">Esta página es la primera página que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-165">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="98bcb-166">Se mostrará una lista de personas de las que seleccionar, para mostrar un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-166">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="98bcb-167">Abra *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-167">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="98bcb-168">Establezca <xref:System.Windows.Controls.Page.Title%2A> en " `ExpenseIt - Home` ".</span><span class="sxs-lookup"><span data-stu-id="98bcb-168">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="98bcb-169">Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-169">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="98bcb-170">El XAML aparece ahora como se indica a continuación para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="98bcb-170">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="98bcb-171">Y similar a lo siguiente para C#:</span><span class="sxs-lookup"><span data-stu-id="98bcb-171">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="98bcb-172">Abra *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-172">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="98bcb-173">Agregue una <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad al <xref:System.Windows.Navigation.NavigationWindow> elemento y establézcala en " `ExpenseItHome.xaml` ".</span><span class="sxs-lookup"><span data-stu-id="98bcb-173">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="98bcb-174">Esto establece *`ExpenseItHome.xaml`* como la primera página que se abre cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-174">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="98bcb-175">XAML de ejemplo en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="98bcb-175">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="98bcb-176">Y en C#:</span><span class="sxs-lookup"><span data-stu-id="98bcb-176">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="98bcb-177">También puede establecer la propiedad **origen** en la categoría **varios** de la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-177">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Propiedad de origen en ventana Propiedades](./media/properties-source.png)

1. <span data-ttu-id="98bcb-179">Agregue otra página de WPF nueva al proyecto y asígnele el nombre *ExpenseReportPage. Xaml*::</span><span class="sxs-lookup"><span data-stu-id="98bcb-179">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="98bcb-180">En **Explorador de soluciones**, haga clic con el botón secundario en el **`ExpenseIt`** nodo del proyecto y elija **Agregar**  >  **Página**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-180">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="98bcb-181">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **página (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-181">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="98bcb-182">Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-182">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="98bcb-183">Esta página mostrará el informe de gastos de la persona que está seleccionada en la **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="98bcb-183">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="98bcb-184">Abra *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-184">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="98bcb-185">Establezca <xref:System.Windows.Controls.Page.Title%2A> en " `ExpenseIt - View Expense` ".</span><span class="sxs-lookup"><span data-stu-id="98bcb-185">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="98bcb-186">Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-186">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="98bcb-187">*ExpenseReportPage. Xaml* tiene ahora el siguiente aspecto en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="98bcb-187">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="98bcb-188">Y similar al siguiente en C#:</span><span class="sxs-lookup"><span data-stu-id="98bcb-188">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="98bcb-189">Abra *ExpenseItHome. Xaml. VB* y *ExpenseReportPage. Xaml. VB*o *ExpenseItHome.Xaml.CS* y *ExpenseReportPage.Xaml.CS*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-189">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="98bcb-190">Cuando se crea un nuevo archivo de paginación, Visual Studio crea automáticamente el archivo *de código subyacente* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-190">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="98bcb-191">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-191">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="98bcb-192">El código debe tener un aspecto similar al siguiente para **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="98bcb-192">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="98bcb-193">Y similar a lo siguiente para **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="98bcb-193">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="98bcb-194">Agregue una imagen denominada *watermark.png* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="98bcb-194">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="98bcb-195">Puede crear su propia imagen, copiar el archivo del código de ejemplo u obtenerlo del repositorio de github [Microsoft/WPF-samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="98bcb-195">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="98bcb-196">Haga clic con el botón secundario en el nodo del proyecto y seleccione **Agregar**  >  **elemento existente**o presione **MAYÚS** + **Alt** + **A**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-196">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="98bcb-197">En el cuadro de diálogo **Agregar elemento existente** , establezca el filtro de archivos en **todos los archivos** o **archivos de imagen**, busque el archivo de imagen que desea usar y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-197">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="98bcb-198">Compilación y ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="98bcb-198">Build and run the application</span></span>

1. <span data-ttu-id="98bcb-199">Para compilar y ejecutar la aplicación, presione **F5** o seleccione **iniciar depuración** en el menú **depurar** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-199">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="98bcb-200">En la ilustración siguiente se muestra la aplicación con los <xref:System.Windows.Navigation.NavigationWindow> botones:</span><span class="sxs-lookup"><span data-stu-id="98bcb-200">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Aplicación después de compilarla y ejecutarla.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="98bcb-202">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98bcb-202">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="98bcb-203">Crear el diseño</span><span class="sxs-lookup"><span data-stu-id="98bcb-203">Create the layout</span></span>

<span data-ttu-id="98bcb-204">El diseño proporciona una manera ordenada de colocar los elementos de la interfaz de usuario y también administra el tamaño y la posición de dichos elementos cuando se cambia el tamaño de una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-204">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="98bcb-205">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="98bcb-205">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="98bcb-206"><xref:System.Windows.Controls.Canvas>: Define un área en la que se pueden colocar explícitamente los elementos secundarios usando coordenadas relativas al área de lienzo.</span><span class="sxs-lookup"><span data-stu-id="98bcb-206"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="98bcb-207"><xref:System.Windows.Controls.DockPanel>: Define un área en la que puede organizar los elementos secundarios de forma horizontal o vertical, en relación unos con otros.</span><span class="sxs-lookup"><span data-stu-id="98bcb-207"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="98bcb-208"><xref:System.Windows.Controls.Grid>: Define un área de cuadrícula flexible que consta de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-208"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="98bcb-209"><xref:System.Windows.Controls.StackPanel>: Organiza los elementos secundarios en una sola línea que se puede orientar horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="98bcb-209"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="98bcb-210"><xref:System.Windows.Controls.VirtualizingStackPanel>: Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="98bcb-210"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="98bcb-211"><xref:System.Windows.Controls.WrapPanel>: Coloca los elementos secundarios en una posición secuencial de izquierda a derecha, dividiendo el contenido en la línea siguiente en el borde del cuadro contenedor.</span><span class="sxs-lookup"><span data-stu-id="98bcb-211"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="98bcb-212">La ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, en función del valor de la propiedad Orientation.</span><span class="sxs-lookup"><span data-stu-id="98bcb-212">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="98bcb-213">Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="98bcb-213">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="98bcb-214">`ExpenseIt`se puede cambiar el tamaño de las páginas y cada página tiene elementos que se organizan horizontal y verticalmente junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-214">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="98bcb-215">En este ejemplo, <xref:System.Windows.Controls.Grid> se usa como elemento de diseño para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-215">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="98bcb-216">Para obtener más información sobre <xref:System.Windows.Controls.Panel> los elementos, consulte [información general](../controls/panels-overview.md)de los paneles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-216">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="98bcb-217">Para obtener más información sobre el diseño, vea [diseño](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-217">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="98bcb-218">En esta sección, creará una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a <xref:System.Windows.Controls.Grid> en *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-218">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="98bcb-219">En *`ExpenseItHome.xaml`* , establezca la <xref:System.Windows.FrameworkElement.Margin%2A> propiedad del <xref:System.Windows.Controls.Grid> elemento en "10, 0, 10, 10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:</span><span class="sxs-lookup"><span data-stu-id="98bcb-219">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="98bcb-220">También puede establecer los valores de **margen** en la ventana **propiedades** , en la categoría **diseño** :</span><span class="sxs-lookup"><span data-stu-id="98bcb-220">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valores de margen en ventana Propiedades](./media/properties-margin.png)

2. <span data-ttu-id="98bcb-222">Agregue el código XAML siguiente entre las <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna:</span><span class="sxs-lookup"><span data-stu-id="98bcb-222">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="98bcb-223">La <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A> , lo que significa que el tamaño de las filas se basa en el contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-223">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="98bcb-224">El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> sizing, lo que significa que el alto de fila es una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="98bcb-224">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="98bcb-225">Por ejemplo, si dos filas tienen cada una <xref:System.Windows.Controls.RowDefinition.Height%2A> de "\*", cada una tiene un alto que es la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="98bcb-225">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="98bcb-226"><xref:System.Windows.Controls.Grid>Ahora debe contener el siguiente código XAML:</span><span class="sxs-lookup"><span data-stu-id="98bcb-226">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="98bcb-227">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="98bcb-227">Add controls</span></span>

<span data-ttu-id="98bcb-228">En esta sección, actualizará la interfaz de usuario de la Página principal para mostrar una lista de personas, donde puede seleccionar una persona para mostrar el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-228">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="98bcb-229">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-229">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="98bcb-230">Para obtener más información, consulte [Controles](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-230">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="98bcb-231">Para crear esta interfaz de usuario, agregará los siguientes elementos a *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="98bcb-231">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="98bcb-232">Un <xref:System.Windows.Controls.ListBox> (para la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="98bcb-232">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="98bcb-233">Un <xref:System.Windows.Controls.Label> (para el encabezado de lista).</span><span class="sxs-lookup"><span data-stu-id="98bcb-233">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="98bcb-234">Un <xref:System.Windows.Controls.Button> (para ver el informe de gastos de la persona que está seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="98bcb-234">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="98bcb-235">Cada control se coloca en una fila de estableciendo <xref:System.Windows.Controls.Grid> la <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="98bcb-235">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="98bcb-236">Para obtener más información sobre las propiedades adjuntas, vea [información general sobre las propiedades adjuntas](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-236">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="98bcb-237">En *`ExpenseItHome.xaml`* , agregue el código XAML siguiente en algún lugar entre las <xref:System.Windows.Controls.Grid> Etiquetas:</span><span class="sxs-lookup"><span data-stu-id="98bcb-237">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="98bcb-238">También puede crear los controles arrastrándolos desde la ventana cuadro de **herramientas** hasta la ventana de diseño y, a continuación, estableciendo sus propiedades en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-238">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="98bcb-239">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-239">Build and run the application.</span></span>

    <span data-ttu-id="98bcb-240">En la ilustración siguiente se muestran los controles que ha creado:</span><span class="sxs-lookup"><span data-stu-id="98bcb-240">The following illustration shows the controls you created:</span></span>

![Captura de pantalla de ejemplo ExpenseIt en la que se muestra una lista de nombres](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="98bcb-242">Agregar una imagen y un título</span><span class="sxs-lookup"><span data-stu-id="98bcb-242">Add an image and a title</span></span>

<span data-ttu-id="98bcb-243">En esta sección, actualizará la interfaz de usuario de la Página principal con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="98bcb-243">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="98bcb-244">En *`ExpenseItHome.xaml`* , agregue otra columna a <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles:</span><span class="sxs-lookup"><span data-stu-id="98bcb-244">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewColumn)]

2. <span data-ttu-id="98bcb-245">Agregue otra fila al <xref:System.Windows.Controls.Grid.RowDefinitions%2A> , para un total de cuatro filas:</span><span class="sxs-lookup"><span data-stu-id="98bcb-245">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=2#NewRows)]

3. <span data-ttu-id="98bcb-246">Mueva los controles a la segunda columna estableciendo la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad en 1 en cada uno de los tres controles (borde, cuadro de lista y botón).</span><span class="sxs-lookup"><span data-stu-id="98bcb-246">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="98bcb-247">Baje cada control una fila aumentando su <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valor en 1 para cada uno de los tres controles (borde, cuadro de lista y botón) y para el elemento Border.</span><span class="sxs-lookup"><span data-stu-id="98bcb-247">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="98bcb-248">El código XAML de los tres controles tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="98bcb-248">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="98bcb-249">Establezca la <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> propiedad en el archivo de imagen *watermark.png* agregando el código XAML siguiente en cualquier lugar entre las `<Grid>` `</Grid>` etiquetas y:</span><span class="sxs-lookup"><span data-stu-id="98bcb-249">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="98bcb-250">Antes del <xref:System.Windows.Controls.Border> elemento, agregue <xref:System.Windows.Controls.Label> con el contenido "ver informe de gastos".</span><span class="sxs-lookup"><span data-stu-id="98bcb-250">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="98bcb-251">Esta etiqueta es el título de la página.</span><span class="sxs-lookup"><span data-stu-id="98bcb-251">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="98bcb-252">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-252">Build and run the application.</span></span>

<span data-ttu-id="98bcb-253">En la ilustración siguiente se muestran los resultados de lo que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="98bcb-253">The following illustration shows the results of what you just added:</span></span>

![Captura de pantalla de ejemplo ExpenseIt que muestra el nuevo fondo de imagen y el título de la página](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="98bcb-255">Agregar código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="98bcb-255">Add code to handle events</span></span>

1. <span data-ttu-id="98bcb-256">En *`ExpenseItHome.xaml`* , agregue un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos al <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="98bcb-256">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="98bcb-257">Para obtener más información, vea [Cómo: crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="98bcb-257">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="98bcb-258">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-258">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="98bcb-259">Agregue el código siguiente a la `ExpenseItHome` clase para agregar un controlador de eventos de clic de botón.</span><span class="sxs-lookup"><span data-stu-id="98bcb-259">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="98bcb-260">El controlador de eventos abre la página **ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-260">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="98bcb-261">Crear la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="98bcb-261">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="98bcb-262">*ExpenseReportPage. Xaml* muestra el informe de gastos de la persona que está seleccionada en la **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="98bcb-262">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="98bcb-263">En esta sección, creará la interfaz de usuario para **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-263">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="98bcb-264">También agregará colores de fondo y relleno a los distintos elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-264">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="98bcb-265">Abra *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-265">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="98bcb-266">Agregue el código XAML siguiente entre las <xref:System.Windows.Controls.Grid> Etiquetas:</span><span class="sxs-lookup"><span data-stu-id="98bcb-266">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="98bcb-267">Esta interfaz de usuario es similar a *`ExpenseItHome.xaml`* , excepto en que los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-267">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="98bcb-268">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-268">Build and run the application.</span></span>

4. <span data-ttu-id="98bcb-269">Seleccione el botón **Ver** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-269">Select the **View** button.</span></span>

    <span data-ttu-id="98bcb-270">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="98bcb-270">The expense report page appears.</span></span> <span data-ttu-id="98bcb-271">Observe también que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="98bcb-271">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="98bcb-272">En la ilustración siguiente se muestran los elementos de la interfaz de usuario agregados a *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-272">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Captura de pantalla de ejemplo ExpenseIt que muestra la interfaz de usuario que se acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="98bcb-274">Controles de estilo</span><span class="sxs-lookup"><span data-stu-id="98bcb-274">Style controls</span></span>

<span data-ttu-id="98bcb-275">La apariencia de varios elementos suele ser la misma para todos los elementos del mismo tipo en una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="98bcb-275">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="98bcb-276">La interfaz de usuario usa [estilos](../../../desktop-wpf/fundamentals/styles-templates-overview.md) para que los aspectos se puedan volver a usar en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-276">UI uses [styles](../../../desktop-wpf/fundamentals/styles-templates-overview.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="98bcb-277">La reutilización de los estilos ayuda a simplificar la creación y administración de XAML.</span><span class="sxs-lookup"><span data-stu-id="98bcb-277">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="98bcb-278">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-278">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="98bcb-279">Abra *Application. Xaml* o *app. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-279">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="98bcb-280">Agregue el código XAML siguiente entre las <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> Etiquetas:</span><span class="sxs-lookup"><span data-stu-id="98bcb-280">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="98bcb-281">Este código XAML agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="98bcb-281">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="98bcb-282">`headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="98bcb-282">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="98bcb-283">`labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-283">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="98bcb-284">`columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="98bcb-284">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="98bcb-285">`listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-285">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="98bcb-286">`listHeaderTextStyle`: Para dar formato al encabezado de la lista <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-286">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="98bcb-287">`buttonStyle`: Para dar formato <xref:System.Windows.Controls.Button> al `ExpenseItHome.xaml` .</span><span class="sxs-lookup"><span data-stu-id="98bcb-287">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="98bcb-288">Observe que los estilos son recursos y secundarios del <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="98bcb-288">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="98bcb-289">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-289">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="98bcb-290">Para obtener un ejemplo del uso de recursos en una aplicación .NET, consulte [usar recursos de aplicación](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-290">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="98bcb-291">En *`ExpenseItHome.xaml`* , reemplace todo lo que haya entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="98bcb-291">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="98bcb-292">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-292">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="98bcb-293">Por ejemplo, `headerTextStyle` se aplica a "ver informe de gastos" <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-293">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="98bcb-294">Abra *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-294">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="98bcb-295">Reemplace todo lo que haya entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="98bcb-295">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="98bcb-296">Este código XAML agrega estilos a <xref:System.Windows.Controls.Label> los <xref:System.Windows.Controls.Border> elementos y.</span><span class="sxs-lookup"><span data-stu-id="98bcb-296">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="98bcb-297">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-297">Build and run the application.</span></span> <span data-ttu-id="98bcb-298">La apariencia de la ventana es la misma que antes.</span><span class="sxs-lookup"><span data-stu-id="98bcb-298">The window appearance is the same as previously.</span></span>

    ![Captura de pantalla de ejemplo ExpenseIt con el mismo aspecto que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="98bcb-300">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98bcb-300">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="98bcb-301">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="98bcb-301">Bind data to a control</span></span>

<span data-ttu-id="98bcb-302">En esta sección, creará los datos XML que se enlazan a varios controles.</span><span class="sxs-lookup"><span data-stu-id="98bcb-302">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="98bcb-303">En *`ExpenseItHome.xaml`* , después del elemento de apertura <xref:System.Windows.Controls.Grid> , agregue el código XAML siguiente para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona:</span><span class="sxs-lookup"><span data-stu-id="98bcb-303">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="98bcb-304">Los datos se crean como un <xref:System.Windows.Controls.Grid> recurso.</span><span class="sxs-lookup"><span data-stu-id="98bcb-304">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="98bcb-305">Normalmente, estos datos se cargan como un archivo, pero para simplificar, los datos se agregan en línea.</span><span class="sxs-lookup"><span data-stu-id="98bcb-305">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="98bcb-306">Dentro del `<Grid.Resources>` elemento, agregue el siguiente `<xref:System.Windows.DataTemplate>` elemento, que define cómo mostrar los datos en <xref:System.Windows.Controls.ListBox> , después del `<XmlDataProvider>` elemento:</span><span class="sxs-lookup"><span data-stu-id="98bcb-306">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="98bcb-307">Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="98bcb-307">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="98bcb-308">Reemplace el existente <xref:System.Windows.Controls.ListBox> por el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="98bcb-308">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="98bcb-309">Este código XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> .</span><span class="sxs-lookup"><span data-stu-id="98bcb-309">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="98bcb-310">Conectar datos a controles</span><span class="sxs-lookup"><span data-stu-id="98bcb-310">Connect data to controls</span></span>

<span data-ttu-id="98bcb-311">A continuación, agregará código para recuperar el nombre seleccionado en la **`ExpenseItHome`** página y pasarlo al constructor de **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="98bcb-311">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="98bcb-312">**ExpenseReportPage** establece su contexto de datos con el elemento pasado, que es de lo que se enlazan los controles definidos en *ExpenseReportPage. Xaml* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-312">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="98bcb-313">Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-313">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="98bcb-314">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98bcb-314">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="98bcb-315">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="98bcb-315">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="98bcb-316">Cambie el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al nuevo constructor pasando los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98bcb-316">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="98bcb-317">Estilo de datos con plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="98bcb-317">Style data with data templates</span></span>

<span data-ttu-id="98bcb-318">En esta sección, actualizará la interfaz de usuario para cada elemento de las listas enlazadas a datos mediante plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-318">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="98bcb-319">Abra *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="98bcb-319">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="98bcb-320">Enlace el contenido de los elementos "Name" y "Department" <xref:System.Windows.Controls.Label> a la propiedad de origen de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="98bcb-320">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="98bcb-321">Para obtener más información sobre el enlace de datos, vea [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-321">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="98bcb-322">Después del elemento de apertura <xref:System.Windows.Controls.Grid> , agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos:</span><span class="sxs-lookup"><span data-stu-id="98bcb-322">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="98bcb-323">Reemplace los <xref:System.Windows.Controls.DataGridTextColumn> elementos por <xref:System.Windows.Controls.DataGridTemplateColumn> debajo del <xref:System.Windows.Controls.DataGrid> elemento y aplíqueles las plantillas.</span><span class="sxs-lookup"><span data-stu-id="98bcb-323">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="98bcb-324">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bcb-324">Build and run the application.</span></span>

6. <span data-ttu-id="98bcb-325">Seleccione una persona y, a continuación, seleccione el botón **Ver** .</span><span class="sxs-lookup"><span data-stu-id="98bcb-325">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="98bcb-326">En la ilustración siguiente se muestran las dos páginas de la `ExpenseIt` aplicación con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicados:</span><span class="sxs-lookup"><span data-stu-id="98bcb-326">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Ambas páginas de la aplicación muestran la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="98bcb-328">Este ejemplo muestra una característica específica de WPF y no sigue todos los procedimientos recomendados para cosas como seguridad, localización y accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="98bcb-328">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="98bcb-329">Para obtener una completa cobertura de WPF y los procedimientos recomendados de desarrollo de aplicaciones .NET, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="98bcb-329">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="98bcb-330">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="98bcb-330">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="98bcb-331">Seguridad</span><span class="sxs-lookup"><span data-stu-id="98bcb-331">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="98bcb-332">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="98bcb-332">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="98bcb-333">Rendimiento de WPF</span><span class="sxs-lookup"><span data-stu-id="98bcb-333">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="98bcb-334">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="98bcb-334">Next steps</span></span>

<span data-ttu-id="98bcb-335">En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="98bcb-335">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="98bcb-336">Ahora debería tener un conocimiento básico de los bloques de creación de una aplicación .NET enlazada a datos.</span><span class="sxs-lookup"><span data-stu-id="98bcb-336">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="98bcb-337">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="98bcb-337">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="98bcb-338">Arquitectura de WPF</span><span class="sxs-lookup"><span data-stu-id="98bcb-338">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="98bcb-339">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="98bcb-339">XAML overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="98bcb-340">Introducción a las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="98bcb-340">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="98bcb-341">Diseño</span><span class="sxs-lookup"><span data-stu-id="98bcb-341">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="98bcb-342">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="98bcb-342">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="98bcb-343">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="98bcb-343">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="98bcb-344">Controles</span><span class="sxs-lookup"><span data-stu-id="98bcb-344">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="98bcb-345">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="98bcb-345">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="98bcb-346">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="98bcb-346">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="98bcb-347">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="98bcb-347">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="98bcb-348">Vea también</span><span class="sxs-lookup"><span data-stu-id="98bcb-348">See also</span></span>

- [<span data-ttu-id="98bcb-349">Información general sobre paneles</span><span class="sxs-lookup"><span data-stu-id="98bcb-349">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="98bcb-350">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="98bcb-350">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="98bcb-351">Compilar una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="98bcb-351">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="98bcb-352">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="98bcb-352">Styles and templates</span></span>](../controls/styles-and-templates.md)
