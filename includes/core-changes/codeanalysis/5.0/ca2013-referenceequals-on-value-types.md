---
ms.openlocfilehash: b01424c63d6e7956127bf889c53422b60ba2f219
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065212"
---
### <a name="ca2013-do-not-use-referenceequals-with-value-types"></a><span data-ttu-id="de15e-101">CA2013: No usar ReferenceEquals con tipos de valor</span><span class="sxs-lookup"><span data-stu-id="de15e-101">CA2013: Do not use ReferenceEquals with value types</span></span>

<span data-ttu-id="de15e-102">La regla [CA2013](/visualstudio/code-quality/ca2013) del analizador de código de .NET está habilitada de forma predeterminada a partir de .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="de15e-102">.NET code analyzer rule [CA2013](/visualstudio/code-quality/ca2013) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="de15e-103">Genera una advertencia de compilación para cualquier código donde se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales.</span><span class="sxs-lookup"><span data-stu-id="de15e-103">It produces a build warning for any code where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span>

#### <a name="change-description"></a><span data-ttu-id="de15e-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="de15e-104">Change description</span></span>

<span data-ttu-id="de15e-105">A partir de .NET 5.0, el SDK de .NET incluye [analizadores de código fuente de .NET](../../../../docs/fundamentals/productivity/code-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="de15e-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="de15e-106">Varias de estas reglas están habilitadas de forma predeterminada, incluida la regla [CA2013](/visualstudio/code-quality/ca2013).</span><span class="sxs-lookup"><span data-stu-id="de15e-106">Several of these rules are enabled, by default, including [CA2013](/visualstudio/code-quality/ca2013).</span></span> <span data-ttu-id="de15e-107">Si el proyecto contiene código que infringe esta regla y está configurado para tratar las advertencias como errores, este cambio podría interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="de15e-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="de15e-108">La regla CA2013 busca instancias en las que se usa <xref:System.Object.ReferenceEquals(System.Object,System.Object)> para comparar uno o varios tipos de valor con el fin de determinar si son iguales.</span><span class="sxs-lookup"><span data-stu-id="de15e-108">Rule CA2013 finds instances where <xref:System.Object.ReferenceEquals(System.Object,System.Object)> is used to compare one or more value types for equality.</span></span> <span data-ttu-id="de15e-109">La comparación de los tipos de valor de esta forma para saber si son iguales puede producir resultados incorrectos, ya que se aplica la conversión boxing a los valores antes de compararlos.</span><span class="sxs-lookup"><span data-stu-id="de15e-109">Comparing value types for equality in this way can lead to incorrect results, because the values are boxed before they're compared.</span></span> <span data-ttu-id="de15e-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> devolverá `false` incluso si los valores comparados representan la misma instancia de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="de15e-110"><xref:System.Object.ReferenceEquals(System.Object,System.Object)> will return `false` even if the compared values represent the same instance of a value type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="de15e-111">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="de15e-111">Version introduced</span></span>

<span data-ttu-id="de15e-112">5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="de15e-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="de15e-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="de15e-113">Recommended action</span></span>

- <span data-ttu-id="de15e-114">Cambie el código para usar un operador de igualdad adecuado, por ejemplo, `==`.</span><span class="sxs-lookup"><span data-stu-id="de15e-114">Change the code to use an appropriate equality operator, such as `==`.</span></span> <span data-ttu-id="de15e-115">No debe suprimir esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="de15e-115">You should not suppress this warning.</span></span>

- <span data-ttu-id="de15e-116">Para deshabilitar completamente el análisis de código, establezca `EnableNETAnalyzers` en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="de15e-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="de15e-117">Para obtener más información, vea [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span><span class="sxs-lookup"><span data-stu-id="de15e-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="de15e-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="de15e-118">Category</span></span>

<span data-ttu-id="de15e-119">Análisis de código</span><span class="sxs-lookup"><span data-stu-id="de15e-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="de15e-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="de15e-120">Affected APIs</span></span>

- <xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Object.ReferenceEquals(System.Object,System.Object)`

-->
