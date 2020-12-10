---
title: Creación de una biblioteca de clases de .NET con Visual Studio para Mac
description: Aprenda a crear una biblioteca de clases de .NET mediante Visual Studio para Mac.
ms.date: 11/30/2020
ms.openlocfilehash: 1b6b26de06d18d505fa6dde3ff9779a3dab3f1e6
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599318"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-for-mac"></a><span data-ttu-id="db228-103">Tutorial: Creación de una biblioteca de clases de .NET con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="db228-103">Tutorial: Create a .NET class library using Visual Studio for Mac</span></span>

<span data-ttu-id="db228-104">En este tutorial, creará una biblioteca de clases que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="db228-104">In this tutorial, you create a class library that contains a single string-handling method.</span></span>

<span data-ttu-id="db228-105">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="db228-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="db228-106">Si la biblioteca tiene como destino .NET Standard 2.0, se puede llamar mediante cualquier implementación de .NET (incluido .NET Framework) que admita .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="db228-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="db228-107">Si la biblioteca tiene como destino .NET 5, la puede llamar cualquier aplicación que tenga como destino .NET 5.</span><span class="sxs-lookup"><span data-stu-id="db228-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="db228-108">En este tutorial se muestra cómo seleccionar .NET 5 como destino.</span><span class="sxs-lookup"><span data-stu-id="db228-108">This tutorial shows how to target .NET 5.</span></span>

