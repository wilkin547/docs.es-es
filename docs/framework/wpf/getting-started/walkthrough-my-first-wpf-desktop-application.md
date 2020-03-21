---
title: Cree su primera aplicación WPF en Visual Studio 2019 - .NET Framework
titleSuffix: ''
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
ms.openlocfilehash: 65b6fe31e86380162e90820c2cf118a9d1b96b4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186585"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="a9712-102">Tutorial: Crear la primera aplicación WPF en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="a9712-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="a9712-103">En este artículo se muestra cómo desarrollar una aplicación de escritorio de Windows Presentation Foundation (WPF) que incluye los elementos que son comunes a la mayoría de las aplicaciones WPF: marcado de Lenguaje XAML (Extensible Application Markup Language) extensible, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="a9712-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="a9712-104">Para desarrollar la aplicación, usará Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9712-104">To develop the application, you'll use Visual Studio.</span></span>

<span data-ttu-id="a9712-105">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="a9712-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="a9712-106">Cree un proyecto WPFWPF.</span><span class="sxs-lookup"><span data-stu-id="a9712-106">Create a WPF project.</span></span>
> - <span data-ttu-id="a9712-107">Use XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="a9712-108">Escribir código para compilar el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="a9712-109">Cree una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="a9712-110">Agregue controles y cree el diseño para componer la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="a9712-111">Cree estilos para una apariencia coherente en toda la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="a9712-112">Enlazar la interfaz de usuario a los datos, tanto para rellenar la interfaz de usuario a partir de datos y para mantener los datos y la interfaz de usuario sincronizados.</span><span class="sxs-lookup"><span data-stu-id="a9712-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="a9712-113">Al final del tutorial, habrá creado una aplicación independiente de Windows que permite a los usuarios ver informes de gastos para personas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="a9712-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="a9712-114">La aplicación se compone de varias páginas WPFWPF que se hospedan en una ventana de estilo explorador.</span><span class="sxs-lookup"><span data-stu-id="a9712-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="a9712-115">El código de ejemplo que se usa en este tutorial está disponible tanto para Visual Basic como para C. en [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="a9712-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="a9712-116">Puede alternar el idioma de código del código de ejemplo entre C- y Visual Basic mediante el selector de idioma en la parte superior de esta página.</span><span class="sxs-lookup"><span data-stu-id="a9712-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a9712-117">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a9712-117">Prerequisites</span></span>

