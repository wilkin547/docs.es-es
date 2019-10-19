---
title: -refout (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [Visual Basic]
- /refout compiler option [Visual Basic]
- -refout compiler option [Visual Basic]
ms.openlocfilehash: c11d83ff37da41faa3dc6b66a87e2c52c5f6c7ac
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582874"
---
# <a name="-refout-visual-basic"></a><span data-ttu-id="dc2c1-102">-refout (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dc2c1-102">-refout (Visual Basic)</span></span>

<span data-ttu-id="dc2c1-103">La opción **-refout** especifica una ruta de archivo donde el ensamblado de referencia debe mostrarse.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-103">The **-refout** option specifies a file path where the reference assembly should be output.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="dc2c1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc2c1-104">Syntax</span></span>

```console
-refout:filepath
```

## <a name="arguments"></a><span data-ttu-id="dc2c1-105">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dc2c1-105">Arguments</span></span>

`filepath`  
<span data-ttu-id="dc2c1-106">Ruta de acceso y nombre de archivo del ensamblado de referencia.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-106">The path and filename of the reference assembly.</span></span> <span data-ttu-id="dc2c1-107">Por lo general, debe estar en una subcarpeta del ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-107">It should generally be in a sub-folder of the primary assembly.</span></span> <span data-ttu-id="dc2c1-108">La convención recomendada (que se usa por MSBuild) es colocar el ensamblado de referencia en una subcarpeta "ref/" con relación al ensamblado principal.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-108">The recommended convention (used by MSBuild) is to place the reference assembly in a "ref/" sub-folder relative to the primary assembly.</span></span> <span data-ttu-id="dc2c1-109">Todas las carpetas de `filepath` deben existir; el compilador no los crea.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-109">All folders in `filepath` must exist; the compiler does not create them.</span></span>

## <a name="remarks"></a><span data-ttu-id="dc2c1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dc2c1-110">Remarks</span></span>

<span data-ttu-id="dc2c1-111">Visual Basic admite el modificador de `-refout` a partir de la versión 15,3.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-111">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="dc2c1-112">Los ensamblados de referencia son ensamblados de solo metadatos que contienen metadatos pero no código de implementación.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-112">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="dc2c1-113">Incluyen información de tipo y miembro para todo excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-113">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="dc2c1-114">Sus cuerpos de método se reemplazan por una única instrucción `throw null`.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-114">Their method bodies are replaced with a single `throw null` statement.</span></span> <span data-ttu-id="dc2c1-115">El motivo por el que se usa `throw null` cuerpos de método (no en lugar de cuerpos) es para que PEVerify pueda ejecutarse y pasarse (con lo que se valida la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="dc2c1-115">The reason for using `throw null` method bodies (as opposed to no bodies) is so that PEVerify can run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="dc2c1-116">Los ensamblados de referencia incluyen un atributo [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) de nivel de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-116">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="dc2c1-117">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="dc2c1-117">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="dc2c1-118">Debido a este atributo, los tiempos de ejecución rechazan la carga de ensamblados de referencia para su ejecución (pero todavía se pueden cargar en un contexto de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="dc2c1-118">Because of this attribute, runtimes refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="dc2c1-119">Las herramientas que reflejan en los ensamblados deben asegurarse de que cargan los ensamblados de referencia como solo reflexión. de lo contrario, el tiempo de ejecución produce una <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-119">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="dc2c1-120">Las opciones `-refout` y [`-refonly`](refonly-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="dc2c1-120">The `-refout` and [`-refonly`](refonly-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="dc2c1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc2c1-121">See also</span></span>

- [<span data-ttu-id="dc2c1-122">/refonly</span><span class="sxs-lookup"><span data-stu-id="dc2c1-122">-refonly</span></span>](refonly-compiler-option.md)
- [<span data-ttu-id="dc2c1-123">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc2c1-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="dc2c1-124">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc2c1-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
