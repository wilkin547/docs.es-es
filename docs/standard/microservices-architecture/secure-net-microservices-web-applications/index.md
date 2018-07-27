---
title: Proteger microservicios y aplicaciones web de .NET
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Proteger microservicios y aplicaciones web de .NET
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 0e55a68432dfd44c7a73ae51512f50d481ae100c
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2018
ms.locfileid: "37937038"
---
# <a name="securing-net-microservices-and-web-applications"></a>Proteger microservicios y aplicaciones web de .NET

A menudo es necesario que los recursos y las API expuestas por un servicio se limiten a determinados usuarios o clientes de confianza. El primer paso para tomar este tipo de decisiones de confianza en el nivel de API es la autenticación. La autenticación es el proceso de determinar de forma fiable la identidad de un usuario.

En escenarios de microservicios, la autenticación suele controlarse de manera centralizada. Si usa una puerta de enlace de API, dicha puerta es un buen lugar para realizar la autenticación, como se muestra en la figura 11-1. Si emplea este método, asegúrese de que no es posible ponerse en contacto directamente con los microservicios individuales (sin la puerta de enlace de API), a menos que haya aplicado seguridad adicional para autenticar si los mensajes provienen de la puerta de enlace.

![](./media/image1.png)

**Figura 11-1**. Autenticación centralizada con una puerta de enlace de API.

Si se puede tener acceso directamente a los servicios, entonces para la autenticación de los usuarios se puede usar un servicio de autenticación como Azure Active Directory o un microservicio de autenticación dedicado que actúe como un servicio de token de seguridad (STS). Las decisiones de confianza se comparten entre los servicios con tokens de seguridad o cookies. (Si es necesario, estos se pueden compartir entre aplicaciones en ASP.NET Core con [servicios de protección de datos](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)). Este patrón se ilustra en la figura 11-2.

![](./media/image2.png)

**Figura 11-2**. Autenticación realizada por un microservicio de identidad; la confianza se comparte mediante un token de autorización.

## <a name="authenticating-using-aspnet-core-identity"></a>Autenticación mediante ASP.NET Core Identity

