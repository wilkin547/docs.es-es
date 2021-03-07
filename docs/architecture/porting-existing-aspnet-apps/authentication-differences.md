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
# <a name="compare-authentication-and-authorization-between-aspnet-mvc-and-aspnet-core"></a>Comparación de la autenticación y la autorización entre ASP.NET MVC y ASP.NET Core

En ASP.NET MVC 5, la autenticación se configura en *Startup.auth.CS* en la carpeta *App_Start* . En ASP.NET Core MVC, esta configuración se produce en `Startup.cs` . La autenticación y la autorización se realizan con middleware agregada a la canalización de solicitudes en `ConfigureServices` :

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

Es importante agregar el middleware de autenticación en el orden adecuado en la canalización de middleware. Solo las solicitudes que lo hagan al middleware se verán afectadas por esta. Por ejemplo, si una llamada a `UseStaticFiles()` se colocó sobre el código que se muestra aquí, no estaría protegido por la autenticación y la autorización.

En ASP.NET MVC y Web API, las aplicaciones suelen hacer referencia al usuario actual mediante la `ClaimsPrincipal.Current` propiedad. Esta propiedad no se establece en ASP.NET Core y cualquier comportamiento de la aplicación que dependa de ella tendrá que [migrar de ClaimsPrincipal. Current](/aspnet/core/migration/claimsprincipal-current) mediante la `User` propiedad en `ControllerBase` u obtener acceso a la actual `HttpContext` y hacer referencia a su `User` propiedad. Si ninguna de estas soluciones es una opción, los servicios pueden solicitar al usuario como argumento, en cuyo caso se debe proporcionar desde cualquier parte de la aplicación, o bien `IHttpContextAccessor` se puede solicitar y usar para obtener `HttpContext` .

## <a name="authorization"></a>Autorización

La autorización define lo que puede hacer un usuario determinado dentro de la aplicación. Es independiente de la autenticación, lo que se refiere únicamente a identificar quién es el usuario. ASP.NET Core proporciona un rol sencillo y declarativo y un modelo avanzado basado en directivas para la autorización. Especificar que un recurso requiere autorización suele ser tan sencillo como agregar el `[Authorize]` atributo a la acción o el controlador. Si va a migrar a Razor Pages desde las vistas de MVC, debe [especificar las convenciones de autorización al configurar Razor pages en el inicio](/aspnet/core/security/authorization/razor-pages-authorization).

La autorización en ASP.NET Core puede ser tan simple como la prohibición de usuarios anónimos, al tiempo que permite a los usuarios autenticados. O bien, se puede escalar verticalmente para admitir enfoques de autorización basados en roles, basados en notificaciones o basados en directivas. Para obtener más información sobre estos enfoques, consulte la documentación sobre la [autorización en ASP.net Core](/aspnet/core/security/authorization/introduction). Probablemente encontrará que una de ellas está estrechamente alineada con su enfoque de autorización actual.

## <a name="references"></a>Referencias

- [Seguridad, autenticación y autorización con ASP.NET MVC](/aspnet/mvc/overview/security/)
- [Migración de la autenticación y la identidad a ASP.NET Core](/aspnet/mvc/overview/security/)
- [Migrar desde ClaimsPrincipal. Current](/aspnet/core/migration/claimsprincipal-current)
- [Introducción a la autorización en ASP.NET Core](/aspnet/core/security/authorization/introduction)

>[!div class="step-by-step"]
>[Anterior](webapi-differences.md)
>[Siguiente](identity-differences.md)
