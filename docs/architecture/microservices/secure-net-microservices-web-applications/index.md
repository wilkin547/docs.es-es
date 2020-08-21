---
title: Proteger microservicios y aplicaciones web de .NET
description: 'Seguridad en microservicios y aplicaciones web .NET: familiarícese con las opciones de autenticación en las aplicaciones web ASP.NET Core.'
author: mjrousos
ms.date: 08/07/2020
ms.openlocfilehash: 1dcdb5d2987360ac583fa700a387d977f498d1d9
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608100"
---
# <a name="make-secure-net-microservices-and-web-applications"></a>Protección de microservicios y aplicaciones web .NET

Hay tantos aspectos sobre la seguridad de los microservicios y las aplicaciones web que se podrían escribir varios libros como este al respecto. Por tanto, en esta sección nos centraremos en la autenticación, la autorización y los secretos de aplicación.

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a>Implementación de la autenticación en microservicios y aplicaciones web .NET

A menudo es necesario que los recursos y las API publicados por un servicio se limiten a determinados usuarios o clientes de confianza. El primer paso para tomar este tipo de decisiones de confianza en el nivel de API es la autenticación. La autenticación es el proceso de comprobar de forma fiable la identidad de un usuario.

Cuando hay microservicios, la autenticación normalmente se controla de forma centralizada. Si usa una puerta de enlace de API, esa puerta es un buen lugar para realizar la autenticación, como se muestra en la figura 9-1. Si emplea este método, asegúrese de que no es posible ponerse en contacto directamente con los microservicios individuales (sin la puerta de enlace de API), a menos que haya aplicado seguridad adicional para autenticar si los mensajes provienen de la puerta de enlace.

![Diagrama en el que se muestra cómo interactúa la aplicación móvil cliente con el back-end.](./media/index/api-gateway-centralized-authentication.png)

**Figura 9-1**. Autenticación centralizada con una puerta de enlace de API.

Cuando la puerta de enlace de API centraliza la autenticación, agrega información de usuario al reenviar las solicitudes a los microservicios. Si se puede tener acceso directamente a los servicios, es posible emplear un servicio de autenticación como Azure Active Directory o un microservicio de autenticación dedicado que actúe como servicio de token de seguridad (STS) puede utilizarse para autenticar a los usuarios. Las decisiones de confianza se comparten entre los servicios con tokens de seguridad o cookies. (Si es necesario, estos tokens se pueden compartir entre aplicaciones de ASP.NET Core mediante el [uso compartido de cookies](/aspnet/core/security/cookie-sharing)). Este patrón se ilustra en la figura 9-2.

![Diagrama en el que se muestra la autenticación a través de microservicios de back-end.](./media/index/identity-microservice-authentication.png)

**Figura 9-2**. Autenticación realizada por un microservicio de identidad; la confianza se comparte mediante un token de autorización.

Cuando se accede directamente a los microservicios, la confianza (que incluye la autenticación y la autorización) se controla mediante un token de seguridad emitido por un microservicio dedicado, que se comparte entre los microservicios.

### <a name="authenticate-with-aspnet-core-identity"></a>Autenticación con ASP.NET Core Identity

El principal mecanismo de ASP.NET Core para identificar a los usuarios de una aplicación es el sistema de pertenencia [ASP.NET Core Identity](/aspnet/core/security/authentication/identity). Identity de ASP.NET Core almacena información de usuario (incluida la información de inicio de sesión, roles y notificaciones) en un almacén de datos configurado por el desarrollador. Normalmente, el almacén de datos de ASP.NET Core Identity es un almacén de Entity Framework incluido en el paquete `Microsoft.AspNetCore.Identity.EntityFrameworkCore`. Pero se pueden usar almacenes personalizados u otros paquetes de terceros para almacenar información de identidad en Table Storage de Azure, Cosmos DB u otras ubicaciones.

> [!TIP]
> ASP.NET Core 2.1 y versiones posteriores proporcionan [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) como una [biblioteca de clases de Razor](/aspnet/core/razor-pages/ui-class), así que gran parte del código necesario en el proyecto no se verá, como era el caso de las versiones anteriores. Para más información sobre cómo personalizar el código de Identity para satisfacer sus necesidades, consulte [Identidad de scaffolding en proyectos de ASP.NET Core](/aspnet/core/security/authentication/scaffold-identity).

