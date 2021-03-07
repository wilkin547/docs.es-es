---
title: Comparación de la autenticación y la autorización entre ASP.NET MVC y ASP.NET Core
description: Un resumen de las diferencias de autenticación y autorización entre ASP.NET MVC y ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: c8f3314186b7408e40d3a79cbc922a29eb75c5d2
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401818"
---
# <a name="compare-authentication-and-authorization-between-aspnet-mvc-and-aspnet-core"></a><span data-ttu-id="8bf23-103">Comparación de la autenticación y la autorización entre ASP.NET MVC y ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8bf23-103">Compare authentication and authorization between ASP.NET MVC and ASP.NET Core</span></span>

<span data-ttu-id="8bf23-104">En ASP.NET MVC 5, la autenticación se configura en *Startup.auth.CS* en la carpeta *App_Start* .</span><span class="sxs-lookup"><span data-stu-id="8bf23-104">In ASP.NET MVC 5, authentication is configured in *Startup.Auth.cs* in the *App_Start* folder.</span></span> <span data-ttu-id="8bf23-105">En ASP.NET Core MVC, esta configuración se produce en `Startup.cs` .</span><span class="sxs-lookup"><span data-stu-id="8bf23-105">In ASP.NET Core MVC, this configuration occurs in `Startup.cs`.</span></span> <span data-ttu-id="8bf23-106">La autenticación y la autorización se realizan con middleware agregada a la canalización de solicitudes en `ConfigureServices` :</span><span class="sxs-lookup"><span data-stu-id="8bf23-106">Authentication and authorization are performed using middleware added to the request pipeline in `ConfigureServices`:</span></span>

```csharp
// inside Startup.ConfigureServices

app.UseRouting();

app.UseAuthentication();
app.UseAuthorization();

app.UseEndpoints(endpoints =>
{
    endpoints.MapControllerRoute(
        name: "default",
        pattern: "{controller=Home}/{action=Index}/{id?}");
    endpoints.MapRazorPages();
});
```

<span data-ttu-id="8bf23-107">Es importante agregar el middleware de autenticación en el orden adecuado en la canalización de middleware.</span><span class="sxs-lookup"><span data-stu-id="8bf23-107">It's important to add the auth middleware in the appropriate order in the middleware pipeline.</span></span> <span data-ttu-id="8bf23-108">Solo las solicitudes que lo hagan al middleware se verán afectadas por esta.</span><span class="sxs-lookup"><span data-stu-id="8bf23-108">Only requests that make it to the middleware will be impacted by it.</span></span> <span data-ttu-id="8bf23-109">Por ejemplo, si una llamada a `UseStaticFiles()` se colocó sobre el código que se muestra aquí, no estaría protegido por la autenticación y la autorización.</span><span class="sxs-lookup"><span data-stu-id="8bf23-109">For instance, if a call to `UseStaticFiles()` was placed above the code shown here, it wouldn't be protected by authentication and authorization.</span></span>

<span data-ttu-id="8bf23-110">En ASP.NET MVC y Web API, las aplicaciones suelen hacer referencia al usuario actual mediante la `ClaimsPrincipal.Current` propiedad.</span><span class="sxs-lookup"><span data-stu-id="8bf23-110">In ASP.NET MVC and Web API, apps often refer to the current user using the `ClaimsPrincipal.Current` property.</span></span> <span data-ttu-id="8bf23-111">Esta propiedad no se establece en ASP.NET Core y cualquier comportamiento de la aplicación que dependa de ella tendrá que [migrar de ClaimsPrincipal. Current](/aspnet/core/migration/claimsprincipal-current) mediante la `User` propiedad en `ControllerBase` u obtener acceso a la actual `HttpContext` y hacer referencia a su `User` propiedad.</span><span class="sxs-lookup"><span data-stu-id="8bf23-111">This property isn't set in ASP.NET Core, and any behavior in your app that depends on it will need to [migrate from ClaimsPrincipal.Current](/aspnet/core/migration/claimsprincipal-current) by using the `User` property on `ControllerBase` or getting access to the current `HttpContext` and referencing its `User` property.</span></span> <span data-ttu-id="8bf23-112">Si ninguna de estas soluciones es una opción, los servicios pueden solicitar al usuario como argumento, en cuyo caso se debe proporcionar desde cualquier parte de la aplicación, o bien `IHttpContextAccessor` se puede solicitar y usar para obtener `HttpContext` .</span><span class="sxs-lookup"><span data-stu-id="8bf23-112">If neither of these solutions is an option, services can request the User as an argument, in which case it must be supplied from elsewhere in the app, or the `IHttpContextAccessor` can be requested and used to get the `HttpContext`.</span></span>

