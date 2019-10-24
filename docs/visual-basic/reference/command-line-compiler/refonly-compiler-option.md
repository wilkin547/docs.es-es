---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 8e64989ac1410b51991027ffcb33e8dae0c0284b
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775565"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="bc2ef-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc2ef-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="bc2ef-103">La opción **-refonly** indica que la salida principal de la compilación debe ser un ensamblado de referencia en lugar de un ensamblado de implementación.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="bc2ef-104">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="bc2ef-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc2ef-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="bc2ef-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bc2ef-106">Remarks</span></span>

<span data-ttu-id="bc2ef-107">Visual Basic admite el modificador de `-refonly` a partir de la versión 15,3.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-107">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="bc2ef-108">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-108">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="bc2ef-109">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-109">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="bc2ef-110">Para obtener más información, consulte [ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en .net Guide.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-110">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="bc2ef-111">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="bc2ef-111">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc2ef-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bc2ef-112">See also</span></span>

- [<span data-ttu-id="bc2ef-113">/refout</span><span class="sxs-lookup"><span data-stu-id="bc2ef-113">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="bc2ef-114">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bc2ef-114">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="bc2ef-115">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc2ef-115">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
