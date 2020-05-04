---
title: Procedimiento para compilar un ensamblado de un solo archivo de .NET Framework
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
ms.openlocfilehash: b7cb06da74a21dab6f60f0d4c3ac1748fcbe4526
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644300"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="05063-102">Procedimiento para compilar un ensamblado de un solo archivo de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="05063-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="05063-103">Un ensamblado de único archivo, que es el tipo de ensamblado más sencillo, contiene información y la implementación del tipo, así como el [manifiesto del ensamblado](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="05063-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="05063-104">Puede usar los compiladores de la línea de comandos o Visual Studio para crear un ensamblado de un solo archivo que tenga como destino .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05063-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="05063-105">De forma predeterminada, el compilador crea un archivo de ensamblado con la extensión *.exe*.</span><span class="sxs-lookup"><span data-stu-id="05063-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="05063-106">Visual Studio para C# y Visual Basic solo se pueden usar para crear ensamblados de único archivo.</span><span class="sxs-lookup"><span data-stu-id="05063-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="05063-107">Si desea crear ensamblados de múltiples archivos, debe usar compiladores de la línea de comandos o Visual C++.</span><span class="sxs-lookup"><span data-stu-id="05063-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="05063-108">En los procedimientos siguientes se muestra cómo crear ensamblados de único archivo mediante los compiladores de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="05063-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="05063-109">Creación de un ensamblado con una extensión .exe</span><span class="sxs-lookup"><span data-stu-id="05063-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="05063-110">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="05063-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="05063-111">\<*comando del compilador*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="05063-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="05063-112">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="05063-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="05063-113">En el ejemplo siguiente se crea un ensamblado llamado *myCode.exe* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="05063-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="05063-114">Creación de un ensamblado con la extensión .exe y especificar el nombre del archivo de salida</span><span class="sxs-lookup"><span data-stu-id="05063-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="05063-115">En el símbolo del sistema, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="05063-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="05063-116">\<*comando del compilador*>  **/out:** \<*nombre del archivo*> \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="05063-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="05063-117">En este comando, *comando del compilador* es el comando del compilador del lenguaje usado en el módulo del código, *nombre del archivo* es el nombre del archivo de salida y *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="05063-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="05063-118">En el ejemplo siguiente se crea un ensamblado llamado *myAssembly.exe* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="05063-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="05063-119">Creación de ensamblados de biblioteca</span><span class="sxs-lookup"><span data-stu-id="05063-119">Create library assemblies</span></span>
 <span data-ttu-id="05063-120">Los ensamblados de biblioteca se parecen a las bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="05063-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="05063-121">Contiene tipos a los que harán referencia otros ensamblados, pero no tiene ningún punto de entrada para comenzar la ejecución.</span><span class="sxs-lookup"><span data-stu-id="05063-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="05063-122">En el símbolo del sistema, escriba este comando para crear un ensamblado de biblioteca:</span><span class="sxs-lookup"><span data-stu-id="05063-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="05063-123">\<*comando del compilador*>  **-t:library** \<*nombre del módulo*></span><span class="sxs-lookup"><span data-stu-id="05063-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="05063-124">En este comando, *comando de compilador* es el comando del compilador del lenguaje usado en el módulo del código, mientras que *nombre del módulo* es el nombre del módulo del código al compilarlo en el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="05063-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="05063-125">También puede usar otras opciones del compilador, como la opción **-out:** .</span><span class="sxs-lookup"><span data-stu-id="05063-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="05063-126">En el ejemplo siguiente se crea un ensamblado de biblioteca llamado *myCodeAssembly.dll* desde un módulo de código denominado `myCode`.</span><span class="sxs-lookup"><span data-stu-id="05063-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="05063-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="05063-127">See also</span></span>

- [<span data-ttu-id="05063-128">Creación de ensamblados</span><span class="sxs-lookup"><span data-stu-id="05063-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="05063-129">Ensamblados de varios archivos</span><span class="sxs-lookup"><span data-stu-id="05063-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="05063-130">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="05063-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="05063-131">Programación con ensamblados</span><span class="sxs-lookup"><span data-stu-id="05063-131">Program with assemblies</span></span>](../../standard/assembly/index.md)
