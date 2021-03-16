---
title: 'Cambio importante: CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA2247.
ms.date: 09/03/2020
ms.openlocfilehash: 6c7accaad312352a1448406f2bbf4189f3df1ee5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257705"
---
# <a name="warning-ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="278e3-103">Advertencia CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="278e3-103">Warning CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="278e3-104">La regla [CA2247](/visualstudio/code-quality/ca2247) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="278e3-104">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="278e3-105">Genera una advertencia de compilación para las llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="278e3-105">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

## <a name="change-description"></a><span data-ttu-id="278e3-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="278e3-106">Change description</span></span>

<span data-ttu-id="278e3-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="278e3-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="278e3-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="278e3-108">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="278e3-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="278e3-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="278e3-110">La regla CA2247 busca llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="278e3-110">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="278e3-111">El tipo <xref:System.Threading.Tasks.TaskCompletionSource%601> tiene un constructor que acepta un valor <xref:System.Threading.Tasks.TaskCreationOptions> y otro constructor que acepta <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="278e3-111">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="278e3-112">Si por accidente se pasa un valor <xref:System.Threading.Tasks.TaskContinuationOptions> en lugar de un valor <xref:System.Threading.Tasks.TaskCreationOptions>, se llama al constructor con el parámetro <xref:System.Object> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="278e3-112">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="278e3-113">El código se compilará y ejecutará, pero no tendrá el comportamiento previsto.</span><span class="sxs-lookup"><span data-stu-id="278e3-113">Your code will compile and run but won't have the intended behavior.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="278e3-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="278e3-114">Version introduced</span></span>

<span data-ttu-id="278e3-115">5.0</span><span class="sxs-lookup"><span data-stu-id="278e3-115">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="278e3-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="278e3-116">Recommended action</span></span>

- <span data-ttu-id="278e3-117">Reemplace el argumento <xref:System.Threading.Tasks.TaskContinuationOptions> por el valor <xref:System.Threading.Tasks.TaskCreationOptions> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="278e3-117">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="278e3-118">No suprima esta advertencia, ya que casi siempre resalta un error en el código.</span><span class="sxs-lookup"><span data-stu-id="278e3-118">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="278e3-119">Para obtener más información, vea [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="278e3-119">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="278e3-120">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="278e3-120">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="278e3-121">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="278e3-121">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="278e3-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="278e3-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

### Category

Code analysis

-->
