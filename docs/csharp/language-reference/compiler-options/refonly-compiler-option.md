---
description: -refonly (Opciones del compilador de C#)
title: -refonly (Opciones del compilador de C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: f9a92462203bedff93a4a711ca8742465b7a561c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89124752"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="44e33-103">-refonly (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="44e33-103">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="44e33-104">La opción **-refonly** indica que un ensamblado de referencia debe mostrarse en lugar de un ensamblado de implementación, como el resultado principal.</span><span class="sxs-lookup"><span data-stu-id="44e33-104">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="44e33-105">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="44e33-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="44e33-106">Esta opción corresponde a la propiedad de proyecto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="44e33-106">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="44e33-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44e33-107">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="44e33-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44e33-108">Remarks</span></span>

<span data-ttu-id="44e33-109">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="44e33-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="44e33-110">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="44e33-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="44e33-111">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="44e33-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="44e33-112">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="44e33-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="44e33-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="44e33-113">See also</span></span>

- [<span data-ttu-id="44e33-114">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="44e33-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="44e33-115">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="44e33-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
