---
title: Creación de una biblioteca de clases de .NET Standard en Visual Studio
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard escrita en C# o Visual Basic con Visual Studio
ms.date: 12/09/2019
ms.custom: vs-dotnet
ms.openlocfilehash: 748a1499e0c3a4a41613a69b715dbcfbd585bfe3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714019"
---
# <a name="build-a-net-standard-library-in-visual-studio"></a><span data-ttu-id="c1174-103">Creación de una de .NET Standard en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1174-103">Build a .NET Standard library in Visual Studio</span></span>

<span data-ttu-id="c1174-104">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1174-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="c1174-105">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="c1174-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="c1174-106">Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c1174-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="c1174-107">Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="c1174-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="c1174-108">En este tema, se creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="c1174-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="c1174-109">Se implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="c1174-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="create-a-visual-studio-solution"></a><span data-ttu-id="c1174-110">Creación de una solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c1174-110">Create a Visual Studio solution</span></span>

<span data-ttu-id="c1174-111">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="c1174-111">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="c1174-112">Una solución de Visual Studio sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="c1174-112">A Visual Studio solution serves as a container for one or more projects.</span></span> <span data-ttu-id="c1174-113">Agregará proyectos adicionales relacionados a la misma solución si continúa con la serie de tutoriales.</span><span class="sxs-lookup"><span data-stu-id="c1174-113">You'll add additional, related projects to the same solution if you continue on with the tutorial series.</span></span>

<span data-ttu-id="c1174-114">Para crear la solución en blanco:</span><span class="sxs-lookup"><span data-stu-id="c1174-114">To create the blank solution:</span></span>

1. <span data-ttu-id="c1174-115">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c1174-115">Open Visual Studio.</span></span>

2. <span data-ttu-id="c1174-116">En la ventana de inicio, elija **Crear un proyecto nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c1174-116">On the start window, choose **Create a new project**.</span></span>

3. <span data-ttu-id="c1174-117">En el cuadro de búsqueda de la página **Crear un nuevo proyecto**, escriba **solución**.</span><span class="sxs-lookup"><span data-stu-id="c1174-117">On the **Create a new project** page, enter **solution** in the search box.</span></span> <span data-ttu-id="c1174-118">Elija la plantilla **Solución en blanco** y luego seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1174-118">Choose the **Blank Solution** template, and then choose **Next**.</span></span>

   ![Plantilla Solución en blanco en Visual Studio](media/library-with-visual-studio/blank-solution.png)

4. <span data-ttu-id="c1174-120">En la página **Configure el nuevo proyecto**, escriba **ClassLibraryProjects** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-120">On the **Configure your new project** page, enter **ClassLibraryProjects** in the **Project name** box.</span></span> <span data-ttu-id="c1174-121">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c1174-121">Then, choose **Create**.</span></span>

> [!TIP]
> <span data-ttu-id="c1174-122">También puede omitir este paso y dejar que Visual Studio cree la solución automáticamente al crear el proyecto en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="c1174-122">You can also skip this step and let Visual Studio create the solution for you when you create the project in the next step.</span></span> <span data-ttu-id="c1174-123">Busque las opciones de la solución en la página **Configure el nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-123">Look for the solution options on the **Configure your new project** page.</span></span>

## <a name="create-a-class-library-project"></a><span data-ttu-id="c1174-124">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="c1174-124">Create a class library project</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="ctabcsharp"></a>[<span data-ttu-id="c1174-125">C#</span><span class="sxs-lookup"><span data-stu-id="c1174-125">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="c1174-126">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard para C# denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="c1174-126">Add a new C# .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="c1174-127">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-127">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c1174-128">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c1174-128">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="c1174-129">Elija **C#** en la lista de lenguajes y, luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="c1174-129">Choose **C#** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c1174-130">Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1174-130">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c1174-131">En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-131">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="c1174-132">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c1174-132">Then, choose **Create**.</span></span>

1. <span data-ttu-id="c1174-133">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c1174-133">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="c1174-134">Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c1174-134">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="c1174-135">El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1174-135">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/library-project-properties.png)

1. <span data-ttu-id="c1174-137">Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="c1174-137">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="c1174-138">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="c1174-138">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="c1174-139">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="c1174-139">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="c1174-140">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c1174-140">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="c1174-141">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c1174-141">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="c1174-142">En la barra de menús, seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="c1174-142">On the menu bar, select **Build** > **Build Solution**.</span></span>