El principal mecanismo de ASP.NET Core para identificar a los usuarios de una aplicación es el sistema de pertenencia [ASP.NET Core Identity](https://docs.microsoft.com/aspnet/core/security/authentication/identity). ASP.NET Core Identity almacena la información del usuario (incluida la información de inicio de sesión, los roles y las notificaciones) en un almacén de datos configurado por el desarrollador. Normalmente, el almacén de datos de ASP.NET Core Identity es un almacén de Entity Framework incluido en el paquete Microsoft.AspNetCore.Identity.EntityFrameworkCore. Aun así, se pueden usar almacenes personalizados u otros paquetes de terceros para almacenar información de identidad en Table Storage de Azure, DocumentDB u otras ubicaciones.

El código siguiente procede de la plantilla de proyecto de aplicación web de ASP.NET Core con la autenticación de cuentas de usuario individuales seleccionada. Muestra cómo configurar ASP.NET Core Identity mediante EntityFramework.Core en el método Startup.ConfigureServices.

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

Una vez configurado ASP.NET Core Identity, debe habilitarlo. Para ello, llame a app.UseIdentity en el método Startup.Configure del servicio.

El uso de ASP.NET Core Identity permite varios escenarios:

-   Crear información de usuario con el tipo UserManager (userManager.CreateAsync).

-   Autenticar a los usuarios con el tipo SignInManager. Puede usar signInManager.SignInAsync para iniciar sesión directamente, o bien signInManager.PasswordSignInAsync para confirmar que la contraseña del usuario es correcta y, después, iniciar sesión.

-   Identificar a un usuario en función de la información almacenada en una cookie (que se lee mediante el software intermedio de ASP.NET Core Identity), de modo que las solicitudes posteriores desde un explorador incluyan la identidad y las notificaciones del usuario que ha iniciado sesión.

ASP.NET Core Identity también es compatible con la [autenticación en dos fases](https://docs.microsoft.com/aspnet/core/security/authentication/2fa).

ASP.NET Core Identity es una solución recomendada para los escenarios de autenticación que usan un almacén de datos de usuario local y que conservan la identidad entre las solicitudes mediante el uso de cookies (como es habitual en las aplicaciones web MVC).

## <a name="authenticating-using-external-providers"></a>Autenticar mediante proveedores externos

ASP.NET Core también admite el uso de [proveedores de autenticación externos](https://docs.microsoft.com/aspnet/core/security/authentication/social/) para permitir que los usuarios inicien sesión a través de flujos [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Esto significa que los usuarios pueden iniciar sesión mediante los procesos de autenticación existentes de proveedores como Microsoft, Google, Facebook o Twitter y asociar las identidades con una identidad de ASP.NET Core en la aplicación.

Para usar la autenticación externa, incluya el software intermedio de autenticación adecuado en la canalización de procesamiento de solicitudes HTTP de la aplicación. Este software intermedio es responsable de controlar las solicitudes para devolver las rutas URI desde el proveedor de autenticación, capturar información de identidad y hacer que esté disponible mediante el método SignInManager.GetExternalLoginInfo.

A continuación se muestran proveedores de autenticación externos populares y sus paquetes NuGet asociados.

**Microsoft:** Microsoft.AspNetCore.Authentication.MicrosoftAccount

**Google:** Microsoft.AspNetCore.Authentication.Google

**Facebook:** Microsoft.AspNetCore.Authentication.Facebook

**Twitter:** Microsoft.AspNetCore.Authentication.Twitter

En todos los casos, el software intermedio se registra con una llamada a un método de registro similar a app.Use{ExternalProvider}Authentication en Startup.Configure. Estos métodos de registro toman un objeto de opciones que contiene un identificador de aplicación e información secreta (una contraseña, por ejemplo), según requiera el proveedor. Los proveedores de autenticación externos requieren que la aplicación se registre (como se explica en la [documentación de ASP.NET Core](https://docs.microsoft.com/aspnet/core/security/authentication/social/)) para que puedan informar al usuario sobre qué aplicación solicita acceso a su identidad.

Una vez que se haya registrado el software intermedio en Startup.Configure, podrá pedirles a los usuarios que inicien sesión desde cualquier acción de controlador. Para ello, cree un objeto AuthenticationProperties que incluya el nombre del proveedor de autenticación y una dirección URL de redireccionamiento. Después, devuelva una respuesta Challenge que pase el objeto AuthenticationProperties. El código siguiente muestra un ejemplo de esto.

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

El parámetro redirectUrl incluye la dirección URL a la que el proveedor externo debe redirigir una vez que se ha autenticado el usuario. La dirección URL debe representar una acción que iniciará la sesión del usuario en función de información de identidad externa, como en el siguiente ejemplo simplificado:

```csharp
// Sign in the user with this external login provider if the user
// already has a login.
var result = await _signInManager.ExternalLoginSignInAsync(info.LoginProvider, info.ProviderKey, isPersistent: false);

if (result.Succeeded)
{
    return RedirectToLocal(returnUrl);
}
else
{
    ApplicationUser newUser = new ApplicationUser
    {
        // The user object can be constructed with claims from the
        // external authentication provider, combined with information
        // supplied by the user after they have authenticated with
        // the external provider.
        UserName = info.Principal.FindFirstValue(ClaimTypes.Name),
        Email = info.Principal.FindFirstValue(ClaimTypes.Email)
    };
    var identityResult = await _userManager.CreateAsync(newUser);
    if (identityResult.Succeeded)
    {
        identityResult = await _userManager.AddLoginAsync(newUser, info);
        if (identityResult.Succeeded)
        {
            await _signInManager.SignInAsync(newUser, isPersistent: false);
        }
        return RedirectToLocal(returnUrl);
    }
}
```

Si elige la opción de autenticación **Individual User Account** (Cuenta de usuario individual) al crear el proyecto de aplicación web de ASP.NET Core en Visual Studio, todo el código necesario para iniciar sesión con un proveedor externo ya está en el proyecto, como se muestra en la figura 11-3.

![https://msdnshared.blob.core.windows.net/media/2016/10/new-web-app.png](./media/image3.png)

**Figura 11-3**. Proceso de selección de una opción para usar la autenticación externa al crear un proyecto de aplicación web.

Además de los proveedores de autenticación externa mencionados anteriormente, hay disponibles paquetes de terceros que proporcionan software intermedio para el uso de muchos otros proveedores de autenticación externos. Para obtener una lista, vea el repositorio [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) en GitHub.

Por supuesto, también puede crear su propio software intermedio de autenticación externo.

## <a name="authenticating-with-bearer-tokens"></a>Autenticar mediante tokens de portador

La autenticación con ASP.NET Core Identity (o con Identity y proveedores de autenticación externos) funciona bien en muchos escenarios de aplicación web en los que es adecuado almacenar información de usuario en una cookie. En cambio, en otros escenarios las cookies no son una manera natural de conservar y transmitir datos.

Por ejemplo, en una Web API de ASP.NET Core que expone puntos de conexión RESTful a los que podrían tener acceso aplicaciones de una sola página (SPA), clientes nativos o incluso otras Web API, normalmente le interesa usar la autenticación mediante token de portador. Estos tipos de aplicaciones no funcionan con cookies, pero pueden recuperar fácilmente un token de portador e incluirlo en el encabezado de autorización de las solicitudes posteriores. Con objeto de habilitar la autenticación mediante token, ASP.NET Core admite varias opciones para el uso de [OAuth 2.0](https://oauth.net/2/) y [OpenID Connect](https://openid.net/connect/).

## <a name="authenticating-with-an-openid-connect-or-oauth-20-identity-provider"></a>Autenticar con un proveedor de identidad OpenID Connect u OAuth 2.0

Si la información de usuario se almacena en Azure Active Directory u otra solución de identidad compatible con OpenID Connect u OAuth 2.0, puede usar el paquete Microsoft.AspNetCore.Authentication.OpenIdConnect para autenticarse con el flujo de trabajo de OpenID Connect. Por ejemplo, para [autenticarse con Azure Active Directory](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/), una aplicación web de ASP.NET Core puede usar el software intermedio de ese paquete tal como se muestra en el ejemplo siguiente:

```csharp
// Configure the OWIN pipeline to use OpenID Connect auth
app.UseOpenIdConnectAuthentication(new OpenIdConnectOptions
{
    ClientId = Configuration["AzureAD:ClientId"],
    Authority = String.Format(Configuration["AzureAd:AadInstance"],
    Configuration["AzureAd:Tenant"]),
    ResponseType = OpenIdConnectResponseType.IdToken,
    PostLogoutRedirectUri = Configuration["AzureAd:PostLogoutRedirectUri"]
});
```

Los valores de configuración son los valores de Azure Active Directory que se crean cuando la aplicación se [registra como cliente de Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios#basics-of-registering-an-application-in-azure-ad). Es posible compartir un identificador de cliente único entre varios microservicios de una aplicación si todos necesitan autenticar a usuarios autenticados mediante Azure Active Directory.

Tenga en cuenta que, cuando se usa este flujo de trabajo, el software intermedio de ASP.NET Core Identity no es necesario, porque Azure Active Directory controla el almacenamiento y la autenticación de la información del usuario.

## <a name="issuing-security-tokens-from-an-aspnet-core-service"></a>Emitir tokens de seguridad desde un servicio de ASP.NET Core

Si prefiere emitir tokens de seguridad para los usuarios locales de ASP.NET Core Identity en lugar de usar un proveedor de identidades externo, puede aprovechar algunas buenas bibliotecas de terceros.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) y [OpenIddict](https://github.com/openiddict/openiddict-core) son proveedores de OpenID Connect que se integran fácilmente con ASP.NET Core Identity y le permiten emitir tokens de seguridad desde un servicio de ASP.NET Core. En la [documentación de IdentityServer4](https://identityserver4.readthedocs.io/en/release/) encontrará instrucciones detalladas para usar la biblioteca, pero los pasos básicos para emitir tokens con IdentityServer4 son los que se indican a continuación.

1.  Llame a app.UseIdentityServer en el método Startup.Configure para agregar IdentityServer4 a la canalización de procesamiento de solicitudes HTTP de la aplicación. Esto permite a la biblioteca atender las solicitudes a los puntos de conexión de OpenID Connect y OAuth2 como /connect/token.

2.  Configure IdentityServer4 en Startup.ConfigureServices mediante una llamada a services.AddIdentityServer.

3.  Para configurar el servidor de identidades, proporcione los datos siguientes:

-   Las [credenciales](https://identityserver4.readthedocs.io/en/release/topics/crypto.html) que se van a usar para la firma.

-   Los [recursos de identidad y de API](https://identityserver4.readthedocs.io/en/release/topics/resources.html) a los que los usuarios podrían solicitar acceso:

<!-- -->

-   Los recursos de API representan funciones o datos protegidos a los que los usuarios pueden tener acceso con un token de acceso. Un ejemplo de un recurso de API sería una API web (o un conjunto de API) que requiere autorización.

-   Los recursos de identidad representan información (notificaciones) que se entregan a un cliente para identificar a un usuario. Las notificaciones pueden incluir el nombre de usuario, la dirección de correo electrónico, etc.

<!-- -->

-   Los [clientes](https://identityserver4.readthedocs.io/en/release/topics/clients.html) que se conectarán para solicitar tokens.

-   El mecanismo de almacenamiento de la información de usuario, como [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/release/quickstarts/6_aspnet_identity.html) u otra alternativa.

Al especificar los clientes y los recursos que usará IdentityServer4, puede pasar una colección IEnumerable&lt;T&gt; del tipo adecuado a los métodos que toman almacenes de recursos o cliente en memoria. En escenarios más complejos, puede proporcionar tipos de proveedor de recursos o cliente mediante la inserción de dependencias.

En el ejemplo siguiente se muestra el aspecto que podría tener una configuración para que IdentityServer4 use clientes y recursos en memoria proporcionados por un tipo IClientStore personalizado:

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

## <a name="consuming-security-tokens"></a>Consumir tokens de seguridad

La autenticación con un punto de conexión de OpenID Connect o mediante la emisión de tokens de seguridad propios se aplica a diversos escenarios. Pero ¿qué sucede si un servicio solo necesita limitar el acceso a los usuarios que tienen tokens de seguridad válidos proporcionados por otro servicio?

Para este escenario, en el paquete Microsoft.AspNetCore.Authentication.JwtBearer está disponible el software intermedio de autenticación que controla los tokens JWT. JWT es el acrónimo de "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" y es un formato común de token de seguridad (definido en RFC 7519) para la comunicación de notificaciones de seguridad. Un ejemplo sencillo de cómo emplear el software intermedio para usar esos tokens tendría un aspecto similar al siguiente. Este código debe preceder a las llamadas al software intermedio MVC de ASP.NET Core (app.UseMvc).

```csharp
app.UseJwtBearerAuthentication(new JwtBearerOptions()
{
    Audience = "http://localhost:5001/",
    Authority = "http://localhost:5000/",
    AutomaticAuthenticate = true
});
```

Los parámetros de este uso son los siguientes:

-   Audience representa el receptor del token entrante o el recurso al que el token concede acceso. Si el valor especificado en este parámetro no coincide con el parámetro aud del token, se rechazará el token.

-   Authority es la dirección del servidor de autenticación de emisión de tokens. El software intermedio de autenticación del portador de JWT usa este URI para obtener la clave pública que puede usarse para validar la firma del token. El software intermedio también confirma que el parámetro iss del token coincide con este URI.

-   AutomaticAuthenticate es un valor booleano que indica si la sesión del usuario definido por el token debe iniciarse automáticamente.

En este ejemplo no se usa el parámetro RequireHttpsMetadata. Resulta útil para la realización de pruebas; establézcalo en false para efectuar pruebas en los entornos en los que no tiene certificados. En implementaciones reales, los tokens de portador de JWT siempre se deben pasar a través de HTTPS exclusivamente.

Con este software intermedio, los tokens JWT se extraen automáticamente de los encabezados de autorización. Después, se deserializan, se validan (mediante los valores de los parámetros Audience y Authority) y se almacenan como información del usuario a la que se hará referencia más adelante a través de acciones de MVC o filtros de autorización.

El software intermedio de autenticación del portador de JWT también puede admitir escenarios más avanzados, como el uso de un certificado local para validar un token si la entidad no está disponible. En este escenario, puede especificar un objeto TokenValidationParameters en el objeto JwtBearerOptions.

## <a name="additional-resources"></a>Recursos adicionales

-   **Uso compartido de cookies entre aplicaciones**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing\#sharing-authentication-cookies-between-applications*](https://docs.microsoft.com/aspnet/core/security/data-protection/compatibility/cookie-sharing#sharing-authentication-cookies-between-applications)

-   **Introducción a Identity**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/identity*](https://docs.microsoft.com/aspnet/core/security/authentication/identity)

-   **Rick Anderson. Autenticación en dos fases con SMS**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/2fa*](https://docs.microsoft.com/aspnet/core/security/authentication/2fa)

-   **Habilitación de la autenticación con Facebook, Google y otros proveedores externos**
    [*https://docs.microsoft.com/aspnet/core/security/authentication/social/*](https://docs.microsoft.com/aspnet/core/security/authentication/social/)

-   **Michell Anicas. An Introduction to OAuth 2**
    [*https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2*](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) (Una introducción a OAuth 2)

-   **AspNet.Security.OAuth.Providers** (repositorio de GitHub para proveedores de OAuth de ASP.NET).
    [*https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src*](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src)

-   **Danny Strockis. Integración de Azure AD en una aplicación web ASP.NET Core**
    [*https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/*](https://azure.microsoft.com/resources/samples/active-directory-dotnet-webapp-openidconnect-aspnetcore/)

-   **IdentityServer4. Documentación oficial**
    [*https://identityserver4.readthedocs.io/en/release/*](https://identityserver4.readthedocs.io/en/release/)


>[!div class="step-by-step"]
[Anterior](../implement-resilient-applications/monitor-app-health.md)
[Siguiente](authorization-net-microservices-web-applications.md)
