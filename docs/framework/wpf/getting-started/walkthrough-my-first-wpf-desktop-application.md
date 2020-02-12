---
title: Cree su primera aplicación de WPF en Visual Studio 2019-.NET Framework
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
ms.openlocfilehash: bc47405636c4727f502caf1f6e27050367eda74a
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124343"
---
# <a name="tutorial-create-your-first-wpf-application-in-visual-studio-2019"></a><span data-ttu-id="ec5ea-102">Tutorial: crear su primera aplicación de WPF en Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="ec5ea-102">Tutorial: Create your first WPF application in Visual Studio 2019</span></span>

<span data-ttu-id="ec5ea-103">En este artículo se muestra cómo desarrollar una aplicación de escritorio Windows Presentation Foundation (WPF) que incluya los elementos que son comunes a la mayoría de las aplicaciones de WPF: marcado de lenguaje XAML (XAML), código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="ec5ea-104">Para desarrollar la aplicación, usará Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="ec5ea-105">En este tutorial, aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-105">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ec5ea-106">Cree un proyecto de WPF.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-106">Create a WPF project.</span></span>
> - <span data-ttu-id="ec5ea-107">Use XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-107">Use XAML to design the appearance of the application's user interface (UI).</span></span>
> - <span data-ttu-id="ec5ea-108">Escriba código para compilar el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-108">Write code to build the application's behavior.</span></span>
> - <span data-ttu-id="ec5ea-109">Cree una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-109">Create an application definition to manage the application.</span></span>
> - <span data-ttu-id="ec5ea-110">Agregue controles y cree el diseño para crear la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-110">Add controls and create the layout to compose the application UI.</span></span>
> - <span data-ttu-id="ec5ea-111">Cree estilos para un aspecto coherente en la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-111">Create styles for a consistent appearance throughout the application's UI.</span></span>
> - <span data-ttu-id="ec5ea-112">Enlace la interfaz de usuario a los datos, para rellenar la interfaz de usuario a partir de los datos y para mantener sincronizados los datos y la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-112">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="ec5ea-113">Al final del tutorial, habrá creado una aplicación de Windows independiente que permite a los usuarios ver informes de gastos para personas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-113">By the end of the tutorial, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="ec5ea-114">La aplicación se compone de varias páginas de WPF que se hospedan en una ventana de estilo de explorador.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-114">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="ec5ea-115">El código de ejemplo que se usa en este tutorial está disponible para Visual Basic y C# en el tutorial del código de ejemplo de la [aplicación WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-115">The sample code that is used in this tutorial is available for both Visual Basic and C# at [Tutorial WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="ec5ea-116">Puede alternar el lenguaje de código del código de ejemplo entre C# y Visual Basic mediante el selector de idioma situado en la parte superior de esta página.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-116">You can toggle the code language of the sample code between C# and Visual Basic by using the language selector on top of this page.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ec5ea-117">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="ec5ea-117">Prerequisites</span></span>

