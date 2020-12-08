---
title: Creación de una biblioteca de clases de .NET con Visual Studio Code
description: Obtenga información sobre cómo crear una biblioteca de clases de .NET mediante Visual Studio Code.
ms.date: 11/18/2020
ms.openlocfilehash: 4473163b76060623b364d7dabf7366c3575e3dcd
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599504"
---
# <a name="tutorial-create-a-net-class-library-using-visual-studio-code"></a><span data-ttu-id="96e04-103">Tutorial: Creación de una biblioteca de clases de .NET con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="96e04-103">Tutorial: Create a .NET class library using Visual Studio Code</span></span>

<span data-ttu-id="96e04-104">En este tutorial, creará una sencilla biblioteca de utilidades que contiene un único método de control de cadenas.</span><span class="sxs-lookup"><span data-stu-id="96e04-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span>

<span data-ttu-id="96e04-105">Una *biblioteca de clases* define los tipos y los métodos que se llaman desde una aplicación.</span><span class="sxs-lookup"><span data-stu-id="96e04-105">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="96e04-106">Si la biblioteca tiene como destino .NET Standard 2.0, se puede llamar mediante cualquier implementación de .NET (incluido .NET Framework) que admita .NET Standard 2.0.</span><span class="sxs-lookup"><span data-stu-id="96e04-106">If the library targets .NET Standard 2.0, it can be called by any .NET implementation (including .NET Framework) that supports .NET Standard 2.0.</span></span> <span data-ttu-id="96e04-107">Si la biblioteca tiene como destino .NET 5, la puede llamar cualquier aplicación que tenga como destino .NET 5.</span><span class="sxs-lookup"><span data-stu-id="96e04-107">If the library targets .NET 5, it can be called by any application that targets .NET 5.</span></span> <span data-ttu-id="96e04-108">En este tutorial se muestra cómo seleccionar .NET 5 como destino.</span><span class="sxs-lookup"><span data-stu-id="96e04-108">This tutorial shows how to target .NET 5.</span></span>

<span data-ttu-id="96e04-109">Al crear una biblioteca de clases, puede distribuirla como un componente de terceros o como un componente empaquetado con una o varias aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="96e04-109">When you create a class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96e04-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96e04-110">Prerequisites</span></span>

