---
description: -target:module (Opciones del compilador de C#)
title: -target:module (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: d8691e5e4477dbbe989344469b44382d5e0e7c8b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193613"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="1ae54-103">-target:module (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="1ae54-103">-target:module (C# Compiler Options)</span></span>

<span data-ttu-id="1ae54-104">Esta opción hace que el compilador no genere un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1ae54-104">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ae54-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ae54-105">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="1ae54-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ae54-106">Remarks</span></span>  

 <span data-ttu-id="1ae54-107">De forma predeterminada, el archivo de salida creado al compilar con esta opción tendrá una extensión de .netmodule.</span><span class="sxs-lookup"><span data-stu-id="1ae54-107">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="1ae54-108">El runtime de .NET no puede cargar un archivo que no tiene un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="1ae54-108">A file that does not have an assembly manifest cannot be loaded by the .NET runtime.</span></span> <span data-ttu-id="1ae54-109">En cambio, este archivo se puede incorporar en el manifiesto de un ensamblado mediante [-addmodule](./addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1ae54-109">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](./addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="1ae54-110">Si se crea más de un módulo en una única compilación, los tipos [internal](../keywords/internal.md) que haya en un módulo estarán disponibles para otros módulos de la compilación.</span><span class="sxs-lookup"><span data-stu-id="1ae54-110">If more than one module is created in a single compilation, [internal](../keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="1ae54-111">Cuando el código de un módulo hace referencia a tipos `internal` de otro módulo, se deben incorporar ambos módulos en un manifiesto del ensamblado, mediante **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="1ae54-111">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="1ae54-112">No se admite la creación de un módulo en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ae54-112">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="1ae54-113">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ae54-113">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ae54-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ae54-114">Example</span></span>  

 <span data-ttu-id="1ae54-115">Compilación de `in.cs` y creación de `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="1ae54-115">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ae54-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ae54-116">See also</span></span>

- [<span data-ttu-id="1ae54-117">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="1ae54-117">-target (C# Compiler Options)</span></span>](./target-compiler-option.md)
- [<span data-ttu-id="1ae54-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="1ae54-118">C# Compiler Options</span></span>](./index.md)