El código siguiente procede de la plantilla de proyecto de aplicación web ASP.NET Core MVC 3.1 con la autenticación de cuentas de usuario individuales seleccionada. Muestra cómo configurar ASP.NET Core Identity mediante Entity Framework Core en el método `Startup.ConfigureServices`.

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDbContext<ApplicationDbContext>(options =>
        options.UseSqlServer(
            Configuration.GetConnectionString("DefaultConnection")));

    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddRazorPages();
    //...
}
```

Una vez configurado ASP.NET Core Identity, para habilitarlo agregue `app.UseAuthentication()` y `endpoints.MapRazorPages()`, como se muestra en el siguiente código en el método `Startup.Configure` del servicio:

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    //...
    app.UseRouting();

    app.UseAuthentication();
    app.UseAuthorization();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapRazorPages();
    });
    //...
}
```

> [!IMPORTANT]
> Las líneas del código anterior **DEBEN ESTAR EN EL ORDEN MOSTRADO** para que Identity funcione correctamente.

El uso de ASP.NET Core Identity permite varios escenarios:

- Crear información de usuario con el tipo UserManager (userManager.CreateAsync).

- Autenticar a los usuarios con el tipo SignInManager. Puede usar `signInManager.SignInAsync` para iniciar sesión directamente, o bien `signInManager.PasswordSignInAsync` para confirmar que la contraseña del usuario es correcta y, después, iniciar su sesión.

- Identificar a un usuario en función de la información almacenada en una cookie (que se lee mediante el software intermedio de ASP.NET Core Identity), de modo que las solicitudes posteriores desde un explorador incluyan la identidad y las notificaciones del usuario que ha iniciado sesión.

ASP.NET Core Identity también es compatible con la [autenticación en dos fases](/aspnet/core/security/authentication/2fa).

ASP.NET Core Identity es una solución recomendada para los escenarios de autenticación que usan un almacén de datos de usuario local y que conservan la identidad entre las solicitudes mediante el uso de cookies (como es habitual en las aplicaciones web MVC).

### <a name="authenticate-with-external-providers"></a>Autenticación con proveedores externos

ASP.NET Core también admite el uso de [proveedores de autenticación externos](/aspnet/core/security/authentication/social/) para permitir que los usuarios inicien sesión a través de flujos [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2). Esto significa que los usuarios pueden iniciar sesión mediante los procesos de autenticación existentes de proveedores como Microsoft, Google, Facebook o Twitter, y asociar esas identidades con una identidad de ASP.NET Core en la aplicación.

Para usar autenticación externa, además de incluir el middleware de autenticación, como se mencionó antes, con el método `app.UseAuthentication()`, también tiene que registrar el proveedor externo en `Startup`, como se muestra en el ejemplo siguiente:

```csharp
public void ConfigureServices(IServiceCollection services)
{
    //...
    services.AddDefaultIdentity<IdentityUser>(options => options.SignIn.RequireConfirmedAccount = true)
        .AddEntityFrameworkStores<ApplicationDbContext>();

    services.AddAuthentication()
        .AddMicrosoftAccount(microsoftOptions =>
        {
            microsoftOptions.ClientId = Configuration["Authentication:Microsoft:ClientId"];
            microsoftOptions.ClientSecret = Configuration["Authentication:Microsoft:ClientSecret"];
        })
        .AddGoogle(googleOptions => { ... })
        .AddTwitter(twitterOptions => { ... })
        .AddFacebook(facebookOptions => { ... });
    //...
}
```

En la tabla siguiente se muestran proveedores de autenticación externos populares y sus paquetes NuGet asociados:

| **Proveedor**  | **Package**                                          |
| ------------- | ---------------------------------------------------- |
| **Microsoft** | **Microsoft.AspNetCore.Authentication.MicrosoftAccount** |
| **Google**    | **Microsoft.AspNetCore.Authentication.Google**           |
| **Facebook**  | **Microsoft.AspNetCore.Authentication.Facebook**         |
| **Twitter**   | **Microsoft.AspNetCore.Authentication.Twitter**          |

En todos los casos, debe completar un procedimiento de registro de aplicaciones que sea dependiente del proveedor y que normalmente supone:

1. Obtener un identificador de aplicación cliente.
2. Obtener un secreto de aplicación cliente.
3. Configurar una dirección URL de redireccionamiento administrada por el middleware de autorización y el proveedor registrado.
4. Opcionalmente, configurar una dirección URL de cierre de sesión para administrar correctamente el cierre de sesión en un escenario de inicio de sesión único (SSO).

Para más información sobre la configuración de la aplicación para un proveedor externo, consulte la [autenticación de proveedores externos en la documentación de ASP.NET Core](/aspnet/core/security/authentication/social/)).

>[!TIP]
>El middleware de autorización y los servicios mencionados anteriormente administran todos los detalles. Por lo tanto, solo tiene que elegir la opción de autenticación **Cuenta de usuario individual** al crear el proyecto de aplicación web de ASP.NET Code en Visual Studio, como se muestra en la figura 9-3, además de registrar los proveedores de autenticación mencionados anteriormente.

