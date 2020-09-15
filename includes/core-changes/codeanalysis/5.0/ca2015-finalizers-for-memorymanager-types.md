---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065175"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="42f66-101">CA2015: No definir finalizadores para los tipos derivados de MemoryManager\<T></span><span class="sxs-lookup"><span data-stu-id="42f66-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="42f66-102">La regla [CA2015](/visualstudio/code-quality/ca2015) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="42f66-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="42f66-103">Genera una advertencia de compilación para todos los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.</span><span class="sxs-lookup"><span data-stu-id="42f66-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="42f66-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="42f66-104">Change description</span></span>

<span data-ttu-id="42f66-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="42f66-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="42f66-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="42f66-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="42f66-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="42f66-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="42f66-108">La regla CA2015 marca los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.</span><span class="sxs-lookup"><span data-stu-id="42f66-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="42f66-109">Agregar un finalizador a un tipo que deriva de <xref:System.Buffers.MemoryManager%601> es probablemente una indicación de un error.</span><span class="sxs-lookup"><span data-stu-id="42f66-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="42f66-110">Sugiere que un recurso nativo que se podría haber obtenido en un elemento <xref:System.Span%601> se va a limpiar, posiblemente mientras <xref:System.Span%601> lo sigue usando.</span><span class="sxs-lookup"><span data-stu-id="42f66-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="42f66-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="42f66-111">Version introduced</span></span>

<span data-ttu-id="42f66-112">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="42f66-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="42f66-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="42f66-113">Recommended action</span></span>

- <span data-ttu-id="42f66-114">Quite la definición del finalizador.</span><span class="sxs-lookup"><span data-stu-id="42f66-114">Remove the finalizer definition.</span></span> <span data-ttu-id="42f66-115">Para obtener más información, vea [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="42f66-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="42f66-116">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="42f66-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="42f66-117">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="42f66-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="42f66-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="42f66-118">Category</span></span>

<span data-ttu-id="42f66-119">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="42f66-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="42f66-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="42f66-120">Affected APIs</span></span>

<span data-ttu-id="42f66-121">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="42f66-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
