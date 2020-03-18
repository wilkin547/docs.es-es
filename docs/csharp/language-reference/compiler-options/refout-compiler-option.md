---
title: -refout (Opciones del compilador de C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: f48316a1e6f657e3bd0190d269dfe0e875a833d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72771761"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="ac06b-102">-refout (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="ac06b-102">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="ac06b-103">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="ac06b-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="ac06b-104">Esto se traduce en `metadataPeStream` en la API de emisión.</span><span class="sxs-lookup"><span data-stu-id="ac06b-104">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="ac06b-105">Esta opción corresponde a la propiedad de proyecto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="ac06b-105">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="ac06b-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac06b-106">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="ac06b-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ac06b-107">Arguments</span></span>

 <span data-ttu-id="ac06b-108">`filepath` La ruta de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="ac06b-108">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="ac06b-109">Generalmente debe coincidir con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="ac06b-109">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="ac06b-110">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="ac06b-110">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac06b-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ac06b-111">Remarks</span></span>

<span data-ttu-id="ac06b-112">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ac06b-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="ac06b-113">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="ac06b-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="ac06b-114">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="ac06b-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="ac06b-115">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="ac06b-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac06b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac06b-116">See also</span></span>

- [<span data-ttu-id="ac06b-117">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="ac06b-117">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="ac06b-118">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="ac06b-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
