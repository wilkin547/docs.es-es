---
description: -refout (Opciones del compilador de C#)
title: -refout (Opciones del compilador de C#)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 424782e4607fea63130e95ab09a671c75fe1404d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128719"
---
# <a name="-refout-c-compiler-options"></a><span data-ttu-id="51143-103">-refout (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="51143-103">-refout (C# Compiler Options)</span></span>

<span data-ttu-id="51143-104">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="51143-104">The **-refout** option specifies a file path where the reference assembly should be output.</span></span> <span data-ttu-id="51143-105">Esto se traduce en `metadataPeStream` en la API de emisión.</span><span class="sxs-lookup"><span data-stu-id="51143-105">This translates to `metadataPeStream` in the Emit API.</span></span> <span data-ttu-id="51143-106">Esta opción corresponde a la propiedad de proyecto [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="51143-106">This option corresponds to the [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="51143-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51143-107">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="51143-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="51143-108">Arguments</span></span>

 <span data-ttu-id="51143-109">`filepath` La ruta de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="51143-109">`filepath` The filepath for the reference assembly.</span></span> <span data-ttu-id="51143-110">Generalmente debe coincidir con el ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="51143-110">It should generally match that of the primary assembly.</span></span> <span data-ttu-id="51143-111">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="51143-111">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span>

## <a name="remarks"></a><span data-ttu-id="51143-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="51143-112">Remarks</span></span>

<span data-ttu-id="51143-113">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="51143-113">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="51143-114">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="51143-114">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="51143-115">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="51143-115">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="51143-116">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="51143-116">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="51143-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="51143-117">See also</span></span>

- [<span data-ttu-id="51143-118">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="51143-118">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="51143-119">Administrar propiedades de soluciones y proyectos</span><span class="sxs-lookup"><span data-stu-id="51143-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
