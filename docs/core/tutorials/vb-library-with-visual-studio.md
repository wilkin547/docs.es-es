---
title: Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017
description: Obtenga información sobre cómo crear una biblioteca de clases escrita en Visual Basic con Visual Studio 2017
author: rpetrusha
ms.author: ronpet
ms.date: 08/07/2017
dev_langs:
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 52bbae330afe4a9ea376c6388a06941f74f6606a
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2018
ms.locfileid: "48035979"
---
# <a name="building-a-class-library-with-visual-basic-and-net-core-in-visual-studio-2017"></a><span data-ttu-id="7d4ed-103">Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="7d4ed-103">Building a class library with Visual Basic and .NET Core in Visual Studio 2017</span></span>

<span data-ttu-id="7d4ed-104">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="7d4ed-105">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-105">A class library that targets the .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of the .NET Standard.</span></span> <span data-ttu-id="7d4ed-106">Cuando termine la biblioteca de clases, puede decidir si quiere distribuirla como un componente de terceros o si la quiere incluir como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-106">When you finish your class library, you can decide whether you want to distribute it as a third-party component or whether you want to include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="7d4ed-107">Para ver una lista de las versiones de .NET Standard y las plataformas que admiten, vea [.NET Standard](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="7d4ed-107">For a list of the .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="7d4ed-108">En este tema, se creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-108">In this topic, you'll create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="7d4ed-109">Se implementará como un [método de extensión](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-109">You'll implement it as an [extension method](../../visual-basic/programming-guide/language-features/procedures/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="creating-a-class-library-solution"></a><span data-ttu-id="7d4ed-110">Creación de una solución de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7d4ed-110">Creating a class library solution</span></span>

<span data-ttu-id="7d4ed-111">Para empezar, se crea una solución para el proyecto de biblioteca de clases y sus proyectos relacionados.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-111">Start by creating a solution for your class library project and its related projects.</span></span> <span data-ttu-id="7d4ed-112">Una solución de Visual Studio solo sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-112">A Visual Studio Solution just serves as a container for one or more projects.</span></span> <span data-ttu-id="7d4ed-113">Para crear la solución:</span><span class="sxs-lookup"><span data-stu-id="7d4ed-113">To create the solution:</span></span>

1. <span data-ttu-id="7d4ed-114">En la barra de menús de Visual Studio, elija **Archivo** > **Nuevo** > **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-114">On the Visual Studio menu bar, choose **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="7d4ed-115">En el cuadro de diálogo **Nuevo proyecto**, expanda el nodo **Otros tipos de proyectos** y seleccione **Soluciones de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-115">In the **New Project** dialog, expand the **Other Project Types** node, and select **Visual Studio Solutions**.</span></span> <span data-ttu-id="7d4ed-116">Asigne a la solución el nombre "ClassLibraryProjects" y pulse el botón **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-116">Name the solution "ClassLibraryProjects" and select the **OK** button.</span></span>

   ![Cuadro de diálogo Nuevo proyecto](./media/library-with-visual-studio/newproject.png)

## <a name="creating-the-class-library-project"></a><span data-ttu-id="7d4ed-118">Creación del proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="7d4ed-118">Creating the class library project</span></span>

<span data-ttu-id="7d4ed-119">Crear el proyecto de biblioteca de clases:</span><span class="sxs-lookup"><span data-stu-id="7d4ed-119">Create your class library project:</span></span>

1. <span data-ttu-id="7d4ed-120">En el **Explorador de soluciones**, haga clic con el botón derecho en el archivo de solución **ClassLibraryProjects** y seleccione **Agregar** > **Nuevo proyecto** en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-120">In **Solution Explorer**, right-click on the **ClassLibraryProjects** solution file and from the context menu, select **Add** > **New Project**.</span></span>

1. <span data-ttu-id="7d4ed-121">En el cuadro de diálogo **Agregar nuevo proyecto**, expanda el nodo **Visual Basic**, después seleccione el nodo **.NET Standard** seguido de la plantilla del proyecto **Biblioteca de clases (.NET Standard)**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-121">In the **Add New Project** dialog, expand the **Visual Basic** node, then select the **.NET Standard** node followed by the **Class Library (.NET Standard)** project template.</span></span> <span data-ttu-id="7d4ed-122">En el cuadro de texto **Nombre**, escriba "StringLibrary" como nombre del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-122">In the **Name** text box, enter "StringLibrary" as the name of the project.</span></span> <span data-ttu-id="7d4ed-123">Pulse **Aceptar** para crear el proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-123">Select **OK** to create the class library project.</span></span>

   ![Cuadro de diálogo Agregar nuevo proyecto](./media/vb-library-with-visual-studio/libproject.png)

   <span data-ttu-id="7d4ed-125">La ventana de código se abre después en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-125">The code window then opens in the Visual Studio development environment.</span></span> 
 
   ![Ventana de aplicación de Visual Studio que muestra el código de plantilla de biblioteca de clases predeterminado](./media/vb-library-with-visual-studio/stringlibrary.png)

1. <span data-ttu-id="7d4ed-127">Compruebe para asegurarse de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-127">Check to make sure that the library targets the correct version of the .NET Standard.</span></span> <span data-ttu-id="7d4ed-128">Haga clic con el botón derecho en el proyecto de la biblioteca en las ventanas del **Explorador de soluciones** y, después, seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-128">Right-click on the library project in the **Solution Explorer** windows, then select **Properties**.</span></span> <span data-ttu-id="7d4ed-129">El cuadro de texto **Plataforma de destino** muestra que nos referimos a .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-129">The **Target Framework** text box shows that we're targeting .NET Standard 2.0.</span></span>

   ![Propiedades del proyecto para la biblioteca de clases](./media/library-with-visual-studio/properties.png)

1. <span data-ttu-id="7d4ed-131">Además en el cuadro de diálogo **Propiedades**, borre el texto del cuadro de texto **Espacio de nombres raíz**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-131">Also in the **Properties** dialog, clear the text in the **Root namespace** text box.</span></span> <span data-ttu-id="7d4ed-132">Para cada proyecto, Visual Basic crea automáticamente un espacio de nombres que corresponde al nombre del proyecto, y cualquier espacio de nombres definido en los archivos de código fuente es un elemento primario de ese espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-132">For each project, Visual Basic automatically creates a namespace that corresponds to the project name, and any namespaces defined in source code files are parents of that namespace.</span></span> <span data-ttu-id="7d4ed-133">Queremos definir un espacio de nombres de nivel superior con la palabra clave [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md).</span><span class="sxs-lookup"><span data-stu-id="7d4ed-133">We want to define a top-level namespace by using the [`namespace`](../../visual-basic/language-reference/statements/namespace-statement.md) keyword.</span></span>
  
1. <span data-ttu-id="7d4ed-134">Reemplace el código de la ventana de código por el código siguiente y guarde el archivo:</span><span class="sxs-lookup"><span data-stu-id="7d4ed-134">Replace the code in the code window with the following code and save the file:</span></span>

  [!CODE-vb[ClassLib#1](../../../samples/snippets/core/tutorials/vb-library-with-visual-studio/stringlibrary.vb)]

   <span data-ttu-id="7d4ed-135">la biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método llamado `StartsWithUpper`, que devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`, which returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="7d4ed-136">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="7d4ed-137">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="7d4ed-138">En la barra de menús, seleccione **Compilar** > **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-138">On the menu bar, select **Build** > **Build Solution**.</span></span> <span data-ttu-id="7d4ed-139">El proyecto se debería compilar sin errores.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-139">The project should compile without error.</span></span>

   ![Panel de salida que muestra que la compilación se ha realizado correctamente](./media/library-with-visual-studio/buildsucceeds.png)



## <a name="next-step"></a><span data-ttu-id="7d4ed-141">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="7d4ed-141">Next step</span></span>

<span data-ttu-id="7d4ed-142">La biblioteca se ha creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-142">You've successfully built the library.</span></span> <span data-ttu-id="7d4ed-143">Como no se ha llamado a ninguno de los métodos, no se sabe si funciona como estaba previsto.</span><span class="sxs-lookup"><span data-stu-id="7d4ed-143">Because you haven't called any of its methods, you don't know whether it works as expected.</span></span> <span data-ttu-id="7d4ed-144">El siguiente paso en el desarrollo de la biblioteca consiste en probarla mediante un [proyecto de prueba unitaria](testing-library-with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="7d4ed-144">The next step in developing your library is to test it by using a [Unit Test Project](testing-library-with-visual-studio.md).</span></span>
