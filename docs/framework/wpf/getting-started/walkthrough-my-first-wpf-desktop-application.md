---
title: Crear una aplicación de WPF en Visual Studio
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
author: mairaw
ms.author: mairaw
ms.custom: vs-dotnet
ms.openlocfilehash: c3440ddf6cdae6b24bcf1059ab2c76d8fb957263
ms.sourcegitcommit: 11deacc8ec9f229ab8ee3cd537515d4c2826515f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2019
ms.locfileid: "66003863"
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="19b8e-102">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="19b8e-102">Walkthrough: My first WPF desktop application</span></span>

<span data-ttu-id="19b8e-103">Este artículo muestra cómo desarrollar una aplicación de escritorio de Windows Presentation Foundation (WPF) que incluye los elementos que son comunes a la mayoría de las aplicaciones de WPF: Extensible Application Markup Language (XAML) marcado, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-103">This article shows you how to develop a Windows Presentation Foundation (WPF) desktop application that includes the elements that are common to most WPF applications: Extensible Application Markup Language (XAML) markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> <span data-ttu-id="19b8e-104">Para desarrollar la aplicación, usará Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="19b8e-104">To develop the application, you'll use Visual Studio.</span></span> 

<span data-ttu-id="19b8e-105">En este tutorial incluye los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="19b8e-105">This walkthrough includes the following steps:</span></span>

- <span data-ttu-id="19b8e-106">Usar XAML para diseñar la apariencia de la interfaz de usuario (UI) de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-106">Use XAML to design the appearance of the application's user interface (UI).</span></span>

- <span data-ttu-id="19b8e-107">Escribir código para construir el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-107">Write code to build the application's behavior.</span></span>

- <span data-ttu-id="19b8e-108">Crear una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-108">Create an application definition to manage the application.</span></span>

- <span data-ttu-id="19b8e-109">Agregar controles y crear el diseño para crear la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-109">Add controls and create the layout to compose the application UI.</span></span>

- <span data-ttu-id="19b8e-110">Crear estilos para una apariencia coherente en toda la interfaz de usuario de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-110">Create styles for a consistent appearance throughout the application's UI.</span></span>

- <span data-ttu-id="19b8e-111">Enlazar la interfaz de usuario a los datos tanto para rellenar la interfaz de usuario de datos para mantener los datos y la interfaz de usuario sincronizada.</span><span class="sxs-lookup"><span data-stu-id="19b8e-111">Bind the UI to data, both to populate the UI from data and to keep the data and UI synchronized.</span></span>

<span data-ttu-id="19b8e-112">Al final del tutorial, habrá creado una aplicación de Windows que permite a los usuarios ver los informes de gastos para personas seleccionadas independiente.</span><span class="sxs-lookup"><span data-stu-id="19b8e-112">By the end of the walkthrough, you'll have built a standalone Windows application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="19b8e-113">La aplicación se compone de varias páginas WPF que se hospedan en una ventana del explorador de estilo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-113">The application is composed of several WPF pages that are hosted in a browser-style window.</span></span>

> [!TIP]
> <span data-ttu-id="19b8e-114">El código de ejemplo que se usa para crear este tutorial está disponible para Visual Basic y C# en [código de ejemplo de aplicación de WPF tutorial](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="19b8e-114">The sample code that is used to build this walkthrough is available for both Visual Basic and C# at [Walkthrough WPF App Sample Code](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>
>
> <span data-ttu-id="19b8e-115">Puede alternar el lenguaje de código del código de ejemplo entre C# y Visual Basic utilizando la **\< />** desplegable en la parte superior derecha de este artículo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-115">You can toggle the code language of the sample code between C# and Visual Basic by using the **\</>** drop-down on the upper right side of this article.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19b8e-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="19b8e-116">Prerequisites</span></span>

