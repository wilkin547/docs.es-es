---
title: -refonly (Opciones del compilador de C#)
ms.date: 07/08/2017
f1_keywords:
- /refonly
helpviewer_keywords:
- /refonly compiler option [C#]
- -refonly compiler option [C#]
- refonly compiler option [C#]
ms.openlocfilehash: 856b65d3b2217dbe5d53ecda00723b47247d80a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72773851"
---
# <a name="-refonly-c-compiler-options"></a><span data-ttu-id="2db05-102">-refonly (Opciones del compilador de C#)</span><span class="sxs-lookup"><span data-stu-id="2db05-102">-refonly (C# Compiler Options)</span></span>

<span data-ttu-id="2db05-103">La opción **-refonly** indica que un ensamblado de referencia debe mostrarse en lugar de un ensamblado de implementación, como el resultado principal.</span><span class="sxs-lookup"><span data-stu-id="2db05-103">The **-refonly** option indicates that a reference assembly should be output instead of an implementation assembly, as the primary output.</span></span> <span data-ttu-id="2db05-104">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="2db05-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span> <span data-ttu-id="2db05-105">Esta opción corresponde a la propiedad de proyecto [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="2db05-105">This option corresponds to the [ProduceOnlyReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) project property of MSBuild.</span></span>

## <a name="syntax"></a><span data-ttu-id="2db05-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2db05-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="2db05-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2db05-107">Remarks</span></span>

<span data-ttu-id="2db05-108">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="2db05-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="2db05-109">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="2db05-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="2db05-110">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="2db05-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="2db05-111">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="2db05-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="2db05-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="2db05-112">See also</span></span>

- [<span data-ttu-id="2db05-113">Opciones del compilador de C#</span><span class="sxs-lookup"><span data-stu-id="2db05-113">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="2db05-114">Administrar propiedades de proyectos y de soluciones</span><span class="sxs-lookup"><span data-stu-id="2db05-114">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
