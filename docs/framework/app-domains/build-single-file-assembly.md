---
title: Procedimiento para compilar un ensamblado de un solo archivo de .NET Framework
description: Explore cómo compilar un ensamblado de un solo archivo en .NET. Un ensamblado de un solo archivo puede ser una biblioteca (.dll) destinada a .NET o puede ser un archivo ejecutable (.exe).
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: 482a973631e899b8d4bfc4640eef1ea26173605e
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104922"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="7cce0-104">Procedimiento para compilar un ensamblado de un solo archivo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7cce0-104">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="7cce0-105">Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="7cce0-105">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="7cce0-106">Puede usar los compiladores de la línea de comandos o Visual Studio para crear un ensamblado de un solo archivo que tenga como destino .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7cce0-106">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="7cce0-107">De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión *.exe*.</span><span class="sxs-lookup"><span data-stu-id="7cce0-107">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="7cce0-108">Visual Studio para C# y Visual Basic solo se pueden usar para crear ensamblados de único archivo.</span><span class="sxs-lookup"><span data-stu-id="7cce0-108">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="7cce0-109">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="7cce0-109">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="7cce0-110">En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="7cce0-110">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="7cce0-111">Creación de un ensamblado con una extensión .exe</span><span class="sxs-lookup"><span data-stu-id="7cce0-111">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="7cce0-112">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7cce0-112">At the command prompt, type the following command:</span></span>

<span data-ttu-id="7cce0-113">\<*compiler command*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7cce0-113">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="7cce0-114">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7cce0-114">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="7cce0-115">En el ejemplo siguiente se crea un ensamblado llamado *myCode.exe* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7cce0-115">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="7cce0-116">Creación de un ensamblado con la extensión .exe y especificar el nombre del archivo de salida</span><span class="sxs-lookup"><span data-stu-id="7cce0-116">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="7cce0-117">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="7cce0-117">At the command prompt, type the following command:</span></span>

<span data-ttu-id="7cce0-118">\<*compiler command*> **/out:** \<*file name*> \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7cce0-118">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="7cce0-119">En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7cce0-119">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="7cce0-120">En el ejemplo siguiente se crea un ensamblado llamado *myAssembly.exe* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7cce0-120">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="7cce0-121">Creación de ensamblados de biblioteca</span><span class="sxs-lookup"><span data-stu-id="7cce0-121">Create library assemblies</span></span>
 <span data-ttu-id="7cce0-122">Los ensamblados de biblioteca se parecen a las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="7cce0-122">A library assembly is similar to a class library.</span></span> <span data-ttu-id="7cce0-123">Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="7cce0-123">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="7cce0-124">En el símbolo del sistema, escriba este comando para crear un ensamblado de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="7cce0-124">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="7cce0-125">\<*compiler command*> **-t:library** \<*module name*></span><span class="sxs-lookup"><span data-stu-id="7cce0-125">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="7cce0-126">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7cce0-126">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="7cce0-127">También puede usar otras opciones del compilador, como la opción **-out:** .</span><span class="sxs-lookup"><span data-stu-id="7cce0-127">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="7cce0-128">En el ejemplo siguiente se crea un ensamblado de biblioteca llamado *myCodeAssembly.dll* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7cce0-128">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="7cce0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="7cce0-129">See also</span></span>

- [<span data-ttu-id="7cce0-130">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="7cce0-130">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="7cce0-131">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="7cce0-131">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="7cce0-132">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="7cce0-132">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="7cce0-133">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="7cce0-133">Program with assemblies</span></span>](../../standard/assembly/index.md)
