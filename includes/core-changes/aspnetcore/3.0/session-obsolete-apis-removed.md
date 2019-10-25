---
ms.openlocfilehash: bbf8a02096a4a654a041cfe17c760939fc17f2f5
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394162"
---
### <a name="session-state-obsolete-apis-removed"></a><span data-ttu-id="c370d-101">Estado de sesión: se han quitado las API obsoletas</span><span class="sxs-lookup"><span data-stu-id="c370d-101">Session state: Obsolete APIs removed</span></span> 

<span data-ttu-id="c370d-102">Se han quitado las API obsoletas para configurar las cookies de sesión.</span><span class="sxs-lookup"><span data-stu-id="c370d-102">Obsolete APIs for configuring session cookies were removed.</span></span> <span data-ttu-id="c370d-103">Para obtener más información, consulte [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span><span class="sxs-lookup"><span data-stu-id="c370d-103">For more information, see [aspnet/Announcements#257](https://github.com/aspnet/Announcements/issues/257).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c370d-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c370d-104">Version introduced</span></span>

<span data-ttu-id="c370d-105">3.0</span><span class="sxs-lookup"><span data-stu-id="c370d-105">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c370d-106">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="c370d-106">Reason for change</span></span>

<span data-ttu-id="c370d-107">Este cambio exige coherencia entre las API para configurar las características que usan cookies.</span><span class="sxs-lookup"><span data-stu-id="c370d-107">This change enforces consistency across APIs for configuring features that use cookies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c370d-108">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="c370d-108">Recommended action</span></span>

<span data-ttu-id="c370d-109">Migre el uso de las API quitadas a sus reemplazos más recientes.</span><span class="sxs-lookup"><span data-stu-id="c370d-109">Migrate usage of the removed APIs to their newer replacements.</span></span> <span data-ttu-id="c370d-110">Considere el ejemplo siguiente de `Startup.ConfigureServices`:</span><span class="sxs-lookup"><span data-stu-id="c370d-110">Consider the following example in `Startup.ConfigureServices`:</span></span>

```csharp
public void ConfigureServices(ServiceCollection services)
{
    services.AddSession(options =>
    {
        // Removed obsolete APIs
        options.CookieName = "SessionCookie";
        options.CookieDomain = "contoso.com";
        options.CookiePath = "/";
        options.CookieHttpOnly = true;
        options.CookieSecure = CookieSecurePolicy.Always;

        // new API
        options.Cookie.Name = "SessionCookie";
        options.Cookie.Domain = "contoso.com";
        options.Cookie.Path = "/";
        options.Cookie.HttpOnly = true;
        options.Cookie.SecurePolicy = CookieSecurePolicy.Always;
    });
}
```

#### <a name="category"></a><span data-ttu-id="c370d-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="c370d-111">Category</span></span>

<span data-ttu-id="c370d-112">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c370d-112">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c370d-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c370d-113">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieName?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure?displayProperty=fullName>

<!-- 

#### Affected APIs

- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieDomain`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieHttpOnly`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieName`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookiePath`
- `P:Microsoft.AspNetCore.Builder.SessionOptions.CookieSecure`

-->
