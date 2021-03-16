---
title: 'Cambio importante: CA2014: No usar stackalloc en los bucles'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA2014.
ms.date: 09/03/2020
ms.openlocfilehash: ac17c8ee588576947e21618a55c0eea883aa37ad
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257783"
---
# <a name="warning-ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="55cd7-103">Advertencia CA2014: No usar stackalloc en los bucles</span><span class="sxs-lookup"><span data-stu-id="55cd7-103">Warning CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="55cd7-104">La regla [CA2014](/visualstudio/code-quality/ca2014) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="55cd7-104">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="55cd7-105">Genera una advertencia de compilación para cualquier código de C# donde se usa una expresión [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="55cd7-105">It produces a build warning for any C# code where a [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

## <a name="change-description"></a><span data-ttu-id="55cd7-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="55cd7-106">Change description</span></span>

<span data-ttu-id="55cd7-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="55cd7-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="55cd7-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="55cd7-108">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="55cd7-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="55cd7-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="55cd7-110">La regla CA2014 busca código de C# en el que se usa una [expresión stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de un bucle.</span><span class="sxs-lookup"><span data-stu-id="55cd7-110">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="55cd7-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) asigna memoria del marco de pila actual.</span><span class="sxs-lookup"><span data-stu-id="55cd7-111">[stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="55cd7-112">La memoria no se libera hasta que se devuelve la llamada al método actual, lo que puede provocar desbordamientos de pila.</span><span class="sxs-lookup"><span data-stu-id="55cd7-112">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="55cd7-113">Como las excepciones de desbordamiento de pila no se pueden detectar, la aplicación finalizará en caso de desbordamiento de pila.</span><span class="sxs-lookup"><span data-stu-id="55cd7-113">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="55cd7-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="55cd7-114">Version introduced</span></span>

<span data-ttu-id="55cd7-115">5.0</span><span class="sxs-lookup"><span data-stu-id="55cd7-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="55cd7-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="55cd7-116">Recommended action</span></span>

- <span data-ttu-id="55cd7-117">Evite usar [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) dentro de bucles.</span><span class="sxs-lookup"><span data-stu-id="55cd7-117">Avoid using [stackalloc](../../../../csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="55cd7-118">Asigne el bloque de memoria fuera de un bucle y vuelva a usarlo dentro del bucle.</span><span class="sxs-lookup"><span data-stu-id="55cd7-118">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="55cd7-119">Para obtener más información, vea [CA2014](/visualstudio/code-quality/ca2014).</span><span class="sxs-lookup"><span data-stu-id="55cd7-119">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="55cd7-120">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55cd7-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="55cd7-121">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="55cd7-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="55cd7-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="55cd7-122">Affected APIs</span></span>

<span data-ttu-id="55cd7-123">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="55cd7-123">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
