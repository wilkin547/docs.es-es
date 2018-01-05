---
title: "Tutorial: Mi primera aplicación de escritorio WPF"
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
- getting started [WPF], WPF
- WPF [WPF], getting started
ms.assetid: b96bed40-8946-4285-8fe4-88045ab854ed
caps.latest.revision: "71"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3667d507f4c35174c1e888c9781b5f74ffd496a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-my-first-wpf-desktop-application"></a><span data-ttu-id="f4248-102">Tutorial: Mi primera aplicación de escritorio WPF</span><span class="sxs-lookup"><span data-stu-id="f4248-102">Walkthrough: My first WPF desktop application</span></span>
<span data-ttu-id="f4248-103">Este tutorial proporciona una introducción al desarrollo de un [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] aplicación que incluye los elementos que son comunes a la mayoría [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicaciones: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] marcado, código subyacente, definiciones de aplicación, controles, diseño, enlace de datos y estilos.</span><span class="sxs-lookup"><span data-stu-id="f4248-103">This walkthrough provides an introduction to the development of a [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] application that includes the elements that are common to most [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] applications: [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup, code-behind, application definitions, controls, layout, data binding, and styles.</span></span> 
  
 <span data-ttu-id="f4248-104">Este tutorial le guía a través del desarrollo de un sencillo [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f4248-104">This walkthrough guides you through the development of a simple [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application using the following steps.</span></span> 
  
-   <span data-ttu-id="f4248-105">Definir [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para diseñar el aspecto de la aplicación [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-105">Defining [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] to design the appearance of the application's [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="f4248-106">Escribir código para crear el comportamiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-106">Writing code to build the application's behavior.</span></span> 
  
-   <span data-ttu-id="f4248-107">Crear una definición de aplicación para administrar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-107">Creating an application definition to manage the application.</span></span> 
  
-   <span data-ttu-id="f4248-108">Agregar controles y crear un diseño para crear la aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-108">Adding controls and creating the layout to compose the application [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="f4248-109">Creación de estilos para crear una apariencia coherente en toda una aplicación [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-109">Creating styles to create a consistent appearance throughout an application's [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> 
  
-   <span data-ttu-id="f4248-110">Enlace el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] a los datos en ambos rellenar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] de datos y mantener los datos y [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sincronizado.</span><span class="sxs-lookup"><span data-stu-id="f4248-110">Binding the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] to data to both populate the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] from data and keep the data and [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] synchronized.</span></span> 
  
 <span data-ttu-id="f4248-111">Al final del tutorial, habrá creado una independiente [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] aplicación que permite a los usuarios ver informes de gastos para los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f4248-111">By the end of the walkthrough, you will have built a standalone [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] application that allows users to view expense reports for selected people.</span></span> <span data-ttu-id="f4248-112">La aplicación podría estar compuesta por varios [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] páginas que se hospedan en una ventana del estilo del explorador.</span><span class="sxs-lookup"><span data-stu-id="f4248-112">The application will be composed of several [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] pages that are hosted in a browser-style window.</span></span> 
  
 <span data-ttu-id="f4248-113">El código de ejemplo que se utiliza para compilar este tutorial está disponible para [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] y [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] en [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span><span class="sxs-lookup"><span data-stu-id="f4248-113">The sample code that is used to build this walkthrough is available for both [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] and [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] at  [Introduction to Building WPF Applications](http://go.microsoft.com/fwlink/?LinkID=160008).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f4248-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f4248-114">Prerequisites</span></span>  

- [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="f4248-115"> o posterior</span><span class="sxs-lookup"><span data-stu-id="f4248-115"> or later</span></span>

<span data-ttu-id="f4248-116">Para obtener más información acerca de cómo instalar la versión más reciente de Visual Studio, vea [instalar Visual Studio](/visualstudio/install/install-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f4248-116">For more information about installing the latest version of Visual Studio, see [Install Visual Studio](/visualstudio/install/install-visual-studio).</span></span>
  
## <a name="creating-the-application-project"></a><span data-ttu-id="f4248-117">Crear el proyecto de aplicación</span><span class="sxs-lookup"><span data-stu-id="f4248-117">Creating the application project</span></span>  
 <span data-ttu-id="f4248-118">En esta sección, va a crear la infraestructura de la aplicación, que incluye una definición de aplicación, dos páginas y una imagen.</span><span class="sxs-lookup"><span data-stu-id="f4248-118">In this section, you create the application infrastructure, which includes an application definition, two pages, and an image.</span></span> 
  
1. <span data-ttu-id="f4248-119">Cree un proyecto de aplicación de WPF en Visual Basic o Visual C# denominado `ExpenseIt`.</span><span class="sxs-lookup"><span data-stu-id="f4248-119">Create a new WPF Application project in Visual Basic or Visual C# named `ExpenseIt`.</span></span> <span data-ttu-id="f4248-120">Para obtener más información, vea [Cómo: Crear un nuevo proyecto de aplicación de WPF](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span><span class="sxs-lookup"><span data-stu-id="f4248-120">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="f4248-121">Este tutorial se utiliza el <xref:System.Windows.Controls.DataGrid> control que está disponible en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="f4248-121">This walkthrough uses the <xref:System.Windows.Controls.DataGrid> control that is available in the .NET Framework 4.</span></span> <span data-ttu-id="f4248-122">Estar seguro de que su proyecto tiene como destino .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f4248-122">Be sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="f4248-123">Para obtener más información, consulte[Cómo: elegir como destino una versión de .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="f4248-123">For more information, see[How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
2. <span data-ttu-id="f4248-124">Abra Application.xaml (Visual Basic) o App.xaml (C#).</span><span class="sxs-lookup"><span data-stu-id="f4248-124">Open Application.xaml (Visual Basic) or App.xaml (C#).</span></span> 
  
     <span data-ttu-id="f4248-125">Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo define un [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] aplicación y los recursos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-125">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file defines a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application and any application resources.</span></span> <span data-ttu-id="f4248-126">También usa este archivo para especificar el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] que automáticamente se muestra cuando se inicia la aplicación; en este caso, MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-126">You also use this file to specify the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] that automatically shows when the application starts; in this case, MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="f4248-127">El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="f4248-127">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#1_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/Application.xaml#1_a)]  
  
     <span data-ttu-id="f4248-128">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="f4248-128">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/App.xaml#1)]  
  
3. <span data-ttu-id="f4248-129">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-129">Open MainWindow.xaml.</span></span> 
  
     <span data-ttu-id="f4248-130">Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo es la ventana principal de la aplicación y muestra el contenido creado en páginas.</span><span class="sxs-lookup"><span data-stu-id="f4248-130">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file is the main window of your application and displays content created in pages.</span></span> <span data-ttu-id="f4248-131">La <xref:System.Windows.Window> clase define las propiedades de una ventana, como su título, tamaño o icono y controla los eventos, por ejemplo, cerrar u ocultar.</span><span class="sxs-lookup"><span data-stu-id="f4248-131">The <xref:System.Windows.Window> class defines the properties of a window, such as its title, size, or icon, and handles events, such as closing or hiding.</span></span> 
  
4. <span data-ttu-id="f4248-132">Cambiar el <xref:System.Windows.Window> elemento a una <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="f4248-132">Change the <xref:System.Windows.Window> element to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="f4248-133">Esta aplicación irá a contenido diferente según la interacción del usuario.</span><span class="sxs-lookup"><span data-stu-id="f4248-133">This application will navigate to different content depending on the user interaction.</span></span> <span data-ttu-id="f4248-134">Por lo tanto, el método main <xref:System.Windows.Window> debe cambiarse a un <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="f4248-134">Therefore, the main <xref:System.Windows.Window> needs to be changed to a <xref:System.Windows.Navigation.NavigationWindow>.</span></span> <span data-ttu-id="f4248-135"><xref:System.Windows.Navigation.NavigationWindow>hereda todas las propiedades de <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="f4248-135"><xref:System.Windows.Navigation.NavigationWindow> inherits all the properties of <xref:System.Windows.Window>.</span></span> <span data-ttu-id="f4248-136">El <xref:System.Windows.Navigation.NavigationWindow> elemento en el archivo XAML crea una instancia de la <xref:System.Windows.Navigation.NavigationWindow> clase.</span><span class="sxs-lookup"><span data-stu-id="f4248-136">The <xref:System.Windows.Navigation.NavigationWindow> element in the XAML file creates an instance of the <xref:System.Windows.Navigation.NavigationWindow> class.</span></span> <span data-ttu-id="f4248-137">Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-137">For more information, see [Navigation Overview](../../../../docs/framework/wpf/app-development/navigation-overview.md).</span></span> 
  
5. <span data-ttu-id="f4248-138">Cambie las propiedades siguientes en el <xref:System.Windows.Navigation.NavigationWindow> elemento:</span><span class="sxs-lookup"><span data-stu-id="f4248-138">Change the following properties on the <xref:System.Windows.Navigation.NavigationWindow> element:</span></span>  
  
    -   <span data-ttu-id="f4248-139">Establecer el <xref:System.Windows.Window.Title%2A> propiedad en "ExpenseIt".</span><span class="sxs-lookup"><span data-stu-id="f4248-139">Set the <xref:System.Windows.Window.Title%2A> property to "ExpenseIt".</span></span> 
  
    -   <span data-ttu-id="f4248-140">Establecer el <xref:System.Windows.FrameworkElement.Width%2A> propiedad en 500 píxeles.</span><span class="sxs-lookup"><span data-stu-id="f4248-140">Set the <xref:System.Windows.FrameworkElement.Width%2A> property to 500 pixels.</span></span> 
  
    -   <span data-ttu-id="f4248-141">Establecer el <xref:System.Windows.FrameworkElement.Height%2A> propiedad a 350 píxeles.</span><span class="sxs-lookup"><span data-stu-id="f4248-141">Set the <xref:System.Windows.FrameworkElement.Height%2A> property to 350 pixels.</span></span> 
  
    -   <span data-ttu-id="f4248-142">Quitar el <xref:System.Windows.Controls.Grid> elementos entre el <xref:System.Windows.Navigation.NavigationWindow> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f4248-142">Remove the <xref:System.Windows.Controls.Grid> elements between the <xref:System.Windows.Navigation.NavigationWindow> tags.</span></span> 
  
     <span data-ttu-id="f4248-143">El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="f4248-143">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#2_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt/MainWindow.xaml#2_a)]  
  
     <span data-ttu-id="f4248-144">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="f4248-144">Or like this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml#2)]  
  
6. <span data-ttu-id="f4248-145">Abra MainWindow.xaml.vb o MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="f4248-145">Open MainWindow.xaml.vb or MainWindow.xaml.cs.</span></span> 
  
     <span data-ttu-id="f4248-146">Este archivo es un archivo de código subyacente que contiene código para controlar los eventos declarados en MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-146">This file is a code-behind file that contains code to handle the events declared in MainWindow.xaml.</span></span> <span data-ttu-id="f4248-147">Este archivo contiene una clase parcial para la ventana definida en código XAML.</span><span class="sxs-lookup"><span data-stu-id="f4248-147">This file contains a partial class for the window defined in XAML.</span></span> 
  
7. <span data-ttu-id="f4248-148">Si está utilizando C#, cambie la `MainWindow` clase se deriva de <xref:System.Windows.Navigation.NavigationWindow>.</span><span class="sxs-lookup"><span data-stu-id="f4248-148">If you are using C#, change the `MainWindow` class to derive from <xref:System.Windows.Navigation.NavigationWindow>.</span></span> 
  
     <span data-ttu-id="f4248-149">En Visual Basic, esto sucede automáticamente cuando se cambia la ventana en código XAML.</span><span class="sxs-lookup"><span data-stu-id="f4248-149">In Visual Basic, this happens automatically when you change the window in XAML.</span></span> 
  
     <span data-ttu-id="f4248-150">El código debe ser similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4248-150">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/MainWindow.xaml.cs#3)]
    [!code-vb[ExpenseIt#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml.vb#3)]  
  
## <a name="adding-files-to-the-application"></a><span data-ttu-id="f4248-151">Agregar archivos a la aplicación</span><span class="sxs-lookup"><span data-stu-id="f4248-151">Adding files to the application</span></span>  
 <span data-ttu-id="f4248-152">En esta sección, va a agregar dos páginas y una imagen a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-152">In this section, you add two pages and an image to the application.</span></span> 
  
1. <span data-ttu-id="f4248-153">Agregar una nueva página (WPF) al proyecto denominado `ExpenseItHome.xaml`.</span><span class="sxs-lookup"><span data-stu-id="f4248-153">Add a new Page (WPF) to the project named `ExpenseItHome.xaml`.</span></span> <span data-ttu-id="f4248-154">Para obtener más información, consulte [Cómo: agregar nuevos elementos a un proyecto de WPF](http://msdn.microsoft.com/en-us/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span><span class="sxs-lookup"><span data-stu-id="f4248-154">For more information, see [How to: Add New Items to a WPF Project](http://msdn.microsoft.com/en-us/17e6b238-fc32-4385-98ef-2f66ca09d9ad).</span></span> 
  
     <span data-ttu-id="f4248-155">Esta página es la primera que se muestra cuando se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-155">This page is the first page that is displayed when the application is launched.</span></span> <span data-ttu-id="f4248-156">Mostrará una lista de personas entre las que un usuario puede seleccionar una para mostrar el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="f4248-156">It will show a list of people from which a user can select a person to show an expense report for.</span></span> 
  
2. <span data-ttu-id="f4248-157">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-157">Open ExpenseItHome.xaml.</span></span> 
  
3. <span data-ttu-id="f4248-158">Establecer el <xref:System.Windows.Controls.Page.Title%2A> a "ExpenseIt - Home".</span><span class="sxs-lookup"><span data-stu-id="f4248-158">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - Home".</span></span> 
  
     <span data-ttu-id="f4248-159">El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="f4248-159">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#6_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml#6_a)]  
  
     <span data-ttu-id="f4248-160">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="f4248-160">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml#6)]  
  
4. <span data-ttu-id="f4248-161">Abra MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-161">Open MainWindow.xaml.</span></span> 
  
5. <span data-ttu-id="f4248-162">Establecer el <xref:System.Windows.Navigation.NavigationWindow.Source%2A> propiedad en el <xref:System.Windows.Navigation.NavigationWindow> en "ExpenseItHome.xaml".</span><span class="sxs-lookup"><span data-stu-id="f4248-162">Set the <xref:System.Windows.Navigation.NavigationWindow.Source%2A> property on the <xref:System.Windows.Navigation.NavigationWindow> to "ExpenseItHome.xaml".</span></span> 
  
     <span data-ttu-id="f4248-163">Así se establece ExpenseItHome.xaml como la primera página que se abre al iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-163">This sets ExpenseItHome.xaml to be the first page opened when the application starts.</span></span> <span data-ttu-id="f4248-164">El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="f4248-164">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#7_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/MainWindow.xaml#7_a)]  
  
     <span data-ttu-id="f4248-165">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="f4248-165">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/MainWindow.xaml#7)]  
  
6. <span data-ttu-id="f4248-166">Agregar una nueva página (WPF) al proyecto denominado `ExpenseReportPage.xaml`.</span><span class="sxs-lookup"><span data-stu-id="f4248-166">Add a new Page (WPF) to the project named `ExpenseReportPage.xaml`.</span></span> 
  
     <span data-ttu-id="f4248-167">Esta página mostrará el informe de gastos de la persona que se haya seleccionado en ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-167">This page will show the expense report for the person that is selected on ExpenseItHome.xaml.</span></span> 
  
7. <span data-ttu-id="f4248-168">Abra ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-168">Open ExpenseReportPage.xaml.</span></span> 
  
8. <span data-ttu-id="f4248-169">Establecer el <xref:System.Windows.Controls.Page.Title%2A> en "ExpenseIt - ver gastos".</span><span class="sxs-lookup"><span data-stu-id="f4248-169">Set the <xref:System.Windows.Controls.Page.Title%2A> to "ExpenseIt - View Expense".</span></span> 
  
     <span data-ttu-id="f4248-170">El [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] debe ser similar en Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="f4248-170">Your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] should look like this in Visual Basic:</span></span>  
  
    [!code-xaml[ExpenseIt#4_A](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml#4_a)]  
  
     <span data-ttu-id="f4248-171">O a este en C#:</span><span class="sxs-lookup"><span data-stu-id="f4248-171">Or this in C#:</span></span>  
  
    [!code-xaml[ExpenseIt#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml#4)]  
  
9. <span data-ttu-id="f4248-172">Abra ExpenseItHome.xaml.vb y ExpenseReportPage.xaml.vb o ExpenseItHome.xaml.cs y ExpenseReportPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="f4248-172">Open ExpenseItHome.xaml.vb and ExpenseReportPage.xaml.vb, or ExpenseItHome.xaml.cs and ExpenseReportPage.xaml.cs.</span></span> 
  
     <span data-ttu-id="f4248-173">Cuando se crea un archivo de página, Visual Studio crea automáticamente un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="f4248-173">When you create a new Page file, Visual Studio automatically creates a code behind file.</span></span> <span data-ttu-id="f4248-174">Estos archivos de código subyacente controlan la lógica para responder a la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="f4248-174">These code-behind files handle the logic for responding to user input.</span></span> 
  
     <span data-ttu-id="f4248-175">El código debe ser similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4248-175">Your code should look like this.</span></span> 
  
    [!code-csharp[ExpenseIt#2_5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt2/ExpenseItHome.xaml.cs#2_5)]
    [!code-vb[ExpenseIt#2_5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseItHome.xaml.vb#2_5)]  
  
    [!code-csharp[ExpenseIt#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt/ExpenseReportPage.xaml.cs#5)]
    [!code-vb[ExpenseIt#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt1_A/ExpenseReportPage.xaml.vb#5)]  
  
10. <span data-ttu-id="f4248-176">Agregue una imagen denominada watermark.png al proyecto.</span><span class="sxs-lookup"><span data-stu-id="f4248-176">Add an image named watermark.png to the project.</span></span> <span data-ttu-id="f4248-177">Puede crear su propia imagen o copiar el archivo del código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4248-177">You can either create your own image, or copy the file from the sample code.</span></span> <span data-ttu-id="f4248-178">Para obtener más información, consulte [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="f4248-178">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/en-us/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span> 

## <a name="building-and-running-the-application"></a><span data-ttu-id="f4248-179">Compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f4248-179">Building and running the application</span></span>  
 <span data-ttu-id="f4248-180">En esta sección, va a compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-180">In this section, you build and run the application.</span></span> 
  
1. <span data-ttu-id="f4248-181">Compile y ejecute la aplicación presionando F5 o seleccione **Iniciar depuración** desde el **depurar** menú.</span><span class="sxs-lookup"><span data-stu-id="f4248-181">Build and run the application by pressing F5 or select **Start Debugging** from the **Debug** menu.</span></span> 
  
     <span data-ttu-id="f4248-182">En la siguiente ilustración muestra la aplicación con el <xref:System.Windows.Navigation.NavigationWindow> botones.</span><span class="sxs-lookup"><span data-stu-id="f4248-182">The following illustration shows the application with the <xref:System.Windows.Navigation.NavigationWindow> buttons.</span></span> 
  
     <span data-ttu-id="f4248-183">![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span><span class="sxs-lookup"><span data-stu-id="f4248-183">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure1.png "GettingStartedFigure1")</span></span>  
  
2. <span data-ttu-id="f4248-184">Cierre la aplicación para volver a [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-184">Close the application to return to [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span> 
  
## <a name="creating-the-layout"></a><span data-ttu-id="f4248-185">Crear un diseño</span><span class="sxs-lookup"><span data-stu-id="f4248-185">Creating the layout</span></span>  
 <span data-ttu-id="f4248-186">Diseño proporciona una manera ordenada para colocar [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos y también administra el tamaño y la posición de dichos elementos cuando un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se cambia el tamaño.</span><span class="sxs-lookup"><span data-stu-id="f4248-186">Layout provides an ordered way to place [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements, and also manages the size and position of those elements when a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is resized.</span></span> <span data-ttu-id="f4248-187">Normalmente, se crea un diseño con uno de los controles de diseño siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4248-187">You typically create a layout with one of the following layout controls:</span></span>  
  
-   <xref:System.Windows.Controls.Canvas>  
  
-   <xref:System.Windows.Controls.DockPanel>  
  
-   <xref:System.Windows.Controls.Grid>  
  
-   <xref:System.Windows.Controls.StackPanel>  
  
-   <xref:System.Windows.Controls.VirtualizingStackPanel>  
  
-   <xref:System.Windows.Controls.WrapPanel>  
  
 <span data-ttu-id="f4248-188">Cada uno de estos controles de diseño admite un tipo especial de diseño para sus elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="f4248-188">Each of these layout controls supports a special type of layout for its child elements.</span></span> <span data-ttu-id="f4248-189">Puede cambiar el tamaño de las páginas de ExpenseIt, y cada página tiene elementos organizados en horizontal y vertical junto con otros elementos.</span><span class="sxs-lookup"><span data-stu-id="f4248-189">ExpenseIt pages can be resized, and each page has elements that are arranged horizontally and vertically alongside other elements.</span></span> <span data-ttu-id="f4248-190">Por lo tanto, el <xref:System.Windows.Controls.Grid> es el elemento de diseño ideal para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-190">Consequently, the <xref:System.Windows.Controls.Grid> is the ideal layout element for the application.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="f4248-191">Para obtener más información acerca de <xref:System.Windows.Controls.Panel> elementos, consulte [paneles de información general sobre](../../../../docs/framework/wpf/controls/panels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-191">For more information about <xref:System.Windows.Controls.Panel> elements, see [Panels Overview](../../../../docs/framework/wpf/controls/panels-overview.md).</span></span> <span data-ttu-id="f4248-192">Para obtener más información acerca del diseño, vea [diseño](../../../../docs/framework/wpf/advanced/layout.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-192">For more information about layout, see [Layout](../../../../docs/framework/wpf/advanced/layout.md).</span></span> 
  
 <span data-ttu-id="f4248-193">En la sección, se crea una tabla de una sola columna con tres filas y un margen de 10 píxeles agregando definiciones de columna y fila a la <xref:System.Windows.Controls.Grid> en ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-193">In the section, you create a single-column table with three rows and a 10-pixel margin by adding column and row definitions to the <xref:System.Windows.Controls.Grid> in ExpenseItHome.xaml.</span></span> 
  
1. <span data-ttu-id="f4248-194">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-194">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-195">Establecer el <xref:System.Windows.FrameworkElement.Margin%2A> propiedad en el <xref:System.Windows.Controls.Grid> elemento a "10,0,10,10", que corresponde a los márgenes izquierdo, superior, derecho e inferior.</span><span class="sxs-lookup"><span data-stu-id="f4248-195">Set the <xref:System.Windows.FrameworkElement.Margin%2A> property on the <xref:System.Windows.Controls.Grid> element to "10,0,10,10" which corresponds to left, top, right and bottom margins.</span></span> 
  
3. <span data-ttu-id="f4248-196">Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entre el <xref:System.Windows.Controls.Grid> etiquetas para crear las definiciones de fila y columna.</span><span class="sxs-lookup"><span data-stu-id="f4248-196">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags to create the row and column definitions.</span></span> 
  
    [!code-xaml[ExpenseIt#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#8)]  
  
     <span data-ttu-id="f4248-197">El <xref:System.Windows.Controls.RowDefinition.Height%2A> de dos filas se establece en <xref:System.Windows.GridLength.Auto%2A> lo que significa que se dimensionarán las filas se base en el contenido de las filas.</span><span class="sxs-lookup"><span data-stu-id="f4248-197">The <xref:System.Windows.Controls.RowDefinition.Height%2A> of two rows is set to <xref:System.Windows.GridLength.Auto%2A> which means that the rows will be sized base on the content in the rows.</span></span> <span data-ttu-id="f4248-198">El valor predeterminado <xref:System.Windows.Controls.RowDefinition.Height%2A> es <xref:System.Windows.GridUnitType.Star> ajuste de tamaño, lo que significa que la fila será una proporción ponderada del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="f4248-198">The default <xref:System.Windows.Controls.RowDefinition.Height%2A> is <xref:System.Windows.GridUnitType.Star> sizing, which means that the row will be a weighted proportion of the available space.</span></span> <span data-ttu-id="f4248-199">Por ejemplo, si dos filas tienen un alto de "*", ambas tendrán un alto que sea la mitad del espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="f4248-199">For example if two rows each have a height of "*", they will each have a height that is half of the available space.</span></span>  
  
     <span data-ttu-id="f4248-200">Su <xref:System.Windows.Controls.Grid> debería ser ahora similar el siguiente código XAML:</span><span class="sxs-lookup"><span data-stu-id="f4248-200">Your <xref:System.Windows.Controls.Grid> should now look like the following XAML:</span></span>  
  
    [!code-xaml[ExpenseIt#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt3/ExpenseItHome.xaml#9)]  
  
## <a name="adding-controls"></a><span data-ttu-id="f4248-201">Agregar controles</span><span class="sxs-lookup"><span data-stu-id="f4248-201">Adding controls</span></span>  
 <span data-ttu-id="f4248-202">En esta sección, la página principal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualiza para mostrar una lista de personas que los usuarios pueden seleccionar para mostrar el informe de gastos para un rol seleccionado.</span><span class="sxs-lookup"><span data-stu-id="f4248-202">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated to show a list of people that users can select from to show the expense report for a selected person.</span></span> <span data-ttu-id="f4248-203">Los controles son objetos de interfaz de usuario que permiten a los usuarios interactuar con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-203">Controls are UI objects that allow users to interact with your application.</span></span> <span data-ttu-id="f4248-204">Para obtener más información, consulte [Controles](../../../../docs/framework/wpf/controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-204">For more information, see [Controls](../../../../docs/framework/wpf/controls/index.md).</span></span> 
  
 <span data-ttu-id="f4248-205">Para crear esta [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], se agregan los elementos siguientes a ExpenseItHome.xaml:</span><span class="sxs-lookup"><span data-stu-id="f4248-205">To create this [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], the following elements are added to ExpenseItHome.xaml:</span></span>  
  
-   <span data-ttu-id="f4248-206"><xref:System.Windows.Controls.ListBox>(para obtener la lista de personas).</span><span class="sxs-lookup"><span data-stu-id="f4248-206"><xref:System.Windows.Controls.ListBox> (for the list of people).</span></span> 
  
-   <span data-ttu-id="f4248-207"><xref:System.Windows.Controls.Label>(para el encabezado de lista).</span><span class="sxs-lookup"><span data-stu-id="f4248-207"><xref:System.Windows.Controls.Label> (for the list header).</span></span> 
  
-   <span data-ttu-id="f4248-208"><xref:System.Windows.Controls.Button>(debe hacer clic para ver el informe de gastos de la persona que está seleccionada en la lista).</span><span class="sxs-lookup"><span data-stu-id="f4248-208"><xref:System.Windows.Controls.Button> (to click to view the expense report for the person that is selected in the list).</span></span> 
  
 <span data-ttu-id="f4248-209">Cada control se coloca en una fila de la <xref:System.Windows.Controls.Grid> estableciendo el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> propiedad adjunta.</span><span class="sxs-lookup"><span data-stu-id="f4248-209">Each control is placed in a row of the <xref:System.Windows.Controls.Grid> by setting the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> attached property.</span></span> <span data-ttu-id="f4248-210">Para obtener más información acerca de las propiedades asociadas, consulte [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-210">For more information about attached properties, see [Attached Properties Overview](../../../../docs/framework/wpf/advanced/attached-properties-overview.md).</span></span> 
  
1. <span data-ttu-id="f4248-211">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-211">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-212">Agregue el siguiente [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] entre el <xref:System.Windows.Controls.Grid> etiquetas.</span><span class="sxs-lookup"><span data-stu-id="f4248-212">Add the following [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
    [!code-xaml[ExpenseIt#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt4/ExpenseItHome.xaml#10)]  
  
3. <span data-ttu-id="f4248-213">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-213">Build and run the application.</span></span> 
  
 <span data-ttu-id="f4248-214">En la siguiente ilustración se muestran los controles creados por el código XAML en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f4248-214">The following illustration shows the controls that are created by the XAML in this section.</span></span> 
  
 <span data-ttu-id="f4248-215">![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span><span class="sxs-lookup"><span data-stu-id="f4248-215">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure2.png "GettingStartedFigure2")</span></span>  
  
## <a name="adding-an-image-and-a-title"></a><span data-ttu-id="f4248-216">Agregar una imagen y un título</span><span class="sxs-lookup"><span data-stu-id="f4248-216">Adding an image and a title</span></span>  
 <span data-ttu-id="f4248-217">En esta sección, la página principal [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] se actualiza con una imagen y un título de página.</span><span class="sxs-lookup"><span data-stu-id="f4248-217">In this section, the home page [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] is updated with an image and a page title.</span></span> 
  
1. <span data-ttu-id="f4248-218">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-218">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-219">Agregue otra columna a la <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> con un fijo <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de 230 píxeles.</span><span class="sxs-lookup"><span data-stu-id="f4248-219">Add another column to the <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> with a fixed <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of 230 pixels.</span></span> 
  
    [!code-xaml[ExpenseIt#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11)]  
  
3. <span data-ttu-id="f4248-220">Agregue otra fila a la <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4248-220">Add another row to the <xref:System.Windows.Controls.Grid.RowDefinitions%2A>.</span></span> 
  
    [!code-xaml[ExpenseIt#11b](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#11b)]  
  
4. <span data-ttu-id="f4248-221">Mover los controles a la segunda columna estableciendo <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> en 1.</span><span class="sxs-lookup"><span data-stu-id="f4248-221">Move the controls to the second column by setting <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> to 1.</span></span> <span data-ttu-id="f4248-222">Baje cada control una fila aumentando el <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> en 1.</span><span class="sxs-lookup"><span data-stu-id="f4248-222">Move each control down a row, by increasing the <xref:System.Windows.Controls.Grid.Row%2A?displayProperty=nameWithType> by 1.</span></span> 
  
    [!code-xaml[ExpenseIt#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#12)]  
  
5. <span data-ttu-id="f4248-223">Establecer el <xref:System.Windows.Controls.Panel.Background%2A> de la <xref:System.Windows.Controls.Grid> sea el archivo de imagen watermark.png.</span><span class="sxs-lookup"><span data-stu-id="f4248-223">Set the <xref:System.Windows.Controls.Panel.Background%2A> of the <xref:System.Windows.Controls.Grid> to be the watermark.png image file.</span></span> 
  
    [!code-xaml[ExpenseIt#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#14)]  
  
6. <span data-ttu-id="f4248-224">Antes de la <xref:System.Windows.Controls.Border>, agregue un <xref:System.Windows.Controls.Label> con el contenido "View Expense Report" para que sea el título de la página.</span><span class="sxs-lookup"><span data-stu-id="f4248-224">Before the <xref:System.Windows.Controls.Border>, add a <xref:System.Windows.Controls.Label> with the content "View Expense Report" to be the title of the page.</span></span> 
  
    [!code-xaml[ExpenseIt#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt5/ExpenseItHome.xaml#13)]  
  
7. <span data-ttu-id="f4248-225">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-225">Build and run the application.</span></span> 
  
 <span data-ttu-id="f4248-226">En la ilustración siguiente se muestran los resultados de esta sección.</span><span class="sxs-lookup"><span data-stu-id="f4248-226">The following illustration shows the results of this section.</span></span> 
  
 <span data-ttu-id="f4248-227">![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span><span class="sxs-lookup"><span data-stu-id="f4248-227">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure3.png "GettingStartedFigure3")</span></span>  
  
## <a name="adding-code-to-handle-events"></a><span data-ttu-id="f4248-228">Agregar código para controlar eventos</span><span class="sxs-lookup"><span data-stu-id="f4248-228">Adding code to handle events</span></span>  
  
1. <span data-ttu-id="f4248-229">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-229">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-230">Agregar un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para el <xref:System.Windows.Controls.Button> elemento.</span><span class="sxs-lookup"><span data-stu-id="f4248-230">Add a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to the <xref:System.Windows.Controls.Button> element.</span></span> <span data-ttu-id="f4248-231">Para obtener más información, consulte [Cómo: crear un controlador de eventos Simple](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span><span class="sxs-lookup"><span data-stu-id="f4248-231">For more information, see [How to: Create a Simple Event Handler](http://msdn.microsoft.com/en-us/b1456e07-9dec-4354-99cf-18666b64f480).</span></span> 
  
    [!code-xaml[ExpenseIt#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml#15)]  
  
3. <span data-ttu-id="f4248-232">Abra el archivo ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="f4248-232">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="f4248-233">Agregue el código siguiente a la <xref:System.Windows.Controls.Primitives.ButtonBase.Click> el controlador de eventos, lo que hace que la ventana para navegar hasta el archivo ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-233">Add the following code to the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler, which causes the window to navigate to the ExpenseReportPage.xaml file.</span></span> 
  
    [!code-csharp[ExpenseIt#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseItHome.xaml.cs#16)]
    [!code-vb[ExpenseIt#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt6/ExpenseItHome.xaml.vb#16)]  
  
## <a name="creating-the-ui-for-expensereportpage"></a><span data-ttu-id="f4248-234">Crear la interfaz de usuario para ExpenseReportPage</span><span class="sxs-lookup"><span data-stu-id="f4248-234">Creating the UI for ExpenseReportPage</span></span>  
 <span data-ttu-id="f4248-235">ExpenseReportPage.xaml muestra el informe de gastos de la persona que se seleccionó en ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-235">ExpenseReportPage.xaml displays the expense report for the person that was selected on the ExpenseItHome.xaml.</span></span> <span data-ttu-id="f4248-236">En esta sección se agregan controles y se crea el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-236">This section adds controls and creates the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for ExpenseReportPage.xaml.</span></span> <span data-ttu-id="f4248-237">En esta sección también agrega los colores de fondo y relleno a los distintos [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos.</span><span class="sxs-lookup"><span data-stu-id="f4248-237">This section also adds background and fill colors to the various [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements.</span></span> 
  
1. <span data-ttu-id="f4248-238">Abra ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-238">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-239">Agregue el código XAML siguiente entre las etiquetas <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="f4248-239">Add the following XAML between the <xref:System.Windows.Controls.Grid> tags.</span></span> 
  
     <span data-ttu-id="f4248-240">Esta interfaz de usuario es similar a la interfaz de usuario creada en ExpenseItHome.xaml salvo los datos del informe se muestran en un <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="f4248-240">This UI is similar to the UI created on ExpenseItHome.xaml except the report data is displayed in a <xref:System.Windows.Controls.DataGrid>.</span></span> 
  
    [!code-xaml[ExpenseIt#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt6/ExpenseReportPage.xaml#17)]  
  
3. <span data-ttu-id="f4248-241">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-241">Build and run the application.</span></span> 
  
    > [!NOTE]
    >  <span data-ttu-id="f4248-242">Si se produce un error que el <xref:System.Windows.Controls.DataGrid> no se encontró o no existe, asegúrese de que el proyecto tiene como destino .NET Framework 4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="f4248-242">If you get an error that the <xref:System.Windows.Controls.DataGrid> was not found or does not exist, make sure that your project targets the .NET Framework 4 or later.</span></span> <span data-ttu-id="f4248-243">Para obtener más información, consulte [Cómo: Usar como destino una versión de .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span><span class="sxs-lookup"><span data-stu-id="f4248-243">For more information, see [How to: Target a Version of the .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).</span></span> 
  
4. <span data-ttu-id="f4248-244">Haga clic en el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="f4248-244">Click the **View** button.</span></span> 
  
     <span data-ttu-id="f4248-245">Se mostrará la página de informe de gastos</span><span class="sxs-lookup"><span data-stu-id="f4248-245">The expense report page appears.</span></span> 
  
 <span data-ttu-id="f4248-246">La siguiente ilustración muestra el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elementos agregados a ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-246">The following illustration shows the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] elements added to ExpenseReportPage.xaml.</span></span> <span data-ttu-id="f4248-247">Observe que el botón de navegación hacia atrás está habilitado.</span><span class="sxs-lookup"><span data-stu-id="f4248-247">Notice that the back navigation button is enabled.</span></span> 
  
 <span data-ttu-id="f4248-248">![Captura de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span><span class="sxs-lookup"><span data-stu-id="f4248-248">![ExpenseIt sample screen shot](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure4.png "GettingStartedFigure4")</span></span>  
  
## <a name="styling-controls"></a><span data-ttu-id="f4248-249">Aplicar estilos a controles</span><span class="sxs-lookup"><span data-stu-id="f4248-249">Styling controls</span></span>  
 <span data-ttu-id="f4248-250">La apariencia de varios elementos a menudo puede ser el mismo para todos los elementos del mismo tipo en un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-250">The appearance of various elements can often be the same for all elements of the same type in a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].</span></span> [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]<span data-ttu-id="f4248-251"> utiliza estilos para permitir que las apariencias sean reutilizables en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="f4248-251"> uses styles to make appearances reusable across multiple elements.</span></span> <span data-ttu-id="f4248-252">La reutilización de estilos ayuda a simplificar [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la creación y administración.</span><span class="sxs-lookup"><span data-stu-id="f4248-252">The reusability of styles helps to simplify [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] creation and management.</span></span> <span data-ttu-id="f4248-253">Para obtener más información sobre los estilos, consulte [estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-253">For more information about styles, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span> <span data-ttu-id="f4248-254">En esta sección se reemplazan los atributos de cada elemento que se definieron en pasos anteriores por estilos.</span><span class="sxs-lookup"><span data-stu-id="f4248-254">This section replaces the per-element attributes that were defined in previous steps with styles.</span></span> 
  
1. <span data-ttu-id="f4248-255">Abra Application.xaml o App.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-255">Open Application.xaml or App.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-256">Agregue el código XAML siguiente entre las <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> etiquetas:</span><span class="sxs-lookup"><span data-stu-id="f4248-256">Add the following XAML between the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> tags:</span></span>  
  
    [!code-xaml[ExpenseIt#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/App.xaml#18)]  
  
     <span data-ttu-id="f4248-257">Esto [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] agrega los estilos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4248-257">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] adds the following styles:</span></span>  
  
    -  <span data-ttu-id="f4248-258">`headerTextStyle`: para dar formato al título de la página <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="f4248-258">`headerTextStyle`: To format the page title <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="f4248-259">`labelStyle`: para dar formato a los controles <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="f4248-259">`labelStyle`: To format the <xref:System.Windows.Controls.Label> controls.</span></span> 
  
    -  <span data-ttu-id="f4248-260">`columnHeaderStyle`: para dar formato a <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span><span class="sxs-lookup"><span data-stu-id="f4248-260">`columnHeaderStyle`: To format the <xref:System.Windows.Controls.Primitives.DataGridColumnHeader>.</span></span> 
  
    -  <span data-ttu-id="f4248-261">`listHeaderStyle`: para dar formato a los controles del encabezado de lista <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="f4248-261">`listHeaderStyle`: To format the list header <xref:System.Windows.Controls.Border> controls.</span></span> 
  
    -  <span data-ttu-id="f4248-262">`listHeaderTextStyle`: Para dar formato al encabezado de lista <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="f4248-262">`listHeaderTextStyle`: To format the list header <xref:System.Windows.Controls.Label>.</span></span> 
  
    -  <span data-ttu-id="f4248-263">`buttonStyle`: Para dar formato a la <xref:System.Windows.Controls.Button> en ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-263">`buttonStyle`: To format the <xref:System.Windows.Controls.Button> on ExpenseItHome.xaml.</span></span> 
  
     <span data-ttu-id="f4248-264">Tenga en cuenta que los estilos son recursos y elementos secundarios de la <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> elemento property.</span><span class="sxs-lookup"><span data-stu-id="f4248-264">Notice that the styles are resources and children of the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property element.</span></span> <span data-ttu-id="f4248-265">En esta ubicación, los estilos se aplican a todos los elementos de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-265">In this location, the styles are applied to all the elements in an application.</span></span> <span data-ttu-id="f4248-266">Para obtener un ejemplo del uso de recursos en un [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplicación, consulte [recursos de la aplicación de uso](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-266">For an example of using resources in a [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application, see [Use Application Resources](../../../../docs/framework/wpf/advanced/how-to-use-application-resources.md).</span></span> 
  
3. <span data-ttu-id="f4248-267">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-267">Open ExpenseItHome.xaml.</span></span> 
  
4. <span data-ttu-id="f4248-268">Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4248-268">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseItHome.xaml#19)]  
  
     <span data-ttu-id="f4248-269">Las propiedades como <xref:System.Windows.VerticalAlignment> y <xref:System.Windows.Media.FontFamily> que definen la apariencia de cada control se quitan y reemplazan aplicando los estilos.</span><span class="sxs-lookup"><span data-stu-id="f4248-269">The properties such as <xref:System.Windows.VerticalAlignment> and <xref:System.Windows.Media.FontFamily> that define the look of each control are removed and replaced by applying the styles.</span></span> <span data-ttu-id="f4248-270">Por ejemplo, el `headerTextStyle` se aplica a "View Expense Report" <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="f4248-270">For example, the `headerTextStyle` is applied to the "View Expense Report" <xref:System.Windows.Controls.Label>.</span></span> 
  
5. <span data-ttu-id="f4248-271">Abra ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-271">Open ExpenseReportPage.xaml.</span></span> 
  
6. <span data-ttu-id="f4248-272">Reemplace todo entre los <xref:System.Windows.Controls.Grid> elementos con el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4248-272">Replace everything between the <xref:System.Windows.Controls.Grid> elements with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt7/ExpenseReportPage.xaml#20)]  
  
     <span data-ttu-id="f4248-273">Esto agrega estilos a los elementos <xref:System.Windows.Controls.Label> y <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="f4248-273">This adds styles to the <xref:System.Windows.Controls.Label> and <xref:System.Windows.Controls.Border> elements.</span></span> 
  
7. <span data-ttu-id="f4248-274">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-274">Build and run the application.</span></span> 
  
     <span data-ttu-id="f4248-275">Después de agregar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en esta sección, la aplicación tiene el mismo aspecto igual que antes de que se actualiza con los estilos.</span><span class="sxs-lookup"><span data-stu-id="f4248-275">After adding the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in this section, the application looks the same as it did before being updated with styles.</span></span> 
  
## <a name="binding-data-to-a-control"></a><span data-ttu-id="f4248-276">Enlazar datos a un control</span><span class="sxs-lookup"><span data-stu-id="f4248-276">Binding data to a control</span></span>  
 <span data-ttu-id="f4248-277">En esta sección, creará el [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] datos que está enlazados a varios controles.</span><span class="sxs-lookup"><span data-stu-id="f4248-277">In this section, you create the [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] data that is bound to various controls.</span></span> 
  
1. <span data-ttu-id="f4248-278">Abra ExpenseItHome.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-278">Open ExpenseItHome.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-279">Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue el siguiente código XAML para crear un <xref:System.Windows.Data.XmlDataProvider> que contiene los datos de cada persona.</span><span class="sxs-lookup"><span data-stu-id="f4248-279">After the opening <xref:System.Windows.Controls.Grid> element, add the following XAML to create an <xref:System.Windows.Data.XmlDataProvider> that contains the data for each person.</span></span> 
  
     <span data-ttu-id="f4248-280">Los datos se crean como un <xref:System.Windows.Controls.Grid> recursos.</span><span class="sxs-lookup"><span data-stu-id="f4248-280">The data is created as a <xref:System.Windows.Controls.Grid> resource.</span></span> <span data-ttu-id="f4248-281">Normalmente esto se cargaría como archivo, pero los datos se agregan en línea para simplificar.</span><span class="sxs-lookup"><span data-stu-id="f4248-281">Normally this would be loaded as a file, but for simplicity the data is added inline.</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#23](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#23)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
3. <span data-ttu-id="f4248-282">En el <xref:System.Windows.Controls.Grid> recursos, agregue el siguiente <xref:System.Windows.DataTemplate>, que define cómo mostrar los datos en el <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="f4248-282">In the <xref:System.Windows.Controls.Grid> resource, add the following <xref:System.Windows.DataTemplate>, which defines how to display the data in the <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="f4248-283">Para más información sobre las plantillas de datos, consulte [Información general sobre plantillas de datos](../../../../docs/framework/wpf/data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-283">For more information about data templates, see [Data Templating Overview](../../../../docs/framework/wpf/data/data-templating-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#21](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#21)]  
    [!code-xaml[ExpenseIt#24](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#24)]  
    [!code-xaml[ExpenseIt#22](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#22)]  
  
4. <span data-ttu-id="f4248-284">Reemplazar el existente <xref:System.Windows.Controls.ListBox> con el código XAML siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4248-284">Replace the existing <xref:System.Windows.Controls.ListBox> with the following XAML.</span></span> 
  
    [!code-xaml[ExpenseIt#25](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml#25)]  
  
     <span data-ttu-id="f4248-285">Este código XAML enlaza la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de la <xref:System.Windows.Controls.ListBox> al origen de datos y aplica la plantilla de datos como el <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="f4248-285">This XAML binds the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> property of the <xref:System.Windows.Controls.ListBox> to the data source and applies the data template as the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>.</span></span> 
  
## <a name="connecting-data-to-controls"></a><span data-ttu-id="f4248-286">Conectar los datos a controles</span><span class="sxs-lookup"><span data-stu-id="f4248-286">Connecting data to controls</span></span>  
 <span data-ttu-id="f4248-287">En esta sección, se escribe el código que recupera el elemento actual que está seleccionado en la lista de personas en la página ExpenseItHome.xaml y pasa su referencia al constructor de `ExpenseReportPage` durante la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="f4248-287">In this section, you write the code that retrieves the current item that is selected in the list of people on the ExpenseItHome.xaml page, and passes its reference to the constructor of `ExpenseReportPage` during instantiation.</span></span> <span data-ttu-id="f4248-288">`ExpenseReportPage` establece el contexto de datos con el elemento pasado, que es a lo que los controles definidos en ExpenseReportPage.xaml se enlazarán.</span><span class="sxs-lookup"><span data-stu-id="f4248-288">`ExpenseReportPage` sets its data context with the passed item, which is what the controls defined in ExpenseReportPage.xaml will bind to.</span></span> 
  
1. <span data-ttu-id="f4248-289">Abra ExpenseReportPage.xaml.vb o ExpenseReportPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="f4248-289">Open ExpenseReportPage.xaml.vb or ExpenseReportPage.xaml.cs.</span></span> 
  
2. <span data-ttu-id="f4248-290">Agregue un constructor que acepte un objeto, para que pueda pasar los datos del informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f4248-290">Add a constructor that takes an object so you can pass the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#26](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseReportPage.xaml.cs#26)]
    [!code-vb[ExpenseIt#26](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseReportPage.xaml.vb#26)]  
  
3. <span data-ttu-id="f4248-291">Abra el archivo ExpenseItHome.xaml.vb o ExpenseItHome.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="f4248-291">Open ExpenseItHome.xaml.vb or ExpenseItHome.xaml.cs.</span></span> 
  
4. <span data-ttu-id="f4248-292">Cambiar el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos para llamar al constructor nuevo pasar los datos de informe de gastos de la persona seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f4248-292">Change the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler to call the new constructor passing the expense report data of the selected person.</span></span> 
  
    [!code-csharp[ExpenseIt#27](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt8/ExpenseItHome.xaml.cs#27)]
    [!code-vb[ExpenseIt#27](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ExpenseIt/VB/ExpenseIt8/ExpenseItHome.xaml.vb#27)]  
  
## <a name="styling-data-with-data-templates"></a><span data-ttu-id="f4248-293">Datos de aplicación de estilos con las plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="f4248-293">Styling data with data templates</span></span>  
 <span data-ttu-id="f4248-294">En esta sección, se actualiza el [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] para cada elemento de los datos enlazados listas mediante el uso de plantillas de datos.</span><span class="sxs-lookup"><span data-stu-id="f4248-294">In this section, you update the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] for each item in the data bound lists by using data templates.</span></span> 
  
1. <span data-ttu-id="f4248-295">Abra ExpenseReportPage.xaml.</span><span class="sxs-lookup"><span data-stu-id="f4248-295">Open ExpenseReportPage.xaml.</span></span> 
  
2. <span data-ttu-id="f4248-296">Enlazar el contenido de la "Name" y "Departamento" <xref:System.Windows.Controls.Label> propiedad de origen de elementos a los datos apropiados.</span><span class="sxs-lookup"><span data-stu-id="f4248-296">Bind the content of the "Name" and "Department" <xref:System.Windows.Controls.Label> elements to the appropriate data source property.</span></span> <span data-ttu-id="f4248-297">Para más información sobre el enlace de datos, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4248-297">For more information about data binding, see [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).</span></span> 
  
    [!code-xaml[ExpenseIt#31](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#31)]  
  
3. <span data-ttu-id="f4248-298">Después de la apertura <xref:System.Windows.Controls.Grid> elemento, agregue las siguientes plantillas de datos, que definen cómo se muestran los datos de informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="f4248-298">After the opening <xref:System.Windows.Controls.Grid> element, add the following data templates, which define how to display the expense report data.</span></span>  
    [!code-xaml[ExpenseIt#30](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#30)]  
  
4. <span data-ttu-id="f4248-299">Aplicar las plantillas a la <xref:System.Windows.Controls.DataGrid> datos de informe de las columnas que muestran el gasto.</span><span class="sxs-lookup"><span data-stu-id="f4248-299">Apply the templates to the <xref:System.Windows.Controls.DataGrid> columns that display the expense report data.</span></span> 
  
    [!code-xaml[ExpenseIt#32](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ExpenseIt/CSharp/ExpenseIt9/ExpenseReportPage.xaml#32)]  
  
5. <span data-ttu-id="f4248-300">Compile y ejecute la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-300">Build and run the application.</span></span> 
  
6. <span data-ttu-id="f4248-301">Seleccione una persona y haga clic en el **vista** botón.</span><span class="sxs-lookup"><span data-stu-id="f4248-301">Select a person and click the **View** button.</span></span> 
  
 <span data-ttu-id="f4248-302">La ilustración siguiente muestra ambas páginas de la aplicación ExpenseIt con los controles, el diseño, los estilos, el enlace de datos y las plantillas de datos aplicadas.</span><span class="sxs-lookup"><span data-stu-id="f4248-302">The following illustration shows both pages of the ExpenseIt application with controls, layout, styles, data binding, and data templates applied.</span></span> 
  
 <span data-ttu-id="f4248-303">![Capturas de pantalla de ejemplo ExpenseIt](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span><span class="sxs-lookup"><span data-stu-id="f4248-303">![ExpenseIt sample screen shots](../../../../docs/framework/wpf/getting-started/media/gettingstartedfigure5.png "GettingStartedFigure5")</span></span>  
  
## <a name="best-practices"></a><span data-ttu-id="f4248-304">Procedimientos recomendados</span><span class="sxs-lookup"><span data-stu-id="f4248-304">Best practices</span></span>  
 <span data-ttu-id="f4248-305">En este ejemplo, se ilustra una característica específica de WPF y, por consiguiente, no sigue los procedimientos recomendados para el desarrollo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f4248-305">This sample demonstrates a specific feature of WPF and, consequently, does not follow application development best practices.</span></span> <span data-ttu-id="f4248-306">Para una completa cobertura de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] prácticas recomendadas de desarrollo de aplicaciones, vea los temas siguientes según corresponda:</span><span class="sxs-lookup"><span data-stu-id="f4248-306">For comprehensive coverage of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] and the [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application development best practices, see the following topics as appropriate:</span></span>  
  
-   <span data-ttu-id="f4248-307">Accesibilidad: [Procedimientos de accesibilidad recomendados](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span><span class="sxs-lookup"><span data-stu-id="f4248-307">Accessibility - [Accessibility Best Practices](../../../../docs/framework/ui-automation/accessibility-best-practices.md)</span></span>  
  
-   <span data-ttu-id="f4248-308">Seguridad - [seguridad](../../../../docs/framework/wpf/security-wpf.md)</span><span class="sxs-lookup"><span data-stu-id="f4248-308">Security - [Security](../../../../docs/framework/wpf/security-wpf.md)</span></span>  
  
-   <span data-ttu-id="f4248-309">Localización: [Información general sobre la globalización y la localización de WPF](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f4248-309">Localization - [WPF Globalization and Localization Overview](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)</span></span>  
  
-   <span data-ttu-id="f4248-310">Rendimiento: [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span><span class="sxs-lookup"><span data-stu-id="f4248-310">Performance - [Optimizing WPF Application Performance](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)</span></span>  
  
## <a name="whats-next"></a><span data-ttu-id="f4248-311">¿Qué es el siguiente</span><span class="sxs-lookup"><span data-stu-id="f4248-311">What's next</span></span>  
 <span data-ttu-id="f4248-312">Ahora tiene una serie de técnicas a su disposición para crear un [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] con [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4248-312">You now have a number of techniques at your disposal for creating a [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] using [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span> <span data-ttu-id="f4248-313">Ahora debería tener un amplio conocimiento de los bloques de creación básicos de un enlace de datos [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] aplicación.</span><span class="sxs-lookup"><span data-stu-id="f4248-313">You should now have a broad understanding of the basic building blocks of a data-bound [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] application.</span></span> <span data-ttu-id="f4248-314">Este tema no pretende ser exhaustivo, pero espero que ya tenga una idea de las posibilidades que puede descubrir por sí mismo además de las técnicas descritas en este tema.</span><span class="sxs-lookup"><span data-stu-id="f4248-314">This topic is by no means exhaustive, but hopefully you also now have a sense of some of the possibilities you might discover on your own beyond the techniques in this topic.</span></span> 
  
 <span data-ttu-id="f4248-315">Para más información sobre los modelos de programación y arquitectura de WPF, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4248-315">For more information about the WPF architecture and programming models, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f4248-316">Arquitectura de WPF</span><span class="sxs-lookup"><span data-stu-id="f4248-316">WPF Architecture</span></span>](../../../../docs/framework/wpf/advanced/wpf-architecture.md)  
  
-   [<span data-ttu-id="f4248-317">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="f4248-317">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
  
-   [<span data-ttu-id="f4248-318">Información general sobre las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="f4248-318">Dependency Properties Overview</span></span>](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
  
-   [<span data-ttu-id="f4248-319">Diseño</span><span class="sxs-lookup"><span data-stu-id="f4248-319">Layout</span></span>](../../../../docs/framework/wpf/advanced/layout.md)  
  
 <span data-ttu-id="f4248-320">Para más información sobre la creación de aplicaciones, vea los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="f4248-320">For more information about creating applications, see the following topics:</span></span>  
  
-   [<span data-ttu-id="f4248-321">Desarrollo de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f4248-321">Application Development</span></span>](../../../../docs/framework/wpf/app-development/index.md)  
  
-   [<span data-ttu-id="f4248-322">Controles</span><span class="sxs-lookup"><span data-stu-id="f4248-322">Controls</span></span>](../../../../docs/framework/wpf/controls/index.md)  
  
-   [<span data-ttu-id="f4248-323">Información general sobre el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="f4248-323">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
  
-   [<span data-ttu-id="f4248-324">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="f4248-324">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)  
  
-   [<span data-ttu-id="f4248-325">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="f4248-325">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
  
## <a name="see-also"></a><span data-ttu-id="f4248-326">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4248-326">See also</span></span>  
 [<span data-ttu-id="f4248-327">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="f4248-327">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="f4248-328">Información general sobre plantillas de datos</span><span class="sxs-lookup"><span data-stu-id="f4248-328">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="f4248-329">Compilar una aplicación de WPF</span><span class="sxs-lookup"><span data-stu-id="f4248-329">Building a WPF Application</span></span>](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [<span data-ttu-id="f4248-330">Estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="f4248-330">Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/styles-and-templates.md)
