---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
ms.openlocfilehash: b22fb9ae24a04d9fe530811bf764352199c31813
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2018
ms.locfileid: "50036065"
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="5a974-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a974-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="5a974-103">El **- refonly** opción indica que la salida principal de la compilación debe ser un ensamblado de referencia en lugar de un ensamblado de implementación.</span><span class="sxs-lookup"><span data-stu-id="5a974-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="5a974-104">El parámetro `-refonly` deshabilita de forma automática la generación de archivos PDB, ya que los ensamblados de referencia no pueden ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="5a974-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="5a974-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a974-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="5a974-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a974-106">Remarks</span></span>

<span data-ttu-id="5a974-107">Visual Basic admite la `-refout` cambiar comenzando con la versión 15.3.</span><span class="sxs-lookup"><span data-stu-id="5a974-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="5a974-108">Los ensamblados de referencia son solo metadatos de los ensamblados que contienen metadatos pero ningún código de implementación.</span><span class="sxs-lookup"><span data-stu-id="5a974-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="5a974-109">Incluyen información de los tipos y miembros para todo excepto los tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="5a974-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="5a974-110">El motivo de usar cuerpos `throw null` (en lugar de no usar ningún cuerpo) es que PEVerify pueda ejecutar y pasar (por lo tanto, validar la integridad de los metadatos).</span><span class="sxs-lookup"><span data-stu-id="5a974-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="5a974-111">Los ensamblados de referencia incluyen un nivel de ensamblado [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) atributo.</span><span class="sxs-lookup"><span data-stu-id="5a974-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="5a974-112">Este atributo puede especificarse en el origen (por lo tanto, el compilador no necesitará sintetizarlo).</span><span class="sxs-lookup"><span data-stu-id="5a974-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="5a974-113">Debido a este atributo, los tiempos de ejecución rechazarán cargar ensamblados de referencia para la ejecución (pero todavía se pueden cargar en un contexto de solo reflexión).</span><span class="sxs-lookup"><span data-stu-id="5a974-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="5a974-114">Las herramientas que se reflejan en los ensamblados deben asegurarse de que cargan los ensamblados de referencia como de solo reflexión; en caso contrario, el runtime produce una <xref:System.BadImageFormatException>.</span><span class="sxs-lookup"><span data-stu-id="5a974-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="5a974-115">Las opciones `-refonly` y [`-refout`](refout-compiler-option.md) son mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="5a974-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a974-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a974-116">See also</span></span>
<span data-ttu-id="5a974-117">[-refout](refout-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="5a974-117">[-refout](refout-compiler-option.md) </span></span>  
[<span data-ttu-id="5a974-118">Compilador de línea de comandos de Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a974-118">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="5a974-119">Líneas de comandos de compilación de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a974-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)   
