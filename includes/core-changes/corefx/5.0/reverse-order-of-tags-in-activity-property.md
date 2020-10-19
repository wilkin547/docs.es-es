---
ms.openlocfilehash: 24b88b3ba1b6cfe9fb9fb1f6398a6daeb57596a9
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756120"
---
### <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="0d7cc-101">Se ha invertido el orden de las etiquetas en Activity.Tags</span><span class="sxs-lookup"><span data-stu-id="0d7cc-101">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="0d7cc-102">Ahora <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos de la lista según el orden en que se agregan, es decir, el primer elemento que se ha agregado es el primero de la lista.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-102"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="0d7cc-103">Este cambio se ha realizado para que coincida con la [especificación de atributos de OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span><span class="sxs-lookup"><span data-stu-id="0d7cc-103">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

#### <a name="change-description"></a><span data-ttu-id="0d7cc-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="0d7cc-104">Change description</span></span>

<span data-ttu-id="0d7cc-105">En versiones anteriores de .NET, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos en el orden inverso al que se han agregado.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-105">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="0d7cc-106">Es decir, el primer elemento que se agrega es el último de la lista.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-106">That is, the first item added is last in the list.</span></span> <span data-ttu-id="0d7cc-107">A partir de .NET 5.0, se invierte el orden de los elementos y el primero que se agrega siempre es el primero de la lista.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-107">Starting in .NET 5.0, the order of the items is reversed, and the first item added is always first in the list.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="0d7cc-108">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="0d7cc-108">Version introduced</span></span>

<span data-ttu-id="0d7cc-109">5.0</span><span class="sxs-lookup"><span data-stu-id="0d7cc-109">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0d7cc-110">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="0d7cc-110">Recommended action</span></span>

<span data-ttu-id="0d7cc-111">Si la aplicación tiene una dependencia en el orden de lista de <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> y va a actualizar a .NET 5.0 o una versión posterior, tendrá que cambiar esta parte del código.</span><span class="sxs-lookup"><span data-stu-id="0d7cc-111">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5.0 or later, you'll need to change this part of your code.</span></span>

#### <a name="category"></a><span data-ttu-id="0d7cc-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="0d7cc-112">Category</span></span>

<span data-ttu-id="0d7cc-113">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="0d7cc-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0d7cc-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0d7cc-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