- <span data-ttu-id="19b8e-117">Visual Studio 2017 o posterior (en este artículo usa 2019 de Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="19b8e-117">Visual Studio 2017 or later (this article uses Visual Studio 2019)</span></span>

   <span data-ttu-id="19b8e-118">Para obtener más información acerca de cómo instalar la versión más reciente de Visual Studio, consulte [instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="19b8e-118">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>

## <a name="create-the-application-project"></a><span data-ttu-id="19b8e-119">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="19b8e-119">Create the application project</span></span>

<span data-ttu-id="19b8e-120">El primer paso es crear la infraestructura de aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="19b8e-120">The first step is to create the application infrastructure, which includes an application definition, two pages, and an image.</span></span>

1. <span data-ttu-id="19b8e-121">Cree un nuevo proyecto de aplicación de WPF en Visual Basic o Visual C# llamado **`ExpenseIt`**:</span><span class="sxs-lookup"><span data-stu-id="19b8e-121">Create a new WPF Application project in Visual Basic or Visual C# named **`ExpenseIt`**:</span></span>

   1. <span data-ttu-id="19b8e-122">Abra Visual Studio y seleccione **crear un nuevo proyecto** bajo el **comenzar** menú.</span><span class="sxs-lookup"><span data-stu-id="19b8e-122">Open Visual Studio and select **Create a new project** under the **Get started** menu.</span></span>

      <span data-ttu-id="19b8e-123">El **crear un nuevo proyecto** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-123">The **Create a new project** dialog opens.</span></span>

   2. <span data-ttu-id="19b8e-124">En el **lenguaje** lista desplegable, seleccione **C#** o **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-124">In the **Language** dropdown, select either **C#** or **Visual Basic**.</span></span>
      
   3. <span data-ttu-id="19b8e-125">Seleccione el **aplicación de WPF (.NET Framework)** plantilla y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-125">Select the **WPF App (.NET Framework)** template and then select **Next**.</span></span> 
     
      ![Crear un cuadro de diálogo nuevo proyecto](./media/walkthrough-my-first-wpf-desktop-application/create-new-project-dialog.png)
    
      <span data-ttu-id="19b8e-127">El **configurar el nuevo proyecto** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-127">The **Configure your new project** dialog opens.</span></span>

   4. <span data-ttu-id="19b8e-128">Escriba el nombre del proyecto **`ExpenseIt`** y, a continuación, seleccione **crear**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-128">Enter the project name **`ExpenseIt`** and then select **Create**.</span></span>

      ![Configurar un cuadro de diálogo nuevo proyecto](./media/walkthrough-my-first-wpf-desktop-application/configure-new-project-dialog.png)

      <span data-ttu-id="19b8e-130">Visual Studio crea el proyecto y abre el Diseñador de la ventana de aplicación predeterminada denominado **MainWindow.xaml**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-130">Visual Studio creates the project and opens the designer for the default application window named **MainWindow.xaml**.</span></span>

2. <span data-ttu-id="19b8e-131">Abra *Application.xaml* (Visual Basic) o *App.xaml* (C#).</span><span class="sxs-lookup"><span data-stu-id="19b8e-131">Open *Application.xaml* (Visual Basic) or *App.xaml* (C#).</span></span>

    <span data-ttu-id="19b8e-132">Este archivo XAML define una aplicación de WPF y los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-132">This XAML file defines a WPF application and any application resources.</span></span> <span data-ttu-id="19b8e-133">También usa este archivo para especificar la interfaz de usuario, en este caso *MainWindow.xaml*, que se muestra automáticamente cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-133">You also use this file to specify the UI, in this case *MainWindow.xaml*, that automatically shows when the application starts.</span></span>

    <span data-ttu-id="19b8e-134">El XAML debe ser similar al siguiente en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="19b8e-134">Your XAML should look like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#1_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]

    <span data-ttu-id="19b8e-135">Al igual que con las siguientes acciones en C#:</span><span class="sxs-lookup"><span data-stu-id="19b8e-135">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]

3. <span data-ttu-id="19b8e-136">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-136">Open *MainWindow.xaml*.</span></span>

    <span data-ttu-id="19b8e-137">Este archivo XAML es la ventana principal de la aplicación y muestra contenido creado en páginas.</span><span class="sxs-lookup"><span data-stu-id="19b8e-137">This XAML file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="19b8e-138">La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono y controla los eventos, como cerrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="19b8e-138">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span>

4. <span data-ttu-id="19b8e-139">Cambiar el <xref:System.Windows.Window> elemento a un <xref:System.Windows.Navigation.NavigationWindow>, tal y como se muestra en el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-139">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>, as shown in the following XAML:</span></span>

   ```xaml
   <NavigationWindow x:Class="ExpenseIt.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        ...
   </NavigationWindow>
   ```

   <span data-ttu-id="19b8e-140">Esta aplicación accede a contenido diferente según la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="19b8e-140">This app navigates to different content depending on the user input.</span></span> <span data-ttu-id="19b8e-141">Por ello principal <xref:System.Windows.Window> debe cambiarse a un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-141">This is why the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="19b8e-142"><xref:System.Windows.Navigation.NavigationWindow> hereda todas las propiedades de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-142"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="19b8e-143">El <xref:System.Windows.Navigation.NavigationWindow> elemento en el archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase.</span><span class="sxs-lookup"><span data-stu-id="19b8e-143">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="19b8e-144">Para obtener más información, consulte [información general sobre navegación](../app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-144">For more information, see [Navigation overview](../app-development/navigation-overview.md).</span></span>

5. <span data-ttu-id="19b8e-145">Quitar el <xref:System.Windows.Controls.Grid> elementos de entre el <xref:System.Windows.Navigation.NavigationWindow> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="19b8e-145">Remove the <xref:System.Windows.Controls.Grid> elements from between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span>

6. <span data-ttu-id="19b8e-146">Cambie las siguientes propiedades en el código XAML para el <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="19b8e-146">Change the following properties in the XAML code for the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>

    - <span data-ttu-id="19b8e-147">Establecer el <xref:System.Windows.Window.Title%2A> propiedad en "`ExpenseIt`".</span><span class="sxs-lookup"><span data-stu-id="19b8e-147">Set the <xref:System.Windows.Window.Title%2A> property to "`ExpenseIt`".</span></span>

    - <span data-ttu-id="19b8e-148">Establecer el <xref:System.Windows.FrameworkElement.Height%2A> propiedad en 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-148">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span>

    - <span data-ttu-id="19b8e-149">Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-149">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span>

    <span data-ttu-id="19b8e-150">El XAML debe ser similar al siguiente de Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="19b8e-150">Your XAML should look like the following for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#2_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]

    <span data-ttu-id="19b8e-151">Al igual que con los siguientes aspectos para C#:</span><span class="sxs-lookup"><span data-stu-id="19b8e-151">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]

7. <span data-ttu-id="19b8e-152">Abra *MainWindow.xaml.vb* o *MainWindow.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-152">Open *MainWindow.xaml.vb* or *MainWindow.xaml.cs*.</span></span>

    <span data-ttu-id="19b8e-153">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-153">This file is a code-behind file that contains code to handle the events declared in *MainWindow.xaml*.</span></span> <span data-ttu-id="19b8e-154">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="19b8e-154">This file contains a partial class for the window defined in XAML.</span></span>

8. <span data-ttu-id="19b8e-155">Si usas C#, cambie el `MainWindow` clase derive de <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-155">If you're using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="19b8e-156">(En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en XAML.) Su C# código debe ser ahora similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-156">(In Visual Basic, this happens automatically when you change the window in XAML.) Your C# code should now look like this:</span></span>

   [!code-csharp[ExpenseIt#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/MainWindow.xaml.cs?highlight=21)]

## <a name="add-files-to-the-application"></a><span data-ttu-id="19b8e-157">Agregar archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="19b8e-157">Add files to the application</span></span>

<span data-ttu-id="19b8e-158">En esta sección, agregará dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-158">In this section, you'll add two pages and an image to the application.</span></span>

1. <span data-ttu-id="19b8e-159">Agregue una nueva página al proyecto y asígnele el nombre *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="19b8e-159">Add a new page to the project, and name it *`ExpenseItHome.xaml`*:</span></span>

   1. <span data-ttu-id="19b8e-160">En **el Explorador de soluciones**, haga doble clic en el **`ExpenseIt`** nodo de proyecto y elija **agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-160">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="19b8e-161">En el **Agregar nuevo elemento** cuadro de diálogo, el **página (WPF)** plantilla ya está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="19b8e-161">In the **Add New Item** dialog, the **Page (WPF)** template is already selected.</span></span> <span data-ttu-id="19b8e-162">Escriba el nombre **`ExpenseItHome`** y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-162">Enter the name **`ExpenseItHome`**, and then select **Add**.</span></span>

    <span data-ttu-id="19b8e-163">Esta página es la primera página que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-163">This page is the first page that's displayed when the application is launched.</span></span> <span data-ttu-id="19b8e-164">Mostrará una lista de personas para seleccionar una, para mostrar un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-164">It will show a list of people to select from, to show an expense report for.</span></span>

1. <span data-ttu-id="19b8e-165">Abra *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-165">Open *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="19b8e-166">Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - Home`".</span><span class="sxs-lookup"><span data-stu-id="19b8e-166">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - Home`".</span></span>

1. <span data-ttu-id="19b8e-167">Establecer el `DesignHeight` y `DesignWidth` valores de elemento a 300 píxeles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-167">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="19b8e-168">El XAML aparece ahora como sigue para Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="19b8e-168">The XAML now appears as follows for Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#6_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]

    <span data-ttu-id="19b8e-169">Al igual que con los siguientes aspectos para C#:</span><span class="sxs-lookup"><span data-stu-id="19b8e-169">And like the following for C#:</span></span>

    [!code-xaml[ExpenseIt#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]

1. <span data-ttu-id="19b8e-170">Abra *MainWindow.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-170">Open *MainWindow.xaml*.</span></span>

1. <span data-ttu-id="19b8e-171">Agregar un <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad a la <xref:System.Windows.Navigation.NavigationWindow> elemento y establézcala en "`ExpenseItHome.xaml`".</span><span class="sxs-lookup"><span data-stu-id="19b8e-171">Add a <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property to the <xref:System.Windows.Navigation.NavigationWindow> element and set it to "`ExpenseItHome.xaml`".</span></span>

    <span data-ttu-id="19b8e-172">Esto establece *`ExpenseItHome.xaml`* como la primera página se abre cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-172">This sets *`ExpenseItHome.xaml`* to be the first page opened when the application starts.</span></span> 

    <span data-ttu-id="19b8e-173">Ejemplo XAML en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="19b8e-173">Example XAML in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#7_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]

    <span data-ttu-id="19b8e-174">Y en C#:</span><span class="sxs-lookup"><span data-stu-id="19b8e-174">And in C#:</span></span>

    [!code-xaml[ExpenseIt#7](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]

   > [!TIP]
   > <span data-ttu-id="19b8e-175">También puede establecer el **origen** propiedad en el **varios** categoría de la **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="19b8e-175">You can also set the **Source** property in the **Miscellaneous** category of the **Properties** window.</span></span>
   >
   > ![Propiedad de origen en la ventana Propiedades](./media/properties-source.png)

1. <span data-ttu-id="19b8e-177">Agregue otra nueva página WPF al proyecto y asígnele el nombre *ExpenseReportPage.xaml*::</span><span class="sxs-lookup"><span data-stu-id="19b8e-177">Add another new WPF page to the project, and name it *ExpenseReportPage.xaml*::</span></span>

   1. <span data-ttu-id="19b8e-178">En **el Explorador de soluciones**, haga doble clic en el **`ExpenseIt`** nodo de proyecto y elija **agregar** > **página**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-178">In **Solution Explorer**, right-click on the **`ExpenseIt`** project node and choose **Add** > **Page**.</span></span>

   1. <span data-ttu-id="19b8e-179">En el **Agregar nuevo elemento** cuadro de diálogo, seleccione el **página (WPF)** plantilla.</span><span class="sxs-lookup"><span data-stu-id="19b8e-179">In the **Add New Item** dialog, select the **Page (WPF)** template.</span></span> <span data-ttu-id="19b8e-180">Escriba el nombre **ExpenseReportPage**y, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-180">Enter the name **ExpenseReportPage**, and then select **Add**.</span></span>

    <span data-ttu-id="19b8e-181">Esta página mostrará el informe de gastos de la persona que está seleccionada en el **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="19b8e-181">This page will show the expense report for the person that is selected on the **`ExpenseItHome`** page.</span></span>

1. <span data-ttu-id="19b8e-182">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-182">Open *ExpenseReportPage.xaml*.</span></span>

1. <span data-ttu-id="19b8e-183">Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "`ExpenseIt - View Expense`".</span><span class="sxs-lookup"><span data-stu-id="19b8e-183">Set the <xref:System.Windows.Controls.Page.Title%2A> to "`ExpenseIt - View Expense`".</span></span>

1. <span data-ttu-id="19b8e-184">Establecer el `DesignHeight` y `DesignWidth` valores de elemento a 300 píxeles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-184">Set the `DesignHeight` and `DesignWidth` element values to 300 pixels.</span></span>

    <span data-ttu-id="19b8e-185">*ExpenseReportPage.xaml* ahora el siguiente aspecto en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="19b8e-185">*ExpenseReportPage.xaml* now looks like the following in Visual Basic:</span></span>

    [!code-xaml[ExpenseIt#4_A](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]

    <span data-ttu-id="19b8e-186">Al igual que con las siguientes acciones en C#:</span><span class="sxs-lookup"><span data-stu-id="19b8e-186">And like the following in C#:</span></span>

    [!code-xaml[ExpenseIt#4](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]

1. <span data-ttu-id="19b8e-187">Abra *ExpenseItHome.xaml.vb* y *ExpenseReportPage.xaml.vb*, o *ExpenseItHome.xaml.cs* y *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-187">Open *ExpenseItHome.xaml.vb* and *ExpenseReportPage.xaml.vb*, or *ExpenseItHome.xaml.cs* and *ExpenseReportPage.xaml.cs*.</span></span>

    <span data-ttu-id="19b8e-188">Cuando se crea un nuevo archivo de paginación, Visual Studio crea automáticamente su *código* archivo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-188">When you create a new Page file, Visual Studio automatically creates its *code-behind* file.</span></span> <span data-ttu-id="19b8e-189">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="19b8e-189">These code-behind files handle the logic for responding to user input.</span></span>

    <span data-ttu-id="19b8e-190">El código debe ser similar al siguiente para **`ExpenseItHome`**:</span><span class="sxs-lookup"><span data-stu-id="19b8e-190">Your code should look like the following for **`ExpenseItHome`**:</span></span>

    [!code-csharp[ExpenseIt#2_5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]

    [!code-vb[ExpenseIt#2_5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]

    <span data-ttu-id="19b8e-191">Al igual que con los siguientes aspectos para **ExpenseReportPage**:</span><span class="sxs-lookup"><span data-stu-id="19b8e-191">And like the following for **ExpenseReportPage**:</span></span>

    [!code-csharp[ExpenseIt#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]

    [!code-vb[ExpenseIt#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]

1. <span data-ttu-id="19b8e-192">Agregue una imagen denominada *watermark.png* al proyecto.</span><span class="sxs-lookup"><span data-stu-id="19b8e-192">Add an image named *watermark.png* to the project.</span></span> <span data-ttu-id="19b8e-193">Puede crear su propia imagen, copie el archivo desde el código de ejemplo u obtenerlo [aquí](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span><span class="sxs-lookup"><span data-stu-id="19b8e-193">You can create your own image, copy the file from the sample code, or get it [here](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/WalkthroughFirstWPFApp).</span></span>

    1. <span data-ttu-id="19b8e-194">Haga doble clic en el nodo del proyecto y seleccione **agregar** > **elemento existente**, o bien presione **MAYÚS**+**Alt** + **A**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-194">Right-click on the project node and select **Add** > **Existing Item**, or press **Shift**+**Alt**+**A**.</span></span>

    2. <span data-ttu-id="19b8e-195">En el **Agregar elemento existente** cuadro de diálogo, establecer el filtro de archivos en **todos los archivos** o **archivos de imagen**, busque el archivo de imagen que desea usar y, a continuación, seleccione **agregar** .</span><span class="sxs-lookup"><span data-stu-id="19b8e-195">In the **Add Existing Item** dialog, set the file filter to either **All Files** or **Image Files**, browse to the image file you want to use, and then select **Add**.</span></span>

## <a name="build-and-run-the-application"></a><span data-ttu-id="19b8e-196">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="19b8e-196">Build and run the application</span></span>

1. <span data-ttu-id="19b8e-197">Para compilar y ejecutar la aplicación, presione **F5** o seleccione **Iniciar depuración** desde el **depurar** menú.</span><span class="sxs-lookup"><span data-stu-id="19b8e-197">To build and run the application, press **F5** or select **Start Debugging** from the **Debug** menu.</span></span>

    <span data-ttu-id="19b8e-198">La siguiente ilustración muestra la aplicación con el <xref:System.Windows.Navigation.NavigationWindow> botones:</span><span class="sxs-lookup"><span data-stu-id="19b8e-198">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons:</span></span>

    ![Después de compilar y ejecutar la aplicación.](./media/walkthrough-my-first-wpf-desktop-application/build-run-application.png)

2. <span data-ttu-id="19b8e-200">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="19b8e-200">Close the application to return to Visual Studio.</span></span>

## <a name="create-the-layout"></a><span data-ttu-id="19b8e-201">Crear el diseño</span><span class="sxs-lookup"><span data-stu-id="19b8e-201">Create the layout</span></span>

<span data-ttu-id="19b8e-202">Diseño proporciona una manera ordenada colocar los elementos de interfaz de usuario y también administra el tamaño y posición de dichos elementos cuando se cambia el tamaño de una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="19b8e-202">Layout provides an ordered way to place UI elements, and also manages the size and position of those elements when a UI is resized.</span></span> <span data-ttu-id="19b8e-203">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="19b8e-203">You typically create a layout with one of the following layout controls:</span></span>

- <span data-ttu-id="19b8e-204"><xref:System.Windows.Controls.Canvas> -Define un área dentro de la cual puede colocar elementos secundarios explícitamente mediante coordenadas relativas al área del lienzo.</span><span class="sxs-lookup"><span data-stu-id="19b8e-204"><xref:System.Windows.Controls.Canvas> - Defines an area within which you can explicitly position child elements by using coordinates that are relative to the Canvas area.</span></span>
- <span data-ttu-id="19b8e-205"><xref:System.Windows.Controls.DockPanel> -Define un área donde puede organizar elementos secundarios horizontal o verticalmente, relacionados entre sí.</span><span class="sxs-lookup"><span data-stu-id="19b8e-205"><xref:System.Windows.Controls.DockPanel> - Defines an area where you can arrange child elements either horizontally or vertically, relative to each other.</span></span>
- <span data-ttu-id="19b8e-206"><xref:System.Windows.Controls.Grid> -Define un área de cuadrícula flexible que consta de columnas y filas.</span><span class="sxs-lookup"><span data-stu-id="19b8e-206"><xref:System.Windows.Controls.Grid> - Defines a flexible grid area that consists of columns and rows.</span></span>
- <span data-ttu-id="19b8e-207"><xref:System.Windows.Controls.StackPanel> -Organiza los elementos secundarios en una sola línea que puede orientarse horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="19b8e-207"><xref:System.Windows.Controls.StackPanel> - Arranges child elements into a single line that can be oriented horizontally or vertically.</span></span>
- <span data-ttu-id="19b8e-208"><xref:System.Windows.Controls.VirtualizingStackPanel> -Organiza y virtualiza contenido en una sola línea que está orientada horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="19b8e-208"><xref:System.Windows.Controls.VirtualizingStackPanel> - Arranges and virtualizes content on a single line that is oriented either horizontally or vertically.</span></span>
- <span data-ttu-id="19b8e-209"><xref:System.Windows.Controls.WrapPanel> -Coloca elementos secundarios en posición secuencial de izquierda a derecha y traslada el contenido a la línea siguiente en el borde del cuadro contenedor.</span><span class="sxs-lookup"><span data-stu-id="19b8e-209"><xref:System.Windows.Controls.WrapPanel> - Positions child elements in sequential position from left to right, breaking content to the next line at the edge of the containing box.</span></span> <span data-ttu-id="19b8e-210">La ordenación subsiguiente se realiza secuencialmente de arriba a abajo o de derecha a izquierda, dependiendo del valor de la propiedad Orientation.</span><span class="sxs-lookup"><span data-stu-id="19b8e-210">Subsequent ordering happens sequentially from top to bottom or from right to left, depending on the value of the Orientation property.</span></span>

<span data-ttu-id="19b8e-211">Cada uno de estos controles de diseño admite un tipo determinado de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="19b8e-211">Each of these layout controls supports a particular type of layout for its child elements.</span></span> <span data-ttu-id="19b8e-212">`ExpenseIt` se pueden cambiar el tamaño de las páginas y cada página tiene elementos organizados horizontalmente y verticalmente junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-212">`ExpenseIt` pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="19b8e-213">En este ejemplo, el <xref:System.Windows.Controls.Grid> se utiliza como elemento de diseño para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-213">In this example, the <xref:System.Windows.Controls.Grid> is used as  layout element for the application.</span></span>

> [!TIP]
> <span data-ttu-id="19b8e-214">Para obtener más información acerca de <xref:System.Windows.Controls.Panel> elementos, vea [información general sobre](../controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-214">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels overview](../controls/panels-overview.md).</span></span> <span data-ttu-id="19b8e-215">Para obtener más información acerca del diseño, vea [diseño](../advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-215">For more information about layout, see [Layout](../advanced/layout.md).</span></span>

<span data-ttu-id="19b8e-216">En esta sección, creará una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a la <xref:System.Windows.Controls.Grid> en *`ExpenseItHome.xaml`*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-216">In this section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in *`ExpenseItHome.xaml`*.</span></span>

1. <span data-ttu-id="19b8e-217">En *`ExpenseItHome.xaml`*, establezca el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en el <xref:System.Windows.Controls.Grid> elemento en "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior:</span><span class="sxs-lookup"><span data-stu-id="19b8e-217">In *`ExpenseItHome.xaml`*, set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10", which corresponds to left, top, right and bottom margins:</span></span>

   ```xaml
   <Grid Margin="10,0,10,10">
   ```

   > [!TIP]
   > <span data-ttu-id="19b8e-218">También puede establecer el **margen** valores en el **propiedades** ventana, en el **diseño** categoría:</span><span class="sxs-lookup"><span data-stu-id="19b8e-218">You can also set the **Margin** values in the **Properties** window, under the **Layout** category:</span></span>
   >
   > ![Valores de margen en la ventana Propiedades](./media/properties-margin.png)

2. <span data-ttu-id="19b8e-220">Agregue el siguiente XAML entre el <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna:</span><span class="sxs-lookup"><span data-stu-id="19b8e-220">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions:</span></span>

    [!code-xaml[ExpenseIt#8](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]

    <span data-ttu-id="19b8e-221">El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A>, lo que significa que las filas se ajusta el tamaño en función del contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="19b8e-221">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A>, which means that the rows are sized based on the content in the rows.</span></span> <span data-ttu-id="19b8e-222">El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> ajuste de tamaño, lo que significa que el alto de fila es una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="19b8e-222">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row height is a weighted proportion of the available space.</span></span> <span data-ttu-id="19b8e-223">Por ejemplo, si dos filas tienen un <xref:System.Windows.Controls.RowDefinition.Height%2A> de "\*", cada uno de ellos tiene un alto que sea la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="19b8e-223">For example if two rows each have a <xref:System.Windows.Controls.RowDefinition.Height%2A> of "\*", they each have a height that is half of the available space.</span></span>

    <span data-ttu-id="19b8e-224">Su <xref:System.Windows.Controls.Grid> debe contener ahora el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-224">Your <xref:System.Windows.Controls.Grid> should now contain the following XAML:</span></span>

    [!code-xaml[ExpenseIt#9](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]

## <a name="add-controls"></a><span data-ttu-id="19b8e-225">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="19b8e-225">Add controls</span></span>

<span data-ttu-id="19b8e-226">En esta sección, actualizará la página principal de la interfaz de usuario para mostrar una lista de personas, donde selecciona una persona para mostrar su informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-226">In this section, you'll update the home page UI to show a list of people, where you select one person to display their expense report.</span></span> <span data-ttu-id="19b8e-227">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-227">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="19b8e-228">Para obtener más información, consulte [Controles](../controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-228">For more information, see [Controls](../controls/index.md).</span></span>

<span data-ttu-id="19b8e-229">Para crear esta interfaz de usuario, agregará los siguientes elementos para *`ExpenseItHome.xaml`*:</span><span class="sxs-lookup"><span data-stu-id="19b8e-229">To create this UI, you'll add the following elements to *`ExpenseItHome.xaml`*:</span></span>

- <span data-ttu-id="19b8e-230">Un <xref:System.Windows.Controls.ListBox> (para obtener la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="19b8e-230">A <xref:System.Windows.Controls.ListBox> (for the list of people).</span></span>
- <span data-ttu-id="19b8e-231">Un <xref:System.Windows.Controls.Label> (para el encabezado de lista).</span><span class="sxs-lookup"><span data-stu-id="19b8e-231">A <xref:System.Windows.Controls.Label> (for the list header).</span></span>
- <span data-ttu-id="19b8e-232">Un <xref:System.Windows.Controls.Button> (hacer clic para ver el informe de gastos de la persona que está seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="19b8e-232">A <xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span>

<span data-ttu-id="19b8e-233">Cada control se coloca en una fila de la <xref:System.Windows.Controls.Grid> estableciendo el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="19b8e-233">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="19b8e-234">Para obtener más información sobre las propiedades adjuntas, consulte [Attached Properties Overview](../advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-234">For more information about attached properties, see [Attached Properties Overview](../advanced/attached-properties-overview.md).</span></span>

1. <span data-ttu-id="19b8e-235">En *`ExpenseItHome.xaml`*, agregue el siguiente XAML en algún lugar entre el <xref:System.Windows.Controls.Grid> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="19b8e-235">In *`ExpenseItHome.xaml`*, add the following XAML somewhere between the <xref:System.Windows.Controls.Grid> tags:</span></span>

   [!code-xaml[ExpenseIt#10](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]

   > [!TIP]
   > <span data-ttu-id="19b8e-236">También puede crear los controles arrastrándolos desde el **cuadro de herramientas** ventana en la ventana de diseño y, a continuación, establecer sus propiedades en el **propiedades** ventana.</span><span class="sxs-lookup"><span data-stu-id="19b8e-236">You can also create the controls by dragging them from the **Toolbox** window onto the design window, and then setting their properties in the **Properties** window.</span></span>

2. <span data-ttu-id="19b8e-237">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-237">Build and run the application.</span></span>

    <span data-ttu-id="19b8e-238">La ilustración siguiente muestra los controles que creó:</span><span class="sxs-lookup"><span data-stu-id="19b8e-238">The following illustration shows the controls you created:</span></span>

![Muestra una lista de nombres de captura de pantalla de ejemplo ExpenseIt](./media/walkthrough-my-first-wpf-desktop-application/add-application-controls.png)

## <a name="add-an-image-and-a-title"></a><span data-ttu-id="19b8e-240">Agregar un título y una imagen</span><span class="sxs-lookup"><span data-stu-id="19b8e-240">Add an image and a title</span></span>

<span data-ttu-id="19b8e-241">En esta sección, actualizará la página principal de la interfaz de usuario con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="19b8e-241">In this section, you'll update the home page UI with an image and a page title.</span></span>

1. <span data-ttu-id="19b8e-242">En *`ExpenseItHome.xaml`*, agregue otra columna a la <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles:</span><span class="sxs-lookup"><span data-stu-id="19b8e-242">In *`ExpenseItHome.xaml`*, add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels:</span></span>

    [!code-xaml[ExpenseIt#11](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=52-55)]

2. <span data-ttu-id="19b8e-243">Agregar otra fila a la <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, para un total de cuatro filas:</span><span class="sxs-lookup"><span data-stu-id="19b8e-243">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>, for a total of four rows:</span></span>

    [!code-xaml[ExpenseIt#11b](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseItHome.xaml?highlight=57-62)]

3. <span data-ttu-id="19b8e-244">Mueva los controles a la segunda columna estableciendo el <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> propiedad en 1 en cada uno de los tres controles (borde, ListBox y botón).</span><span class="sxs-lookup"><span data-stu-id="19b8e-244">Move the controls to the second column by setting the <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> property to 1 in each of the three controls (Border, ListBox, and Button).</span></span>

4. <span data-ttu-id="19b8e-245">Baje cada control una fila aumentando su <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> valor en 1 para cada uno de los tres controles (borde, ListBox y botón) y para el elemento Border.</span><span class="sxs-lookup"><span data-stu-id="19b8e-245">Move each control down a row by incrementing its <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> value by 1 for each of the three controls (Border, ListBox, and Button) and for the Border element.</span></span>

   <span data-ttu-id="19b8e-246">El XAML para los tres controles ahora el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="19b8e-246">The XAML for the three controls now looks like the following:</span></span>

    [!code-xaml[ExpenseIt#12](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]

5. <span data-ttu-id="19b8e-247">Establecer el <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> propiedad a la *watermark.png* archivo de imagen, agregando el siguiente XAML en cualquier lugar entre el `<Grid>` y `</Grid>` etiquetas:</span><span class="sxs-lookup"><span data-stu-id="19b8e-247">Set the <xref:System.Windows.Controls.Panel.Background%2A?displayProperty=nameWithType> property to the *watermark.png* image file, by adding the following XAML anywhere between the `<Grid>` and `</Grid>` tags:</span></span>

    [!code-xaml[ExpenseIt#14](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]

6. <span data-ttu-id="19b8e-248">Antes de la <xref:System.Windows.Controls.Border> elemento, agregue un <xref:System.Windows.Controls.Label> con el contenido "View Expense Report".</span><span class="sxs-lookup"><span data-stu-id="19b8e-248">Before the <xref:System.Windows.Controls.Border> element, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report".</span></span> <span data-ttu-id="19b8e-249">Esta etiqueta es el título de la página.</span><span class="sxs-lookup"><span data-stu-id="19b8e-249">This label is the title of the page.</span></span>

    [!code-xaml[ExpenseIt#13](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]

7. <span data-ttu-id="19b8e-250">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-250">Build and run the application.</span></span>

<span data-ttu-id="19b8e-251">La ilustración siguiente muestra los resultados de lo que acaba de agregar:</span><span class="sxs-lookup"><span data-stu-id="19b8e-251">The following illustration shows the results of what you just added:</span></span>

![Captura de pantalla de ejemplo ExpenseIt que muestra el nuevo título de página y en segundo plano de imagen](./media/walkthrough-my-first-wpf-desktop-application/add-application-image-title.png)

## <a name="add-code-to-handle-events"></a><span data-ttu-id="19b8e-253">Agregue código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="19b8e-253">Add code to handle events</span></span>

1. <span data-ttu-id="19b8e-254">En *`ExpenseItHome.xaml`*, agregue un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para el <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="19b8e-254">In *`ExpenseItHome.xaml`*, add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="19b8e-255">Para obtener más información, vea [Cómo: Crear un controlador de eventos simple](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="19b8e-255">For more information, see [How to: Create a simple event handler](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/bb675300(v=vs.100)).</span></span>

    [!code-xaml[ExpenseIt#15](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]

2. <span data-ttu-id="19b8e-256">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-256">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

3. <span data-ttu-id="19b8e-257">Agregue el código siguiente a la `ExpenseItHome` clase para agregar un botón de controlador de eventos click.</span><span class="sxs-lookup"><span data-stu-id="19b8e-257">Add the following code to the `ExpenseItHome` class to add a button click event handler.</span></span> <span data-ttu-id="19b8e-258">El controlador de eventos abre la **ExpenseReportPage** página.</span><span class="sxs-lookup"><span data-stu-id="19b8e-258">The event handler opens the **ExpenseReportPage** page.</span></span>

    [!code-csharp[ExpenseIt#16](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]

## <a name="create-the-ui-for-expensereportpage"></a><span data-ttu-id="19b8e-259">Crear la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="19b8e-259">Create the UI for ExpenseReportPage</span></span>

<span data-ttu-id="19b8e-260">*ExpenseReportPage.xaml* muestra el informe de gastos de la persona que está seleccionada en el **`ExpenseItHome`** página.</span><span class="sxs-lookup"><span data-stu-id="19b8e-260">*ExpenseReportPage.xaml* displays the expense report for the person that's selected on the **`ExpenseItHome`** page.</span></span> <span data-ttu-id="19b8e-261">En esta sección, creará la interfaz de usuario para **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-261">In this section, you'll create the UI for **ExpenseReportPage**.</span></span> <span data-ttu-id="19b8e-262">También agregará en segundo plano y los colores a los distintos elementos de interfaz de usuario de relleno.</span><span class="sxs-lookup"><span data-stu-id="19b8e-262">You'll also add background and fill colors to the various UI elements.</span></span>

1. <span data-ttu-id="19b8e-263">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-263">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="19b8e-264">Agregue el siguiente XAML entre el <xref:System.Windows.Controls.Grid> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="19b8e-264">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags:</span></span>

    [!code-xaml[ExpenseIt#17](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]

    <span data-ttu-id="19b8e-265">Esta interfaz de usuario es similar a *`ExpenseItHome.xaml`*, excepto en que los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-265">This UI is similar to *`ExpenseItHome.xaml`*, except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span>

3. <span data-ttu-id="19b8e-266">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-266">Build and run the application.</span></span>

4. <span data-ttu-id="19b8e-267">Seleccione el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="19b8e-267">Select the **View** button.</span></span>

    <span data-ttu-id="19b8e-268">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="19b8e-268">The expense report page appears.</span></span> <span data-ttu-id="19b8e-269">Tenga en cuenta que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="19b8e-269">Also notice that the back navigation button is enabled.</span></span>

<span data-ttu-id="19b8e-270">La ilustración siguiente muestra los elementos de interfaz de usuario agregados al *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-270">The following illustration shows the UI elements added to *ExpenseReportPage.xaml*.</span></span>

![Pantalla de ejemplo ExpenseIt que muestra la interfaz de usuario que acaba de crear para el ExpenseReportPage.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

## <a name="style-controls"></a><span data-ttu-id="19b8e-272">Aplicar estilo a controles</span><span class="sxs-lookup"><span data-stu-id="19b8e-272">Style controls</span></span>

<span data-ttu-id="19b8e-273">La apariencia de los diversos elementos a menudo es el mismo para todos los elementos del mismo tipo en una interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="19b8e-273">The appearance of various elements is often the same for all elements of the same type in a UI.</span></span> <span data-ttu-id="19b8e-274">Interfaz de usuario usa [estilos](../controls/styling-and-templating.md) para que las apariencias sean reutilizables en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-274">UI uses [styles](../controls/styling-and-templating.md) to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="19b8e-275">La reutilización de los estilos ayuda a simplificar la administración y creación de XAML.</span><span class="sxs-lookup"><span data-stu-id="19b8e-275">The reusability of styles helps to simplify XAML creation and management.</span></span> <span data-ttu-id="19b8e-276">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-276">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span>

1. <span data-ttu-id="19b8e-277">Abra *Application.xaml* o *App.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-277">Open *Application.xaml* or *App.xaml*.</span></span>

2. <span data-ttu-id="19b8e-278">Agregue el siguiente XAML entre el <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="19b8e-278">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>

    [!code-xaml[ExpenseIt#18](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]

    <span data-ttu-id="19b8e-279">Este código XAML agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="19b8e-279">This XAML adds the following styles:</span></span>

    - <span data-ttu-id="19b8e-280">`headerTextStyle`: Para dar formato al título de página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-280">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="19b8e-281">`labelStyle`: Para dar formato a la <xref:System.Windows.Controls.Label> controles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-281">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span>

    - <span data-ttu-id="19b8e-282">`columnHeaderStyle`: Para dar formato a la <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-282">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span>

    - <span data-ttu-id="19b8e-283">`listHeaderStyle`: Aplica formato al encabezado de lista <xref:System.Windows.Controls.Border> controles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-283">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span>

    - <span data-ttu-id="19b8e-284">`listHeaderTextStyle`: Aplica formato al encabezado de lista <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-284">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span>

    - <span data-ttu-id="19b8e-285">`buttonStyle`: Para dar formato a la <xref:System.Windows.Controls.Button> en `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="19b8e-285">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on `ExpenseItHome.xaml`.</span></span>

    <span data-ttu-id="19b8e-286">Tenga en cuenta que los estilos son recursos y elementos secundarios de la <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property (elemento).</span><span class="sxs-lookup"><span data-stu-id="19b8e-286">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="19b8e-287">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-287">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="19b8e-288">Para obtener un ejemplo del uso de recursos en una aplicación. NET, consulte [usar recursos de aplicaciones](../advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-288">For an example of using resources in a .NET app, see [Use Application Resources](../advanced/how-to-use-application-resources.md).</span></span>

3. <span data-ttu-id="19b8e-289">En *`ExpenseItHome.xaml`*, reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-289">In *`ExpenseItHome.xaml`*, replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#19](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]

    <span data-ttu-id="19b8e-290">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-290">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="19b8e-291">Por ejemplo, el `headerTextStyle` se aplica a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-291">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span>

4. <span data-ttu-id="19b8e-292">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-292">Open *ExpenseReportPage.xaml*.</span></span>

5. <span data-ttu-id="19b8e-293">Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-293">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#20](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]

    <span data-ttu-id="19b8e-294">Este XAML agrega estilos a la <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Border> elementos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-294">This XAML adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span>

6. <span data-ttu-id="19b8e-295">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-295">Build and run the application.</span></span> <span data-ttu-id="19b8e-296">El aspecto de la ventana es igual que anteriormente.</span><span class="sxs-lookup"><span data-stu-id="19b8e-296">The window appearance is the same as previously.</span></span>

    ![Captura de pantalla de ejemplo ExpenseIt con la misma apariencia que en la última sección.](./media/walkthrough-my-first-wpf-desktop-application/create-application-ui.png)

7. <span data-ttu-id="19b8e-298">Cierre la aplicación para volver a Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="19b8e-298">Close the application to return to Visual Studio.</span></span>

## <a name="bind-data-to-a-control"></a><span data-ttu-id="19b8e-299">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="19b8e-299">Bind data to a control</span></span>

<span data-ttu-id="19b8e-300">En esta sección, creará los datos XML que se enlazan a diversos controles.</span><span class="sxs-lookup"><span data-stu-id="19b8e-300">In this section, you'll create the XML data that is bound to various controls.</span></span>

1. <span data-ttu-id="19b8e-301">En *`ExpenseItHome.xaml`*, después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue el siguiente XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contiene los datos para cada persona:</span><span class="sxs-lookup"><span data-stu-id="19b8e-301">In *`ExpenseItHome.xaml`*, after the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person:</span></span>

    [!code-xaml[ExpenseIt#23](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,16-40,49)]

    <span data-ttu-id="19b8e-302">Los datos se crean como un <xref:System.Windows.Controls.Grid> recursos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-302">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="19b8e-303">Normalmente estos datos se cargan como un archivo, pero por motivos de simplicidad, los datos se agregan en línea.</span><span class="sxs-lookup"><span data-stu-id="19b8e-303">Normally this data would be loaded as a file, but for simplicity the data is added inline.</span></span>

2. <span data-ttu-id="19b8e-304">Dentro de la `<Grid.Resources>` elemento, agregue el siguiente `<xref:System.Windows.DataTemplate>` elemento, que define cómo mostrar los datos en el <xref:System.Windows.Controls.ListBox>, después el `<XmlDataProvider>` elemento:</span><span class="sxs-lookup"><span data-stu-id="19b8e-304">Within the `<Grid.Resources>` element, add the following `<xref:System.Windows.DataTemplate>` element, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>, after the `<XmlDataProvider>` element:</span></span>

    [!code-xaml[ExpenseIt#24](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml?range=13,43-46,49)]

    <span data-ttu-id="19b8e-305">Para obtener más información acerca de las plantillas de datos, vea [información general sobre plantillas de datos](../data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-305">For more information about data templates, see [Data templating overview](../data/data-templating-overview.md).</span></span>

3. <span data-ttu-id="19b8e-306">Reemplazar existente <xref:System.Windows.Controls.ListBox> con el XAML siguiente:</span><span class="sxs-lookup"><span data-stu-id="19b8e-306">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML:</span></span>

    [!code-xaml[ExpenseIt#25](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]

    <span data-ttu-id="19b8e-307">Este XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="19b8e-307">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span>

## <a name="connect-data-to-controls"></a><span data-ttu-id="19b8e-308">Conectar datos a controles</span><span class="sxs-lookup"><span data-stu-id="19b8e-308">Connect data to controls</span></span>

<span data-ttu-id="19b8e-309">A continuación, agregará código para recuperar el nombre que se han seleccionado en el **`ExpenseItHome`** página y pasarlo al constructor de **ExpenseReportPage**.</span><span class="sxs-lookup"><span data-stu-id="19b8e-309">Next, you'll add code to retrieve the name that's selected on the **`ExpenseItHome`** page and pass it to the constructor of **ExpenseReportPage**.</span></span> <span data-ttu-id="19b8e-310">**ExpenseReportPage** establece el contexto de datos con el elemento pasado, que es lo que los controles definidos en *ExpenseReportPage.xaml* enlazar.</span><span class="sxs-lookup"><span data-stu-id="19b8e-310">**ExpenseReportPage** sets its data context with the passed item, which is what the controls defined in *ExpenseReportPage.xaml* bind to.</span></span>

1. <span data-ttu-id="19b8e-311">Abra *ExpenseReportPage.xaml.vb* o *ExpenseReportPage.xaml.cs*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-311">Open *ExpenseReportPage.xaml.vb* or *ExpenseReportPage.xaml.cs*.</span></span>

2. <span data-ttu-id="19b8e-312">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="19b8e-312">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#26](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]

3. <span data-ttu-id="19b8e-313">Abra *`ExpenseItHome.xaml.vb`* o *`ExpenseItHome.xaml.cs`*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-313">Open *`ExpenseItHome.xaml.vb`* or *`ExpenseItHome.xaml.cs`*.</span></span>

4. <span data-ttu-id="19b8e-314">Cambiar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al nuevo constructor y pase los datos de informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="19b8e-314">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span>

    [!code-csharp[ExpenseIt#27](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]

## <a name="style-data-with-data-templates"></a><span data-ttu-id="19b8e-315">Datos de estilo con plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="19b8e-315">Style data with data templates</span></span>

<span data-ttu-id="19b8e-316">En esta sección, actualizará la interfaz de usuario para cada elemento en las listas de enlazado a datos mediante el uso de plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-316">In this section, you'll update the UI for each item in the data-bound lists by using data templates.</span></span>

1. <span data-ttu-id="19b8e-317">Abra el archivo *ExpenseReportPage.xaml*.</span><span class="sxs-lookup"><span data-stu-id="19b8e-317">Open *ExpenseReportPage.xaml*.</span></span>

2. <span data-ttu-id="19b8e-318">Enlazar el contenido de la "Name" y "Department" <xref:System.Windows.Controls.Label> elementos a los datos apropiados del origen de propiedad.</span><span class="sxs-lookup"><span data-stu-id="19b8e-318">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="19b8e-319">Para obtener más información sobre el enlace de datos, vea [información general sobre el enlace de datos](../data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19b8e-319">For more information about data binding, see [Data binding overview](../data/data-binding-overview.md).</span></span>

    [!code-xaml[ExpenseIt#31](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]

3. <span data-ttu-id="19b8e-320">Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue las siguientes plantillas de datos, que definen cómo se muestran los datos de informe de gastos:</span><span class="sxs-lookup"><span data-stu-id="19b8e-320">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data:</span></span>

    [!code-xaml[ExpenseIt#30](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]

4. <span data-ttu-id="19b8e-321">Reemplace el <xref:System.Windows.Controls.DataGridTextColumn> elementos con <xref:System.Windows.Controls.DataGridTemplateColumn> bajo el <xref:System.Windows.Controls.DataGrid> elemento y aplicar las plantillas.</span><span class="sxs-lookup"><span data-stu-id="19b8e-321">Replace the <xref:System.Windows.Controls.DataGridTextColumn> elements with <xref:System.Windows.Controls.DataGridTemplateColumn> under the <xref:System.Windows.Controls.DataGrid> element and apply the templates to them.</span></span>

    [!code-xaml[ExpenseIt#32](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]

5. <span data-ttu-id="19b8e-322">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19b8e-322">Build and run the application.</span></span>

6. <span data-ttu-id="19b8e-323">Seleccione una persona y, a continuación, seleccione el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="19b8e-323">Select a person and then select the **View** button.</span></span>

<span data-ttu-id="19b8e-324">La ilustración siguiente muestra ambas páginas de la `ExpenseIt` aplicación con controles, diseño, estilos, el enlace de datos y aplicar las plantillas de datos:</span><span class="sxs-lookup"><span data-stu-id="19b8e-324">The following illustration shows both pages of the `ExpenseIt` application with controls, layout, styles, data binding, and data templates applied:</span></span>

![Ambas páginas de la aplicación que muestra la lista de nombres y un informe de gastos.](./media/walkthrough-my-first-wpf-desktop-application/application-data-templates.png)

> [!NOTE]
> <span data-ttu-id="19b8e-326">En este ejemplo se muestra una característica específica de WPF y no sigue todos los procedimientos recomendados para cosas como la seguridad, localización y accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="19b8e-326">This sample demonstrates a specific feature of WPF and doesn't follow all best practices for things like security, localization, and accessibility.</span></span> <span data-ttu-id="19b8e-327">Para una completa cobertura de WPF y el desarrollo de aplicación .NET procedimientos recomendados, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="19b8e-327">For comprehensive coverage of WPF and the .NET app development best practices, see the following topics:</span></span>
>
> - [<span data-ttu-id="19b8e-328">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="19b8e-328">Accessibility</span></span>](../../ui-automation/accessibility-best-practices.md)
>
> - [<span data-ttu-id="19b8e-329">Seguridad</span><span class="sxs-lookup"><span data-stu-id="19b8e-329">Security</span></span>](../security-wpf.md)
>
> - [<span data-ttu-id="19b8e-330">Globalización y localización de WPF</span><span class="sxs-lookup"><span data-stu-id="19b8e-330">WPF globalization and localization</span></span>](../advanced/wpf-globalization-and-localization-overview.md)
>
> - [<span data-ttu-id="19b8e-331">WPF: rendimiento</span><span class="sxs-lookup"><span data-stu-id="19b8e-331">WPF performance</span></span>](../advanced/optimizing-wpf-application-performance.md)

## <a name="next-steps"></a><span data-ttu-id="19b8e-332">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="19b8e-332">Next steps</span></span>

<span data-ttu-id="19b8e-333">En este tutorial ha aprendido varias técnicas para crear una interfaz de usuario mediante Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="19b8e-333">In this walkthrough you learned a number of techniques for creating a UI using Windows Presentation Foundation (WPF).</span></span> <span data-ttu-id="19b8e-334">Ahora debería tener un conocimiento básico de los bloques de creación de una aplicación de .NET enlazados a datos.</span><span class="sxs-lookup"><span data-stu-id="19b8e-334">You should now have a basic understanding of the building blocks of a data-bound .NET app.</span></span> <span data-ttu-id="19b8e-335">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="19b8e-335">For more information about the WPF architecture and programming models, see the following topics:</span></span>

- [<span data-ttu-id="19b8e-336">Arquitectura de WPF</span><span class="sxs-lookup"><span data-stu-id="19b8e-336">WPF architecture</span></span>](../advanced/wpf-architecture.md)
- [<span data-ttu-id="19b8e-337">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="19b8e-337">XAML overview (WPF)</span></span>](../advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="19b8e-338">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="19b8e-338">Dependency properties overview</span></span>](../advanced/dependency-properties-overview.md)
- [<span data-ttu-id="19b8e-339">Diseño</span><span class="sxs-lookup"><span data-stu-id="19b8e-339">Layout</span></span>](../advanced/layout.md)

<span data-ttu-id="19b8e-340">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="19b8e-340">For more information about creating applications, see the following topics:</span></span>

- [<span data-ttu-id="19b8e-341">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="19b8e-341">Application development</span></span>](../app-development/index.md)
- [<span data-ttu-id="19b8e-342">Controles</span><span class="sxs-lookup"><span data-stu-id="19b8e-342">Controls</span></span>](../controls/index.md)
- [<span data-ttu-id="19b8e-343">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="19b8e-343">Data binding overview</span></span>](../data/data-binding-overview.md)
- [<span data-ttu-id="19b8e-344">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="19b8e-344">Graphics and multimedia</span></span>](../graphics-multimedia/index.md)
- [<span data-ttu-id="19b8e-345">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="19b8e-345">Documents in WPF</span></span>](../advanced/documents-in-wpf.md)

## <a name="see-also"></a><span data-ttu-id="19b8e-346">Vea también</span><span class="sxs-lookup"><span data-stu-id="19b8e-346">See also</span></span>

- [<span data-ttu-id="19b8e-347">Información general sobre</span><span class="sxs-lookup"><span data-stu-id="19b8e-347">Panels overview</span></span>](../controls/panels-overview.md)
- [<span data-ttu-id="19b8e-348">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="19b8e-348">Data templating overview</span></span>](../data/data-templating-overview.md)
- [<span data-ttu-id="19b8e-349">Crear una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="19b8e-349">Build a WPF application</span></span>](../app-development/building-a-wpf-application-wpf.md)
- [<span data-ttu-id="19b8e-350">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="19b8e-350">Styles and templates</span></span>](../controls/styles-and-templates.md)
