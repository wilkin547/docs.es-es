---
title: 'Cambio importante: CA2013: No usar ReferenceEquals con tipos de valor'
description: Obtenga información sobre el cambio importante en .NET 5 causado por la habilitación de la regla de análisis de código CA2013.
ms.date: 09/03/2020
ms.openlocfilehash: fc68d9a3af0d629dc39aba0091d32b1982d6f2c5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257770"
---
# <a name="warning-ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="7fc01-103">Advertencia CA2013: No usar ReferenceEquals con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="7fc01-103">Warning CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="7fc01-104">La regla [CA2013](/visualstudio/code-quality/ca2013) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7fc01-104">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="7fc01-105">Genera una advertencia de compilación para cualquier código donde se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales.</span><span class="sxs-lookup"><span data-stu-id="7fc01-105">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

## <a name="change-description"></a><span data-ttu-id="7fc01-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7fc01-106">Change description</span></span>

<span data-ttu-id="7fc01-107">A partir de .NET 5, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../fundamentals/code-analysis/overview.md).</span><span class="sxs-lookup"><span data-stu-id="7fc01-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="7fc01-108">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="7fc01-108">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="7fc01-109">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="7fc01-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="7fc01-110">La regla CA2013 busca instancias en las que se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales.</span><span class="sxs-lookup"><span data-stu-id="7fc01-110">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="7fc01-111">La comparación de los tipos de valor de esta forma para saber si son iguales puede producir resultados incorrectos, ya que se aplica la conversión boxing a los valores antes de compararlos.</span><span class="sxs-lookup"><span data-stu-id="7fc01-111">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="7fc01-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> devolverá `false` incluso si los valores comparados representan la misma instancia de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="7fc01-112"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="7fc01-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7fc01-113">Version introduced</span></span>

<span data-ttu-id="7fc01-114">5.0</span><span class="sxs-lookup"><span data-stu-id="7fc01-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7fc01-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7fc01-115">Recommended action</span></span>

- <span data-ttu-id="7fc01-116">Cambie el código para usar un operador de igualdad adecuado, por ejemplo, `==`.</span><span class="sxs-lookup"><span data-stu-id="7fc01-116">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="7fc01-117">No debe suprimir esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="7fc01-117">You should not suppress this warning.</span></span>

- <span data-ttu-id="7fc01-118">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="7fc01-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="7fc01-119">Para obtener más información, vea [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="7fc01-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7fc01-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7fc01-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

### Category

Code analysis

-->
