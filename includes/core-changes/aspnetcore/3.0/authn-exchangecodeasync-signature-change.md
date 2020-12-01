---
ms.openlocfilehash: a4e20e0468d861138ad801c9dbfa15340b3f388c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032706"
---
### <a name="authentication-oauthhandler-exchangecodeasync-signature-changed"></a><span data-ttu-id="9934b-101">Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler</span><span class="sxs-lookup"><span data-stu-id="9934b-101">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>

<span data-ttu-id="9934b-102">En ASP.NET Core 3.0, la firma de `OAuthHandler.ExchangeCodeAsync` cambió de:</span><span class="sxs-lookup"><span data-stu-id="9934b-102">In ASP.NET Core 3.0, the signature of `OAuthHandler.ExchangeCodeAsync` was changed from:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(string code, string redirectUri) { throw null; }
```

<span data-ttu-id="9934b-103">A:</span><span class="sxs-lookup"><span data-stu-id="9934b-103">To:</span></span>

```csharp
protected virtual System.Threading.Tasks.Task<Microsoft.AspNetCore.Authentication.OAuth.OAuthTokenResponse> ExchangeCodeAsync(Microsoft.AspNetCore.Authentication.OAuth.OAuthCodeExchangeContext context) { throw null; }
```

#### <a name="version-introduced"></a><span data-ttu-id="9934b-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="9934b-104">Version introduced</span></span>

<span data-ttu-id="9934b-105">3.0</span><span class="sxs-lookup"><span data-stu-id="9934b-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="9934b-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="9934b-106">Old behavior</span></span>

<span data-ttu-id="9934b-107">Las cadenas `code` y `redirectUri` se pasaron como argumentos independientes.</span><span class="sxs-lookup"><span data-stu-id="9934b-107">The `code` and `redirectUri` strings were passed as separate arguments.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="9934b-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="9934b-108">New behavior</span></span>

<span data-ttu-id="9934b-109">`Code` y `RedirectUri` son propiedades de `OAuthCodeExchangeContext` que se pueden establecer mediante el constructor de `OAuthCodeExchangeContext`.</span><span class="sxs-lookup"><span data-stu-id="9934b-109">`Code` and `RedirectUri` are properties on `OAuthCodeExchangeContext` that can be set via the `OAuthCodeExchangeContext` constructor.</span></span> <span data-ttu-id="9934b-110">El nuevo tipo de `OAuthCodeExchangeContext` es el único argumento que se pasa a `OAuthHandler.ExchangeCodeAsync`.</span><span class="sxs-lookup"><span data-stu-id="9934b-110">The new `OAuthCodeExchangeContext` type is the only argument passed to `OAuthHandler.ExchangeCodeAsync`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="9934b-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="9934b-111">Reason for change</span></span>

<span data-ttu-id="9934b-112">Este cambio permite proporcionar parámetros adicionales de forma no interrumpida.</span><span class="sxs-lookup"><span data-stu-id="9934b-112">This change allows additional parameters to be provided in a non-breaking manner.</span></span> <span data-ttu-id="9934b-113">No es necesario crear sobrecargas nuevas de `ExchangeCodeAsync`.</span><span class="sxs-lookup"><span data-stu-id="9934b-113">There's no need to create new `ExchangeCodeAsync` overloads.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9934b-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="9934b-114">Recommended action</span></span>

<span data-ttu-id="9934b-115">Construya un elemento `OAuthCodeExchangeContext` con los valores adecuados de `code` y `redirectUri`.</span><span class="sxs-lookup"><span data-stu-id="9934b-115">Construct an `OAuthCodeExchangeContext` with the appropriate `code` and `redirectUri` values.</span></span> <span data-ttu-id="9934b-116">Se debe proporcionar una instancia de <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties>.</span><span class="sxs-lookup"><span data-stu-id="9934b-116">An <xref:Microsoft.AspNetCore.Authentication.AuthenticationProperties> instance must be provided.</span></span> <span data-ttu-id="9934b-117">Esta instancia de `OAuthCodeExchangeContext` única se puede pasar a `OAuthHandler.ExchangeCodeAsync` en lugar de varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="9934b-117">This single `OAuthCodeExchangeContext` instance can be passed to `OAuthHandler.ExchangeCodeAsync` instead of multiple arguments.</span></span>

#### <a name="category"></a><span data-ttu-id="9934b-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="9934b-118">Category</span></span>

<span data-ttu-id="9934b-119">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="9934b-119">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9934b-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="9934b-120">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler%601.ExchangeCodeAsync(System.String,System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Authentication.OAuth.OAuthHandler`1.ExchangeCodeAsync(System.String,System.String)`

-->
