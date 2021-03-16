---
title: 'Cambio importante: Se ha invertido el orden de las etiquetas en Activity.Tags'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde Activity.Tags ahora almacena los elementos de la lista según el orden en que se agregan.
ms.date: 11/01/2020
ms.openlocfilehash: f37f44cbe2ea467f0962cd8971d5bf38ce958dfd
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257133"
---
# <a name="order-of-tags-in-activitytags-is-reversed"></a><span data-ttu-id="145aa-103">Se ha invertido el orden de las etiquetas en Activity.Tags</span><span class="sxs-lookup"><span data-stu-id="145aa-103">Order of tags in Activity.Tags is reversed</span></span>

<span data-ttu-id="145aa-104">Ahora <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos de la lista según el orden en que se agregan, es decir, el primer elemento que se ha agregado es el primero de la lista.</span><span class="sxs-lookup"><span data-stu-id="145aa-104"><xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> now stores items in the list according to the order they are added, that is, the first item that's added is first in the list.</span></span> <span data-ttu-id="145aa-105">Este cambio se ha realizado para que coincida con la [especificación de atributos de OpenTelemetry](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span><span class="sxs-lookup"><span data-stu-id="145aa-105">This change was made to match the [OpenTelemetry Attributes specification](https://github.com/open-telemetry/opentelemetry-specification/blob/master/specification/common/common.md#attributes).</span></span>

## <a name="change-description"></a><span data-ttu-id="145aa-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="145aa-106">Change description</span></span>

<span data-ttu-id="145aa-107">En versiones anteriores de .NET, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> almacena los elementos en el orden inverso al que se han agregado.</span><span class="sxs-lookup"><span data-stu-id="145aa-107">In previous .NET versions, <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> stores items in the reverse order from which they're added.</span></span> <span data-ttu-id="145aa-108">Es decir, el primer elemento que se agrega es el último de la lista.</span><span class="sxs-lookup"><span data-stu-id="145aa-108">That is, the first item added is last in the list.</span></span> <span data-ttu-id="145aa-109">A partir de .NET 5, se invierte el orden de los elementos y el primero que se agrega siempre es el primero de la lista.</span><span class="sxs-lookup"><span data-stu-id="145aa-109">Starting in .NET 5, the order of the items is reversed, and the first item added is always first in the list.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="145aa-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="145aa-110">Version introduced</span></span>

<span data-ttu-id="145aa-111">5.0</span><span class="sxs-lookup"><span data-stu-id="145aa-111">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="145aa-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="145aa-112">Recommended action</span></span>

<span data-ttu-id="145aa-113">Si la aplicación tiene una dependencia en el orden de lista de <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> y va a actualizar a .NET 5 o una versión posterior, tendrá que cambiar esta parte del código.</span><span class="sxs-lookup"><span data-stu-id="145aa-113">If your app has a dependency on the <xref:System.Diagnostics.Activity.Tags?displayProperty=nameWithType> list order and you're upgrading to .NET 5 or later, you'll need to change this part of your code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="145aa-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="145aa-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Activity.Tags?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.Tags`

-->