![Captura de pantalla del cuadro de diálogo Nueva aplicación web ASP.NET Core.](./media/index/select-individual-user-account-authentication-option.png)

**Figura 9-3**. Selección de la opción Cuentas de usuario individuales para usar la autenticación externa al crear un proyecto de aplicación web en Visual Studio 2019.

Además de los proveedores de autenticación externa mencionados anteriormente, hay disponibles paquetes de terceros que proporcionan software intermedio para el uso de muchos otros proveedores de autenticación externos. Para ver una lista, consulte el repositorio [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) en GitHub.

También puede crear middleware de autenticación externo propio para resolver alguna necesidad especial.

### <a name="authenticate-with-bearer-tokens"></a>Autenticación con tokens de portador

La autenticación con ASP.NET Core Identity (o con Identity y proveedores de autenticación externos) funciona bien en muchos escenarios de aplicación web en los que es adecuado almacenar información de usuario en una cookie. En cambio, en otros escenarios las cookies no son una manera natural de conservar y transmitir datos.

Por ejemplo, en una Web API de ASP.NET Core que expone puntos de conexión RESTful a los que podrían tener acceso aplicaciones de una sola página (SPA), clientes nativos o incluso otras Web API, normalmente le interesa usar la autenticación mediante token de portador. Estos tipos de aplicaciones no funcionan con cookies, pero pueden recuperar fácilmente un token de portador e incluirlo en el encabezado de autorización de las solicitudes posteriores. Con objeto de habilitar la autenticación mediante token, ASP.NET Core admite varias opciones para el uso de [OAuth 2.0](https://oauth.net/2/) y [OpenID Connect](https://openid.net/connect/).

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a>Autenticación con un proveedor de identidad OpenID Connect u OAuth 2.0

Si la información de usuario se almacena en Azure Active Directory u otra solución de identidad compatible con OpenID Connect u OAuth 2.0, puede usar el paquete **Microsoft.AspNetCore.Authentication.OpenIdConnect** para autenticarse con el flujo de trabajo de OpenID Connect. Por ejemplo, para autenticarse en el microservicio Identity.Api de eShopOnContainers, una aplicación web ASP.NET Core puede usar el middleware de ese paquete como se muestra en el siguiente ejemplo simplificado de `Startup.cs`:

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");
    var sessionCookieLifetime = Configuration.GetValue("SessionCookieLifetimeMinutes", 60);

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;
    })
    .AddCookie(setup => setup.ExpireTimeSpan = TimeSpan.FromMinutes(sessionCookieLifetime))
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl.ToString();
        options.SignedOutRedirectUri = callBackUrl.ToString();
        options.ClientId = useLoadTest ? "mvctest" : "mvc";
        options.ClientSecret = "secret";
        options.ResponseType = useLoadTest ? "code id_token token" : "code id_token";
        options.SaveTokens = true;
        options.GetClaimsFromUserInfoEndpoint = true;
        options.RequireHttpsMetadata = false;
        options.Scope.Add("openid");
        options.Scope.Add("profile");
        options.Scope.Add("orders");
        options.Scope.Add("basket");
        options.Scope.Add("marketing");
        options.Scope.Add("locations");
        options.Scope.Add("webshoppingagg");
        options.Scope.Add("orders.signalrhub");
    });
}
```

Tenga en cuenta que, cuando se usa este flujo de trabajo, el software intermedio de ASP.NET Core Identity no es necesario, porque el servicio de identidad controla el almacenamiento y la autenticación de la información del usuario.

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a>Emisión de tokens de seguridad desde un servicio de ASP.NET Core

Si prefiere emitir tokens de seguridad para los usuarios locales de ASP.NET Core Identity en lugar de usar un proveedor de identidades externo, puede aprovechar algunas buenas bibliotecas de terceros.

[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) y [OpenIddict](https://github.com/openiddict/openiddict-core) son proveedores de OpenID Connect que se integran fácilmente con ASP.NET Core Identity y le permiten emitir tokens de seguridad desde un servicio de ASP.NET Core. En la [documentación de IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) encontrará instrucciones detalladas para usar la biblioteca, pero los pasos básicos para emitir tokens con IdentityServer4 son los que se indican a continuación.

1. Llame a app.UseIdentityServer en el método Startup.Configure para agregar IdentityServer4 a la canalización de procesamiento de solicitudes HTTP de la aplicación. Esto permite a la biblioteca atender las solicitudes a los puntos de conexión de OpenID Connect y OAuth2 como /connect/token.

2. Configure IdentityServer4 en Startup.ConfigureServices mediante una llamada a services.AddIdentityServer.

3. Para configurar el servidor de identidades, establezca los datos siguientes:

   - Las [credenciales](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) que se van a usar para la firma.

   - Los [recursos de identidad y de API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) a los que los usuarios podrían solicitar acceso:

      - Los recursos de API representan funciones o datos protegidos a los que los usuarios pueden tener acceso con un token de acceso. Un ejemplo de un recurso de API sería una API web (o un conjunto de API) que requiere autorización.

      - Los recursos de identidad representan información (notificaciones) que se entregan a un cliente para identificar a un usuario. Las notificaciones pueden incluir el nombre de usuario, la dirección de correo electrónico, etc.

   - Los [clientes](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) que se conectarán para solicitar tokens.

   - El mecanismo de almacenamiento de la información de usuario, como [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) u otra alternativa.

Al especificar los clientes y los recursos que se van a usar en IdentityServer4, puede pasar una colección <xref:System.Collections.Generic.IEnumerable%601> del tipo adecuado a los métodos que toman almacenes de recursos o clientes en memoria. En escenarios más complejos, puede proporcionar tipos de proveedor de recursos o cliente mediante la inserción de dependencias.

En el ejemplo siguiente se muestra el aspecto que podría tener una configuración para que IdentityServer4 use clientes y recursos en memoria proporcionados por un tipo IClientStore personalizado:

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //...
    services.AddSingleton<IClientStore, CustomClientStore>();
    services.AddIdentityServer()
        .AddSigningCredential("CN=sts")
        .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
        .AddAspNetIdentity<ApplicationUser>();
    //...
}
```

