---
title: Creación de una biblioteca de clases de .NET Standard en Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio.
ms.date: 05/21/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 7d64ca32bdbe20f949ae575bc4c3f9bbb594fffd
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2020
ms.locfileid: "84283629"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="bf7a4-103">Tutorial: Creación de una biblioteca de .NET Standard en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf7a4-103">Tutorial: Create a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="bf7a4-104">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="bf7a4-105">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="bf7a4-106">Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="bf7a4-107">Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="bf7a4-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="bf7a4-108">En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="bf7a4-109">Lo implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf7a4-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="bf7a4-110">Prerequisites</span></span>

- <span data-ttu-id="bf7a4-111">[Visual Studio 2019, versión 16.6 o posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-111">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="bf7a4-112">El SDK de .NET Core 3.1 se instala automáticamente al seleccionar esta carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-112">.NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="bf7a4-113">Para más información, consulte la sección [Instalación con Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) del artículo [Instalación del SDK de .NET Core](../install/sdk.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="bf7a4-113">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="bf7a4-114">Creación de una solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf7a4-114">Create a Visual Studio solution</span></span>

<span data-ttu-id="bf7a4-115">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="bf7a4-116">Una solución de Visual Studio sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-116">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="bf7a4-117">Agregará otros proyectos relacionados a la misma solución.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-117">You'll add additional, related projects to the same solution.</span></span>

<span data-ttu-id="bf7a4-118">Para crear la solución en blanco:</span><span class="sxs-lookup"><span data-stu-id="bf7a4-118">To create the blank solution:</span></span>

1. <span data-ttu-id="bf7a4-119">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-119">Open Visual Studio.</span></span>

2. <span data-ttu-id="bf7a4-120">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-120">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="bf7a4-121">En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-121">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="bf7a4-122">Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-122">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="bf7a4-124">En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-124">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="bf7a4-125">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-125">Then choose **Create**.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="bf7a4-126">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="bf7a4-126">Create a class library project</span></span>

1. <span data-ttu-id="bf7a4-127">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-127">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="bf7a4-128">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-128">Right-click on the solution in **Solution Explorer** and select **Add** > **New Project**.</span></span>

   1. <span data-ttu-id="bf7a4-129">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-129">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="bf7a4-130">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-130">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="bf7a4-131">Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-131">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="bf7a4-132">En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-132">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="bf7a4-133">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-133">Then, choose **Create**.</span></span>

1. <span data-ttu-id="bf7a4-134">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-134">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="bf7a4-135">Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-135">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="bf7a4-136">El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-136">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="bf7a4-138">Si usa Visual Basic, borre el texto del cuadro de texto **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-138">If you're using Visual Basic, clear the text in the **Root namespace** text box.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

   <span data-ttu-id="bf7a4-140">En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-140">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="bf7a4-141">En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-141">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="bf7a4-142">Reemplace el código de la ventana de código por *Class1.cs* o *Class1.vb* y guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-142">Replace the code in the code window for *Class1.cs*  or *Class1.vb* with the following code, and save the file.</span></span> <span data-ttu-id="bf7a4-143">Si no se muestra el idioma que quiere usar, cambie el selector de idioma en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-143">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/StringLibrary/Class1.vb":::

   <span data-ttu-id="bf7a4-144">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-144">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="bf7a4-145">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-145">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="bf7a4-146">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-146">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="bf7a4-147">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-147">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="bf7a4-148">En la barra de menús, seleccione **Compilar** > **Compilar solución** para comprobar que el proyecto se compila sin errores.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-148">On the menu bar, select **Build** > **Build Solution** to verify that the project compiles without error.</span></span>

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="bf7a4-149">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="bf7a4-149">Add a console app to the solution</span></span>

<span data-ttu-id="bf7a4-150">Use la biblioteca de clases en una aplicación de consola que pida al usuario que escriba una cadena e indique si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-150">Use the class library in a console application that prompts the user to enter a string and reports whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="bf7a4-151">Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-151">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="bf7a4-152">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-152">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="bf7a4-153">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-153">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="bf7a4-154">Elija **C#** o **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-154">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span>

   1. <span data-ttu-id="bf7a4-155">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-155">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="bf7a4-156">En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-156">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="bf7a4-157">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-157">Then choose **Create**.</span></span>

1. <span data-ttu-id="bf7a4-158">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-158">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](media/library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="bf7a4-160">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-160">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="bf7a4-161">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-161">To allow it to call methods in the class library, create a project reference to the class library project.</span></span> <span data-ttu-id="bf7a4-162">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-162">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node, and select **Add Project Reference**.</span></span>

   ![Menú contextual Agregar referencia de Visual Studio](media/library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="bf7a4-164">En el cuadro de diálogo **Administrador de referencias**, seleccione el proyecto **StringLibrary** y después **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-164">In the **Reference Manager** dialog, select the **StringLibrary** project, and select **OK**.</span></span>

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](media/library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="bf7a4-166">En la ventana de código del archivo *Program.cs* o *Program.vb*, reemplace todo el código con el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-166">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::
   :::code language="vb" source="./snippets/library-with-visual-studio/vb/ShowCase/Program.vb":::

   <span data-ttu-id="bf7a4-167">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-167">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="bf7a4-168">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-168">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="bf7a4-169">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-169">The program prompts the user to enter a string.</span></span> <span data-ttu-id="bf7a4-170">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-170">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="bf7a4-171">Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-171">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="bf7a4-172">Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-172">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="bf7a4-173">Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-173">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](media/library-with-visual-studio/visual-studio-project-toolbar.png)

1. <span data-ttu-id="bf7a4-175">Para probar el programa, escriba cadenas y presione **Entrar** y, después, presione **Entrar** para salir.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-175">Try out the program by entering strings and pressing **Enter**, then press **Enter** to exit.</span></span>

   :::image type="content" source="media/library-with-visual-studio/run-showcase.png" alt-text="Ventana de la consola con ShowCase en ejecución":::

## <a name="next-steps"></a><span data-ttu-id="bf7a4-177">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="bf7a4-177">Next steps</span></span>

<span data-ttu-id="bf7a4-178">En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-178">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="bf7a4-179">En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.</span><span class="sxs-lookup"><span data-stu-id="bf7a4-179">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf7a4-180">Prueba de una biblioteca .NET Standard con .NET Core en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bf7a4-180">Test a .NET Standard library with .NET Core in Visual Studio</span></span>](testing-library-with-visual-studio.md)