# <a name="visual-basictabvb"></a>[<span data-ttu-id="c1174-143">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c1174-143">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="c1174-144">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard para Visual Basic denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="c1174-144">Add a new Visual Basic .NET Standard class library project named "StringLibrary" to the solution.</span></span>

   1. <span data-ttu-id="c1174-145">Haga clic con el botón derecho en la solución en el **Explorador de soluciones** y seleccione **Agregar** > **Nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-145">Right-click on the solution in **Solution Explorer** and select **Add** > **New project**.</span></span>

   1. <span data-ttu-id="c1174-146">En el cuadro de búsqueda de la página **Agregar un nuevo proyecto**, escriba **biblioteca**.</span><span class="sxs-lookup"><span data-stu-id="c1174-146">On the **Add a new project** page, enter **library** in the search box.</span></span> <span data-ttu-id="c1174-147">Elija **Visual Basic** en la lista de lenguajes y luego, **Todas las plataformas** en la lista de plataformas.</span><span class="sxs-lookup"><span data-stu-id="c1174-147">Choose **Visual Basic** from the Language list, and then choose **All platforms** from the Platform list.</span></span> <span data-ttu-id="c1174-148">Elija la plantilla **Biblioteca de clases (.NET Standard)** y, luego, **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c1174-148">Choose the **Class Library (.NET Standard)** template, and then choose **Next**.</span></span>

   1. <span data-ttu-id="c1174-149">En la página **Configure el nuevo proyecto**, escriba **StringLibrary** en el cuadro **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1174-149">On the **Configure your new project** page, enter **StringLibrary** in the **Project name** box.</span></span> <span data-ttu-id="c1174-150">Luego, elija **Crear**.</span><span class="sxs-lookup"><span data-stu-id="c1174-150">Then, choose **Create**.</span></span>

1. <span data-ttu-id="c1174-151">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c1174-151">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="c1174-152">Haga clic con el botón derecho en el proyecto de biblioteca en el **Explorador de soluciones** y, luego, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c1174-152">Right-click on the library project in **Solution Explorer**, and then select **Properties**.</span></span> <span data-ttu-id="c1174-153">El cuadro de texto **Plataforma de destino** muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="c1174-153">The **Target Framework** text box shows that the project targets .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/vb/library-project-properties.png)

1. <span data-ttu-id="c1174-155">En el cuadro de diálogo **Propiedades**, borre el texto del cuadro de texto **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="c1174-155">In the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="c1174-156">En cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c1174-156">For each project, Visual Basic automatically creates a namespace that corresponds to the project name.</span></span> <span data-ttu-id="c1174-157">En este tutorial, definirá un espacio de nombres de nivel superior mediante la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) en el archivo de código.</span><span class="sxs-lookup"><span data-stu-id="c1174-157">In this tutorial, you define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword in the code file.</span></span>

1. <span data-ttu-id="c1174-158">Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="c1174-158">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="c1174-159">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="c1174-159">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="c1174-160">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="c1174-160">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="c1174-161">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c1174-161">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="c1174-162">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="c1174-162">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="c1174-163">En la barra de menús, seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="c1174-163">On the menu bar, select **Build** > **Build Solution**.</span></span>

---

   <span data-ttu-id="c1174-164">El proyecto se debería compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="c1174-164">The project should compile without error.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1174-165">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c1174-165">Next steps</span></span>

<span data-ttu-id="c1174-166">La biblioteca se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="c1174-166">You've successfully built the library.</span></span> <span data-ttu-id="c1174-167">Como no se ha llamado a ninguno de los métodos, no se sabe si funciona como estaba previsto.</span><span class="sxs-lookup"><span data-stu-id="c1174-167">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="c1174-168">El siguiente paso en el desarrollo de la biblioteca consiste en probarla.</span><span class="sxs-lookup"><span data-stu-id="c1174-168">The next step in developing your library is to test it.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="c1174-169">Crear un proyecto de prueba unitaria</span><span class="sxs-lookup"><span data-stu-id="c1174-169">Create a unit test project</span></span>](testing-library-with-visual-studio.md)
