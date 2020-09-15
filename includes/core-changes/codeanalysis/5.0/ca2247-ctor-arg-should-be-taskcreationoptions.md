---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065187"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="7ac2c-101">CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="7ac2c-101">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="7ac2c-102">La regla [CA2247](/visualstudio/code-quality/ca2247) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-102">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="7ac2c-103">Genera una advertencia de compilación para las llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-103">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7ac2c-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7ac2c-104">Change description</span></span>

<span data-ttu-id="7ac2c-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="7ac2c-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="7ac2c-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="7ac2c-106">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="7ac2c-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="7ac2c-108">La regla CA2247 busca llamadas al constructor <xref:System.Threading.Tasks.TaskCompletionSource%601> que pasan un argumento de tipo <xref:System.Threading.Tasks.TaskContinuationOptions>.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-108">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="7ac2c-109">El tipo <xref:System.Threading.Tasks.TaskCompletionSource%601> tiene un constructor que acepta un valor <xref:System.Threading.Tasks.TaskCreationOptions> y otro constructor que acepta <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-109">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="7ac2c-110">Si por accidente se pasa un valor <xref:System.Threading.Tasks.TaskContinuationOptions> en lugar de un valor <xref:System.Threading.Tasks.TaskCreationOptions>, se llama al constructor con el parámetro <xref:System.Object> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-110">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="7ac2c-111">El código se compilará y ejecutará, pero no tendrá el comportamiento previsto.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-111">Your code will compile and run but won't have the intended behavior.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7ac2c-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7ac2c-112">Version introduced</span></span>

<span data-ttu-id="7ac2c-113">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="7ac2c-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7ac2c-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7ac2c-114">Recommended action</span></span>

- <span data-ttu-id="7ac2c-115">Reemplace el argumento <xref:System.Threading.Tasks.TaskContinuationOptions> por el valor <xref:System.Threading.Tasks.TaskCreationOptions> correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-115">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="7ac2c-116">No suprima esta advertencia, ya que casi siempre resalta un error en el código.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-116">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="7ac2c-117">Para obtener más información, vea [CA2247](/visualstudio/code-quality/ca2247).</span><span class="sxs-lookup"><span data-stu-id="7ac2c-117">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="7ac2c-118">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7ac2c-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="7ac2c-119">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="7ac2c-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="7ac2c-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="7ac2c-120">Category</span></span>

<span data-ttu-id="7ac2c-121">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="7ac2c-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7ac2c-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7ac2c-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
