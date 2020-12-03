---
title: 'Cambio importante: Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 43a66d204f8309dc5afc57d099b2201c477cc3ad
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760165"
---
# <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="93f58-103">Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.</span><span class="sxs-lookup"><span data-stu-id="93f58-103">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="93f58-104">Los nuevos tipos `Microsoft.JSInterop.JSObjectReference` y `Microsoft.JSInterop.JSInProcessObjectReference` introducidos en ASP.NET Core 5.0 RC1 se han marcado como `internal`.</span><span class="sxs-lookup"><span data-stu-id="93f58-104">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="93f58-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="93f58-105">Version introduced</span></span>

<span data-ttu-id="93f58-106">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="93f58-106">5.0 RC2</span></span>

## <a name="old-behavior"></a><span data-ttu-id="93f58-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="93f58-107">Old behavior</span></span>

<span data-ttu-id="93f58-108">Se puede obtener una referencia `JSObjectReference` a partir de una llamada de interoperabilidad de JavaScript mediante `IJSRuntime`.</span><span class="sxs-lookup"><span data-stu-id="93f58-108">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="93f58-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="93f58-109">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

## <a name="new-behavior"></a><span data-ttu-id="93f58-110">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="93f58-110">New behavior</span></span>

<span data-ttu-id="93f58-111">`JSObjectReference` utiliza el modificador de acceso [internal](../../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="93f58-111">`JSObjectReference` uses the [internal](../../../../csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="93f58-112">En su lugar, se debe usar la interfaz `public` de `IJSObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="93f58-112">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="93f58-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="93f58-113">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="93f58-114">`JSInProcessObjectReference` también se marcó como `internal` y se ha reemplazado por `IJSInProcessObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="93f58-114">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="93f58-115">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="93f58-115">Reason for change</span></span>

<span data-ttu-id="93f58-116">El cambio hace que la característica de interoperabilidad de JavaScript sea más coherente con otros patrones de Blazor.</span><span class="sxs-lookup"><span data-stu-id="93f58-116">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="93f58-117">`IJSObjectReference` es análogo a `IJSRuntime` en que sirve para un propósito similar y tiene métodos y extensiones similares.</span><span class="sxs-lookup"><span data-stu-id="93f58-117">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="93f58-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="93f58-118">Recommended action</span></span>

<span data-ttu-id="93f58-119">Reemplace las apariciones de `JSObjectReference` y `JSInProcessObjectReference` por `IJSObjectReference` y `IJSInProcessObjectReference`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="93f58-119">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="93f58-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="93f58-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
