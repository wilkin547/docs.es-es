---
title: Creación de una biblioteca de clases de .NET Standard con C# en Visual Studio 2017
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard escrita en C# con Visual Studio 2017.
author: BillWagner
ms.author: wiwagn
ms.date: 08/07/2017
ms.custom: vs-dotnet, seodec18
ms.openlocfilehash: 2af688057dbb3724ea03818157368ff0b54f0cf2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53144587"
---
# <a name="build-a-net-standard-class-library-with-c-and-the-net-core-sdk-in-visual-studio-2017"></a><span data-ttu-id="98bb7-103">Creación de una biblioteca de clases de .NET Standard con C# y el SDK de .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="98bb7-103">Build a .NET Standard class library with C# and the .NET Core SDK in Visual Studio 2017</span></span>

<span data-ttu-id="98bb7-104">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="98bb7-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="98bb7-105">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="98bb7-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="98bb7-106">Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="98bb7-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="98bb7-107">Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="98bb7-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="98bb7-108">En este tema, se creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="98bb7-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="98bb7-109">Se implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="98bb7-109">You'll implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="98bb7-110">Creación de una solución de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="98bb7-110">Creating a class library solution</span></span>

<span data-ttu-id="98bb7-111">Para empezar, se crea una solución para el proyecto de biblioteca de clases y sus proyectos relacionados.</span><span class="sxs-lookup"><span data-stu-id="98bb7-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="98bb7-112">Una solución de Visual Studio solo sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="98bb7-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="98bb7-113">Para crear la solución:</span><span class="sxs-lookup"><span data-stu-id="98bb7-113">To create the solution:</span></span>

1. <span data-ttu-id="98bb7-114">En la barra de menús de Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="98bb7-115">En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Otros tipos de proyectos** y seleccione **Soluciones de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="98bb7-116">Asigne a la solución el nombre "ClassLibraryProjects" y pulse el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Cuadro de diálogo Nuevo proyecto](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="98bb7-118">Creación del proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="98bb7-118">Creating the class library project</span></span>

<span data-ttu-id="98bb7-119">Crear el proyecto de biblioteca de clases:</span><span class="sxs-lookup"><span data-stu-id="98bb7-119">Create your class library project:</span></span>

1. <span data-ttu-id="98bb7-120">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="98bb7-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="98bb7-121">En el cuadro de diálogo **Agregar nuevo proyecto**, expanda el nodo **Visual C#**, después seleccione el nodo **.NET Standard** seguido de la plantilla del proyecto **Biblioteca de clases (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-121">In the **Add New Project** dialog, expand the **Visual C#** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="98bb7-122">En el cuadro de texto **Nombre**, escriba "StringLibrary" como nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="98bb7-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="98bb7-123">Pulse **Aceptar** para crear el proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="98bb7-123">Select **OK** to create the class library project.</span></span>

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/library-with-visual-studio/libproject.png)

   <span data-ttu-id="98bb7-125">La ventana de código se abre después en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="98bb7-125">The code window then opens in the Visual Studio development environment.</span></span>

   ![Ventana de aplicación de Visual Studio que muestra el código de plantilla de biblioteca de clases predeterminado](./media/library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="98bb7-127">Compruebe para asegurarse de que nuestra biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="98bb7-127">Check to make sure that our library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="98bb7-128">Haga clic con el botón derecho en el proyecto de la biblioteca en las ventanas del **Explorador de soluciones** y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="98bb7-129">El cuadro de texto **Plataforma de destino** muestra que nos referimos a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="98bb7-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="98bb7-131">Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="98bb7-131">Replace the code in the code window with the following code and save the file:</span></span>

   [!CODE-csharp[ClassLib#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/classlib.cs)]

   <span data-ttu-id="98bb7-132">la biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método llamado `StartsWithUpper`, que devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="98bb7-132">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="98bb7-133">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="98bb7-133">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="98bb7-134">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="98bb7-134">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="98bb7-135">En la barra de menús, seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="98bb7-135">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="98bb7-136">El proyecto se debería compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="98bb7-136">The project should compile without error.</span></span>

   ![Panel de salida que muestra que la compilación se ha realizado correctamente](./media/library-with-visual-studio/buildsucceeds.png)

## <a name="next-step"></a><span data-ttu-id="98bb7-138">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="98bb7-138">Next step</span></span>

<span data-ttu-id="98bb7-139">La biblioteca se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="98bb7-139">You've successfully built the library.</span></span> <span data-ttu-id="98bb7-140">Como no se ha llamado a ninguno de los métodos, no se sabe si funciona como estaba previsto.</span><span class="sxs-lookup"><span data-stu-id="98bb7-140">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="98bb7-141">El siguiente paso en el desarrollo de la biblioteca consiste en probarla mediante un [proyecto de prueba unitaria](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="98bb7-141">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>