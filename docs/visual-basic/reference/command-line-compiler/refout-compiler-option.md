---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: 552e611f222bfcc3ce12520ecdb891fd7b8b21de
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775546"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="db42a-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db42a-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="db42a-103">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="db42a-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="db42a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db42a-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="db42a-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="db42a-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="db42a-106">Ruta de acceso y nombre de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="db42a-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="db42a-107">Por lo general, debe estar en una subcarpeta del ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="db42a-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="db42a-108">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="db42a-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="db42a-109">Todas las carpetas de `filepath` deben existir; el compilador no los crea.</span><span class="sxs-lookup"><span data-stu-id="db42a-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="db42a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db42a-110">Remarks</span></span>

<span data-ttu-id="db42a-111">Visual Basic admite el modificador de `-refout` a partir de la versión 15,3.</span><span class="sxs-lookup"><span data-stu-id="db42a-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="db42a-112">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="db42a-112">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="db42a-113">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="db42a-113">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="db42a-114">Para obtener más información, consulte [ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en .net Guide.</span><span class="sxs-lookup"><span data-stu-id="db42a-114">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="db42a-115">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="db42a-115">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="db42a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="db42a-116">See also</span></span>

- [<span data-ttu-id="db42a-117">/refonly</span><span class="sxs-lookup"><span data-stu-id="db42a-117">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="db42a-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="db42a-118">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="db42a-119">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="db42a-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
