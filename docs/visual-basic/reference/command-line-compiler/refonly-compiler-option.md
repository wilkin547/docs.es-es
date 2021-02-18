---
description: Más información sobre -refonly (Visual Basic)
title: -refonly
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: 283aa75fceead38c62c4cf10c1ffe08151aeac9c
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474140"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="6d96d-103">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d96d-103">-refonly (Visual Basic)</span></span>

<span data-ttu-id="6d96d-104">La opción **-refonly** indica que el resultado principal de la compilación debe ser un ensamblado de referencia, en lugar de un ensamblado de implementación.</span><span class="sxs-lookup"><span data-stu-id="6d96d-104">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="6d96d-105">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6d96d-105">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="6d96d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6d96d-106">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="6d96d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d96d-107">Remarks</span></span>

<span data-ttu-id="6d96d-108">Visual Basic admite el modificador `-refonly` a partir de la versión 15.3.</span><span class="sxs-lookup"><span data-stu-id="6d96d-108">Visual Basic supports the `-refonly` switch starting with version 15.3.</span></span>

<span data-ttu-id="6d96d-109">Los ensamblados de referencia son un tipo especial de ensamblado que contiene solo la cantidad mínima de metadatos necesarios para representar la superficie de la API pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="6d96d-109">Reference assemblies are a special type of assembly that contain only the minimum amount of metadata required to represent the library's public API surface.</span></span> <span data-ttu-id="6d96d-110">Incluyen declaraciones para todos los miembros que son significativos al hacer referencia a un ensamblado en las herramientas de compilación, pero excluyen todas las implementaciones de miembros y las declaraciones de miembros privados que no tienen ningún impacto observable en su contrato de API.</span><span class="sxs-lookup"><span data-stu-id="6d96d-110">They include declarations for all members that are significant when referencing an assembly in build tools, but exclude all member implementations and declarations of private members that have no observable impact on their API contract.</span></span> <span data-ttu-id="6d96d-111">Para obtener más información, consulte [Ensamblados de referencia](../../../standard/assembly/reference-assemblies.md) en la Guía de .NET.</span><span class="sxs-lookup"><span data-stu-id="6d96d-111">For more information, see [Reference assemblies](../../../standard/assembly/reference-assemblies.md) in .NET Guide.</span></span>

<span data-ttu-id="6d96d-112">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="6d96d-112">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="6d96d-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d96d-113">See also</span></span>

- [<span data-ttu-id="6d96d-114">/refout</span><span class="sxs-lookup"><span data-stu-id="6d96d-114">-refout</span></span>](refout-compiler-option.md)
- [<span data-ttu-id="6d96d-115">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d96d-115">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="6d96d-116">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d96d-116">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