- <span data-ttu-id="a9712-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo de desarrollo de **escritorio de .NET** instalada.</span><span class="sxs-lookup"><span data-stu-id="a9712-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="a9712-119">Para obtener más información acerca de la instalación de la versión más reciente de Visual Studio, vea [Instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="a9712-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="a9712-120">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="a9712-120">Create the application project</span></span>

<span data-ttu-id="a9712-121">El primer paso es crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="a9712-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="a9712-122">Cree un nuevo proyecto de aplicación WPF **`ExpenseIt`** en Visual Basic o Visual C. denominado:</span><span class="sxs-lookup"><span data-stu-id="a9712-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="a9712-123">Abra Visual Studio y seleccione **Crear un nuevo proyecto** en el menú **Introducción.**</span><span class="sxs-lookup"><span data-stu-id="a9712-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="a9712-124">Se abre el cuadro de diálogo **Crear un nuevo proyecto.**</span><span class="sxs-lookup"><span data-stu-id="a9712-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="a9712-125">En la lista desplegable **Idioma,** seleccione **C o** **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="a9712-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>

   3. <span data-ttu-id="a9712-126">Seleccione la plantilla **Aplicación WPF (.NET Framework)** y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a9712-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span>

      ![Cuadro de diálogo Crear un proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)

      <span data-ttu-id="a9712-128">Se abre el cuadro de diálogo **Configurar el nuevo proyecto.**</span><span class="sxs-lookup"><span data-stu-id="a9712-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="a9712-129">Escriba el **`ExpenseIt`** nombre del proyecto y, a continuación, seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="a9712-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Configurar un nuevo cuadro de diálogo de proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="a9712-131">Visual Studio crea el proyecto y abre el diseñador para la ventana de aplicación predeterminada denominada **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="a9712-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="a9712-132">Abra *Application.xaml* (Visual Basic) o *App.xaml* (C-).</span><span class="sxs-lookup"><span data-stu-id="a9712-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="a9712-133">Este archivo XAML define una aplicación WPFWPF y cualquier recurso de aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="a9712-134">También se usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow.xaml*, que se muestra automáticamente cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="a9712-135">El XAML debe tener el siguiente aspecto en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a9712-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="a9712-136">Y, como lo siguiente, en C-:</span><span class="sxs-lookup"><span data-stu-id="a9712-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="a9712-137">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="a9712-138">Este archivo XAML es la ventana principal de la aplicación y muestra el contenido creado en las páginas.</span><span class="sxs-lookup"><span data-stu-id="a9712-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="a9712-139">La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono, y controla eventos, como cerrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="a9712-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="a9712-140">Cambie <xref:System.Windows.Window> el elemento <xref:System.Windows.Navigation.NavigationWindow>a un , como se muestra en el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="a9712-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="a9712-141">Esta aplicación navega a contenido diferente dependiendo de la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="a9712-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="a9712-142">Esta es la <xref:System.Windows.Window> razón por la <xref:System.Windows.Navigation.NavigationWindow>que el principal necesita ser cambiado a un archivo .</span><span class="sxs-lookup"><span data-stu-id="a9712-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="a9712-143"><xref:System.Windows.Navigation.NavigationWindow>hereda todas las <xref:System.Windows.Window>propiedades de .</span><span class="sxs-lookup"><span data-stu-id="a9712-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="a9712-144">El <xref:System.Windows.Navigation.NavigationWindow> elemento del archivo XAML crea <xref:System.Windows.Navigation.NavigationWindow> una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="a9712-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="a9712-145">Para obtener más información, consulte [Información general sobre la navegación](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9712-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="a9712-146">Elimine <xref:System.Windows.Controls.Grid> los elementos <xref:System.Windows.Navigation.NavigationWindow> de entre las etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a9712-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="a9712-147">Cambie las siguientes propiedades en <xref:System.Windows.Navigation.NavigationWindow> el código XAML para el elemento:</span><span class="sxs-lookup"><span data-stu-id="a9712-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="a9712-148">Establezca <xref:System.Windows.Window.Title%2A> la propiedad`ExpenseIt`en " ".</span><span class="sxs-lookup"><span data-stu-id="a9712-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="a9712-149">Establezca <xref:System.Windows.FrameworkElement.Height%2A> la propiedad en 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="a9712-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="a9712-150">Establezca <xref:System.Windows.FrameworkElement.Width%2A> la propiedad en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="a9712-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="a9712-151">El XAML debe tener el siguiente aspecto para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a9712-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="a9712-152">Y de la siguiente manera para C-:</span><span class="sxs-lookup"><span data-stu-id="a9712-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="a9712-153">Abra *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="a9712-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="a9712-154">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="a9712-155">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="a9712-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="a9712-156">Si está utilizando C,, `MainWindow` cambie la <xref:System.Windows.Navigation.NavigationWindow>clase para derivar de .</span><span class="sxs-lookup"><span data-stu-id="a9712-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="a9712-157">(En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML.) Ahora, el código de CTM debería tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="a9712-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="a9712-158">Añadir archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="a9712-158">Add files to the application</span></span>

<span data-ttu-id="a9712-159">En esta sección, agregará dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="a9712-160">Agregue una nueva página al proyecto *`ExpenseItHome.xaml`* y asígnelle el nombre :</span><span class="sxs-lookup"><span data-stu-id="a9712-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="a9712-161">En **el Explorador**de soluciones **`ExpenseIt`** , haga clic con el botón derecho en el nodo del proyecto y elija **Agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="a9712-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="a9712-162">En el cuadro de diálogo **Agregar nuevo elemento,** la plantilla **Página (WPF)** ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a9712-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="a9712-163">Escriba el **`ExpenseItHome`** nombre y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a9712-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="a9712-164">Esta página es la primera página que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="a9712-165">Mostrará una lista de personas para las que seleccionar, para mostrar un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="a9712-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="a9712-166">Abrir *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="a9712-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="a9712-167">Establezca <xref:System.Windows.Controls.Page.Title%2A> el`ExpenseIt - Home`botón en " ".</span><span class="sxs-lookup"><span data-stu-id="a9712-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="a9712-168">Establezca `DesignHeight` los 350 píxeles y los `DesignWidth` 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="a9712-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="a9712-169">El XAML ahora aparece de la siguiente manera para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a9712-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="a9712-170">Y de la siguiente manera para C-:</span><span class="sxs-lookup"><span data-stu-id="a9712-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="a9712-171">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="a9712-172">Agregue <xref:System.Windows.Navigation.NavigationWindow.Source%2A> una propiedad <xref:System.Windows.Navigation.NavigationWindow> al elemento y`ExpenseItHome.xaml`establézquela en " ".</span><span class="sxs-lookup"><span data-stu-id="a9712-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="a9712-173">Esto *`ExpenseItHome.xaml`* establece que será la primera página abierta cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span>

    <span data-ttu-id="a9712-174">Ejemplo xaml en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a9712-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="a9712-175">Y en C-:</span><span class="sxs-lookup"><span data-stu-id="a9712-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="a9712-176">También puede establecer la propiedad **Source** en la categoría **Varios** de la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="a9712-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Propiedad de origen en la ventana Propiedades](./media/properties-source.png)

1. <span data-ttu-id="a9712-178">Agregue otra nueva página WPF al proyecto y asígnelse el nombre *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="a9712-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="a9712-179">En **el Explorador**de soluciones **`ExpenseIt`** , haga clic con el botón derecho en el nodo del proyecto y elija **Agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="a9712-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="a9712-180">En el cuadro de diálogo **Agregar nuevo elemento,** seleccione la plantilla **Página (WPF).**</span><span class="sxs-lookup"><span data-stu-id="a9712-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="a9712-181">Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a9712-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="a9712-182">Esta página mostrará el informe de gastos **`ExpenseItHome`** de la persona seleccionada en la página.</span><span class="sxs-lookup"><span data-stu-id="a9712-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="a9712-183">Abra *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="a9712-184">Establezca <xref:System.Windows.Controls.Page.Title%2A> el`ExpenseIt - View Expense`botón en " ".</span><span class="sxs-lookup"><span data-stu-id="a9712-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="a9712-185">Establezca `DesignHeight` los 350 píxeles y los `DesignWidth` 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="a9712-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="a9712-186">*ExpenseReportPage.xaml* ahora tiene el siguiente aspecto en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="a9712-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="a9712-187">Y, como lo siguiente, en C-:</span><span class="sxs-lookup"><span data-stu-id="a9712-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="a9712-188">Abra *ExpenseItHome.xaml.vb* y *ExpenseReportPage.xaml.vb*o *ExpenseItHome.xaml.cs* y *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="a9712-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="a9712-189">Al crear un nuevo archivo de página, Visual Studio crea automáticamente su archivo *de código subyacente.*</span><span class="sxs-lookup"><span data-stu-id="a9712-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="a9712-190">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="a9712-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="a9712-191">El código debe tener **`ExpenseItHome`** el siguiente aspecto para:</span><span class="sxs-lookup"><span data-stu-id="a9712-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="a9712-192">Y como lo siguiente para **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="a9712-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="a9712-193">Agregue una imagen denominada *watermark.png* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9712-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="a9712-194">Puede crear su propia imagen, copiar el archivo del código de ejemplo u obtenerlo desde el repositorio GitHub [de microsoft/WPF-Samples.](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png)</span><span class="sxs-lookup"><span data-stu-id="a9712-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="a9712-195">Haga clic con el botón derecho en el nodo del proyecto y seleccione **Agregar** > **elemento existente**o pulse **Mayús**+**Alt**+**A**.</span><span class="sxs-lookup"><span data-stu-id="a9712-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="a9712-196">En el cuadro de diálogo **Agregar elemento existente,** establezca el filtro de archivos en **Todos los archivos** o **Archivos**de imagen , busque el archivo de imagen que desea usar y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a9712-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="a9712-197">Compilación y ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="a9712-197">Build and run the application</span></span>

1. <span data-ttu-id="a9712-198">Para compilar y ejecutar la aplicación, presione **F5** o seleccione **Iniciar depuración** en el menú **Depurar.**</span><span class="sxs-lookup"><span data-stu-id="a9712-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="a9712-199">La siguiente ilustración muestra <xref:System.Windows.Navigation.NavigationWindow> la aplicación con los botones:</span><span class="sxs-lookup"><span data-stu-id="a9712-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Aplicación después de compilarla y ejecutarla.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="a9712-201">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9712-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="a9712-202">Crear el diseño</span><span class="sxs-lookup"><span data-stu-id="a9712-202">Create the layout</span></span>

<span data-ttu-id="a9712-203">Layout proporciona una forma ordenada de colocar elementos de interfaz de usuario y también administra el tamaño y la posición de esos elementos cuando se cambia el tamaño de una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9712-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="a9712-204">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9712-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="a9712-205"><xref:System.Windows.Controls.Canvas>- Define un área dentro de la cual puede colocar explícitamente los elementos secundarios mediante coordenadas relativas al área Canvas.</span><span class="sxs-lookup"><span data-stu-id="a9712-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="a9712-206"><xref:System.Windows.Controls.DockPanel>- Define un área donde puede organizar los elementos secundarios horizontal o verticalmente, en relación entre sí.</span><span class="sxs-lookup"><span data-stu-id="a9712-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="a9712-207"><xref:System.Windows.Controls.Grid>- Define un área de cuadrícula flexible que consta de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="a9712-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="a9712-208"><xref:System.Windows.Controls.StackPanel>- Organiza los elementos secundarios en una sola línea que se puede orientar horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="a9712-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="a9712-209"><xref:System.Windows.Controls.VirtualizingStackPanel>- Organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="a9712-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="a9712-210"><xref:System.Windows.Controls.WrapPanel>- Coloca los elementos secundarios en posición secuencial de izquierda a derecha, rompiendo el contenido a la siguiente línea en el borde del cuadro contenedor.</span><span class="sxs-lookup"><span data-stu-id="a9712-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="a9712-211">El orden posterior se realiza secuencialmente de arriba a abajo o de derecha a izquierda, dependiendo del valor de la Propiedad Orientation.</span><span class="sxs-lookup"><span data-stu-id="a9712-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="a9712-212">Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="a9712-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="a9712-213">`ExpenseIt`las páginas se pueden cambiar de tamaño y cada página tiene elementos que se organizan horizontal y verticalmente junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="a9712-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="a9712-214">En este ejemplo, se <xref:System.Windows.Controls.Grid> utiliza como elemento de diseño para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="a9712-215">Para obtener <xref:System.Windows.Controls.Panel> más información acerca de los elementos, consulte [Introducción a los paneles](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9712-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="a9712-216">Para obtener más información sobre el diseño, consulte [Diseño](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="a9712-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="a9712-217">En esta sección, creará una tabla de una sola columna con tres filas y un <xref:System.Windows.Controls.Grid> *`ExpenseItHome.xaml`* margen de 10 píxeles agregando definiciones de columna y fila al archivo in .</span><span class="sxs-lookup"><span data-stu-id="a9712-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="a9712-218">En *`ExpenseItHome.xaml`*, <xref:System.Windows.FrameworkElement.Margin%2A> establezca la <xref:System.Windows.Controls.Grid> propiedad del elemento en "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:</span><span class="sxs-lookup"><span data-stu-id="a9712-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="a9712-219">También puede establecer los valores **de Margen** en la ventana **Propiedades,** en la categoría **Diseño:**</span><span class="sxs-lookup"><span data-stu-id="a9712-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valores de margen en la ventana Propiedades](./media/properties-margin.png)

