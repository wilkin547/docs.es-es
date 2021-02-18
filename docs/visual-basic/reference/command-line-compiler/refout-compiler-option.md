---
description: Más información sobre -refout (Visual Basic)
title: -refout
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 2760f7e60d950aaff90becad843824a2e2b4379f
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474127"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="e3930-103">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3930-103">-refout (Visual Basic)</span></span>

<span data-ttu-id="e3930-104">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="e3930-104">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="e3930-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e3930-105">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="e3930-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e3930-106">Arguments</span></span>

`filepath`  
<span data-ttu-id="e3930-107">Ruta de acceso y nombre de archivo del servicio ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="e3930-107">The path and filename of the reference assembly.</span></span> <span data-ttu-id="e3930-108">Generalmente debe estar en una subcarpeta del ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="e3930-108">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="e3930-109">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="e3930-109">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="e3930-110">Todas las carpetas de `filepath` deben existir; el compilador no las crea.</span><span class="sxs-lookup"><span data-stu-id="e3930-110">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="e3930-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e3930-111">Remarks</span></span>

<span data-ttu-id="e3930-112">Visual Basic admite el modificador `-refout` a partir de la versión 15.3.</span><span class="sxs-lookup"><span data-stu-id="e3930-112">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="e3930-113">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="e3930-113">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="e3930-114">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="e3930-114">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="e3930-115">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="e3930-115">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="e3930-116">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="e3930-116">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3930-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3930-117">See also</span></span>

- [<span data-ttu-id="e3930-118">/refonly</span><span class="sxs-lookup"><span data-stu-id="e3930-118">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="e3930-119">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e3930-119">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e3930-120">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="e3930-120">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
