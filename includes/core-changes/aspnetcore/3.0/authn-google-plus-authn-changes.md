---
ms.openlocfilehash: c634c43e72d345721f2d8f2e9f45760e927a86ab
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032701"
---
### <a name="authentication-google-deprecated-and-replaced"></a>Autenticación: Google+ se ha dejado en desuso y se ha reemplazado

Google está empezando a [apagar](https://developers.google.com/+/api-shutdown) el inicio de sesión de Google+ en las aplicaciones a partir del 28 de enero de 2019.

#### <a name="change-description"></a>Descripción del cambio

ASP.NET 4.x y ASP.NET Core han estado usando las API de inicio de sesión de Google+ para autenticar a los usuarios de cuentas de Google en las aplicaciones web. Los paquetes NuGet afectados son [Microsoft.AspNetCore.Authentication.Google](https://www.nuget.org/packages/Microsoft.AspNetCore.Authentication.Google/) para ASP.NET Core y [Microsoft.Owin.Security.Google](https://www.nuget.org/packages/Microsoft.Owin.Security.Google/) para `Microsoft.Owin` con ASP.NET Web Forms y MVC.

Las API de reemplazo de Google utilizan un formato y un origen de datos distintos. Las mitigaciones y soluciones que se proporcionan a continuación tienen en cuenta los cambios estructurales. Las aplicaciones deben comprobar que los datos en sí cumplen sus requisitos. Por ejemplo, los nombres, las direcciones de correo electrónico, los vínculos de perfil y las fotos de perfil pueden proporcionar valores ligeramente distintos a los anteriores.

#### <a name="version-introduced"></a>Versión introducida

Todas las versiones. Este cambio es externo a ASP.NET Core.

#### <a name="recommended-action"></a>Acción recomendada

##### <a name="owin-with-aspnet-web-forms-and-mvc"></a>Owin con ASP.NET Web Forms y MVC

En el caso de `Microsoft.Owin` 3.1.0 y versiones posteriores, se describe una mitigación temporal [aquí](https://github.com/aspnet/AspNetKatana/issues/251#issuecomment-449587635). Las aplicaciones deben completar las pruebas con la mitigación para comprobar si hay cambios en el formato de datos. Existen planes para lanzar `Microsoft.Owin` 4.0.1 con una corrección. Las aplicaciones que usen cualquier versión anterior deben actualizarse a la versión 4.0.1.

##### <a name="aspnet-core-1x"></a>ASP.NET Core 1.x

La mitigación en [Owin con ASP.NET Web Forms y MVC](#owin-with-aspnet-web-forms-and-mvc) puede adaptarse a ASP.NET Core 1.x. Las revisiones del paquete NuGet no están planeadas porque 1.x ha alcanzado el estado [final del ciclo de vida](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-2x"></a>ASP.NET Core 2.x

En el caso la versión 2.x de `Microsoft.AspNetCore.Authentication.Google`, reemplace la llamada existente a `AddGoogle` en `Startup.ConfigureServices` por el código siguiente:

```csharp
.AddGoogle(o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.UserInformationEndpoint = "https://www.googleapis.com/oauth2/v2/userinfo";
    o.ClaimActions.Clear();
    o.ClaimActions.MapJsonKey(ClaimTypes.NameIdentifier, "id");
    o.ClaimActions.MapJsonKey(ClaimTypes.Name, "name");
    o.ClaimActions.MapJsonKey(ClaimTypes.GivenName, "given_name");
    o.ClaimActions.MapJsonKey(ClaimTypes.Surname, "family_name");
    o.ClaimActions.MapJsonKey("urn:google:profile", "link");
    o.ClaimActions.MapJsonKey(ClaimTypes.Email, "email");
});
```

Las revisiones 2.1 y 2.2 de febrero incorporaron la reconfiguración anterior como el nuevo valor predeterminado. No hay ninguna revisión planeada para ASP.NET Core 2.0 porque ha alcanzado el [final del ciclo de vida](https://dotnet.microsoft.com/platform/support-policy).

##### <a name="aspnet-core-30"></a>ASP.NET Core 3.0

La mitigación proporcionada para ASP.NET Core 2.x también puede usarse para ASP.NET Core 3.0. En versiones preliminares futuras de la versión 3.0, se puede quitar el paquete `Microsoft.AspNetCore.Authentication.Google`. A los usuarios se les dirigirá a `Microsoft.AspNetCore.Authentication.OpenIdConnect` en su lugar. El código siguiente muestra cómo reemplazar `AddGoogle` por `AddOpenIdConnect` en `Startup.ConfigureServices`. Este reemplazo se puede usar con ASP.NET Core 2.0 y versiones posteriores, y se puede adaptar para ASP.NET Core 1.x, según sea necesario.

```csharp
.AddOpenIdConnect("Google", o =>
{
    o.ClientId = Configuration["Authentication:Google:ClientId"];
    o.ClientSecret = Configuration["Authentication:Google:ClientSecret"];
    o.Authority = "https://accounts.google.com";
    o.ResponseType = OpenIdConnectResponseType.Code;
    o.CallbackPath = "/signin-google"; // Or register the default "/sigin-oidc"
    o.Scope.Add("email");
});
JwtSecurityTokenHandler.DefaultInboundClaimTypeMap.Clear();
```

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.AspNetCore.Authentication.Google?displayProperty=fullName>

<!-- 

#### Affected APIs

`N:Microsoft.AspNetCore.Authentication.Google`

-->
