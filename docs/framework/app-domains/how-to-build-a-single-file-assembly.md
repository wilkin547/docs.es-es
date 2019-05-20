---
title: Procedimiento para compilar un ensamblado de un solo archivo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a409a93e5d84e96bbab13f2f6268d7f7ce6464ed
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634246"
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="96b5a-102">Procedimiento para compilar un ensamblado de un solo archivo</span><span class="sxs-lookup"><span data-stu-id="96b5a-102">How to: Build a Single-File Assembly</span></span>

<span data-ttu-id="96b5a-103">Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="96b5a-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="96b5a-104">Puede usar los compiladores de la línea de comandos o Visual Studio para crear un ensamblado de único archivo.</span><span class="sxs-lookup"><span data-stu-id="96b5a-104">You can use command-line compilers or Visual Studio to create a single-file assembly.</span></span> <span data-ttu-id="96b5a-105">De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión .exe.</span><span class="sxs-lookup"><span data-stu-id="96b5a-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>

> [!NOTE]
> <span data-ttu-id="96b5a-106">Visual Studio para C# y Visual Basic solo se pueden usar para crear ensamblados de único archivo.</span><span class="sxs-lookup"><span data-stu-id="96b5a-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="96b5a-107">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="96b5a-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="96b5a-108">En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="96b5a-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="96b5a-109">Para crear un ensamblado con una extensión .exe</span><span class="sxs-lookup"><span data-stu-id="96b5a-109">To create an assembly with an .exe extension</span></span>

1. <span data-ttu-id="96b5a-110">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="96b5a-110">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="96b5a-111">\<*comando del compilador*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="96b5a-111">\<*compiler command*> \<*module name*></span></span>

     <span data-ttu-id="96b5a-112">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="96b5a-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="96b5a-113">En el ejemplo siguiente se crea un ensamblado llamado `myCode.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="96b5a-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="96b5a-114">Para crear un ensamblado con la extensión .exe y especificar el nombre de archivo de salida</span><span class="sxs-lookup"><span data-stu-id="96b5a-114">To create an assembly with an .exe extension and specify the output file name</span></span>

1. <span data-ttu-id="96b5a-115">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="96b5a-115">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="96b5a-116">\<*comando del compilador*> **/out:**\<*nombre del archivo*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="96b5a-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

     <span data-ttu-id="96b5a-117">En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="96b5a-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="96b5a-118">En el ejemplo siguiente se crea un ensamblado llamado `myAssembly.exe` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="96b5a-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a><span data-ttu-id="96b5a-119">Crear ensamblados de biblioteca</span><span class="sxs-lookup"><span data-stu-id="96b5a-119">Creating Library Assemblies</span></span>
 <span data-ttu-id="96b5a-120">Los ensamblados de biblioteca se parecen a las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="96b5a-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="96b5a-121">Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="96b5a-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

### <a name="to-create-a-library-assembly"></a><span data-ttu-id="96b5a-122">Para crear un ensamblado de biblioteca</span><span class="sxs-lookup"><span data-stu-id="96b5a-122">To create a library assembly</span></span>

1. <span data-ttu-id="96b5a-123">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="96b5a-123">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="96b5a-124">\<*comando del compilador*> **-t:library** \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="96b5a-124">\<*compiler command*> **-t:library** \<*module name*></span></span>

     <span data-ttu-id="96b5a-125">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="96b5a-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="96b5a-126">También puede usar otras opciones del compilador, como la opción **-out:**.</span><span class="sxs-lookup"><span data-stu-id="96b5a-126">You can also use other compiler options, such as the **-out:** option.</span></span>

 <span data-ttu-id="96b5a-127">En el ejemplo siguiente se crea un ensamblado de biblioteca llamado `myCodeAssembly.dll` desde un módulo de código llamado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="96b5a-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="96b5a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="96b5a-128">See also</span></span>

- [<span data-ttu-id="96b5a-129">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="96b5a-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="96b5a-130">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="96b5a-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="96b5a-131">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="96b5a-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="96b5a-132">Programar con ensamblados</span><span class="sxs-lookup"><span data-stu-id="96b5a-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
