---
title: Creación de una biblioteca de clases .NET Standard con Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: ef9c62b0378e1064d8cfd90a8c59aed74ea312b2
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701570"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio"></a><span data-ttu-id="6a1eb-103">Tutorial: Creación de una biblioteca .NET Standard con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6a1eb-103">Tutorial: Create a .NET Standard library using Visual Studio</span></span>

<span data-ttu-id="6a1eb-104">En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="6a1eb-105">Lo implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="6a1eb-106">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="6a1eb-107">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="6a1eb-108">Cuando termine la biblioteca de clases, puede distribuirla como un componente de terceros o como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a1eb-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="6a1eb-109">Prerequisites</span></span>

- <span data-ttu-id="6a1eb-110">[Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-110">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="6a1eb-111">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-111">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="6a1eb-112">Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="6a1eb-112">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="6a1eb-113">Crear una solución</span><span class="sxs-lookup"><span data-stu-id="6a1eb-113">Create a solution</span></span>

<span data-ttu-id="6a1eb-114">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="6a1eb-115">Una solución de Visual Studio sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-115">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="6a1eb-116">Agregará otros proyectos relacionados a la misma solución.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-116">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="6a1eb-117">Para crear la solución en blanco:</span><span class="sxs-lookup"><span data-stu-id="6a1eb-117">To create the blank solution:</span></span>

1. <span data-ttu-id="6a1eb-118">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-118">Start Visual Studio.</span></span>

2. <span data-ttu-id="6a1eb-119">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-119">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="6a1eb-120">En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-120">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="6a1eb-121">Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-121">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="6a1eb-123">En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-123">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="6a1eb-124">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-124">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="6a1eb-125">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="6a1eb-125">Create a class library project</span></span>

1. <span data-ttu-id="6a1eb-126">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-126">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="6a1eb-127">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="6a1eb-128">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="6a1eb-129">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-129">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="6a1eb-130">Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="6a1eb-131">En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="6a1eb-132">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="6a1eb-133">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="6a1eb-134">Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="6a1eb-135">El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="6a1eb-137">Si usa Visual Basic, borre el texto del cuadro de texto **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-137">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="6a1eb-139">En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-139">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="6a1eb-140">En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-140">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="6a1eb-141">Reemplace el código de la ventana de código por *Class1.cs* o *Class1.vb* y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-141">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="6a1eb-142">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-142">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="6a1eb-143">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-143">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="6a1eb-144">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-144">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="6a1eb-145">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-145">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="6a1eb-146">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-146">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="6a1eb-147">En la barra de menús, seleccione **Compilar** > **Compilar solución** para comprobar que el proyecto se compila sin errores.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-147">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="6a1eb-148">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="6a1eb-148">Add a console app to the solution</span></span>

<span data-ttu-id="6a1eb-149">Agregue una aplicación de consola que use la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-149">Add a console application that uses the class library.</span></span> <span data-ttu-id="6a1eb-150">La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-150">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="6a1eb-151">Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="6a1eb-152">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="6a1eb-153">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="6a1eb-154">Elija **C#** o **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="6a1eb-155">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="6a1eb-156">En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="6a1eb-157">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="6a1eb-158">En la ventana de código del archivo *Program.cs* o *Program.vb*, reemplace todo el código con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-158">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="6a1eb-159">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-159">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="6a1eb-160">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-160">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="6a1eb-161">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-161">The program prompts the user to enter a string.</span></span> <span data-ttu-id="6a1eb-162">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-162">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="6a1eb-163">Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-163">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="6a1eb-164">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="6a1eb-164">Add a project reference</span></span>

<span data-ttu-id="6a1eb-165">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-165">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="6a1eb-166">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-166">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="6a1eb-167">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-167">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Menú contextual Agregar referencia de Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="6a1eb-169">En el cuadro de diálogo **Administrador de referencias**, seleccione el proyecto **StringLibrary** y después **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-169">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](media/library-with-visual-studio/manage-project-references.png)

## <a name="run-the-app"></a><span data-ttu-id="6a1eb-171">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="6a1eb-171">Run the app</span></span>

1. <span data-ttu-id="6a1eb-172">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-172">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="6a1eb-174">Presione <kbd>Mayús</kbd>+<kbd>F5</kbd> para compilar y ejecutar el programa sin depuración.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-174">Press <kbd>Shift</kbd>+<kbd>F5</kbd> to compile and run the program without debugging.</span></span>

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="6a1eb-176">Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-176">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Ventana de la consola con ShowCase en ejecución":::

## <a name="additional-resources"></a><span data-ttu-id="6a1eb-178">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6a1eb-178">Additional resources</span></span>

* [<span data-ttu-id="6a1eb-179">Desarrollo de bibliotecas con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6a1eb-179">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="6a1eb-180">[Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="6a1eb-180">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6a1eb-181">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6a1eb-181">Next steps</span></span>

<span data-ttu-id="6a1eb-182">En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-182">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="6a1eb-183">En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.</span><span class="sxs-lookup"><span data-stu-id="6a1eb-183">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6a1eb-184">Prueba de una biblioteca .NET Standard con .NET Core mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6a1eb-184">Test a .NET Standard library with .NET Core using Visual Studio</span></span>](testing-library-with-visual-studio.md)
