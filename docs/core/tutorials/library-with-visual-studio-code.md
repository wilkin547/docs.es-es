---
title: Creación de una biblioteca de clases .NET Standard mediante Visual Studio Code
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET Standard mediante Visual Studio Code.
ms.date: 06/08/2020
ms.openlocfilehash: f7d2319bcea58f63ca40e43ba39745bdf1b394ce
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2020
ms.locfileid: "84701804"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a><span data-ttu-id="f48c0-103">Tutorial: Creación de una biblioteca .NET Standard mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f48c0-103">Tutorial: Create a .NET Standard library using Visual Studio Code</span></span>

<span data-ttu-id="f48c0-104">En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="f48c0-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="f48c0-105">Lo implementará como un [método de extensión](../../csharp/programming-guide/classes-and-structs/extension-methods.md) de modo que se pueda llamar como si fuera un miembro de la clase <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f48c0-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="f48c0-106">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f48c0-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="f48c0-107">Una biblioteca de clases que tiene como destino .NET Standard 2.0, lo que permite que cualquier implementación .NET que admita esa versión de .NET Standard pueda llamar a su biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f48c0-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="f48c0-108">Cuando termine la biblioteca de clases, puede distribuirla como un componente de terceros o como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f48c0-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f48c0-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f48c0-109">Prerequisites</span></span>

1. <span data-ttu-id="f48c0-110">[Visual Studio Code](https://code.visualstudio.com/) con la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada.</span><span class="sxs-lookup"><span data-stu-id="f48c0-110">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="f48c0-111">Para saber cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="f48c0-111">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="f48c0-112">[SDK de .NET Core 3.1 o posterior](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="f48c0-112">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="f48c0-113">Crear una solución</span><span class="sxs-lookup"><span data-stu-id="f48c0-113">Create a solution</span></span>

<span data-ttu-id="f48c0-114">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="f48c0-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="f48c0-115">Una solución sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="f48c0-115">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="f48c0-116">Agregará otros proyectos relacionados a la misma solución.</span><span class="sxs-lookup"><span data-stu-id="f48c0-116">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="f48c0-117">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="f48c0-117">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="f48c0-118">Seleccione **Archivo** > **Abrir carpeta** (**Abrir...** en macOS) en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="f48c0-118">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="f48c0-119">En el cuadro de diálogo **Abrir carpeta**, cree una carpeta *ClassLibraryProjects* y haga clic en **Seleccionar carpeta** (**Abrir** en macOS).</span><span class="sxs-lookup"><span data-stu-id="f48c0-119">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="f48c0-120">Para abrir el **Terminal**  en Visual Studio Code, seleccione **Ver** > **Terminal** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="f48c0-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="f48c0-121">Se abre el **terminal** con el símbolo del sistema en la carpeta *ClassLibraryProjects*.</span><span class="sxs-lookup"><span data-stu-id="f48c0-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="f48c0-122">En el **Terminal**, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="f48c0-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="f48c0-123">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="f48c0-124">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="f48c0-124">Create a class library project</span></span>

<span data-ttu-id="f48c0-125">Agregue un nuevo proyecto de biblioteca de clases de .NET Standard denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="f48c0-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="f48c0-126">En el terminal, ejecute el siguiente comando para crear un proyecto de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="f48c0-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="f48c0-127">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="f48c0-128">Ejecute el siguiente comando para agregar el proyecto de biblioteca a la solución:</span><span class="sxs-lookup"><span data-stu-id="f48c0-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="f48c0-129">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="f48c0-130">Asegúrese de que la biblioteca tiene como destino la versión correcta de .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="f48c0-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="f48c0-131">En **Explorer**, abra el archivo *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="f48c0-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="f48c0-132">En el elemento `TargetFramework` se muestra que el proyecto tiene como destino .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="f48c0-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="f48c0-133">Abra *Class1.cs* y reemplace el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="f48c0-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="f48c0-134">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="f48c0-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="f48c0-135">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="f48c0-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="f48c0-136">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="f48c0-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="f48c0-137">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="f48c0-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="f48c0-138">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="f48c0-138">Save the file.</span></span>

1. <span data-ttu-id="f48c0-139">Ejecute el siguiente comando para compilar la solución y comprobar que el proyecto se compila sin errores.</span><span class="sxs-lookup"><span data-stu-id="f48c0-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="f48c0-140">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="f48c0-141">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="f48c0-141">Add a console app to the solution</span></span>

<span data-ttu-id="f48c0-142">Agregue una aplicación de consola que use la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="f48c0-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="f48c0-143">La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="f48c0-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="f48c0-144">En el terminal, ejecute el siguiente comando para crear un proyecto de consola de aplicación:</span><span class="sxs-lookup"><span data-stu-id="f48c0-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="f48c0-145">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="f48c0-146">Ejecute el siguiente comando para agregar el proyecto de aplicación de consola a la solución:</span><span class="sxs-lookup"><span data-stu-id="f48c0-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="f48c0-147">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="f48c0-148">Abra *ShowCase/Program.cs* y reemplace todo el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="f48c0-148">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="f48c0-149">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="f48c0-149">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="f48c0-150">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="f48c0-150">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="f48c0-151">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="f48c0-151">The program prompts the user to enter a string.</span></span> <span data-ttu-id="f48c0-152">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="f48c0-152">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="f48c0-153">Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="f48c0-153">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="f48c0-154">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="f48c0-154">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="f48c0-155">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="f48c0-155">Add a project reference</span></span>

<span data-ttu-id="f48c0-156">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="f48c0-156">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="f48c0-157">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="f48c0-157">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="f48c0-158">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f48c0-158">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="f48c0-159">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-159">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="f48c0-160">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f48c0-160">Run the app</span></span>

1. <span data-ttu-id="f48c0-161">Ejecute el siguiente comando en el terminal:</span><span class="sxs-lookup"><span data-stu-id="f48c0-161">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="f48c0-162">Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.</span><span class="sxs-lookup"><span data-stu-id="f48c0-162">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="f48c0-163">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f48c0-163">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="f48c0-164">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f48c0-164">Additional resources</span></span>

* [<span data-ttu-id="f48c0-165">Desarrollo de bibliotecas con la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="f48c0-165">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="f48c0-166">[Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="f48c0-166">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f48c0-167">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f48c0-167">Next steps</span></span>

<span data-ttu-id="f48c0-168">En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="f48c0-168">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="f48c0-169">En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.</span><span class="sxs-lookup"><span data-stu-id="f48c0-169">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f48c0-170">Prueba de una biblioteca .NET Standard con .NET Core mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="f48c0-170">Test a .NET Standard library with .NET Core using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