> [!NOTE]
> <span data-ttu-id="db228-109">Sus comentarios son muy importantes.</span><span class="sxs-lookup"><span data-stu-id="db228-109">Your feedback is highly valued.</span></span> <span data-ttu-id="db228-110">Hay dos maneras de proporcionar comentarios al equipo de desarrollo de Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="db228-110">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> - <span data-ttu-id="db228-111">En Visual Studio para Mac, seleccione **Ayuda** > **Notificar un problema** en el menú o **Notificar un problema** desde la pantalla de bienvenida, que abre una ventana para presentar un informe de errores.</span><span class="sxs-lookup"><span data-stu-id="db228-111">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which opens a window for filing a bug report.</span></span> <span data-ttu-id="db228-112">Puede realizar un seguimiento de sus comentarios en el portal de la [Comunidad de desarrolladores](https://aka.ms/feedback/report?space=41).</span><span class="sxs-lookup"><span data-stu-id="db228-112">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> - <span data-ttu-id="db228-113">Para hacer una sugerencia, seleccione **Ayuda** > **Aportar una sugerencia** en el menú o **Aportar una sugerencia** desde la pantalla de bienvenida, que le lleva a la [página web de la Comunidad de desarrolladores de Visual Studio para Mac](https://aka.ms/feedback/suggest?space=41).</span><span class="sxs-lookup"><span data-stu-id="db228-113">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which takes you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db228-114">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="db228-114">Prerequisites</span></span>

* <span data-ttu-id="db228-115">[Instale Visual Studio para Mac, versión 8.8 o posterior](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="db228-115">[Install Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="db228-116">Seleccione la opción para instalar .NET Core.</span><span class="sxs-lookup"><span data-stu-id="db228-116">Select the option to install .NET Core.</span></span> <span data-ttu-id="db228-117">La instalación de Xamarin es opcional para el desarrollo con .NET.</span><span class="sxs-lookup"><span data-stu-id="db228-117">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="db228-118">Para obtener más información, vea los siguientes recursos:</span><span class="sxs-lookup"><span data-stu-id="db228-118">For more information, see the following resources:</span></span>

  * <span data-ttu-id="db228-119">[Tutorial: Instalación de Visual Studio para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="db228-119">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="db228-120">[Versiones de macOS compatibles](../install/macos.md).</span><span class="sxs-lookup"><span data-stu-id="db228-120">[Supported macOS versions](../install/macos.md).</span></span>
  * <span data-ttu-id="db228-121">[Versiones de .NET compatibles con Visual Studio para Mac](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="db228-121">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-a-solution-with-a-class-library-project"></a><span data-ttu-id="db228-122">Creación de una solución con un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="db228-122">Create a solution with a class library project</span></span>

<span data-ttu-id="db228-123">Una solución de Visual Studio sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="db228-123">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="db228-124">Creación de una solución y un proyecto de biblioteca de clases en la solución.</span><span class="sxs-lookup"><span data-stu-id="db228-124">Create a solution and a class library project in the solution.</span></span> <span data-ttu-id="db228-125">Agregará otros proyectos relacionados a la misma solución más adelante.</span><span class="sxs-lookup"><span data-stu-id="db228-125">You'll add additional, related projects to the same solution later.</span></span>

1. <span data-ttu-id="db228-126">Inicie Visual Studio para Mac:</span><span class="sxs-lookup"><span data-stu-id="db228-126">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="db228-127">En la ventana de inicio, seleccione **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="db228-127">In the start window, select **New Project**.</span></span>

1. <span data-ttu-id="db228-128">En el cuadro de diálogo **Elija una plantilla para el nuevo proyecto**, seleccione **Web and Console** (Web y consola)  > **Biblioteca** > **Biblioteca de clases** y, luego, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db228-128">In the **Choose a template for your new project** dialog select **Web and Console** > **Library** > **Class Library**, and then select **Next**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Cuadro de diálogo Nuevo proyecto":::

1. <span data-ttu-id="db228-130">En el cuadro de diálogo **Configure your new Class Library** (Configurar una nueva biblioteca de clases), elija **.NET 5.0** y, luego, **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db228-130">In the **Configure your new Class Library** dialog, choose **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="db228-131">Asigne al proyecto el nombre "StringLibrary" y a la solución "ClassLibraryProjects".</span><span class="sxs-lookup"><span data-stu-id="db228-131">Name the project "StringLibrary" and the solution "ClassLibraryProjects".</span></span> <span data-ttu-id="db228-132">Deje activada la opción **Crear un directorio de proyecto dentro del directorio de la solución**.</span><span class="sxs-lookup"><span data-stu-id="db228-132">Leave **Create a project directory within the solution directory** selected.</span></span> <span data-ttu-id="db228-133">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="db228-133">Select **Create**.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-new-project-options.png" alt-text="Opciones del cuadro de diálogo Nuevo proyecto de Visual Studio para Mac":::

1. <span data-ttu-id="db228-135">En el menú principal, seleccione **Ver** > **Solución** y elija el icono de acoplamiento para mantener el panel abierto.</span><span class="sxs-lookup"><span data-stu-id="db228-135">From the main menu, select **View** > **Solution**, and select the dock icon to keep the pad open.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/solution-dock-icon.png" alt-text="Icono de acoplamiento del panel de solución":::

1. <span data-ttu-id="db228-137">En el panel **Solución**, expanda el nodo `StringLibrary` para mostrar el archivo de clase proporcionado por la plantilla *Class1.cs*.</span><span class="sxs-lookup"><span data-stu-id="db228-137">In the **Solution** pad, expand the `StringLibrary` node to reveal the class file provided by the template, *Class1.cs*.</span></span> <span data-ttu-id="db228-138">Haga clic presionando <kbd>control</kbd> en el archivo, seleccione **Cambiar nombre** en el menú contextual y denomínelo *StringLibrary.cs*.</span><span class="sxs-lookup"><span data-stu-id="db228-138"><kbd>ctrl</kbd>-click the file, select **Rename** from the context menu, and rename the file to *StringLibrary.cs*.</span></span> <span data-ttu-id="db228-139">Abra el archivo y reemplace el contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="db228-139">Open the file and replace the contents with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

1. <span data-ttu-id="db228-140">Presione <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) para guardar el archivo.</span><span class="sxs-lookup"><span data-stu-id="db228-140">Press <kbd>⌘</kbd><kbd>S</kbd> (<kbd>command</kbd>+<kbd>S</kbd>) to save the file.</span></span>

1. <span data-ttu-id="db228-141">Seleccione **Errores** en el margen inferior de la ventana de IDE para abrir el panel **Errores**.</span><span class="sxs-lookup"><span data-stu-id="db228-141">Select **Errors** in the margin at the bottom of the IDE window to open the **Errors** panel.</span></span> <span data-ttu-id="db228-142">Seleccione el botón **Salida de la compilación**.</span><span class="sxs-lookup"><span data-stu-id="db228-142">Select the **Build Output** button.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-error-button.png" alt-text="Margen inferior del IDE de Visual Studio para Mac con el botón Errores":::

1. <span data-ttu-id="db228-144">Seleccione **Compilar** > **Compilar todo** en el menú.</span><span class="sxs-lookup"><span data-stu-id="db228-144">Select **Build** > **Build All** from the menu.</span></span>

   <span data-ttu-id="db228-145">La solución se compila.</span><span class="sxs-lookup"><span data-stu-id="db228-145">The solution builds.</span></span> <span data-ttu-id="db228-146">El panel de salida de la compilación muestra que la compilación es correcta.</span><span class="sxs-lookup"><span data-stu-id="db228-146">The build output panel shows that the build is successful.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-build-panel.png" alt-text="Panel de salida de la compilación de Visual Studio para Mac del panel Errores con el mensaje de compilación correcta":::

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="db228-148">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="db228-148">Add a console app to the solution</span></span>

<span data-ttu-id="db228-149">Agregue una aplicación de consola que use la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="db228-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="db228-150">La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="db228-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="db228-151">En el panel **Solución**, haga clic pulsando <kbd>control</kbd> en la solución `ClassLibraryProjects`.</span><span class="sxs-lookup"><span data-stu-id="db228-151">In the **Solution** pad, <kbd>ctrl</kbd>-click the `ClassLibraryProjects` solution.</span></span> <span data-ttu-id="db228-152">Agregue un nuevo proyecto de **aplicación de consola**; para ello, seleccione la plantilla de las plantillas de **Web and Console** (Web y consola) > **Aplicación** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db228-152">Add a new **Console Application** project by selecting the template from the **Web and Console** > **App** templates, and select **Next**.</span></span>

1. <span data-ttu-id="db228-153">Seleccione **.NET 5.0** como **Marco de destino** y, a continuación, elija **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db228-153">Select **.NET 5.0** as the **Target Framework** and select **Next**.</span></span>

1. <span data-ttu-id="db228-154">Asigne al proyecto el nombre **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="db228-154">Name the project **ShowCase**.</span></span> <span data-ttu-id="db228-155">Seleccione **Crear** para crear el proyecto en la solución.</span><span class="sxs-lookup"><span data-stu-id="db228-155">Select **Create** to create the project in the solution.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/add-showcase-project.png" alt-text="Adición de Showcase":::

1. <span data-ttu-id="db228-157">Abra el archivo *Program.cs*.</span><span class="sxs-lookup"><span data-stu-id="db228-157">Open the *Program.cs* file.</span></span> <span data-ttu-id="db228-158">Reemplace el código por el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="db228-158">Replace the code with the following code:</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="db228-159">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="db228-159">The program prompts the user to enter a string.</span></span> <span data-ttu-id="db228-160">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="db228-160">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="db228-161">Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="db228-161">If the user presses the <kbd>enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

   <span data-ttu-id="db228-162">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="db228-162">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="db228-163">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="db228-163">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="db228-164">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="db228-164">Add a project reference</span></span>

<span data-ttu-id="db228-165">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="db228-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="db228-166">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="db228-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="db228-167">En el panel **Soluciones**, haga clic presionando <kbd>control</kbd> en el nodo **Dependencias** del nuevo proyecto **ShowCase**.</span><span class="sxs-lookup"><span data-stu-id="db228-167">In the **Solutions** pad, <kbd>ctrl</kbd>-click the **Dependencies** node of the new **ShowCase** project.</span></span> <span data-ttu-id="db228-168">En el menú contextual, seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="db228-168">In the context menu, select **Add Reference**.</span></span>

1. <span data-ttu-id="db228-169">En el cuadro de diálogo **Referencias**, seleccione **StringLibrary** y **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db228-169">In the **References** dialog, select **StringLibrary** and select **OK**.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="db228-170">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="db228-170">Run the app</span></span>

1. <span data-ttu-id="db228-171">Haga clic y presione la tecla <kbd>Ctrl</kbd> en el proyecto **ShowCase** y seleccione **Ejecutar el proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="db228-171"><kbd>ctrl</kbd>-click the **ShowCase** project and select **Run project** from the context menu.</span></span>

1. <span data-ttu-id="db228-172">Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.</span><span class="sxs-lookup"><span data-stu-id="db228-172">Try out the program by entering strings and pressing <kbd>enter</kbd>, then press <kbd>enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio-mac/visual-studio-mac-console-window.png" alt-text="Ventana de la consola de Visual Studio para Mac en la que se muestra la aplicación en ejecución":::

## <a name="additional-resources"></a><span data-ttu-id="db228-174">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="db228-174">Additional resources</span></span>

* [<span data-ttu-id="db228-175">Desarrollo de bibliotecas con la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="db228-175">Develop libraries with the .NET CLI</span></span>](libraries.md)
* [<span data-ttu-id="db228-176">Notas de la versión de Visual Studio 2019 para Mac</span><span class="sxs-lookup"><span data-stu-id="db228-176">Visual Studio 2019 for Mac Release Notes</span></span>](/visualstudio/releasenotes/vs2019-mac-relnotes)
* <span data-ttu-id="db228-177">[Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="db228-177">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="db228-178">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="db228-178">Next steps</span></span>

<span data-ttu-id="db228-179">En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="db228-179">In this tutorial, you created a solution and a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="db228-180">En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.</span><span class="sxs-lookup"><span data-stu-id="db228-180">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="db228-181">Prueba de una biblioteca de clases de .NET con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="db228-181">Test a .NET class library using Visual Studio for Mac</span></span>](testing-library-with-visual-studio-mac.md)
