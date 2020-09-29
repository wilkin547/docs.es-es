---
description: -addmodule (Opciones del compilador de C#)
title: -addmodule (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: ec72fc76b3d550029b1286f64b8f86e69e721468
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150575"
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="7e426-103">-addmodule (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="7e426-103">-addmodule (C# Compiler Options)</span></span>

<span data-ttu-id="7e426-104">Esta opción agrega un módulo que se ha creado con el modificador target:module para la compilación actual.</span><span class="sxs-lookup"><span data-stu-id="7e426-104">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e426-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7e426-105">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="7e426-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7e426-106">Arguments</span></span>  

 <span data-ttu-id="7e426-107">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="7e426-107">`file`, `file2`</span></span>  
 <span data-ttu-id="7e426-108">Un archivo de salida que contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="7e426-108">An output file that contains metadata.</span></span> <span data-ttu-id="7e426-109">El archivo no puede contener un manifiesto de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e426-109">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="7e426-110">Para importar más de un archivo, hay que separar los nombres de archivo con una coma o un punto y coma.</span><span class="sxs-lookup"><span data-stu-id="7e426-110">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e426-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7e426-111">Remarks</span></span>  

 <span data-ttu-id="7e426-112">Todos los módulos agregados mediante **-addmodule** deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7e426-112">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="7e426-113">Es decir, puede especificar un módulo de cualquier directorio en el momento de la compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7e426-113">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="7e426-114">Si dicho módulo no se encuentra en el directorio de la aplicación en tiempo de ejecución, obtendrá <xref:System.TypeLoadException>.</span><span class="sxs-lookup"><span data-stu-id="7e426-114">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="7e426-115">`file` no puede contener ningún ensamblado.</span><span class="sxs-lookup"><span data-stu-id="7e426-115">`file` cannot contain an assembly.</span></span> <span data-ttu-id="7e426-116">Por ejemplo, si el archivo de salida se ha creado con [-target:module](./target-module-compiler-option.md), se pueden importar sus metadatos con **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="7e426-116">For example, if the output file was created with [-target:module](./target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="7e426-117">Si se ha creado el archivo de salida con una opción **-target** diferente de **-target:module**, no se podrán importar sus metadatos con **-addmodule**, pero sí con [-reference](./reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7e426-117">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](./reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="7e426-118">Esta opción del compilador no está disponible en Visual Studio; en un proyecto no se puede hacer referencia a un módulo.</span><span class="sxs-lookup"><span data-stu-id="7e426-118">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="7e426-119">Además, esta opción del compilador no se puede modificar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7e426-119">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e426-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7e426-120">Example</span></span>  

 <span data-ttu-id="7e426-121">Compile el archivo de código fuente `input.cs` y agregue metadatos de `metad1.netmodule` y `metad2.netmodule` para generar `out.exe`:</span><span class="sxs-lookup"><span data-stu-id="7e426-121">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e426-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="7e426-122">See also</span></span>

- [<span data-ttu-id="7e426-123">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="7e426-123">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="7e426-124">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="7e426-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="7e426-125">Ensamblados de múltiples archivos</span><span class="sxs-lookup"><span data-stu-id="7e426-125">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="7e426-126">Cómo: Compilar un ensamblado de varios archivos</span><span class="sxs-lookup"><span data-stu-id="7e426-126">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/build-multifile-assembly.md)
