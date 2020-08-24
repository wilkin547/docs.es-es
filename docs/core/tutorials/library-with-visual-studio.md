---
title: Creación de una biblioteca de clases .NET Standard con Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio.
ms.date: 08/07/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet,contperfq1
ms.openlocfilehash: 595e93d8d8d22478c6770ddd4f70a0214653f5b9
ms.sourcegitcommit: d337df55f83325918cbbd095eb573400bea49064
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "88187945"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="4d560-103">Tutorial: Creación de una biblioteca .NET Standard con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d560-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="4d560-104">En este tutorial, creará una sencilla clases de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="4d560-104">In this tutorial, you create a simple class library that contains a single string-handling method.</span></span>

<span data-ttu-id="4d560-105">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4d560-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="4d560-106">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="4d560-106">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span>

<span data-ttu-id="4d560-107">Al terminar con la biblioteca de clases, puede distribuirla como un paquete NuGet o un componente empaquetado con la aplicación que lo utiliza.</span><span class="sxs-lookup"><span data-stu-id="4d560-107">When you finish your class library, you can distribute it as a NuGet package or as a component bundled with the application that uses it.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d560-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="4d560-108">Prerequisites</span></span>

- <span data-ttu-id="4d560-109">[Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="4d560-109">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="4d560-110">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4d560-110">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="4d560-111">Crear una solución</span><span class="sxs-lookup"><span data-stu-id="4d560-111">Create a solution</span></span>

<span data-ttu-id="4d560-112">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="4d560-112">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="4d560-113">Una solución de Visual Studio sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="4d560-113">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="4d560-114">Agregará otros proyectos relacionados a la misma solución.</span><span class="sxs-lookup"><span data-stu-id="4d560-114">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="4d560-115">Para crear la solución en blanco:</span><span class="sxs-lookup"><span data-stu-id="4d560-115">To create the blank solution:</span></span>

1. <span data-ttu-id="4d560-116">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4d560-116">Start Visual Studio.</span></span>

2. <span data-ttu-id="4d560-117">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4d560-117">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="4d560-118">En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**.</span><span class="sxs-lookup"><span data-stu-id="4d560-118">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="4d560-119">Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4d560-119">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="4d560-121">En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-121">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="4d560-122">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4d560-122">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="4d560-123">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="4d560-123">Create a class library project</span></span>

1. <span data-ttu-id="4d560-124">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="4d560-124">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="4d560-125">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-125">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="4d560-126">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="4d560-126">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="4d560-127">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="4d560-127">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="4d560-128">Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4d560-128">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="4d560-129">En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-129">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="4d560-130">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4d560-130">Then, choose **Create**.</span></span>

1. <span data-ttu-id="4d560-131">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="4d560-131">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="4d560-132">Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="4d560-132">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="4d560-133">El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d560-133">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="4d560-135">Si usa Visual Basic, borre el texto del cuadro de texto **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="4d560-135">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="4d560-137">En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4d560-137">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="4d560-138">En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="4d560-138">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="4d560-139">Reemplace el código de la ventana de código por *Class1.cs* o *Class1.vb* y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="4d560-139">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="4d560-140">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="4d560-140">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="4d560-141">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="4d560-141">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="4d560-142">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="4d560-142">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="4d560-143">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d560-143">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="4d560-144">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d560-144">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

   <span data-ttu-id="4d560-145">`StartsWithUpper` se implementa como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md), de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="4d560-145">`StartsWithUpper` is implemented as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

1. <span data-ttu-id="4d560-146">En la barra de menús, seleccione **Compilar** > **Compilar solución** para comprobar que el proyecto se compila sin errores.</span><span class="sxs-lookup"><span data-stu-id="4d560-146">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="4d560-147">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="4d560-147">Add a console app to the solution</span></span>

