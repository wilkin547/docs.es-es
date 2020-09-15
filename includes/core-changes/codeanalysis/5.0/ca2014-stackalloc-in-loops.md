---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065184"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="c8d81-101">CA2014: No usar stackalloc en los bucles</span><span class="sxs-lookup"><span data-stu-id="c8d81-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="c8d81-102">La regla [CA2014](/visualstudio/code-quality/ca2014) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="c8d81-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="c8d81-103">Genera una advertencia de compilación para cualquier código de C# donde se usa una expresión [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="c8d81-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c8d81-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="c8d81-104">Change description</span></span>

<span data-ttu-id="c8d81-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="c8d81-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="c8d81-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="c8d81-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="c8d81-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="c8d81-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="c8d81-108">La regla CA2014 busca código de C# en el que se usa una [expresión stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="c8d81-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="c8d81-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) asigna memoria del marco de pila actual.</span><span class="sxs-lookup"><span data-stu-id="c8d81-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="c8d81-110">La memoria no se libera hasta que se devuelve la llamada al método actual, lo que puede provocar desbordamientos de pila.</span><span class="sxs-lookup"><span data-stu-id="c8d81-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="c8d81-111">Como las excepciones de desbordamiento de pila no se pueden detectar, la aplicación finalizará en caso de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="c8d81-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c8d81-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c8d81-112">Version introduced</span></span>

<span data-ttu-id="c8d81-113">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="c8d81-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c8d81-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c8d81-114">Recommended action</span></span>

- <span data-ttu-id="c8d81-115">Evite usar [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) dentro de bucles.</span><span class="sxs-lookup"><span data-stu-id="c8d81-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="c8d81-116">Asigne el bloque de memoria fuera de un bucle y vuelva a usarlo dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="c8d81-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="c8d81-117">Para obtener más información, vea [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="c8d81-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="c8d81-118">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c8d81-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="c8d81-119">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="c8d81-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="c8d81-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="c8d81-120">Category</span></span>

<span data-ttu-id="c8d81-121">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="c8d81-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c8d81-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c8d81-122">Affected APIs</span></span>

<span data-ttu-id="c8d81-123">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="c8d81-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
