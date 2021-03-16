---
title: 'Cambio importante: CA2015: No definir finalizadores para los tipos derivados de MemoryManager<T>'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA2015.
ms.date: 09/03/2020
ms.openlocfilehash: 4333cec7657657f7e9ba864bcb9979609ad379e0
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257744"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="3ee0e-103">Advertencia CA2015: No definir finalizadores para los tipos derivados de MemoryManager\<T></span><span class="sxs-lookup"><span data-stu-id="3ee0e-103">Warning CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="3ee0e-104">La regla [CA2015](/visualstudio/code-quality/ca2015) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-104">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="3ee0e-105">Genera una advertencia de compilación para todos los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-105">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

## <a name="change-description"></a><span data-ttu-id="3ee0e-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="3ee0e-106">Change description</span></span>

<span data-ttu-id="3ee0e-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="3ee0e-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="3ee0e-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="3ee0e-108">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="3ee0e-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="3ee0e-110">La regla CA2015 marca los tipos que derivan de <xref:System.Buffers.MemoryManager%601> que definen un finalizador.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-110">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="3ee0e-111">Agregar un finalizador a un tipo que deriva de <xref:System.Buffers.MemoryManager%601> es probablemente una indicación de un error.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-111">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="3ee0e-112">Sugiere que un recurso nativo que se podría haber obtenido en un elemento <xref:System.Span%601> se va a limpiar, posiblemente mientras <xref:System.Span%601> lo sigue usando.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-112">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="3ee0e-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3ee0e-113">Version introduced</span></span>

<span data-ttu-id="3ee0e-114">5.0</span><span class="sxs-lookup"><span data-stu-id="3ee0e-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="3ee0e-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3ee0e-115">Recommended action</span></span>

- <span data-ttu-id="3ee0e-116">Quite la definición del finalizador.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-116">Remove the finalizer definition.</span></span> <span data-ttu-id="3ee0e-117">Para obtener más información, vea [CA2015](/visualstudio/code-quality/ca2015).</span><span class="sxs-lookup"><span data-stu-id="3ee0e-117">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="3ee0e-118">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="3ee0e-119">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="3ee0e-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="3ee0e-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3ee0e-120">Affected APIs</span></span>

<span data-ttu-id="3ee0e-121">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="3ee0e-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