<span data-ttu-id="4d560-148">Agregue una aplicación de consola que use la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4d560-148">Add a console application that uses the class library.</span></span> <span data-ttu-id="4d560-149">La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d560-149">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="4d560-150">Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.</span><span class="sxs-lookup"><span data-stu-id="4d560-150">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="4d560-151">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-151">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="4d560-152">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**.</span><span class="sxs-lookup"><span data-stu-id="4d560-152">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="4d560-153">Elija **C#** o **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="4d560-153">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="4d560-154">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4d560-154">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="4d560-155">En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-155">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="4d560-156">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="4d560-156">Then choose **Create**.</span></span>

1. <span data-ttu-id="4d560-157">En la ventana de código del archivo *Program.cs* o *Program.vb*, reemplace todo el código con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="4d560-157">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="4d560-158">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="4d560-158">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="4d560-159">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="4d560-159">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="4d560-160">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="4d560-160">The program prompts the user to enter a string.</span></span> <span data-ttu-id="4d560-161">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="4d560-161">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="4d560-162">Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="4d560-162">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="4d560-163">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="4d560-163">Add a project reference</span></span>

<span data-ttu-id="4d560-164">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4d560-164">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="4d560-165">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4d560-165">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="4d560-166">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="4d560-166">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Menú contextual Agregar referencia de Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="4d560-168">En el cuadro de diálogo **Administrador de referencias**, seleccione el proyecto **StringLibrary** y después **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4d560-168">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="4d560-170">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="4d560-170">Run the app</span></span>

1. <span data-ttu-id="4d560-171">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="4d560-171">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="4d560-173">Presione <kbd>CTRL</kbd>+<kbd>F5</kbd> para compilar y ejecutar el programa sin depuración.</span><span class="sxs-lookup"><span data-stu-id="4d560-173">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="4d560-175">Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.</span><span class="sxs-lookup"><span data-stu-id="4d560-175">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Ventana de la consola con ShowCase en ejecución":::

## <a name="additional-resources"></a><span data-ttu-id="4d560-177">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4d560-177">Additional resources</span></span>

* [<span data-ttu-id="4d560-178">Desarrollo de bibliotecas con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4d560-178">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="4d560-179">[Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="4d560-179">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4d560-180">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4d560-180">Next steps</span></span>

<span data-ttu-id="4d560-181">En este tutorial, ha creado una prueba unitaria de una biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4d560-181">In this tutorial, you created a class library.</span></span> <span data-ttu-id="4d560-182">En el siguiente tutorial, aprenderá a hacer una prueba unitaria de la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="4d560-182">In the next tutorial, you learn how to unit test the class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d560-183">Prueba unitaria a una biblioteca .NET Standard con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d560-183">Unit test a .NET Standard library using Visual Studio</span></span>](testing-library-with-visual-studio.md)

<span data-ttu-id="4d560-184">También puede omitir las pruebas unitarias automatizadas y aprender a compartir la biblioteca mediante la creación de un paquete NuGet:</span><span class="sxs-lookup"><span data-stu-id="4d560-184">Or you can skip automated unit testing and learn how to share the library by creating a NuGet package:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d560-185">Crear y publicar un paquete con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d560-185">Create and publish a package using Visual Studio</span></span>](/nuget/quickstart/create-and-publish-a-package-using-visual-studio)

<span data-ttu-id="4d560-186">También puede obtener más información sobre cómo publicar una aplicación de consola.</span><span class="sxs-lookup"><span data-stu-id="4d560-186">Or learn how to publish a console app.</span></span> <span data-ttu-id="4d560-187">Si publica la aplicación de consola a partir de la solución que ha creado en este tutorial, la biblioteca de clases lo incluirá como un archivo *.dll*.</span><span class="sxs-lookup"><span data-stu-id="4d560-187">If you publish the console app from the solution you created in this tutorial, the class library goes with it as a *.dll* file.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4d560-188">Publicación de una aplicación de consola de .NET Core con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4d560-188">Publish a .NET Core console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