## <a name="authorization"></a><span data-ttu-id="8bf23-113">Autorización</span><span class="sxs-lookup"><span data-stu-id="8bf23-113">Authorization</span></span>

<span data-ttu-id="8bf23-114">La autorización define lo que puede hacer un usuario determinado dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8bf23-114">Authorization defines what a given user can do within the app.</span></span> <span data-ttu-id="8bf23-115">Es independiente de la autenticación, lo que se refiere únicamente a identificar quién es el usuario.</span><span class="sxs-lookup"><span data-stu-id="8bf23-115">It's separate from authentication, which is concerned merely with identifying who the user is.</span></span> <span data-ttu-id="8bf23-116">ASP.NET Core proporciona un rol sencillo y declarativo y un modelo avanzado basado en directivas para la autorización.</span><span class="sxs-lookup"><span data-stu-id="8bf23-116">ASP.NET Core provides a simple, declarative role and a rich, policy-based model for authorization.</span></span> <span data-ttu-id="8bf23-117">Especificar que un recurso requiere autorización suele ser tan sencillo como agregar el `[Authorize]` atributo a la acción o el controlador.</span><span class="sxs-lookup"><span data-stu-id="8bf23-117">Specifying that a resource requires authorization is often as simple as adding the `[Authorize]` attribute to the action or controller.</span></span> <span data-ttu-id="8bf23-118">Si va a migrar a Razor Pages desde las vistas de MVC, debe [especificar las convenciones de autorización al configurar Razor pages en el inicio](/aspnet/core/security/authorization/razor-pages-authorization).</span><span class="sxs-lookup"><span data-stu-id="8bf23-118">If you're migrating to Razor Pages from MVC views, you should [specify conventions for authorization when you configure Razor Pages in Startup](/aspnet/core/security/authorization/razor-pages-authorization).</span></span>

<span data-ttu-id="8bf23-119">La autorización en ASP.NET Core puede ser tan simple como la prohibición de usuarios anónimos, al tiempo que permite a los usuarios autenticados.</span><span class="sxs-lookup"><span data-stu-id="8bf23-119">Authorization in ASP.NET Core may be as simple as prohibiting anonymous users while allowing authenticated users.</span></span> <span data-ttu-id="8bf23-120">O bien, se puede escalar verticalmente para admitir enfoques de autorización basados en roles, basados en notificaciones o basados en directivas.</span><span class="sxs-lookup"><span data-stu-id="8bf23-120">Or it can scale up to support role-based, claims-based, or policy-based authorization approaches.</span></span> <span data-ttu-id="8bf23-121">Para obtener más información sobre estos enfoques, consulte la documentación sobre la [autorización en ASP.net Core](/aspnet/core/security/authorization/introduction).</span><span class="sxs-lookup"><span data-stu-id="8bf23-121">For more information on these approaches, see the documentation on [authorization in ASP.NET Core](/aspnet/core/security/authorization/introduction).</span></span> <span data-ttu-id="8bf23-122">Probablemente encontrará que una de ellas está estrechamente alineada con su enfoque de autorización actual.</span><span class="sxs-lookup"><span data-stu-id="8bf23-122">You'll likely find that one of them is closely aligned with your current authorization approach.</span></span>

## <a name="references"></a><span data-ttu-id="8bf23-123">Referencias</span><span class="sxs-lookup"><span data-stu-id="8bf23-123">References</span></span>

- [<span data-ttu-id="8bf23-124">Seguridad, autenticación y autorización con ASP.NET MVC</span><span class="sxs-lookup"><span data-stu-id="8bf23-124">Security, Authentication, and Authorization with ASP.NET MVC</span></span>](/aspnet/mvc/overview/security/)
- [<span data-ttu-id="8bf23-125">Migración de la autenticación y la identidad a ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8bf23-125">Migrate Authentication and Identity to ASP.NET Core</span></span>](/aspnet/mvc/overview/security/)
- [<span data-ttu-id="8bf23-126">Migrar desde ClaimsPrincipal. Current</span><span class="sxs-lookup"><span data-stu-id="8bf23-126">Migrate from ClaimsPrincipal.Current</span></span>](/aspnet/core/migration/claimsprincipal-current)
- [<span data-ttu-id="8bf23-127">Introducción a la autorización en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8bf23-127">Introduction to Authorization in ASP.NET Core</span></span>](/aspnet/core/security/authorization/introduction)

>[!div class="step-by-step"]
><span data-ttu-id="8bf23-128">[Anterior](webapi-differences.md)
>[Siguiente](identity-differences.md)</span><span class="sxs-lookup"><span data-stu-id="8bf23-128">[Previous](webapi-differences.md)
[Next](identity-differences.md)</span></span>
