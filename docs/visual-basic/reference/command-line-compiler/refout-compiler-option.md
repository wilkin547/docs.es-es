---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21cea76f31bdf2ac5fcf434ee759f874f917617b
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999473"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="d71cf-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d71cf-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="d71cf-103">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="d71cf-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="d71cf-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d71cf-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="d71cf-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d71cf-105">Arguments</span></span>

 <span data-ttu-id="d71cf-106">`filepath` La ruta de acceso y el nombre del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="d71cf-106">`filepath` The path and filename of the reference assembly.</span></span> <span data-ttu-id="d71cf-107">Por lo general debe ser en una subcarpeta del ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="d71cf-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="d71cf-108">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="d71cf-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="d71cf-109">Todas las carpetas de `filepath` debe existir; el compilador no los crea.</span><span class="sxs-lookup"><span data-stu-id="d71cf-109">All folders in `filepath` must exist; the compiler does not create them.</span></span> 

## <a name="remarks"></a><span data-ttu-id="d71cf-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d71cf-110">Remarks</span></span>

<span data-ttu-id="d71cf-111">Visual Basic admite la `-refout` cambiar comenzando con la versión 15.3.</span><span class="sxs-lookup"><span data-stu-id="d71cf-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="d71cf-112">Los ensamblados de referencia son solo metadatos de los ensamblados que contienen metadatos pero ningún código de implementación.</span><span class="sxs-lookup"><span data-stu-id="d71cf-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="d71cf-113">Incluyen información de los tipos y miembros para todo excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="d71cf-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="d71cf-114">Sus cuerpos de método se reemplazan con una sola `throw null` instrucción.</span><span class="sxs-lookup"><span data-stu-id="d71cf-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="d71cf-115">La razón para usar `throw null` cuerpos de método (en lugar de usar ningún cuerpo) es para que PEVerify pueda ejecutar y pasar (, por tanto, validar la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="d71cf-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="d71cf-116">Los ensamblados de referencia incluyen un nivel de ensamblado [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atributo.</span><span class="sxs-lookup"><span data-stu-id="d71cf-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="d71cf-117">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="d71cf-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="d71cf-118">Debido a este atributo, los tiempos de ejecución no carga ensamblados de referencia para la ejecución (pero todavía se pueden cargar en un contexto de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="d71cf-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="d71cf-119">Las herramientas que se reflejan en los ensamblados deben asegurarse de que cargan los ensamblados de referencia como de solo reflexión; en caso contrario, el runtime produce una <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="d71cf-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="d71cf-120">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="d71cf-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="d71cf-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="d71cf-121">See Also</span></span>
<span data-ttu-id="d71cf-122">[-refonly](refonly-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="d71cf-122">[-refonly](refonly-compiler-option.md) </span></span>  
[<span data-ttu-id="d71cf-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d71cf-123">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="d71cf-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="d71cf-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)  

