---
title: Procedimiento para compilar un ensamblado de varios archivos
description: Obtenga información sobre cómo compilar (crear) un ensamblado de varios archivos en .NET con código de ejemplo para ilustrar cada paso del procedimiento.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
ms.openlocfilehash: a4c298284950ba2989bb73e6d3383b3c4024e6e7
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104951"
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="fd4ee-103">Procedimiento para compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="fd4ee-103">How to: Build a multifile assembly</span></span>

<span data-ttu-id="fd4ee-104">En este artículo se explica cómo crear un ensamblado de múltiples archivos e incluye código que muestra cada paso del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-104">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="fd4ee-105">El IDE de Visual Studio para C# y Visual Basic solo se pueden utilizar para crear ensamblados de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-105">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="fd4ee-106">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-106">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="fd4ee-107">Los ensamblados de varios archivos solo se admiten en .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-107">Multifile assemblies are supported by .NET Framework only.</span></span>

## <a name="create-a-multifile-assembly"></a><span data-ttu-id="fd4ee-108">Crear un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="fd4ee-108">Create a multifile assembly</span></span>

1. <span data-ttu-id="fd4ee-109">Compile en módulos de código todos los archivos que contengan espacios de nombres a los que hacen referencia otros módulos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-109">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="fd4ee-110">La extensión predeterminada de los módulos de código es *.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-110">The default extension for code modules is *.netmodule*.</span></span>

   <span data-ttu-id="fd4ee-111">Por ejemplo, supongamos que el archivo `Stringer` tiene un espacio de nombres denominado `myStringer`, que incluye una clase denominada `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-111">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="fd4ee-112">La clase `Stringer` contiene un método denominado `StringerMethod` que escribe una única línea en la consola.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-112">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>

   ```cpp
   // Assembly building example in the .NET Framework.
   using namespace System;

   namespace myStringer
   {
       public ref class Stringer
       {
       public:
           void StringerMethod()
           {
               System::Console::WriteLine("This is a line from StringerMethod.");
           }
       };
   }
   ```

   ```csharp
   // Assembly building example in the .NET Framework.
   using System;

   namespace myStringer
   {
       public class Stringer
       {
           public void StringerMethod()
           {
               System.Console.WriteLine("This is a line from StringerMethod.");
           }
       }
   }
   ```

   ```vb
   ' Assembly building example in the .NET Framework.
   Namespace myStringer
       Public Class Stringer
           Public Sub StringerMethod()
               System.Console.WriteLine("This is a line from StringerMethod.")
           End Sub
       End Class
   End Namespace
   ```

2. <span data-ttu-id="fd4ee-113">Use el comando siguiente para compilar este código:</span><span class="sxs-lookup"><span data-stu-id="fd4ee-113">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /LN Stringer.cpp
   ```

   ```csharp
   csc /t:module Stringer.cs
   ```

   ```vb
   vbc /t:module Stringer.vb
   ```

   <span data-ttu-id="fd4ee-114">Si se especifica el parámetro *module* con la opción del compilador **/t:** , se indica que el archivo se debe compilar como un módulo y no como un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-114">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="fd4ee-115">El compilador produce un módulo denominado *Stringer.netmodule*, que se puede agregar a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-115">The compiler produces a module called *Stringer.netmodule*, which can be added to an assembly.</span></span>

3. <span data-ttu-id="fd4ee-116">Compile los módulos restantes, usando las opciones de compilador necesarias para indicar los otros módulos a los que hace referencia el código.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-116">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="fd4ee-117">En este paso se usa la opción del compilador **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-117">This step uses the **/addmodule** compiler option.</span></span>

   <span data-ttu-id="fd4ee-118">En el siguiente ejemplo, un módulo de código denominado *Client* tiene un método `Main` de punto de entrada que hace referencia a un método del módulo *Stringer.dll* creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-118">In the following example, a code module called *Client* has an entry point `Main` method that references a method in the *Stringer.dll* module created in step 1.</span></span>

   ```cpp
   #using "Stringer.netmodule"

   using namespace System;
   using namespace myStringer; //The namespace created in Stringer.netmodule.

   ref class MainClientApp
   {
       // Static method Main is the entry point method.
   public:
       static void Main()
       {
           Stringer^ myStringInstance = gcnew Stringer();
           Console::WriteLine("Client code executes");
           myStringInstance->StringerMethod();
       }
   };

   int main()
   {
       MainClientApp::Main();
   }
   ```

   ```csharp
   using System;
   using myStringer;

   class MainClientApp
   {
       // Static method Main is the entry point method.
       public static void Main()
       {
           Stringer myStringInstance = new Stringer();
           Console.WriteLine("Client code executes");
           myStringInstance.StringerMethod();
       }
   }
   ```

   ```vb
   Imports myStringer

   Class MainClientApp
       ' Static method Main is the entry point method.
       Public Shared Sub Main()
           Dim myStringInstance As New Stringer()
           Console.WriteLine("Client code executes")
           myStringInstance.StringerMethod()
       End Sub
   End Class
   ```

