---
title: Proteger microservicios y aplicaciones web de .NET
description: 'Seguridad en microservicios y aplicaciones web .NET: familiarícese con las opciones de autenticación en las aplicaciones web ASP.NET Core.'
author: mjrousos
ms.date: 08/07/2020
ms.openlocfilehash: 01797189ce946c39bc7b8cafdff1e69ff9760e4e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160677"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="30317-103">Protección de microservicios y aplicaciones web .NET</span><span class="sxs-lookup"><span data-stu-id="30317-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="30317-104">Hay tantos aspectos sobre la seguridad de los microservicios y las aplicaciones web que se podrían escribir varios libros como este al respecto.</span><span class="sxs-lookup"><span data-stu-id="30317-104">There are so many aspects about security in microservices and web applications that the topic could easily take several books like this one.</span></span> <span data-ttu-id="30317-105">Por tanto, en esta sección nos centraremos en la autenticación, la autorización y los secretos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="30317-105">So, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="30317-106">Implementación de la autenticación en microservicios y aplicaciones web .NET</span><span class="sxs-lookup"><span data-stu-id="30317-106">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="30317-107">A menudo es necesario que los recursos y las API publicados por un servicio se limiten a determinados usuarios o clientes de confianza.</span><span class="sxs-lookup"><span data-stu-id="30317-107">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="30317-108">El primer paso para tomar este tipo de decisiones de confianza en el nivel de API es la autenticación.</span><span class="sxs-lookup"><span data-stu-id="30317-108">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="30317-109">La autenticación es el proceso de comprobar de forma fiable la identidad de un usuario.</span><span class="sxs-lookup"><span data-stu-id="30317-109">Authentication is the process of reliably verifying a user's identity.</span></span>