2. <span data-ttu-id="a9712-221">Agregue el siguiente <xref:System.Windows.Controls.Grid> XAML entre las etiquetas para crear las definiciones de fila y columna:</span><span class="sxs-lookup"><span data-stu-id="a9712-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="a9712-222">El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas <xref:System.Windows.GridLength.Auto%2A>se establece en , lo que significa que el tamaño de las filas se basa en el contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="a9712-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="a9712-223">El <xref:System.Windows.Controls.RowDefinition.Height%2A> valor <xref:System.Windows.GridUnitType.Star> predeterminado es el tamaño, lo que significa que la altura de la fila es una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="a9712-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="a9712-224">Por ejemplo, si dos <xref:System.Windows.Controls.RowDefinition.Height%2A> filas tienen cada una de "\*", cada una tiene una altura que es la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="a9712-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="a9712-225">Ahora <xref:System.Windows.Controls.Grid> debe contener el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="a9712-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="a9712-226">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="a9712-226">Add controls</span></span>

<span data-ttu-id="a9712-227">En esta sección, actualizará la interfaz de usuario de la página principal para mostrar una lista de personas, donde selecciona una persona para mostrar su informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="a9712-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="a9712-228">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="a9712-229">Para obtener más información, consulte [Controles](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="a9712-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="a9712-230">Para crear esta interfaz de usuario, *`ExpenseItHome.xaml`* agregará los siguientes elementos a:</span><span class="sxs-lookup"><span data-stu-id="a9712-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="a9712-231">A <xref:System.Windows.Controls.ListBox> (para la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="a9712-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="a9712-232">A <xref:System.Windows.Controls.Label> (para el encabezado de lista).</span><span class="sxs-lookup"><span data-stu-id="a9712-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="a9712-233">A <xref:System.Windows.Controls.Button> (para hacer clic para ver el informe de gastos de la persona seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="a9712-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="a9712-234">Cada control se coloca en <xref:System.Windows.Controls.Grid> una <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> fila de la estableciendo la propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="a9712-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="a9712-235">Para obtener más información acerca de las propiedades adjuntas, vea [Información general sobre propiedades adjuntas](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a9712-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="a9712-236">En *`ExpenseItHome.xaml`*, agregue el siguiente <xref:System.Windows.Controls.Grid> XAML en algún lugar entre las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="a9712-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="a9712-237">También puede crear los controles arrastrándolos desde la ventana Cuadro de **herramientas** a la ventana de diseño y, a continuación, estableciendo sus propiedades en la ventana **Propiedades.**</span><span class="sxs-lookup"><span data-stu-id="a9712-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="a9712-238">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-238">Build and run the application.</span></span>

    <span data-ttu-id="a9712-239">En la ilustración siguiente se muestran los controles que ha creado:</span><span class="sxs-lookup"><span data-stu-id="a9712-239">The following illustration shows the controls you created:</span></span>