### <a name="consume-security-tokens"></a>Consumo de tokens de seguridad

La autenticación con un punto de conexión de OpenID Connect o mediante la emisión de tokens de seguridad propios se aplica a diversos escenarios. Pero ¿qué sucede si un servicio solo necesita limitar el acceso a los usuarios que tienen tokens de seguridad válidos proporcionados por otro servicio?

Para este escenario, el middleware de autenticación que controla los tokens JWT está disponible en el paquete **Microsoft.AspNetCore.Authentication.JwtBearer**. JWT es el acrónimo de "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" y es un formato común de token de seguridad (definido en RFC 7519) para la comunicación de notificaciones de seguridad. Un ejemplo simplificado de cómo usar el middleware para consumir esos tokens podría ser similar a este fragmento de código, tomado del microservicio Ordering.Api de eShopOnContainers.

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseEndpoints(endpoints =>
    {
        //...
    });
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = AspNetCore.Authentication.JwtBearer.JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

Los parámetros de este uso son los siguientes:

- `Audience` representa el receptor del token entrante o el recurso al que el token concede acceso. Si el valor especificado en este parámetro no coincide con el parámetro del token, se rechazará el token.

- `Authority` es la dirección del servidor de autenticación de emisión de tokens. El software intermedio de autenticación del portador de JWT usa este URI para obtener la clave pública que puede usarse para validar la firma del token. El middleware también confirma que el parámetro `iss` del token coincide con este URI.

Otro parámetro, `RequireHttpsMetadata`, resulta útil para la realización de pruebas; establézcalo en false para poder realizarlas en los entornos en los que no tiene certificados. En implementaciones reales, los tokens de portador de JWT siempre se deben pasar a través de HTTPS exclusivamente.

Con este software intermedio, los tokens JWT se extraen automáticamente de los encabezados de autorización. Después, se deserializan, se validan (mediante los valores de los parámetros `Audience` y `Authority`) y se almacenan como información del usuario a la que se hará referencia más adelante a través de acciones de MVC o filtros de autorización.

El software intermedio de autenticación del portador de JWT también puede admitir escenarios más avanzados, como el uso de un certificado local para validar un token si la entidad no está disponible. En este escenario, puede especificar un objeto `TokenValidationParameters` en el objeto `JwtBearerOptions`.

## <a name="additional-resources"></a>Recursos adicionales

- **Uso compartido de cookies entre aplicaciones** \
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- **Introducción a Identity** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- **Rick Anderson. Autenticación en dos fases con SMS** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- **Habilitación de la autenticación con Facebook, Google y otros proveedores externos** \
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- **Michell Anicas. Una introducción a OAuth 2** \
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- **repositorio de GitHub para proveedores de OAuth de ASP.NET**\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- **IdentityServer4. Documentación oficial** \
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
>[Anterior](../implement-resilient-applications/monitor-app-health.md)
>[Siguiente](authorization-net-microservices-web-applications.md)
