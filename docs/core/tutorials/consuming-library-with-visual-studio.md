---
title: Consumo de una biblioteca de .NET Standard en Visual Studio
description: Cree una aplicación de .NET Core que llame a los miembros de otra biblioteca de clases con Visual Studio 2019.
ms.date: 12/20/2019
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4eb75f23359334ea483cba1498f1804c4b24c80c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920459"
---
# <a name="consume-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="21a67-103">Consumo de una biblioteca de .NET Standard en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21a67-103">Consume a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="21a67-104">Una vez que haya creado una biblioteca de clases de .NET Standard, la haya probado y haya creado una versión de lanzamiento de dicha biblioteca, el siguiente paso es ponerla a disposición de los autores de las llamadas.</span><span class="sxs-lookup"><span data-stu-id="21a67-104">Once you've created a .NET Standard class library, tested it, and built a release version of the library, the next step is to make it available to callers.</span></span> <span data-ttu-id="21a67-105">Existen dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="21a67-105">You can do this in two ways:</span></span>

- <span data-ttu-id="21a67-106">Si una única solución va a usar la biblioteca (por ejemplo, si es un componente de una sola aplicación más grande), se puede incluir como proyecto en la solución.</span><span class="sxs-lookup"><span data-stu-id="21a67-106">If the library will be used by a single solution (for example, if it's a component in a single large application), you can include it as a project in your solution.</span></span>
- <span data-ttu-id="21a67-107">Si la biblioteca va a estar accesible públicamente, puede distribuirla como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="21a67-107">If the library will be publicly available, you can distribute it as a NuGet package.</span></span>

<span data-ttu-id="21a67-108">En este tutorial aprenderá a:</span><span class="sxs-lookup"><span data-stu-id="21a67-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="21a67-109">Agregue una aplicación de consola a la solución que haga referencia a un proyecto de biblioteca de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="21a67-109">Add a console app to your solution that references a .NET Standard library project.</span></span>
> - <span data-ttu-id="21a67-110">Cree un paquete NuGet que contenga un proyecto de biblioteca de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="21a67-110">Create a NuGet package that contains a .NET Standard library project.</span></span>

## <a name="add-a-console-app-to-your-solution"></a><span data-ttu-id="21a67-111">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="21a67-111">Add a console app to your solution</span></span>

<span data-ttu-id="21a67-112">Así como incluyó pruebas unitarias en la misma solución que la biblioteca de clases en [Prueba de una biblioteca de .NET Standard con .NET Core en Visual Studio 2017](testing-library-with-visual-studio.md), puede incluir la aplicación como parte de esa solución.</span><span class="sxs-lookup"><span data-stu-id="21a67-112">Just as you included unit tests in the same solution as your class library in [Test a .NET Standard library in Visual Studio](testing-library-with-visual-studio.md), you can include your application as part of that solution.</span></span> <span data-ttu-id="21a67-113">Por ejemplo, se puede usar la biblioteca de clases en una aplicación de consola que pide al usuario que inserte una cadena e informa de si su primer carácter está en mayúsculas:</span><span class="sxs-lookup"><span data-stu-id="21a67-113">For example, you can use your class library in a console application that prompts the user to enter a string and reports whether its first character is uppercase:</span></span>

1. <span data-ttu-id="21a67-114">Abra la solución `ClassLibraryProjects` que creó en el artículo [Creación de una biblioteca de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017](library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="21a67-114">Open the `ClassLibraryProjects` solution you created in the [Build a .NET Standard library in Visual Studio](library-with-visual-studio.md) article.</span></span>

1. <span data-ttu-id="21a67-115">Agregue una nueva aplicación de consola de .NET Core denominada "Showcase" a la solución.</span><span class="sxs-lookup"><span data-stu-id="21a67-115">Add a new .NET Core console application named "ShowCase" to the solution.</span></span>

   1. <span data-ttu-id="21a67-116">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="21a67-116">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="21a67-117">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **consola**.</span><span class="sxs-lookup"><span data-stu-id="21a67-117">On the **Add a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="21a67-118">En la lista de lenguajes, elija **C#** o **Visual Basic** y, luego, en la lista de plataformas, elija **Todas las plataformas**.</span><span class="sxs-lookup"><span data-stu-id="21a67-118">Choose **C#** or **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="21a67-119">Elija la plantilla **Aplicación de consola (.NET Core)** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="21a67-119">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="21a67-120">En la página **Configure el nuevo proyecto**, escriba **ShowCase** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="21a67-120">On the **Configure your new project** page, enter **ShowCase** in the **Project name** box.</span></span> <span data-ttu-id="21a67-121">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="21a67-121">Then, choose **Create**.</span></span>

1. <span data-ttu-id="21a67-122">En el **Explorador de soluciones**, haga clic con el botón derecho en el proyecto **Presentación** y seleccione **Establecer como proyecto de inicio** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="21a67-122">In **Solution Explorer**, right-click the **ShowCase** project and select **Set as StartUp Project** in the context menu.</span></span>

   ![Menú contextual del proyecto de Visual Studio para establecer el proyecto de inicio](./media/consuming-library-with-visual-studio/set-startup-project-context-menu.png)

1. <span data-ttu-id="21a67-124">Inicialmente, el proyecto no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="21a67-124">Initially, your project doesn't have access to your class library.</span></span> <span data-ttu-id="21a67-125">Para permitir que se llame a métodos de la biblioteca de clases, puede crear una referencia a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="21a67-125">To allow it to call methods in your class library, you create a reference to the class library.</span></span> <span data-ttu-id="21a67-126">En el **Explorador de soluciones**, haga clic con el botón derecho en el nodo **Dependencias** del proyecto `ShowCase` y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="21a67-126">In **Solution Explorer**, right-click the `ShowCase` project's **Dependencies** node and select **Add Reference**.</span></span>

   ![Menú contextual Agregar referencia de Visual Studio](./media/consuming-library-with-visual-studio/add-reference-context-menu.png)

1. <span data-ttu-id="21a67-128">En el cuadro de diálogo **Administrador de referencias**, seleccione **StringLibrary**, el proyecto de biblioteca de clases, y pulse el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="21a67-128">In the **Reference Manager** dialog, select **StringLibrary**, your class library project, and select the **OK** button.</span></span>

   ![Cuadro de diálogo Administrador de referencias con StringLibrary seleccionado](./media/consuming-library-with-visual-studio/manage-project-references.png)

1. <span data-ttu-id="21a67-130">En la ventana de código del archivo *Program.vb* o *Program.vb*, reemplace todo el código con el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="21a67-130">In the code window for the *Program.cs* or *Program.vb* file, replace all of the code with the following code:</span></span>

   [!code-csharp[UsingClassLib#1](~/samples/snippets/csharp/getting_started/with_visual_studio_2017/showcase.cs)]
   [!code-vb[UsingClassLib#1](~/samples/snippets/core/tutorials/vb-library-with-visual-studio/showcase.vb)]

   <span data-ttu-id="21a67-131">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="21a67-131">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="21a67-132">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="21a67-132">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="21a67-133">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="21a67-133">The program prompts the user to enter a string.</span></span> <span data-ttu-id="21a67-134">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="21a67-134">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="21a67-135">Si el usuario presiona la tecla Entrar sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="21a67-135">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="21a67-136">Si es necesario, cambie la barra de herramientas para compilar la versión de **depuración** del proyecto `ShowCase`.</span><span class="sxs-lookup"><span data-stu-id="21a67-136">If necessary, change the toolbar to compile the **Debug** release of the `ShowCase` project.</span></span> <span data-ttu-id="21a67-137">Compile y ejecute el programa haciendo clic en la flecha verde en el botón **Presentación**.</span><span class="sxs-lookup"><span data-stu-id="21a67-137">Compile and run the program by selecting the green arrow on the **ShowCase** button.</span></span>

   ![Barra de herramientas del proyecto de Visual Studio en la que se muestra el botón Depurar](./media/consuming-library-with-visual-studio/visual-studio-project-toolbar.png)

<span data-ttu-id="21a67-139">La aplicación que usa esta biblioteca se puede depurar y publicar siguiendo los pasos indicados en [Depuración de la aplicación Hola mundo de .NET Core en C# o Visual Basic con Visual Studio 2017](debugging-with-visual-studio.md) y [Publicación de la aplicación Hola mundo de .NET Core con Visual Studio 2017](publishing-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="21a67-139">You can debug and publish the application that uses this library by following the steps in [Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio](debugging-with-visual-studio.md) and [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="21a67-140">Creación de un paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="21a67-140">Create a NuGet package</span></span>

<span data-ttu-id="21a67-141">Puede hacer que la biblioteca de clases tenga una disponibilidad amplia si la publica como un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="21a67-141">You can make your class library widely available by publishing it as a NuGet package.</span></span> <span data-ttu-id="21a67-142">Visual Studio no admite la creación de paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="21a67-142">Visual Studio doesn't support the creation of NuGet packages.</span></span> <span data-ttu-id="21a67-143">Para crear uno, debe usar los comandos de la CLI de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="21a67-143">To create one, you need to use the .NET Core CLI commands:</span></span>

1. <span data-ttu-id="21a67-144">Abra una ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="21a67-144">Open a console window.</span></span>

   <span data-ttu-id="21a67-145">Por ejemplo, escriba **Símbolo del sistema** en el cuadro de búsqueda de la barra de tareas de Windows.</span><span class="sxs-lookup"><span data-stu-id="21a67-145">For example, enter **Command Prompt** in the search box on the Windows task bar.</span></span> <span data-ttu-id="21a67-146">Seleccione la aplicación de escritorio **Símbolo del sistema** o presione **Entrar** si ya está seleccionado en los resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="21a67-146">Select the **Command Prompt** desktop app or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="21a67-147">Vaya al directorio del proyecto de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="21a67-147">Navigate to your library's project directory.</span></span> <span data-ttu-id="21a67-148">El directorio contiene el código fuente y un archivo de proyecto, *StringLibrary.csproj* o *StringLibrary.vbproj*.</span><span class="sxs-lookup"><span data-stu-id="21a67-148">The directory contains your source code and a project file, *StringLibrary.csproj* or *StringLibrary.vbproj*.</span></span>

1. <span data-ttu-id="21a67-149">Ejecute el comando [dotnet pack](../tools/dotnet-pack.md) para generar un paquete con una extensión *.nupkg*:</span><span class="sxs-lookup"><span data-stu-id="21a67-149">Run the [dotnet pack](../tools/dotnet-pack.md) command to generate a package with a *.nupkg* extension:</span></span>

   ```dotnetcli
   dotnet pack --no-build
   ```

   > [!TIP]
   > <span data-ttu-id="21a67-150">Si el directorio que contiene *dotnet.exe* no está en la ruta de acceso, puede encontrar su ubicación escribiendo `where dotnet.exe` en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="21a67-150">If the directory that contains *dotnet.exe* is not in your PATH, you can find its location by entering `where dotnet.exe` in the console window.</span></span>

<span data-ttu-id="21a67-151">Para más información sobre la creación de paquetes NuGet, consulte [Creación de un paquete NuGet con la CLI de .NET Core](../deploying/creating-nuget-packages.md).</span><span class="sxs-lookup"><span data-stu-id="21a67-151">For more information on creating NuGet packages, see [How to create a NuGet package with the .NET Core CLI](../deploying/creating-nuget-packages.md).</span></span>
