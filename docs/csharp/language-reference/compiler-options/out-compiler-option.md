---
description: -out (Opciones del compilador de C#)
title: -out (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 409760ee0b147065a2128c62c304fb5d70cfcf42
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91193886"
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="c08c4-103">-out (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="c08c4-103">-out (C# Compiler Options)</span></span>

<span data-ttu-id="c08c4-104">La opción **-out** especifica el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c08c4-104">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c08c4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c08c4-105">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="c08c4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c08c4-106">Arguments</span></span>  

 `filename`  
 <span data-ttu-id="c08c4-107">El nombre del archivo de salida creado por el compilador.</span><span class="sxs-lookup"><span data-stu-id="c08c4-107">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c08c4-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c08c4-108">Remarks</span></span>  

 <span data-ttu-id="c08c4-109">En la línea de comandos, es posible especificar varios archivos de salida de una compilación.</span><span class="sxs-lookup"><span data-stu-id="c08c4-109">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="c08c4-110">El compilador espera encontrar al menos un archivo de código fuente después de la opción **-out**.</span><span class="sxs-lookup"><span data-stu-id="c08c4-110">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="c08c4-111">Posteriormente, todos los archivos de código fuente se compilarán en el archivo de salida especificado por la opción **-out**.</span><span class="sxs-lookup"><span data-stu-id="c08c4-111">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="c08c4-112">Hay que especificar el nombre completo y la extensión del archivo que se quiere crear.</span><span class="sxs-lookup"><span data-stu-id="c08c4-112">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="c08c4-113">Si no se especifica el nombre del archivo de salida:</span><span class="sxs-lookup"><span data-stu-id="c08c4-113">If you do not specify the name of the output file:</span></span>  
  
- <span data-ttu-id="c08c4-114">Un archivo .exe toma el nombre del archivo de código fuente que contiene el método **Main**.</span><span class="sxs-lookup"><span data-stu-id="c08c4-114">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
- <span data-ttu-id="c08c4-115">Un archivo .dll o .netmodule toma el nombre del primer archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="c08c4-115">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="c08c4-116">Un archivo de código fuente usado para compilar un archivo de salida no puede usarse para compilar otro archivo de este tipo en la misma compilación.</span><span class="sxs-lookup"><span data-stu-id="c08c4-116">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="c08c4-117">Cuando se producen varios archivos de salida en una compilación de línea de comandos, recuerde que solo uno de los archivos de salida puede ser un ensamblado y que solo el primero que haya especificado (ya sea implícita o explícitamente con **-out**) puede ser el ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c08c4-117">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="c08c4-118">Todos los módulos que se produzcan como parte de una compilación se convierten en archivos asociados a cualquier ensamblado que también se haya producido en la compilación.</span><span class="sxs-lookup"><span data-stu-id="c08c4-118">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="c08c4-119">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) para ver el manifiesto del ensamblado y los archivos asociados.</span><span class="sxs-lookup"><span data-stu-id="c08c4-119">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="c08c4-120">Es obligatorio usar la opción -out del compilador para que un archivo exe sea el destino de un ensamblado de confianza.</span><span class="sxs-lookup"><span data-stu-id="c08c4-120">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="c08c4-121">Para obtener más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).</span><span class="sxs-lookup"><span data-stu-id="c08c4-121">For more information see [Friend Assemblies](../../../standard/assembly/friend.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="c08c4-122">Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c08c4-122">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="c08c4-123">Abra la página **Propiedades** del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c08c4-123">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="c08c4-124">Haga clic en la página de propiedades **Aplicación**.</span><span class="sxs-lookup"><span data-stu-id="c08c4-124">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="c08c4-125">Modifique la propiedad **Nombre del ensamblado**.</span><span class="sxs-lookup"><span data-stu-id="c08c4-125">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="c08c4-126">Para establecer esta opción del compilador mediante programación: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> es una propiedad de solo lectura que se determina a partir de una combinación del tipo de proyecto (ejecutable, biblioteca, etc.) y el nombre del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="c08c4-126">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="c08c4-127">Es necesario modificar una de estas propiedades o ambas para establecer el nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c08c4-127">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c08c4-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c08c4-128">Example</span></span>  

 <span data-ttu-id="c08c4-129">Compile `t.cs` y cree el archivo de salida `t.exe`, así como compile `t2.cs` y cree el archivo de salida del módulo `mymodule.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="c08c4-129">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="c08c4-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c08c4-130">See also</span></span>

- [<span data-ttu-id="c08c4-131">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="c08c4-131">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="c08c4-132">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="c08c4-132">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
- [<span data-ttu-id="c08c4-133">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="c08c4-133">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
