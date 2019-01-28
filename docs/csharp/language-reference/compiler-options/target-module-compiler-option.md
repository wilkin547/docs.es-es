---
title: -target:module (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 89139867cb0a207dbe82168015629fcb9e2fa6eb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54601901"
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="a48ea-102">-target:module (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="a48ea-102">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="a48ea-103">Esta opción hace que el compilador no genere un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a48ea-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a48ea-104">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="a48ea-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a48ea-105">Remarks</span></span>  
 <span data-ttu-id="a48ea-106">De forma predeterminada, el archivo de salida creado al compilar con esta opción tendrá una extensión de .netmodule.</span><span class="sxs-lookup"><span data-stu-id="a48ea-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="a48ea-107">Common Language Runtime de .NET Framework no puede cargar un archivo que no tiene un manifiesto del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a48ea-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="a48ea-108">En cambio, este archivo se puede incorporar en el manifiesto de un ensamblado mediante [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a48ea-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="a48ea-109">Si se crea más de un módulo en una única compilación, los tipos [internal](../../../csharp/language-reference/keywords/internal.md) que haya en un módulo estarán disponibles para otros módulos de la compilación.</span><span class="sxs-lookup"><span data-stu-id="a48ea-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="a48ea-110">Cuando el código de un módulo hace referencia a tipos `internal` de otro módulo, se deben incorporar ambos módulos en un manifiesto del ensamblado, mediante **-addmodule**.</span><span class="sxs-lookup"><span data-stu-id="a48ea-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="a48ea-111">No se admite la creación de un módulo en el entorno de desarrollo de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a48ea-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="a48ea-112">Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="a48ea-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a48ea-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a48ea-113">Example</span></span>  
 <span data-ttu-id="a48ea-114">Compilación de `in.cs` y creación de `in.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="a48ea-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="a48ea-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a48ea-115">See also</span></span>

- [<span data-ttu-id="a48ea-116">-target (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="a48ea-116">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)
- [<span data-ttu-id="a48ea-117">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="a48ea-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