<span data-ttu-id="30317-110">Cuando hay microservicios, la autenticación normalmente se controla de forma centralizada.</span><span class="sxs-lookup"><span data-stu-id="30317-110">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="30317-111">Si usa una puerta de enlace de API, esa puerta es un buen lugar para realizar la autenticación, como se muestra en la figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="30317-111">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="30317-112">Si emplea este método, asegúrese de que no es posible ponerse en contacto directamente con los microservicios individuales (sin la puerta de enlace de API), a menos que haya aplicado seguridad adicional para autenticar si los mensajes provienen de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="30317-112">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Diagrama en el que se muestra cómo interactúa la aplicación móvil cliente con el back-end.](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="30317-114">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="30317-114">**Figure 9-1**.</span></span> <span data-ttu-id="30317-115">Autenticación centralizada con una puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="30317-115">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="30317-116">Cuando la puerta de enlace de API centraliza la autenticación, agrega información de usuario al reenviar las solicitudes a los microservicios.</span><span class="sxs-lookup"><span data-stu-id="30317-116">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="30317-117">Si se puede tener acceso directamente a los servicios, es posible emplear un servicio de autenticación como Azure Active Directory o un microservicio de autenticación dedicado que actúe como servicio de token de seguridad (STS) puede utilizarse para autenticar a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="30317-117">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="30317-118">Las decisiones de confianza se comparten entre los servicios con tokens de seguridad o cookies.</span><span class="sxs-lookup"><span data-stu-id="30317-118">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="30317-119">(Si es necesario, estos tokens se pueden compartir entre aplicaciones de ASP.NET Core mediante el [uso compartido de cookies](/aspnet/core/security/cookie-sharing)). Este patrón se ilustra en la figura 9-2.</span><span class="sxs-lookup"><span data-stu-id="30317-119">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![Diagrama en el que se muestra la autenticación a través de microservicios de back-end.](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="30317-121">**Figura 9-2**.</span><span class="sxs-lookup"><span data-stu-id="30317-121">**Figure 9-2**.</span></span> <span data-ttu-id="30317-122">Autenticación realizada por un microservicio de identidad; la confianza se comparte mediante un token de autorización.</span><span class="sxs-lookup"><span data-stu-id="30317-122">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="30317-123">Cuando se accede directamente a los microservicios, la confianza (que incluye la autenticación y la autorización) se controla mediante un token de seguridad emitido por un microservicio dedicado, que se comparte entre los microservicios.</span><span class="sxs-lookup"><span data-stu-id="30317-123">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="30317-124">Autenticación con ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="30317-124">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="30317-125">El principal mecanismo de ASP.NET Core para identificar a los usuarios de una aplicación es el sistema de pertenencia [ASP.NET Core Identity](/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="30317-125">The primary mechanism in ASP.NET Core for identifying an application's users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="30317-126">Identity de ASP.NET Core almacena información de usuario (incluida la información de inicio de sesión, roles y notificaciones) en un almacén de datos configurado por el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="30317-126">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="30317-127">Normalmente, el almacén de datos de ASP.NET Core Identity es un almacén de Entity Framework incluido en el paquete `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="30317-127">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="30317-128">Pero se pueden usar almacenes personalizados u otros paquetes de terceros para almacenar información de identidad en Table Storage de Azure, Cosmos DB u otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="30317-128">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

> [!TIP]
> <span data-ttu-id="30317-129">ASP.NET Core 2.1 y versiones posteriores proporcionan [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) como una [biblioteca de clases de Razor](/aspnet/core/razor-pages/ui-class), así que gran parte del código necesario en el proyecto no se verá, como era el caso de las versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="30317-129">ASP.NET Core 2.1 and later provides [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) as a [Razor Class Library](/aspnet/core/razor-pages/ui-class), so you won't see much of the necessary code in your project, as was the case for previous versions.</span></span> <span data-ttu-id="30317-130">Para más información sobre cómo personalizar el código de Identity para satisfacer sus necesidades, consulte [Identidad de scaffolding en proyectos de ASP.NET Core](/aspnet/core/security/authentication/scaffold-identity).</span><span class="sxs-lookup"><span data-stu-id="30317-130">For details on how to customize the Identity code to suit your needs, see [Scaffold Identity in ASP.NET Core projects](/aspnet/core/security/authentication/scaffold-identity).</span></span>

<span data-ttu-id="30317-131">El código siguiente procede de la plantilla de proyecto de aplicación web ASP.NET Core MVC 3.1 con la autenticación de cuentas de usuario individuales seleccionada.</span><span class="sxs-lookup"><span data-stu-id="30317-131">The following code is taken from the ASP.NET Core Web Application MVC 3.1 project template with individual user account authentication selected.</span></span> <span data-ttu-id="30317-132">Muestra cómo configurar ASP.NET Core Identity mediante Entity Framework Core en el método `Startup.ConfigureServices`.</span><span class="sxs-lookup"><span data-stu-id="30317-132">It shows how to configure ASP.NET Core Identity using Entity Framework Core in the `Startup.ConfigureServices` method.</span></span>

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

<span data-ttu-id="30317-133">Una vez configurado ASP.NET Core Identity, para habilitarlo agregue `app.UseAuthentication()` y `endpoints.MapRazorPages()`, como se muestra en el siguiente código en el método `Startup.Configure` del servicio:</span><span class="sxs-lookup"><span data-stu-id="30317-133">Once ASP.NET Core Identity is configured, you enable it by adding the `app.UseAuthentication()` and `endpoints.MapRazorPages()` as shown in the following code in the service's `Startup.Configure` method:</span></span>

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
> <span data-ttu-id="30317-134">Las líneas del código anterior **DEBEN ESTAR EN EL ORDEN MOSTRADO** para que Identity funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="30317-134">The lines in the preceding code **MUST BE IN THE ORDER SHOWN** for Identity to work correctly.</span></span>

<span data-ttu-id="30317-135">El uso de ASP.NET Core Identity permite varios escenarios:</span><span class="sxs-lookup"><span data-stu-id="30317-135">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="30317-136">Crear información de usuario con el tipo UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="30317-136">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="30317-137">Autenticar a los usuarios con el tipo SignInManager.</span><span class="sxs-lookup"><span data-stu-id="30317-137">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="30317-138">Puede usar `signInManager.SignInAsync` para iniciar sesión directamente, o bien `signInManager.PasswordSignInAsync` para confirmar que la contraseña del usuario es correcta y, después, iniciar su sesión.</span><span class="sxs-lookup"><span data-stu-id="30317-138">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user's password is correct and then sign them in.</span></span>

- <span data-ttu-id="30317-139">Identificar a un usuario en función de la información almacenada en una cookie (que se lee mediante el software intermedio de ASP.NET Core Identity), de modo que las solicitudes posteriores desde un explorador incluyan la identidad y las notificaciones del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="30317-139">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user's identity and claims.</span></span>

<span data-ttu-id="30317-140">ASP.NET Core Identity también es compatible con la [autenticación en dos fases](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="30317-140">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="30317-141">ASP.NET Core Identity es una solución recomendada para los escenarios de autenticación que usan un almacén de datos de usuario local y que conservan la identidad entre las solicitudes mediante el uso de cookies (como es habitual en las aplicaciones web MVC).</span><span class="sxs-lookup"><span data-stu-id="30317-141">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="30317-142">Autenticación con proveedores externos</span><span class="sxs-lookup"><span data-stu-id="30317-142">Authenticate with external providers</span></span>

<span data-ttu-id="30317-143">ASP.NET Core también admite el uso de [proveedores de autenticación externos](/aspnet/core/security/authentication/social/) para permitir que los usuarios inicien sesión a través de flujos [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="30317-143">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="30317-144">Esto significa que los usuarios pueden iniciar sesión mediante los procesos de autenticación existentes de proveedores como Microsoft, Google, Facebook o Twitter, y asociar esas identidades con una identidad de ASP.NET Core en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30317-144">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="30317-145">Para usar autenticación externa, además de incluir el middleware de autenticación, como se mencionó antes, con el método `app.UseAuthentication()`, también tiene que registrar el proveedor externo en `Startup`, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="30317-145">To use external authentication, besides including the authentication middleware as mentioned before, using the `app.UseAuthentication()` method, you also have to register the external provider in `Startup` as shown in the following example:</span></span>

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

<span data-ttu-id="30317-146">En la tabla siguiente se muestran proveedores de autenticación externos populares y sus paquetes NuGet asociados:</span><span class="sxs-lookup"><span data-stu-id="30317-146">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="30317-147">**Proveedor**</span><span class="sxs-lookup"><span data-stu-id="30317-147">**Provider**</span></span>  | <span data-ttu-id="30317-148">**Paquete**</span><span class="sxs-lookup"><span data-stu-id="30317-148">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="30317-149">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="30317-149">**Microsoft**</span></span> | <span data-ttu-id="30317-150">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="30317-150">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="30317-151">**Google**</span><span class="sxs-lookup"><span data-stu-id="30317-151">**Google**</span></span>    | <span data-ttu-id="30317-152">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="30317-152">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="30317-153">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="30317-153">**Facebook**</span></span>  | <span data-ttu-id="30317-154">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="30317-154">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="30317-155">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="30317-155">**Twitter**</span></span>   | <span data-ttu-id="30317-156">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="30317-156">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="30317-157">En todos los casos, debe completar un procedimiento de registro de aplicaciones que sea dependiente del proveedor y que normalmente supone:</span><span class="sxs-lookup"><span data-stu-id="30317-157">In all cases, you must complete an application registration procedure that is vendor dependent and that usually involves:</span></span>

1. <span data-ttu-id="30317-158">Obtener un identificador de aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="30317-158">Getting a Client Application ID.</span></span>
2. <span data-ttu-id="30317-159">Obtener un secreto de aplicación cliente.</span><span class="sxs-lookup"><span data-stu-id="30317-159">Getting a Client Application Secret.</span></span>
3. <span data-ttu-id="30317-160">Configurar una dirección URL de redireccionamiento administrada por el middleware de autorización y el proveedor registrado.</span><span class="sxs-lookup"><span data-stu-id="30317-160">Configuring an redirection URL, that's handled by the authorization middleware and the registered provider</span></span>
4. <span data-ttu-id="30317-161">Opcionalmente, configurar una dirección URL de cierre de sesión para administrar correctamente el cierre de sesión en un escenario de inicio de sesión único (SSO).</span><span class="sxs-lookup"><span data-stu-id="30317-161">Optionally, configuring a sign-out URL to properly handle sign out in a Single Sign On (SSO) scenario.</span></span>

<span data-ttu-id="30317-162">Para más información sobre la configuración de la aplicación para un proveedor externo, consulte la [autenticación de proveedores externos en la documentación de ASP.NET Core](/aspnet/core/security/authentication/social/)).</span><span class="sxs-lookup"><span data-stu-id="30317-162">For details on configuring your app for an external provider, see the [External provider authentication in the ASP.NET Core documentation](/aspnet/core/security/authentication/social/)).</span></span>

>[!TIP]
><span data-ttu-id="30317-163">El middleware de autorización y los servicios mencionados anteriormente administran todos los detalles.</span><span class="sxs-lookup"><span data-stu-id="30317-163">All details are handled by the authorization middleware and services previously mentioned.</span></span> <span data-ttu-id="30317-164">Por lo tanto, solo tiene que elegir la opción de autenticación **Cuenta de usuario individual** al crear el proyecto de aplicación web de ASP.NET Code en Visual Studio, como se muestra en la figura 9-3, además de registrar los proveedores de autenticación mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="30317-164">So, you just have to choose the **Individual User Account** authentication option when you create the ASP.NET Code web application project in Visual Studio, as shown in Figure 9-3, besides registering the authentication providers previously mentioned.</span></span>

![Captura de pantalla del cuadro de diálogo Nueva aplicación web ASP.NET Core.](./media/index/select-individual-user-account-authentication-option.png)

<span data-ttu-id="30317-166">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="30317-166">**Figure 9-3**.</span></span> <span data-ttu-id="30317-167">Selección de la opción Cuentas de usuario individuales para usar la autenticación externa al crear un proyecto de aplicación web en Visual Studio 2019.</span><span class="sxs-lookup"><span data-stu-id="30317-167">Selecting the Individual User Accounts option, for using external authentication, when creating a web application project in Visual Studio 2019.</span></span>

<span data-ttu-id="30317-168">Además de los proveedores de autenticación externa mencionados anteriormente, hay disponibles paquetes de terceros que proporcionan software intermedio para el uso de muchos otros proveedores de autenticación externos.</span><span class="sxs-lookup"><span data-stu-id="30317-168">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="30317-169">Para ver una lista, consulte el repositorio [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="30317-169">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repository on GitHub.</span></span>

<span data-ttu-id="30317-170">También puede crear middleware de autenticación externo propio para resolver alguna necesidad especial.</span><span class="sxs-lookup"><span data-stu-id="30317-170">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="30317-171">Autenticación con tokens de portador</span><span class="sxs-lookup"><span data-stu-id="30317-171">Authenticate with bearer tokens</span></span>

<span data-ttu-id="30317-172">La autenticación con ASP.NET Core Identity (o con Identity y proveedores de autenticación externos) funciona bien en muchos escenarios de aplicación web en los que es adecuado almacenar información de usuario en una cookie.</span><span class="sxs-lookup"><span data-stu-id="30317-172">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="30317-173">En cambio, en otros escenarios las cookies no son una manera natural de conservar y transmitir datos.</span><span class="sxs-lookup"><span data-stu-id="30317-173">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="30317-174">Por ejemplo, en una Web API de ASP.NET Core que expone puntos de conexión RESTful a los que podrían tener acceso aplicaciones de una sola página (SPA), clientes nativos o incluso otras Web API, normalmente le interesa usar la autenticación mediante token de portador.</span><span class="sxs-lookup"><span data-stu-id="30317-174">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="30317-175">Estos tipos de aplicaciones no funcionan con cookies, pero pueden recuperar fácilmente un token de portador e incluirlo en el encabezado de autorización de las solicitudes posteriores.</span><span class="sxs-lookup"><span data-stu-id="30317-175">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="30317-176">Con objeto de habilitar la autenticación mediante token, ASP.NET Core admite varias opciones para el uso de [OAuth 2.0](https://oauth.net/2/) y [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="30317-176">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="30317-177">Autenticación con un proveedor de identidad OpenID Connect u OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="30317-177">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="30317-178">Si la información de usuario se almacena en Azure Active Directory u otra solución de identidad compatible con OpenID Connect u OAuth 2.0, puede usar el paquete **Microsoft.AspNetCore.Authentication.OpenIdConnect** para autenticarse con el flujo de trabajo de OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="30317-178">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="30317-179">Por ejemplo, para autenticarse en el microservicio Identity.Api de eShopOnContainers, una aplicación web ASP.NET Core puede usar el middleware de ese paquete como se muestra en el siguiente ejemplo simplificado de `Startup.cs`:</span><span class="sxs-lookup"><span data-stu-id="30317-179">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

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

<span data-ttu-id="30317-180">Tenga en cuenta que, cuando se usa este flujo de trabajo, el software intermedio de ASP.NET Core Identity no es necesario, porque el servicio de identidad controla el almacenamiento y la autenticación de la información del usuario.</span><span class="sxs-lookup"><span data-stu-id="30317-180">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="30317-181">Emisión de tokens de seguridad desde un servicio de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="30317-181">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="30317-182">Si prefiere emitir tokens de seguridad para los usuarios locales de ASP.NET Core Identity en lugar de usar un proveedor de identidades externo, puede aprovechar algunas buenas bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="30317-182">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="30317-183">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) y [OpenIddict](https://github.com/openiddict/openiddict-core) son proveedores de OpenID Connect que se integran fácilmente con ASP.NET Core Identity y le permiten emitir tokens de seguridad desde un servicio de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="30317-183">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="30317-184">En la [documentación de IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) encontrará instrucciones detalladas para usar la biblioteca,</span><span class="sxs-lookup"><span data-stu-id="30317-184">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="30317-185">pero los pasos básicos para emitir tokens con IdentityServer4 son los que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="30317-185">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="30317-186">Llame a app.UseIdentityServer en el método Startup.Configure para agregar IdentityServer4 a la canalización de procesamiento de solicitudes HTTP de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="30317-186">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application's HTTP request processing pipeline.</span></span> <span data-ttu-id="30317-187">Esto permite a la biblioteca atender las solicitudes a los puntos de conexión de OpenID Connect y OAuth2 como /connect/token.</span><span class="sxs-lookup"><span data-stu-id="30317-187">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="30317-188">Configure IdentityServer4 en Startup.ConfigureServices mediante una llamada a services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="30317-188">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="30317-189">Para configurar el servidor de identidades, establezca los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="30317-189">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="30317-190">Las [credenciales](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) que se van a usar para la firma.</span><span class="sxs-lookup"><span data-stu-id="30317-190">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="30317-191">Los [recursos de identidad y de API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) a los que los usuarios podrían solicitar acceso:</span><span class="sxs-lookup"><span data-stu-id="30317-191">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="30317-192">Los recursos de API representan funciones o datos protegidos a los que los usuarios pueden tener acceso con un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="30317-192">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="30317-193">Un ejemplo de un recurso de API sería una API web (o un conjunto de API) que requiere autorización.</span><span class="sxs-lookup"><span data-stu-id="30317-193">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="30317-194">Los recursos de identidad representan información (notificaciones) que se entregan a un cliente para identificar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="30317-194">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="30317-195">Las notificaciones pueden incluir el nombre de usuario, la dirección de correo electrónico, etc.</span><span class="sxs-lookup"><span data-stu-id="30317-195">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="30317-196">Los [clientes](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) que se conectarán para solicitar tokens.</span><span class="sxs-lookup"><span data-stu-id="30317-196">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="30317-197">El mecanismo de almacenamiento de la información de usuario, como [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) u otra alternativa.</span><span class="sxs-lookup"><span data-stu-id="30317-197">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="30317-198">Al especificar los clientes y los recursos que se van a usar en IdentityServer4, puede pasar una colección <xref:System.Collections.Generic.IEnumerable%601> del tipo adecuado a los métodos que toman almacenes de recursos o clientes en memoria.</span><span class="sxs-lookup"><span data-stu-id="30317-198">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="30317-199">En escenarios más complejos, puede proporcionar tipos de proveedor de recursos o cliente mediante la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="30317-199">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="30317-200">En el ejemplo siguiente se muestra el aspecto que podría tener una configuración para que IdentityServer4 use clientes y recursos en memoria proporcionados por un tipo IClientStore personalizado:</span><span class="sxs-lookup"><span data-stu-id="30317-200">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

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

### <a name="consume-security-tokens"></a><span data-ttu-id="30317-201">Consumo de tokens de seguridad</span><span class="sxs-lookup"><span data-stu-id="30317-201">Consume security tokens</span></span>

<span data-ttu-id="30317-202">La autenticación con un punto de conexión de OpenID Connect o mediante la emisión de tokens de seguridad propios se aplica a diversos escenarios.</span><span class="sxs-lookup"><span data-stu-id="30317-202">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="30317-203">Pero ¿qué sucede si un servicio solo necesita limitar el acceso a los usuarios que tienen tokens de seguridad válidos proporcionados por otro servicio?</span><span class="sxs-lookup"><span data-stu-id="30317-203">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="30317-204">Para este escenario, el middleware de autenticación que controla los tokens JWT está disponible en el paquete **Microsoft.AspNetCore.Authentication.JwtBearer**.</span><span class="sxs-lookup"><span data-stu-id="30317-204">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="30317-205">JWT es el acrónimo de "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" y es un formato común de token de seguridad (definido en RFC 7519) para la comunicación de notificaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="30317-205">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="30317-206">Un ejemplo simplificado de cómo usar el middleware para consumir esos tokens podría ser similar a este fragmento de código, tomado del microservicio Ordering.Api de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="30317-206">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

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

<span data-ttu-id="30317-207">Los parámetros de este uso son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="30317-207">The parameters in this usage are:</span></span>

- <span data-ttu-id="30317-208">`Audience` representa el receptor del token entrante o el recurso al que el token concede acceso.</span><span class="sxs-lookup"><span data-stu-id="30317-208">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="30317-209">Si el valor especificado en este parámetro no coincide con el parámetro del token, se rechazará el token.</span><span class="sxs-lookup"><span data-stu-id="30317-209">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="30317-210">`Authority` es la dirección del servidor de autenticación de emisión de tokens.</span><span class="sxs-lookup"><span data-stu-id="30317-210">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="30317-211">El software intermedio de autenticación del portador de JWT usa este URI para obtener la clave pública que puede usarse para validar la firma del token.</span><span class="sxs-lookup"><span data-stu-id="30317-211">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="30317-212">El middleware también confirma que el parámetro `iss` del token coincide con este URI.</span><span class="sxs-lookup"><span data-stu-id="30317-212">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="30317-213">Otro parámetro, `RequireHttpsMetadata`, resulta útil para la realización de pruebas; establézcalo en false para poder realizarlas en los entornos en los que no tiene certificados.</span><span class="sxs-lookup"><span data-stu-id="30317-213">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="30317-214">En implementaciones reales, los tokens de portador de JWT siempre se deben pasar a través de HTTPS exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="30317-214">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="30317-215">Con este software intermedio, los tokens JWT se extraen automáticamente de los encabezados de autorización.</span><span class="sxs-lookup"><span data-stu-id="30317-215">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="30317-216">Después, se deserializan, se validan (mediante los valores de los parámetros `Audience` y `Authority`) y se almacenan como información del usuario a la que se hará referencia más adelante a través de acciones de MVC o filtros de autorización.</span><span class="sxs-lookup"><span data-stu-id="30317-216">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="30317-217">El software intermedio de autenticación del portador de JWT también puede admitir escenarios más avanzados, como el uso de un certificado local para validar un token si la entidad no está disponible.</span><span class="sxs-lookup"><span data-stu-id="30317-217">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="30317-218">En este escenario, puede especificar un objeto `TokenValidationParameters` en el objeto `JwtBearerOptions`.</span><span class="sxs-lookup"><span data-stu-id="30317-218">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30317-219">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="30317-219">Additional resources</span></span>

- <span data-ttu-id="30317-220">**Uso compartido de cookies entre aplicaciones** </span><span class="sxs-lookup"><span data-stu-id="30317-220">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="30317-221">**Introducción a Identity** </span><span class="sxs-lookup"><span data-stu-id="30317-221">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="30317-222">**Rick Anderson. Autenticación en dos fases con SMS** </span><span class="sxs-lookup"><span data-stu-id="30317-222">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="30317-223">**Habilitación de la autenticación con Facebook, Google y otros proveedores externos** </span><span class="sxs-lookup"><span data-stu-id="30317-223">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="30317-224">**Michell Anicas. Una introducción a OAuth 2** </span><span class="sxs-lookup"><span data-stu-id="30317-224">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="30317-225">**repositorio de GitHub para proveedores de OAuth de ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="30317-225">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="30317-226">**IdentityServer4. Documentación oficial** </span><span class="sxs-lookup"><span data-stu-id="30317-226">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="30317-227">[Anterior](../implement-resilient-applications/monitor-app-health.md)
>[Siguiente](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="30317-227">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