- <span data-ttu-id="ec5ea-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo de **desarrollo de escritorio de .net** instalada.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-118">[Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET desktop development** workload installed.</span></span>

   <span data-ttu-id="ec5ea-119">Para obtener más información sobre cómo instalar la versión más reciente de Visual Studio, vea [instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-119">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="ec5ea-120">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="ec5ea-120">Create the application project</span></span>

<span data-ttu-id="ec5ea-121">El primer paso es crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-121">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="ec5ea-122">Cree un nuevo proyecto de aplicación de WPF en Visual Basic C# o Visual denominado **`ExpenseIt`** :</span><span class="sxs-lookup"><span data-stu-id="ec5ea-122">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="ec5ea-123">Abra Visual Studio y seleccione **crear un nuevo proyecto** **en el menú introducción.**</span><span class="sxs-lookup"><span data-stu-id="ec5ea-123">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="ec5ea-124">Se abre el cuadro de diálogo **crear nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-124">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="ec5ea-125">En la lista desplegable **idioma** , **C#** seleccione o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-125">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="ec5ea-126">Seleccione la plantilla **aplicación WPF (.NET Framework)** y, después, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-126">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Cuadro de diálogo Crear un proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="ec5ea-128">Se abre el cuadro de diálogo **configurar el nuevo proyecto** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-128">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="ec5ea-129">Escriba el nombre del proyecto **`ExpenseIt`** y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-129">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Cuadro de diálogo Configurar un nuevo proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="ec5ea-131">Visual Studio crea el proyecto y abre el diseñador de la ventana de la aplicación predeterminada denominada **MainWindow. Xaml**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-131">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="ec5ea-132">Abra *Application. Xaml* (Visual Basic) o *app. Xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-132">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="ec5ea-133">Este archivo XAML define una aplicación WPF y los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-133">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="ec5ea-134">También se usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow. Xaml*, que se muestra automáticamente cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-134">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="ec5ea-135">El código XAML debe tener un aspecto similar al siguiente en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-135">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="ec5ea-136">Y similar al siguiente en C#:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-136">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="ec5ea-137">Abra *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-137">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="ec5ea-138">Este archivo XAML es la ventana principal de la aplicación y muestra el contenido creado en las páginas.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-138">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="ec5ea-139">La clase <xref:System.Windows.Window> define las propiedades de una ventana, como su título, tamaño o icono, y controla los eventos, como el cierre o la ocultación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-139">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="ec5ea-140">Cambie el elemento <xref:System.Windows.Window> a una <xref:System.Windows.Navigation.NavigationWindow>, como se muestra en el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-140">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="ec5ea-141">Esta aplicación navega a contenido diferente en función de los datos proporcionados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-141">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="ec5ea-142">Este es el motivo por el que es necesario cambiar el <xref:System.Windows.Window> principal a un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-142">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="ec5ea-143"><xref:System.Windows.Navigation.NavigationWindow> hereda todas las propiedades de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-143"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="ec5ea-144">El elemento <xref:System.Windows.Navigation.NavigationWindow> del archivo XAML crea una instancia de la clase <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-144">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="ec5ea-145">Para obtener más información, vea [información general sobre navegación](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-145">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="ec5ea-146">Quite los elementos de <xref:System.Windows.Controls.Grid> entre las etiquetas de <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-146">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="ec5ea-147">Cambie las siguientes propiedades en el código XAML para el elemento <xref:System.Windows.Navigation.NavigationWindow>:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-147">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="ec5ea-148">Establezca la propiedad <xref:System.Windows.Window.Title%2A> en "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-148">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="ec5ea-149">Establezca la propiedad <xref:System.Windows.FrameworkElement.Height%2A> en 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-149">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="ec5ea-150">Establezca la propiedad <xref:System.Windows.FrameworkElement.Width%2A> en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-150">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="ec5ea-151">El código XAML debe tener un aspecto similar al siguiente para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-151">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="ec5ea-152">Y similar al siguiente para C#:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-152">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="ec5ea-153">Abra *MainWindow. Xaml. VB* o *MainWindow.Xaml.CS*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-153">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="ec5ea-154">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-154">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="ec5ea-155">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-155">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="ec5ea-156">Si está utilizando C#, cambie la clase `MainWindow` para que se derive de <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-156">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="ec5ea-157">(En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML). El C# código debería tener ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-157">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="ec5ea-158">Agregar archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec5ea-158">Add files to the application</span></span>

<span data-ttu-id="ec5ea-159">En esta sección, agregará dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-159">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="ec5ea-160">Agregue una nueva página al proyecto y asígnele el nombre *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="ec5ea-160">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="ec5ea-161">En **Explorador de soluciones**, haga clic con el botón derecho en el nodo del proyecto de **`ExpenseIt`** y elija **Agregar** > **Página**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-161">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="ec5ea-162">En el cuadro de diálogo **Agregar nuevo elemento** , la plantilla **página (WPF)** ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-162">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="ec5ea-163">Escriba el nombre **`ExpenseItHome`** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-163">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="ec5ea-164">Esta página es la primera página que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-164">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="ec5ea-165">Se mostrará una lista de personas de las que seleccionar, para mostrar un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-165">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="ec5ea-166">Abra *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-166">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="ec5ea-167">Establezca el <xref:System.Windows.Controls.Page.Title%2A> en "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-167">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="ec5ea-168">Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-168">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span>

    <span data-ttu-id="ec5ea-169">El XAML aparece ahora como se indica a continuación para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-169">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="ec5ea-170">Y similar al siguiente para C#:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-170">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="ec5ea-171">Abra *MainWindow. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-171">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="ec5ea-172">Agregue una propiedad <xref:System.Windows.Navigation.NavigationWindow.Source%2A> al elemento <xref:System.Windows.Navigation.NavigationWindow> y establézcala en "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-172">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="ec5ea-173">Esto establece *`ExpenseItHome.xaml`* como la primera página que se abre cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-173">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="ec5ea-174">XAML de ejemplo en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-174">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="ec5ea-175">Y en C#:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-175">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="ec5ea-176">También puede establecer la propiedad **origen** en la categoría **varios** de la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-176">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Propiedad de origen en ventana Propiedades](./media/properties-source.png)

1. <span data-ttu-id="ec5ea-178">Agregue otra página de WPF nueva al proyecto y asígnele el nombre *ExpenseReportPage. Xaml*::</span><span class="sxs-lookup"><span data-stu-id="ec5ea-178">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="ec5ea-179">En **Explorador de soluciones**, haga clic con el botón derecho en el nodo del proyecto de **`ExpenseIt`** y elija **Agregar** > **Página**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-179">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="ec5ea-180">En el cuadro de diálogo **Agregar nuevo elemento** , seleccione la plantilla **página (WPF)** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-180">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="ec5ea-181">Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-181">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="ec5ea-182">Esta página mostrará el informe de gastos de la persona que está seleccionada en la página **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-182">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="ec5ea-183">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-183">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="ec5ea-184">Establezca el <xref:System.Windows.Controls.Page.Title%2A> en "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-184">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="ec5ea-185">Establezca el `DesignHeight` en 350 píxeles y el `DesignWidth` en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-185">Set the `DesignHeight` to 350 pixels and the `DesignWidth` to 500 pixels.</span></span> 

    <span data-ttu-id="ec5ea-186">*ExpenseReportPage. Xaml* tiene ahora el siguiente aspecto en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-186">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="ec5ea-187">Y similar al siguiente en C#:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-187">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="ec5ea-188">Abra *ExpenseItHome. Xaml. VB* y *ExpenseReportPage. Xaml. VB*o *ExpenseItHome.Xaml.CS* y *ExpenseReportPage.Xaml.CS*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-188">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="ec5ea-189">Cuando se crea un nuevo archivo de paginación, Visual Studio crea automáticamente el archivo *de código subyacente* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-189">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="ec5ea-190">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-190">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="ec5ea-191">El código debe tener un aspecto similar al siguiente para **`ExpenseItHome`** :</span><span class="sxs-lookup"><span data-stu-id="ec5ea-191">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="ec5ea-192">Y similar a lo siguiente para **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-192">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="ec5ea-193">Agregue una imagen denominada *marca de agua. png* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-193">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="ec5ea-194">Puede crear su propia imagen, copiar el archivo del código de ejemplo u obtenerlo del repositorio de github [Microsoft/WPF-samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-194">You can create your own image, copy the file from the sample code, or get it from the [microsoft/WPF-Samples](https://raw.githubusercontent.com/microsoft/WPF-Samples/master/Getting%20Started/WalkthroughFirstWPFApp/csharp/watermark.png) GitHub repository.</span></span>

    1. <span data-ttu-id="ec5ea-195">Haga clic con el botón secundario en el nodo del proyecto y seleccione **agregar** > **elemento existente**o presione **MAYÚS**+**Alt**+**A**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-195">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="ec5ea-196">En el cuadro de diálogo **Agregar elemento existente** , establezca el filtro de archivos en **todos los archivos** o **archivos de imagen**, busque el archivo de imagen que desea usar y, después, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-196">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="ec5ea-197">Compilación y ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="ec5ea-197">Build and run the application</span></span>

1. <span data-ttu-id="ec5ea-198">Para compilar y ejecutar la aplicación, presione **F5** o seleccione **iniciar depuración** en el menú **depurar** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-198">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="ec5ea-199">En la ilustración siguiente se muestra la aplicación con los botones <xref:System.Windows.Navigation.NavigationWindow>:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-199">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Aplicación después de compilarla y ejecutarla.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="ec5ea-201">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-201">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="ec5ea-202">Crear el diseño</span><span class="sxs-lookup"><span data-stu-id="ec5ea-202">Create the layout</span></span>

<span data-ttu-id="ec5ea-203">El diseño proporciona una manera ordenada de colocar los elementos de la interfaz de usuario y también administra el tamaño y la posición de dichos elementos cuando se cambia el tamaño de una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-203">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="ec5ea-204">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-204">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="ec5ea-205"><xref:System.Windows.Controls.Canvas>: define un área en la que se pueden colocar explícitamente los elementos secundarios usando coordenadas relativas al área del lienzo.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-205"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="ec5ea-206"><xref:System.Windows.Controls.DockPanel>: define un área en la que puede organizar los elementos secundarios de forma horizontal o vertical, en relación unos con otros.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-206"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="ec5ea-207"><xref:System.Windows.Controls.Grid>: define un área de cuadrícula flexible que consta de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-207"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="ec5ea-208"><xref:System.Windows.Controls.StackPanel>: organiza los elementos secundarios en una sola línea que se puede orientar horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-208"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="ec5ea-209"><xref:System.Windows.Controls.VirtualizingStackPanel>: organiza y virtualiza el contenido en una sola línea orientada horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-209"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="ec5ea-210"><xref:System.Windows.Controls.WrapPanel>: coloca los elementos secundarios en una posición secuencial de izquierda a derecha, dividiendo el contenido en la línea siguiente en el borde del cuadro contenedor.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-210"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="ec5ea-211">La ordenación subsiguiente se realiza secuencialmente de arriba abajo o de derecha a izquierda, en función del valor de la propiedad Orientation.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-211">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="ec5ea-212">Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-212">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="ec5ea-213">se puede cambiar el tamaño de las páginas `ExpenseIt`, y cada página tiene elementos que se organizan horizontal y verticalmente junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-213">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="ec5ea-214">En este ejemplo, el <xref:System.Windows.Controls.Grid> se utiliza como elemento de diseño para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-214">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="ec5ea-215">Para obtener más información sobre los elementos de <xref:System.Windows.Controls.Panel>, consulte [información general](../controls/panels-overview.md)de los paneles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-215">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="ec5ea-216">Para obtener más información sobre el diseño, vea [diseño](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-216">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="ec5ea-217">En esta sección, creará una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila al <xref:System.Windows.Controls.Grid> en *`ExpenseItHome.xaml`* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-217">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="ec5ea-218">En *`ExpenseItHome.xaml`* , establezca la propiedad <xref:System.Windows.FrameworkElement.Margin%2A> del elemento <xref:System.Windows.Controls.Grid> en "10, 0, 10, 10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-218">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="ec5ea-219">También puede establecer los valores de **margen** en la ventana **propiedades** , en la categoría **diseño** :</span><span class="sxs-lookup"><span data-stu-id="ec5ea-219">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valores de margen en ventana Propiedades](./media/properties-margin.png)

2. <span data-ttu-id="ec5ea-221">Agregue el código XAML siguiente entre las etiquetas de <xref:System.Windows.Controls.Grid> para crear las definiciones de fila y de columna:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-221">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="ec5ea-222">La <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A>, lo que significa que el tamaño de las filas se basa en el contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-222">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="ec5ea-223">El <xref:System.Windows.Controls.RowDefinition.Height%2A> predeterminado es <xref:System.Windows.GridUnitType.Star> el ajuste de tamaño, lo que significa que el alto de fila es una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-223">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="ec5ea-224">Por ejemplo, si dos filas tienen un <xref:System.Windows.Controls.RowDefinition.Height%2A> de "\*", cada una tiene un alto que es la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-224">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="ec5ea-225">El <xref:System.Windows.Controls.Grid> debe contener ahora el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-225">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="ec5ea-226">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="ec5ea-226">Add controls</span></span>

<span data-ttu-id="ec5ea-227">En esta sección, actualizará la interfaz de usuario de la Página principal para mostrar una lista de personas, donde puede seleccionar una persona para mostrar el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-227">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="ec5ea-228">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-228">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="ec5ea-229">Para obtener más información, consulte [Controles](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-229">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="ec5ea-230">Para crear esta interfaz de usuario, agregará los siguientes elementos a *`ExpenseItHome.xaml`* :</span><span class="sxs-lookup"><span data-stu-id="ec5ea-230">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="ec5ea-231"><xref:System.Windows.Controls.ListBox> (para la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-231">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="ec5ea-232"><xref:System.Windows.Controls.Label> (para el encabezado de la lista).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-232">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="ec5ea-233">Un <xref:System.Windows.Controls.Button> (para ver el informe de gastos de la persona que está seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-233">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="ec5ea-234">Cada control se coloca en una fila del <xref:System.Windows.Controls.Grid> estableciendo la propiedad adjunta <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-234">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="ec5ea-235">Para obtener más información sobre las propiedades adjuntas, vea [información general sobre las propiedades adjuntas](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-235">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="ec5ea-236">En *`ExpenseItHome.xaml`* , agregue el código XAML siguiente en algún lugar entre las etiquetas de <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-236">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="ec5ea-237">También puede crear los controles arrastrándolos desde la ventana cuadro de **herramientas** hasta la ventana de diseño y, a continuación, estableciendo sus propiedades en la ventana **propiedades** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-237">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="ec5ea-238">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-238">Build and run the application.</span></span>

    <span data-ttu-id="ec5ea-239">En la ilustración siguiente se muestran los controles que ha creado:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-239">The following illustration shows the controls you created:</span></span>

![Captura de pantalla de ejemplo ExpenseIt en la que se muestra una lista de nombres](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="ec5ea-241">Agregar una imagen y un título</span><span class="sxs-lookup"><span data-stu-id="ec5ea-241">Add an image and a title</span></span>

<span data-ttu-id="ec5ea-242">En esta sección, actualizará la interfaz de usuario de la Página principal con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-242">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="ec5ea-243">En *`ExpenseItHome.xaml`* , agregue otra columna al <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un <xref:System.Windows.Controls.ColumnDefinition.Width%2A> fijo de 230 píxeles:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-243">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="ec5ea-244">Agregue otra fila al <xref:System.Windows.Controls.Grid.RowDefinitions%2A>para un total de cuatro filas:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-244">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="ec5ea-245">Mueva los controles a la segunda columna estableciendo la propiedad <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> en 1 en cada uno de los tres controles (borde, cuadro de lista y botón).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-245">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="ec5ea-246">Baje cada control una fila incrementando su <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valor en 1 para cada uno de los tres controles (borde, cuadro de lista y botón) y para el elemento Border.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-246">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="ec5ea-247">El código XAML de los tres controles tiene ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-247">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="ec5ea-248">Establezca la propiedad <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> en el archivo de imagen de *marca de agua. png* agregando el siguiente código XAML en cualquier lugar entre las etiquetas `<Grid>` y `</Grid>`:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-248">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="ec5ea-249">Antes del elemento <xref:System.Windows.Controls.Border>, agregue un <xref:System.Windows.Controls.Label> con el contenido "ver informe de gastos".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-249">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="ec5ea-250">Esta etiqueta es el título de la página.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-250">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="ec5ea-251">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-251">Build and run the application.</span></span>

<span data-ttu-id="ec5ea-252">En la ilustración siguiente se muestran los resultados de lo que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-252">The following illustration shows the results of what you just added:</span></span>

![Captura de pantalla de ejemplo ExpenseIt que muestra el nuevo fondo de imagen y el título de la página](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="ec5ea-254">Agregar código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="ec5ea-254">Add code to handle events</span></span>

1. <span data-ttu-id="ec5ea-255">En *`ExpenseItHome.xaml`* , agregue un controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> al elemento <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-255">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="ec5ea-256">Para obtener más información, vea [Cómo: crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-256">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="ec5ea-257">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-257">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="ec5ea-258">Agregue el código siguiente a la clase `ExpenseItHome` para agregar un controlador de eventos de clic de botón.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-258">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="ec5ea-259">El controlador de eventos abre la página **ExpenseReportPage** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-259">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="ec5ea-260">Crear la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="ec5ea-260">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="ec5ea-261">*ExpenseReportPage. Xaml* muestra el informe de gastos de la persona que está seleccionada en la página **`ExpenseItHome`** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-261">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="ec5ea-262">En esta sección, creará la interfaz de usuario para **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-262">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="ec5ea-263">También agregará colores de fondo y relleno a los distintos elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-263">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="ec5ea-264">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-264">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="ec5ea-265">Agregue el código XAML siguiente entre las etiquetas de <xref:System.Windows.Controls.Grid>:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-265">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="ec5ea-266">Esta interfaz de usuario es similar a *`ExpenseItHome.xaml`* , salvo que los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-266">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="ec5ea-267">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-267">Build and run the application.</span></span>

4. <span data-ttu-id="ec5ea-268">Seleccione el botón **Ver** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-268">Select the **View** button.</span></span>

    <span data-ttu-id="ec5ea-269">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="ec5ea-269">The expense report page appears.</span></span> <span data-ttu-id="ec5ea-270">Observe también que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-270">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="ec5ea-271">En la ilustración siguiente se muestran los elementos de la interfaz de usuario agregados a *ExpenseReportPage. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-271">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Captura de pantalla de ejemplo ExpenseIt que muestra la interfaz de usuario que se acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="ec5ea-273">Controles de estilo</span><span class="sxs-lookup"><span data-stu-id="ec5ea-273">Style controls</span></span>

<span data-ttu-id="ec5ea-274">La apariencia de varios elementos suele ser la misma para todos los elementos del mismo tipo en una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-274">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="ec5ea-275">La interfaz de usuario usa [estilos](../controls/styling-and-templating.md) para que los aspectos se puedan volver a usar en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-275">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="ec5ea-276">La reutilización de los estilos ayuda a simplificar la creación y administración de XAML.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-276">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="ec5ea-277">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-277">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="ec5ea-278">Abra *Application. Xaml* o *app. Xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-278">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="ec5ea-279">Agregue el código XAML siguiente entre las etiquetas de <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-279">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="ec5ea-280">Este código XAML agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-280">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="ec5ea-281">`headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-281">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="ec5ea-282">`labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-282">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="ec5ea-283">`columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-283">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="ec5ea-284">`listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-284">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="ec5ea-285">`listHeaderTextStyle`: para dar formato al encabezado de la lista <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-285">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="ec5ea-286">`buttonStyle`: para dar formato al <xref:System.Windows.Controls.Button> en `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-286">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="ec5ea-287">Observe que los estilos son recursos y secundarios del elemento de propiedad <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-287">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="ec5ea-288">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-288">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="ec5ea-289">Para obtener un ejemplo del uso de recursos en una aplicación .NET, consulte [usar recursos de aplicación](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-289">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="ec5ea-290">En *`ExpenseItHome.xaml`* , reemplace todo lo que haya entre los elementos <xref:System.Windows.Controls.Grid> por el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-290">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="ec5ea-291">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-291">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="ec5ea-292">Por ejemplo, el `headerTextStyle` se aplica al <xref:System.Windows.Controls.Label>"ver informe de gastos".</span><span class="sxs-lookup"><span data-stu-id="ec5ea-292">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="ec5ea-293">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-293">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="ec5ea-294">Reemplace todo lo que haya entre los elementos <xref:System.Windows.Controls.Grid> con el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-294">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="ec5ea-295">Este código XAML agrega estilos a los elementos <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-295">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="ec5ea-296">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-296">Build and run the application.</span></span> <span data-ttu-id="ec5ea-297">La apariencia de la ventana es la misma que antes.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-297">The window appearance is the same as previously.</span></span>

    ![Captura de pantalla de ejemplo ExpenseIt con el mismo aspecto que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="ec5ea-299">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-299">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="ec5ea-300">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="ec5ea-300">Bind data to a control</span></span>

<span data-ttu-id="ec5ea-301">En esta sección, creará los datos XML que se enlazan a varios controles.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-301">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="ec5ea-302">En *`ExpenseItHome.xaml`* , después del elemento de <xref:System.Windows.Controls.Grid> de apertura, agregue el código XAML siguiente para crear un <xref:System.Windows.Data.XmlDataProvider> que contenga los datos de cada persona:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-302">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="ec5ea-303">Los datos se crean como un recurso de <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-303">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="ec5ea-304">Normalmente, estos datos se cargan como un archivo, pero para simplificar, los datos se agregan en línea.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-304">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="ec5ea-305">En el elemento `<Grid.Resources>`, agregue el siguiente elemento `<xref:System.Windows.DataTemplate>`, que define cómo mostrar los datos en el <xref:System.Windows.Controls.ListBox>, después del elemento `<XmlDataProvider>`:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-305">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="ec5ea-306">Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-306">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="ec5ea-307">Reemplace el <xref:System.Windows.Controls.ListBox> existente por el código XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-307">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="ec5ea-308">Este código XAML enlaza la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de la <xref:System.Windows.Controls.ListBox> con el origen de datos y aplica la plantilla de datos como <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-308">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="ec5ea-309">Conectar datos a controles</span><span class="sxs-lookup"><span data-stu-id="ec5ea-309">Connect data to controls</span></span>

<span data-ttu-id="ec5ea-310">A continuación, agregará código para recuperar el nombre seleccionado en la página de **`ExpenseItHome`** y pasarlo al constructor de **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-310">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="ec5ea-311">**ExpenseReportPage** establece su contexto de datos con el elemento pasado, que es de lo que se enlazan los controles definidos en *ExpenseReportPage. Xaml* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-311">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="ec5ea-312">Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-312">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="ec5ea-313">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-313">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="ec5ea-314">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`* .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-314">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="ec5ea-315">Cambie el controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> para llamar al nuevo constructor que pasa los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-315">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="ec5ea-316">Estilo de datos con plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="ec5ea-316">Style data with data templates</span></span>

<span data-ttu-id="ec5ea-317">En esta sección, actualizará la interfaz de usuario para cada elemento de las listas enlazadas a datos mediante plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-317">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="ec5ea-318">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-318">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="ec5ea-319">Enlace el contenido de los elementos "Name" y "Department" <xref:System.Windows.Controls.Label> a la propiedad de origen de datos adecuada.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-319">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="ec5ea-320">Para obtener más información sobre el enlace de datos, vea [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-320">For more information about data binding, see [Data binding overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="ec5ea-321">Después del elemento de <xref:System.Windows.Controls.Grid> de apertura, agregue las siguientes plantillas de datos, que definen cómo mostrar los datos del informe de gastos:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-321">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="ec5ea-322">Reemplace los elementos <xref:System.Windows.Controls.DataGridTextColumn> por <xref:System.Windows.Controls.DataGridTemplateColumn> en el elemento <xref:System.Windows.Controls.DataGrid> y aplíqueles las plantillas.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-322">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="ec5ea-323">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-323">Build and run the application.</span></span>

6. <span data-ttu-id="ec5ea-324">Seleccione una persona y, a continuación, seleccione el botón **Ver** .</span><span class="sxs-lookup"><span data-stu-id="ec5ea-324">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="ec5ea-325">En la ilustración siguiente se muestran las dos páginas de la aplicación `ExpenseIt` con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicados:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-325">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Ambas páginas de la aplicación muestran la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="ec5ea-327">Este ejemplo muestra una característica específica de WPF y no sigue todos los procedimientos recomendados para cosas como seguridad, localización y accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-327">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="ec5ea-328">Para obtener una completa cobertura de WPF y los procedimientos recomendados de desarrollo de aplicaciones .NET, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-328">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="ec5ea-329">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="ec5ea-329">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
> - [<span data-ttu-id="ec5ea-330">Seguridad</span><span class="sxs-lookup"><span data-stu-id="ec5ea-330">Security</span></span>](../security-wpf.md)
> - [<span data-ttu-id="ec5ea-331">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="ec5ea-331">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
> - [<span data-ttu-id="ec5ea-332">Rendimiento de WPF</span><span class="sxs-lookup"><span data-stu-id="ec5ea-332">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="ec5ea-333">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="ec5ea-333">Next steps</span></span>

<span data-ttu-id="ec5ea-334">En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="ec5ea-334">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="ec5ea-335">Ahora debería tener un conocimiento básico de los bloques de creación de una aplicación .NET enlazada a datos.</span><span class="sxs-lookup"><span data-stu-id="ec5ea-335">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="ec5ea-336">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-336">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="ec5ea-337">Arquitectura de WPF</span><span class="sxs-lookup"><span data-stu-id="ec5ea-337">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="ec5ea-338">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="ec5ea-338">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="ec5ea-339">Información general sobre propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="ec5ea-339">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="ec5ea-340">Diseño</span><span class="sxs-lookup"><span data-stu-id="ec5ea-340">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="ec5ea-341">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ec5ea-341">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="ec5ea-342">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="ec5ea-342">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="ec5ea-343">Controles</span><span class="sxs-lookup"><span data-stu-id="ec5ea-343">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="ec5ea-344">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="ec5ea-344">Data binding overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="ec5ea-345">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="ec5ea-345">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="ec5ea-346">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="ec5ea-346">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="ec5ea-347">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ec5ea-347">See also</span></span>

- [<span data-ttu-id="ec5ea-348">Información general sobre paneles</span><span class="sxs-lookup"><span data-stu-id="ec5ea-348">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="ec5ea-349">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="ec5ea-349">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="ec5ea-350">Compilar una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="ec5ea-350">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="ec5ea-351">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="ec5ea-351">Styles and templates</span></span>](../controls/styles-and-templates.md)