![Captura de pantalla de ejemplo de ExpenseIt que muestra una lista de nombres](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="a9712-241">Añadir una imagen y un título</span><span class="sxs-lookup"><span data-stu-id="a9712-241">Add an image and a title</span></span>

<span data-ttu-id="a9712-242">En esta sección, actualizará la interfaz de usuario de la página principal con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="a9712-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="a9712-243">En *`ExpenseItHome.xaml`*, agregue otra <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> columna <xref:System.Windows.Controls.ColumnDefinition.Width%2A> a la con un fijo de 230 píxeles:</span><span class="sxs-lookup"><span data-stu-id="a9712-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="a9712-244">Agregue otra fila <xref:System.Windows.Controls.Grid.RowDefinitions%2A>a la , para un total de cuatro filas:</span><span class="sxs-lookup"><span data-stu-id="a9712-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="a9712-245">Mueva los controles a la <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> segunda columna estableciendo la propiedad en 1 en cada uno de los tres controles (Border, ListBox y Button).</span><span class="sxs-lookup"><span data-stu-id="a9712-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="a9712-246">Mueva cada control hacia abajo <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> una fila incrementando su valor en 1 para cada uno de los tres controles (Border, ListBox y Button) y para el Border elemento.</span><span class="sxs-lookup"><span data-stu-id="a9712-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="a9712-247">El XAML para los tres controles ahora tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="a9712-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="a9712-248">Establezca <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> la propiedad en el archivo de imagen *watermark.png,* agregando el siguiente XAML en cualquier lugar entre las `<Grid>` etiquetas y: `</Grid>`</span><span class="sxs-lookup"><span data-stu-id="a9712-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="a9712-249">Antes <xref:System.Windows.Controls.Border> del elemento, <xref:System.Windows.Controls.Label> agregue a con el contenido "Ver informe de gastos".</span><span class="sxs-lookup"><span data-stu-id="a9712-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="a9712-250">Esta etiqueta es el título de la página.</span><span class="sxs-lookup"><span data-stu-id="a9712-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="a9712-251">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-251">Build and run the application.</span></span>

<span data-ttu-id="a9712-252">La siguiente ilustración muestra los resultados de lo que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="a9712-252">The following illustration shows the results of what you just added:</span></span>

![Captura de pantalla de ejemplo de ExpenseIt que muestra el nuevo fondo de la imagen y el título de la página](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="a9712-254">Agregar código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="a9712-254">Add code to handle events</span></span>

1. <span data-ttu-id="a9712-255">En *`ExpenseItHome.xaml`*, <xref:System.Windows.Controls.Primitives.ButtonBase.Click> agregue un <xref:System.Windows.Controls.Button> controlador de eventos al elemento.</span><span class="sxs-lookup"><span data-stu-id="a9712-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="a9712-256">Para obtener más información, vea [Cómo: crear un controlador](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100))de eventos simple .</span><span class="sxs-lookup"><span data-stu-id="a9712-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="a9712-257">Abrir *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .</span><span class="sxs-lookup"><span data-stu-id="a9712-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="a9712-258">Agregue el código `ExpenseItHome` siguiente a la clase para agregar un controlador de eventos de clic de botón.</span><span class="sxs-lookup"><span data-stu-id="a9712-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="a9712-259">El controlador de eventos abre el **ExpenseReportPage** página.</span><span class="sxs-lookup"><span data-stu-id="a9712-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="a9712-260">Cree la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="a9712-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="a9712-261">*ExpenseReportPage.xaml* muestra el informe de gastos de **`ExpenseItHome`** la persona seleccionada en la página.</span><span class="sxs-lookup"><span data-stu-id="a9712-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="a9712-262">En esta sección, creará la interfaz de usuario para **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="a9712-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="a9712-263">También agregará colores de fondo y relleno a los distintos elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9712-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="a9712-264">Abra *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="a9712-265">Agregue el siguiente <xref:System.Windows.Controls.Grid> XAML entre las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="a9712-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="a9712-266">Esta interfaz *`ExpenseItHome.xaml`* de usuario es similar a <xref:System.Windows.Controls.DataGrid>, excepto que los datos del informe se muestran en un archivo .</span><span class="sxs-lookup"><span data-stu-id="a9712-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="a9712-267">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-267">Build and run the application.</span></span>

4. <span data-ttu-id="a9712-268">Seleccione el botón **Ver.**</span><span class="sxs-lookup"><span data-stu-id="a9712-268">Select the **View** button.</span></span>

    <span data-ttu-id="a9712-269">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="a9712-269">The expense report page appears.</span></span> <span data-ttu-id="a9712-270">Observe también que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a9712-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="a9712-271">En la ilustración siguiente se muestran los elementos de interfaz de usuario agregados a *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![ExpenseIt captura de pantalla de ejemplo que muestra la interfaz de usuario que acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="a9712-273">Controles de estilo</span><span class="sxs-lookup"><span data-stu-id="a9712-273">Style controls</span></span>

<span data-ttu-id="a9712-274">La apariencia de varios elementos suele ser la misma para todos los elementos del mismo tipo en una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a9712-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="a9712-275">La interfaz de usuario usa [estilos](../controls/styling-and-templating.md) para que las apariencias sean reutilizables en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="a9712-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="a9712-276">La reutilización de estilos ayuda a simplificar la creación y administración de XAML.</span><span class="sxs-lookup"><span data-stu-id="a9712-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="a9712-277">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="a9712-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="a9712-278">Abra *Application.xaml* o *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="a9712-279">Agregue el siguiente <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> XAML entre las etiquetas:</span><span class="sxs-lookup"><span data-stu-id="a9712-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="a9712-280">Este código XAML agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9712-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="a9712-281">`headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="a9712-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="a9712-282">`labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="a9712-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="a9712-283">`columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="a9712-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="a9712-284">`listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="a9712-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="a9712-285">`listHeaderTextStyle`: Para formatear <xref:System.Windows.Controls.Label>el encabezado de lista .</span><span class="sxs-lookup"><span data-stu-id="a9712-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="a9712-286">`buttonStyle`: Para <xref:System.Windows.Controls.Button> formatear `ExpenseItHome.xaml`el archivo .</span><span class="sxs-lookup"><span data-stu-id="a9712-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="a9712-287">Observe que los estilos son <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> recursos y elementos secundarios del elemento de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a9712-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="a9712-288">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="a9712-289">Para obtener un ejemplo del uso de recursos en una aplicación .NET, vea [Usar](../advanced/how-to-use-application-resources.md)recursos de aplicación .</span><span class="sxs-lookup"><span data-stu-id="a9712-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="a9712-290">En *`ExpenseItHome.xaml`*, reemplace <xref:System.Windows.Controls.Grid> todo entre los elementos con el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="a9712-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="a9712-291">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="a9712-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="a9712-292">Por ejemplo, `headerTextStyle` se aplica al "Ver <xref:System.Windows.Controls.Label>informe de gastos".</span><span class="sxs-lookup"><span data-stu-id="a9712-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="a9712-293">Abra *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="a9712-294">Reemplace todo <xref:System.Windows.Controls.Grid> entre los elementos con el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="a9712-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="a9712-295">Este XAML agrega estilos a los <xref:System.Windows.Controls.Label> elementos y. <xref:System.Windows.Controls.Border></span><span class="sxs-lookup"><span data-stu-id="a9712-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="a9712-296">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-296">Build and run the application.</span></span> <span data-ttu-id="a9712-297">La apariencia de la ventana es la misma que anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a9712-297">The window appearance is the same as previously.</span></span>

    ![Captura de pantalla de ejemplo ExpenseIt con la misma apariencia que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="a9712-299">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a9712-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="a9712-300">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="a9712-300">Bind data to a control</span></span>

<span data-ttu-id="a9712-301">En esta sección, creará los datos XML que están enlazados a varios controles.</span><span class="sxs-lookup"><span data-stu-id="a9712-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="a9712-302">En *`ExpenseItHome.xaml`*, después del elemento de apertura, <xref:System.Windows.Controls.Grid> agregue el siguiente XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona:</span><span class="sxs-lookup"><span data-stu-id="a9712-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="a9712-303">Los datos se <xref:System.Windows.Controls.Grid> crean como un recurso.</span><span class="sxs-lookup"><span data-stu-id="a9712-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="a9712-304">Normalmente, estos datos se cargan como un archivo, pero para simplificar los datos se agregan en línea.</span><span class="sxs-lookup"><span data-stu-id="a9712-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="a9712-305">Dentro `<Grid.Resources>` del elemento, `<xref:System.Windows.DataTemplate>` agregue el siguiente elemento, que <xref:System.Windows.Controls.ListBox>define cómo `<XmlDataProvider>` mostrar los datos en el , después del elemento:</span><span class="sxs-lookup"><span data-stu-id="a9712-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="a9712-306">Para obtener más información acerca de las plantillas de datos, consulte [Introducción](../data/data-templating-overview.md)a la creación de plantillas de datos .</span><span class="sxs-lookup"><span data-stu-id="a9712-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="a9712-307">Reemplace el <xref:System.Windows.Controls.ListBox> existente con el siguiente XAML:</span><span class="sxs-lookup"><span data-stu-id="a9712-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="a9712-308">Este XAML enlaza <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> la <xref:System.Windows.Controls.ListBox> propiedad del origen de datos y <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>aplica la plantilla de datos como el archivo .</span><span class="sxs-lookup"><span data-stu-id="a9712-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="a9712-309">Conectar datos a controles</span><span class="sxs-lookup"><span data-stu-id="a9712-309">Connect data to controls</span></span>

<span data-ttu-id="a9712-310">A continuación, agregará código para recuperar el nombre **`ExpenseItHome`** seleccionado en la página y pasarlo al constructor de **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="a9712-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="a9712-311">**ExpenseReportPage** establece su contexto de datos con el elemento pasado, que es a lo que se enlazan los controles definidos en *ExpenseReportPage.xaml.*</span><span class="sxs-lookup"><span data-stu-id="a9712-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="a9712-312">Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="a9712-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="a9712-313">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a9712-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="a9712-314">Abrir *`ExpenseItHome.xaml.vb`* *`ExpenseItHome.xaml.cs`* o .</span><span class="sxs-lookup"><span data-stu-id="a9712-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="a9712-315">Cambie <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el controlador de eventos para llamar al nuevo constructor pasando los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a9712-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="a9712-316">Estilo de datos con plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="a9712-316">Style data with data templates</span></span>

<span data-ttu-id="a9712-317">En esta sección, actualizará la interfaz de usuario para cada elemento de las listas enlazadas a datos mediante plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="a9712-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="a9712-318">Abra *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="a9712-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="a9712-319">Enlazar el contenido de los elementos <xref:System.Windows.Controls.Label> "Name" y "Department" a la propiedad de origen de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="a9712-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="a9712-320">Para obtener más información sobre el enlace de datos, vea [Introducción al enlace](../../../desktop-wpf/data/data-binding-overview.md)de datos .</span><span class="sxs-lookup"><span data-stu-id="a9712-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="a9712-321">Después <xref:System.Windows.Controls.Grid> del elemento de apertura, agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos:</span><span class="sxs-lookup"><span data-stu-id="a9712-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="a9712-322">Reemplace <xref:System.Windows.Controls.DataGridTextColumn> los <xref:System.Windows.Controls.DataGridTemplateColumn> elementos <xref:System.Windows.Controls.DataGrid> por debajo del elemento y aplíqueles las plantillas.</span><span class="sxs-lookup"><span data-stu-id="a9712-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="a9712-323">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9712-323">Build and run the application.</span></span>

6. <span data-ttu-id="a9712-324">Seleccione una persona y, a continuación, seleccione el botón **Ver.**</span><span class="sxs-lookup"><span data-stu-id="a9712-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="a9712-325">En la ilustración siguiente `ExpenseIt` se muestran ambas páginas de la aplicación con controles, diseño, estilos, enlace de datos y plantillas de datos aplicadas:</span><span class="sxs-lookup"><span data-stu-id="a9712-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Ambas páginas de la aplicación que muestran la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="a9712-327">En este ejemplo se muestra una característica específica de WPFWPF y no se siguen todas las prácticas recomendadas para aspectos como la seguridad, la localización y la accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="a9712-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="a9712-328">Para obtener una cobertura completa de WPFWPF y las prácticas recomendadas de desarrollo de aplicaciones .NET, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9712-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="a9712-329">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="a9712-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="a9712-330">Seguridad</span><span class="sxs-lookup"><span data-stu-id="a9712-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="a9712-331">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="a9712-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="a9712-332">Rendimiento de WPF</span><span class="sxs-lookup"><span data-stu-id="a9712-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="a9712-333">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a9712-333">Next steps</span></span>

<span data-ttu-id="a9712-334">En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="a9712-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="a9712-335">Ahora debe tener una comprensión básica de los bloques de creación de una aplicación .NET enlazada a datos.</span><span class="sxs-lookup"><span data-stu-id="a9712-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="a9712-336">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9712-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="a9712-337">Arquitectura WPF</span><span class="sxs-lookup"><span data-stu-id="a9712-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="a9712-338">Información general de XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="a9712-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="a9712-339">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="a9712-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="a9712-340">Diseño</span><span class="sxs-lookup"><span data-stu-id="a9712-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="a9712-341">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a9712-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="a9712-342">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="a9712-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="a9712-343">Controles</span><span class="sxs-lookup"><span data-stu-id="a9712-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="a9712-344">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="a9712-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="a9712-345">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="a9712-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="a9712-346">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="a9712-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="a9712-347">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a9712-347">See also</span></span>

- [<span data-ttu-id="a9712-348">Visión general de los paneles</span><span class="sxs-lookup"><span data-stu-id="a9712-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="a9712-349">Visión general de la plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="a9712-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="a9712-350">Crear una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="a9712-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="a9712-351">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a9712-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