4. <span data-ttu-id="fd4ee-119">Use el comando siguiente para compilar este código:</span><span class="sxs-lookup"><span data-stu-id="fd4ee-119">Use the following command to compile this code:</span></span>

   ```cpp
   cl /clr:pure /FUStringer.netmodule /LN Client.cpp
   ```

   ```csharp
   csc /addmodule:Stringer.netmodule /t:module Client.cs
   ```

   ```vb
   vbc /addmodule:Stringer.netmodule /t:module Client.vb
   ```

   <span data-ttu-id="fd4ee-120">Especifique la opción **/t:module**, ya que este módulo se va a agregar a un ensamblado en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-120">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="fd4ee-121">Especifique la opción **/addmodule**, ya que el código de *Client* hace referencia a un espacio de nombres creado por el código en *Stringer.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-121">Specify the **/addmodule** option because the code in *Client* references a namespace created by the code in *Stringer.netmodule*.</span></span> <span data-ttu-id="fd4ee-122">El compilador produce un módulo denominado *Client.netmodule* que contiene una referencia a otro módulo, *Stringer.netmodule*.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-122">The compiler produces a module called *Client.netmodule* that contains a reference to another module, *Stringer.netmodule*.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fd4ee-123">Los compiladores de C# y Visual Basic son compatibles con la creación directa de ensamblados de múltiples archivos mediante las dos siguientes sintaxis distintas.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-123">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>
   >
   > <span data-ttu-id="fd4ee-124">Dos compilaciones crean un ensamblado de dos archivos:</span><span class="sxs-lookup"><span data-stu-id="fd4ee-124">Two compilations create a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /t:module Stringer.cs
   >   csc Client.cs /addmodule:Stringer.netmodule
   >   ```
   >
   >   ```vb
   >   vbc /t:module Stringer.vb
   >   vbc Client.vb /addmodule:Stringer.netmodule
   >   ```
   >
   > <span data-ttu-id="fd4ee-125">Una compilación crea un ensamblado de dos archivos:</span><span class="sxs-lookup"><span data-stu-id="fd4ee-125">One compilation creates a two-file assembly:</span></span>
   >
   >   ```cpp
   >   cl /clr:pure /LN Stringer.cpp
   >   cl /clr:pure Client.cpp /link /ASSEMBLYMODULE:Stringer.netmodule
   >   ```
   >
   >   ```csharp
   >   csc /out:Client.exe Client.cs /out:Stringer.netmodule Stringer.cs
   >   ```
   >
   >   ```vb
   >   vbc /out:Client.exe Client.vb /out:Stringer.netmodule Stringer.vb
   >   ```

5. <span data-ttu-id="fd4ee-126">Use la [herramienta Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) para crear el archivo de salida que contendrá el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-126">Use the [Assembly Linker (Al.exe)](../tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="fd4ee-127">Este archivo contiene información de referencia de todos los módulos o recursos que forman parte del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-127">This file contains reference information for all modules or resources that are part of the assembly.</span></span>

    <span data-ttu-id="fd4ee-128">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fd4ee-128">At the command prompt, type the following command:</span></span>

    <span data-ttu-id="fd4ee-129">**al** \<*module name*> \<*module name*> …</span><span class="sxs-lookup"><span data-stu-id="fd4ee-129">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="fd4ee-130">**/main:** \<*method name*> **/out:** \<*file name*> **/target:** \<*assembly file type*></span><span class="sxs-lookup"><span data-stu-id="fd4ee-130">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>

    <span data-ttu-id="fd4ee-131">En este comando, los argumentos de *nombre del módulo* especifican el nombre de todos los módulos que se van a incluir en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-131">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="fd4ee-132">La opción **/main:** especifica el nombre del método que es el punto de entrada del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-132">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="fd4ee-133">La opción **/out:** especifica el nombre del archivo de salida, que contiene metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-133">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="fd4ee-134">La opción **/target:** especifica que el ensamblado es un archivo ejecutable de aplicación de consola ( *.exe*), un archivo ejecutable de Windows ( *.win*) o un archivo de biblioteca ( *.lib*).</span><span class="sxs-lookup"><span data-stu-id="fd4ee-134">The **/target:** option specifies that the assembly is a console application executable (*.exe*) file, a Windows executable (*.win*) file, or a library (*.lib*) file.</span></span>

    <span data-ttu-id="fd4ee-135">En el siguiente ejemplo, *Al.exe* crea un ensamblado que es un ejecutable de aplicación de consola denominado *myAssembly.exe*.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-135">In the following example, *Al.exe* creates an assembly that is a console application executable called *myAssembly.exe*.</span></span> <span data-ttu-id="fd4ee-136">Esta aplicación está formada por dos módulos denominados *Client.netmodule* y *Stringer.netmodule*, y por el archivo ejecutable llamado *myAssembly.exe*, que solo contiene metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-136">The application consists of two modules called *Client.netmodule* and *Stringer.netmodule*, and the executable file called *myAssembly.exe*, which contains only assembly metadata.</span></span> <span data-ttu-id="fd4ee-137">El punto de entrada del ensamblado es el método `Main` de la clase `MainClientApp`, el cual se encuentra en *Client.dll*.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-137">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in *Client.dll*.</span></span>

    ```cmd
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe
    ```

    <span data-ttu-id="fd4ee-138">Se puede usar el [Desensamblador de MSIL (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) para examinar el contenido de un ensamblado o determinar si un archivo es un ensamblado o un módulo.</span><span class="sxs-lookup"><span data-stu-id="fd4ee-138">You can use the [MSIL Disassembler (Ildasm.exe)](../tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd4ee-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd4ee-139">See also</span></span>

- [<span data-ttu-id="fd4ee-140">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="fd4ee-140">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="fd4ee-141">Cómo: Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="fd4ee-141">How to: View assembly contents</span></span>](../../standard/assembly/view-contents.md)
- [<span data-ttu-id="fd4ee-142">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="fd4ee-142">How the runtime locates assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="fd4ee-143">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="fd4ee-143">Multifile assemblies</span></span>](multifile-assemblies.md)
