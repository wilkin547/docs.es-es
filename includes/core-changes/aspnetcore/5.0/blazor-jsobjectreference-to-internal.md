---
ms.openlocfilehash: 46f6f77a543dfcf2073063d8ec200ef7d71e6b1f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077597"
---
### <a name="blazor-jsobjectreference-and-jsinprocessobjectreference-types-changed-to-internal"></a><span data-ttu-id="3b8b8-101">Blazor: Los tipos JSObjectReference y JSInProcessObjectReference han cambiado a internal.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-101">Blazor: JSObjectReference and JSInProcessObjectReference types changed to internal</span></span>

<span data-ttu-id="3b8b8-102">Los nuevos tipos `Microsoft.JSInterop.JSObjectReference` y `Microsoft.JSInterop.JSInProcessObjectReference` introducidos en ASP.NET Core 5.0 RC1 se han marcado como `internal`.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-102">The new `Microsoft.JSInterop.JSObjectReference` and `Microsoft.JSInterop.JSInProcessObjectReference` types introduced in ASP.NET Core 5.0 RC1 have been marked as `internal`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3b8b8-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3b8b8-103">Version introduced</span></span>

<span data-ttu-id="3b8b8-104">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="3b8b8-104">5.0 RC2</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="3b8b8-105">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="3b8b8-105">Old behavior</span></span>

<span data-ttu-id="3b8b8-106">Se puede obtener una referencia `JSObjectReference` a partir de una llamada de interoperabilidad de JavaScript mediante `IJSRuntime`.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-106">A `JSObjectReference` can be obtained from a JavaScript interop call via `IJSRuntime`.</span></span> <span data-ttu-id="3b8b8-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3b8b8-107">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<JSObjectReference>(...);
```

#### <a name="new-behavior"></a><span data-ttu-id="3b8b8-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="3b8b8-108">New behavior</span></span>

<span data-ttu-id="3b8b8-109">`JSObjectReference` utiliza el modificador de acceso [internal](../../../../docs/csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="3b8b8-109">`JSObjectReference` uses the [internal](../../../../docs/csharp/language-reference/keywords/internal.md) access modifier.</span></span> <span data-ttu-id="3b8b8-110">En su lugar, se debe usar la interfaz `public` de `IJSObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-110">The `public` `IJSObjectReference` interface must be used instead.</span></span> <span data-ttu-id="3b8b8-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3b8b8-111">For example:</span></span>

```csharp
var jsObjectReference = await JSRuntime.InvokeAsync<IJSObjectReference>(...);
```

<span data-ttu-id="3b8b8-112">`JSInProcessObjectReference` también se marcó como `internal` y se ha reemplazado por `IJSInProcessObjectReference`.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-112">`JSInProcessObjectReference` was also marked as `internal` and was replaced by `IJSInProcessObjectReference`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="3b8b8-113">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="3b8b8-113">Reason for change</span></span>

<span data-ttu-id="3b8b8-114">El cambio hace que la característica de interoperabilidad de JavaScript sea más coherente con otros patrones de Blazor.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-114">The change makes the JavaScript interop feature more consistent with other patterns within Blazor.</span></span> <span data-ttu-id="3b8b8-115">`IJSObjectReference` es análogo a `IJSRuntime` en que sirve para un propósito similar y tiene métodos y extensiones similares.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-115">`IJSObjectReference` is analogous to `IJSRuntime` in that it serves a similar purpose and has similar methods and extensions.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3b8b8-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3b8b8-116">Recommended action</span></span>

<span data-ttu-id="3b8b8-117">Reemplace las apariciones de `JSObjectReference` y `JSInProcessObjectReference` por `IJSObjectReference` y `IJSInProcessObjectReference`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="3b8b8-117">Replace occurrences of `JSObjectReference` and `JSInProcessObjectReference` with `IJSObjectReference` and `IJSInProcessObjectReference`, respectively.</span></span>

#### <a name="category"></a><span data-ttu-id="3b8b8-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="3b8b8-118">Category</span></span>

<span data-ttu-id="3b8b8-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="3b8b8-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3b8b8-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3b8b8-120">Affected APIs</span></span>

- `Microsoft.JSInterop.JSObjectReference`
- `Microsoft.JSInterop.JSInProcessObjectReference`

<!--

#### Affected APIs

- `T:Microsoft.JSInterop.JSObjectReference`
- `T:Microsoft.JSInterop.JSInProcessObjectReference`

-->