1. <span data-ttu-id="96e04-111">[Visual Studio Code](https://code.visualstudio.com/) con la [extensión de C#](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) instalada.</span><span class="sxs-lookup"><span data-stu-id="96e04-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="96e04-112">Para saber cómo instalar extensiones en Visual Studio Code, vea el [Marketplace de extensiones de VS Code](https://code.visualstudio.com/docs/editor/extension-gallery).</span><span class="sxs-lookup"><span data-stu-id="96e04-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="96e04-113">[SDK de .NET 5.0 o posterior](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="96e04-113">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="96e04-114">Crear una solución</span><span class="sxs-lookup"><span data-stu-id="96e04-114">Create a solution</span></span>

<span data-ttu-id="96e04-115">Empiece por crear una solución en blanco para colocar el proyecto de biblioteca de clases en ella.</span><span class="sxs-lookup"><span data-stu-id="96e04-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="96e04-116">Una solución sirve como contenedor de uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="96e04-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="96e04-117">Agregará otros proyectos relacionados a la misma solución.</span><span class="sxs-lookup"><span data-stu-id="96e04-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="96e04-118">Inicie Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="96e04-118">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="96e04-119">Seleccione **Archivo** > **Abrir carpeta** (**Abrir...** en macOS) en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="96e04-119">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="96e04-120">En el cuadro de diálogo **Abrir carpeta**, cree una carpeta *ClassLibraryProjects* y haga clic en **Seleccionar carpeta** (**Abrir** en macOS).</span><span class="sxs-lookup"><span data-stu-id="96e04-120">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="96e04-121">Para abrir el **Terminal**  en Visual Studio Code, seleccione **Ver** > **Terminal** en el menú principal.</span><span class="sxs-lookup"><span data-stu-id="96e04-121">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="96e04-122">Se abre el **terminal** con el símbolo del sistema en la carpeta *ClassLibraryProjects*.</span><span class="sxs-lookup"><span data-stu-id="96e04-122">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="96e04-123">En el **Terminal**, escriba este comando:</span><span class="sxs-lookup"><span data-stu-id="96e04-123">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="96e04-124">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-124">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="96e04-125">Crear un proyecto de biblioteca de clases</span><span class="sxs-lookup"><span data-stu-id="96e04-125">Create a class library project</span></span>

<span data-ttu-id="96e04-126">Agregue un nuevo proyecto de biblioteca de clases de .NET denominado "StringLibrary" a la solución.</span><span class="sxs-lookup"><span data-stu-id="96e04-126">Add a new .NET class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="96e04-127">En el terminal, ejecute el siguiente comando para crear un proyecto de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="96e04-127">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="96e04-128">El comando `-o` o `--output` especifica la ubicación para colocar la salida generada.</span><span class="sxs-lookup"><span data-stu-id="96e04-128">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="96e04-129">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-129">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="96e04-130">Ejecute el siguiente comando para agregar el proyecto de biblioteca a la solución:</span><span class="sxs-lookup"><span data-stu-id="96e04-130">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="96e04-131">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-131">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="96e04-132">Asegúrese de que la biblioteca tiene como destino .NET 5.</span><span class="sxs-lookup"><span data-stu-id="96e04-132">Check to make sure that the library targets .NET 5.</span></span> <span data-ttu-id="96e04-133">En **Explorer**, abra el archivo *StringLibrary/StringLibrary.csproj*.</span><span class="sxs-lookup"><span data-stu-id="96e04-133">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="96e04-134">En el elemento `TargetFramework` se muestra que el proyecto tiene como destino .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="96e04-134">The `TargetFramework` element shows that the project targets .NET 5.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>net5.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="96e04-135">Abra *Class1.cs* y reemplace el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="96e04-135">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="96e04-136">La biblioteca de clases, `UtilityLibraries.StringLibrary`, contiene un método denominado `StartsWithUpper`.</span><span class="sxs-lookup"><span data-stu-id="96e04-136">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="96e04-137">Este método devuelve un valor <xref:System.Boolean> que indica si la instancia de cadena actual comienza con un carácter en mayúscula.</span><span class="sxs-lookup"><span data-stu-id="96e04-137">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="96e04-138">El estándar Unicode distingue caracteres en mayúsculas de caracteres en minúsculas.</span><span class="sxs-lookup"><span data-stu-id="96e04-138">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="96e04-139">El método <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> devuelve `true` si un carácter está en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="96e04-139">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="96e04-140">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="96e04-140">Save the file.</span></span>

1. <span data-ttu-id="96e04-141">Ejecute el siguiente comando para compilar la solución y comprobar que el proyecto se compila sin errores.</span><span class="sxs-lookup"><span data-stu-id="96e04-141">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="96e04-142">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-142">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\net5.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="96e04-143">Incorporación de una aplicación de consola a la solución</span><span class="sxs-lookup"><span data-stu-id="96e04-143">Add a console app to the solution</span></span>

<span data-ttu-id="96e04-144">Agregue una aplicación de consola que use la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="96e04-144">Add a console application that uses the class library.</span></span> <span data-ttu-id="96e04-145">La aplicación solicitará al usuario que escriba una cadena y notificará si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="96e04-145">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="96e04-146">En el terminal, ejecute el siguiente comando para crear un proyecto de consola de aplicación:</span><span class="sxs-lookup"><span data-stu-id="96e04-146">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="96e04-147">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-147">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="96e04-148">Ejecute el siguiente comando para agregar el proyecto de aplicación de consola a la solución:</span><span class="sxs-lookup"><span data-stu-id="96e04-148">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="96e04-149">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-149">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="96e04-150">Abra *ShowCase/Program.cs* y reemplace todo el código por el siguiente.</span><span class="sxs-lookup"><span data-stu-id="96e04-150">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="96e04-151">El código usa la variable `row` para mantener un recuento del número de filas de datos escritas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="96e04-151">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="96e04-152">Siempre que sea mayor o igual a 25, el código borra la ventana de consola y muestra un mensaje al usuario.</span><span class="sxs-lookup"><span data-stu-id="96e04-152">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="96e04-153">El programa le pide al usuario que escriba una cadena.</span><span class="sxs-lookup"><span data-stu-id="96e04-153">The program prompts the user to enter a string.</span></span> <span data-ttu-id="96e04-154">Indica si la cadena comienza con un carácter en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="96e04-154">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="96e04-155">Si el usuario presiona la tecla <kbd>Entrar</kbd> sin especificar una cadena, la aplicación finaliza y la ventana de la consola se cierra.</span><span class="sxs-lookup"><span data-stu-id="96e04-155">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="96e04-156">Guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="96e04-156">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="96e04-157">Agregar una referencia de proyecto</span><span class="sxs-lookup"><span data-stu-id="96e04-157">Add a project reference</span></span>

<span data-ttu-id="96e04-158">En un principio, el nuevo proyecto de aplicación de consola no tiene acceso a la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="96e04-158">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="96e04-159">Para que pueda llamar a los métodos de la biblioteca de clases, cree una referencia de proyecto al proyecto de biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="96e04-159">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="96e04-160">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="96e04-160">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="96e04-161">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-161">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="96e04-162">Ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="96e04-162">Run the app</span></span>

1. <span data-ttu-id="96e04-163">Ejecute el siguiente comando en el terminal:</span><span class="sxs-lookup"><span data-stu-id="96e04-163">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="96e04-164">Para probar el programa, escriba cadenas y presione <kbd>Entrar</kbd> y, después, presione <kbd>Entrar</kbd> para salir.</span><span class="sxs-lookup"><span data-stu-id="96e04-164">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="96e04-165">La salida del terminal se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="96e04-165">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="96e04-166">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="96e04-166">Additional resources</span></span>

* [<span data-ttu-id="96e04-167">Desarrollo de bibliotecas con la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="96e04-167">Develop libraries with the .NET CLI</span></span>](libraries.md)
* <span data-ttu-id="96e04-168">[Versiones de .NET Standard y las plataformas que admiten](../../standard/net-standard.md).</span><span class="sxs-lookup"><span data-stu-id="96e04-168">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="96e04-169">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="96e04-169">Next steps</span></span>

<span data-ttu-id="96e04-170">En este tutorial, ha creado una solución, ha agregado un proyecto de biblioteca y ha agregado un proyecto de aplicación de consola que usa la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="96e04-170">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="96e04-171">En el siguiente tutorial, agregará un proyecto de prueba unitaria a la solución.</span><span class="sxs-lookup"><span data-stu-id="96e04-171">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="96e04-172">Prueba de una biblioteca de clases de .NET con .NET mediante Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="96e04-172">Test a .NET class library with .NET using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
