---
title: "Cómo: Compilar un ensamblado de varios archivos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
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
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f77922d08ce17f8b8659eac0dba5a46ca33a7502
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="4286f-102">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="4286f-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="4286f-103">En este artículo se explica cómo crear un ensamblado de múltiples archivos e incluye código que muestra cada paso del procedimiento.</span><span class="sxs-lookup"><span data-stu-id="4286f-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4286f-104">El IDE de Visual Studio para C# y Visual Basic solo se pueden utilizar para crear ensamblados de un solo archivo.</span><span class="sxs-lookup"><span data-stu-id="4286f-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="4286f-105">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual Studio con Visual C++.</span><span class="sxs-lookup"><span data-stu-id="4286f-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>  
  
### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="4286f-106">Para crear un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="4286f-106">To create a multifile assembly</span></span>  
  
1.  <span data-ttu-id="4286f-107">Compile en módulos de código todos los archivos que contengan espacios de nombres a los que hacen referencia otros módulos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="4286f-108">La extensión predeterminada de los módulos de código es .netmodule.</span><span class="sxs-lookup"><span data-stu-id="4286f-108">The default extension for code modules is .netmodule.</span></span>  
  
     <span data-ttu-id="4286f-109">Por ejemplo, supongamos que el archivo `Stringer` tiene un espacio de nombres denominado `myStringer`, que incluye una clase denominada `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="4286f-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="4286f-110">La clase `Stringer` contiene un método denominado `StringerMethod` que escribe una única línea en la consola.</span><span class="sxs-lookup"><span data-stu-id="4286f-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     <span data-ttu-id="4286f-111">Use el comando siguiente para compilar este código:</span><span class="sxs-lookup"><span data-stu-id="4286f-111">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     <span data-ttu-id="4286f-112">Si se especifica el parámetro *module* con la opción del compilador **/t:**, se indica que el archivo se debe compilar como un módulo y no como un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-112">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="4286f-113">El compilador produce un módulo denominado `Stringer.netmodule`, que se puede agregar a un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-113">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>  
  
2.  <span data-ttu-id="4286f-114">Compile los módulos restantes, usando las opciones de compilador necesarias para indicar los otros módulos a los que hace referencia el código.</span><span class="sxs-lookup"><span data-stu-id="4286f-114">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="4286f-115">En este paso se usa la opción del compilador **/addmodule**.</span><span class="sxs-lookup"><span data-stu-id="4286f-115">This step uses the **/addmodule** compiler option.</span></span>  
  
     <span data-ttu-id="4286f-116">En el siguiente ejemplo, un módulo de código denominado `Client` tiene un método `Main` de punto de entrada que hace referencia a un método del módulo `Stringer.dll` creado en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="4286f-116">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     <span data-ttu-id="4286f-117">Use el comando siguiente para compilar este código:</span><span class="sxs-lookup"><span data-stu-id="4286f-117">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     <span data-ttu-id="4286f-118">Especifique la opción **/t:module**, ya que este módulo se va a agregar a un ensamblado en un paso posterior.</span><span class="sxs-lookup"><span data-stu-id="4286f-118">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="4286f-119">Especifique la opción **/addmodule**, ya que el código de `Client` hace referencia a un espacio de nombres creado por el código en `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="4286f-119">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="4286f-120">El compilador produce un módulo denominado `Client.netmodule` que contiene una referencia a otro módulo, `Stringer.netmodule`.</span><span class="sxs-lookup"><span data-stu-id="4286f-120">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4286f-121">Los compiladores de C# y Visual Basic son compatibles con la creación directa de ensamblados de múltiples archivos mediante las dos siguientes sintaxis distintas.</span><span class="sxs-lookup"><span data-stu-id="4286f-121">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>  
    >   
    >  -   <span data-ttu-id="4286f-122">Dos compilaciones crean un ensamblado de dos archivos:</span><span class="sxs-lookup"><span data-stu-id="4286f-122">Two compilations create a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   <span data-ttu-id="4286f-123">Una compilación crea un ensamblado de dos archivos:</span><span class="sxs-lookup"><span data-stu-id="4286f-123">One compilation creates a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  <span data-ttu-id="4286f-124">Use la [herramienta Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) para crear el archivo de salida que contendrá el manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-124">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="4286f-125">Este archivo contiene información de referencia de todos los módulos o recursos que forman parte del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-125">This file contains reference information for all modules or resources that are part of the assembly.</span></span>  
  
     <span data-ttu-id="4286f-126">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4286f-126">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="4286f-127">**al** \<*nombre del módulo*> \<*nombre del módulo*> …</span><span class="sxs-lookup"><span data-stu-id="4286f-127">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="4286f-128">**/main:**\<*nombre del método*> **/out:**\<*nombre del archivo*> **/target:**\<*tipo de archivo de ensamblado*></span><span class="sxs-lookup"><span data-stu-id="4286f-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>  
  
     <span data-ttu-id="4286f-129">En este comando, los argumentos de *nombre del módulo* especifican el nombre de todos los módulos que se van a incluir en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-129">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="4286f-130">La opción **/main:** especifica el nombre del método que es el punto de entrada del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-130">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="4286f-131">La opción **/out:** especifica el nombre del archivo de salida, que contiene metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-131">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="4286f-132">La opción **/target:** especifica que el ensamblado es un archivo ejecutable de aplicación de consola (.exe), un archivo ejecutable de Windows (.win) o un archivo de biblioteca (.lib).</span><span class="sxs-lookup"><span data-stu-id="4286f-132">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>  
  
     <span data-ttu-id="4286f-133">En el siguiente ejemplo, Al.exe crea un ensamblado que es un ejecutable de aplicación de consola denominado `myAssembly.exe`.</span><span class="sxs-lookup"><span data-stu-id="4286f-133">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="4286f-134">Esta aplicación está formada por dos módulos denominados `Client.netmodule` y `Stringer.netmodule` y por el archivo ejecutable denominado `myAssembly.exe,`, que solo contiene metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4286f-134">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata .</span></span> <span data-ttu-id="4286f-135">El punto de entrada del ensamblado es el método `Main` de la clase `MainClientApp`, que se encuentra en `Client.dll`.</span><span class="sxs-lookup"><span data-stu-id="4286f-135">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     <span data-ttu-id="4286f-136">Se puede usar el [Desensamblador de MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para examinar el contenido de un ensamblado o determinar si un archivo es un ensamblado o un módulo.</span><span class="sxs-lookup"><span data-stu-id="4286f-136">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4286f-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="4286f-137">See Also</span></span>  
 [<span data-ttu-id="4286f-138">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="4286f-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="4286f-139">Ver el contenido de un ensamblado</span><span class="sxs-lookup"><span data-stu-id="4286f-139">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [<span data-ttu-id="4286f-140">Cómo el motor en tiempo de ejecución ubica ensamblados</span><span class="sxs-lookup"><span data-stu-id="4286f-140">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="4286f-141">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="4286f-141">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
