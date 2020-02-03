---
title: Proteger microservicios y aplicaciones web de .NET
description: 'Seguridad en microservicios y aplicaciones web .NET: familiarícese con las opciones de autenticación en las aplicaciones web ASP.NET Core.'
author: mjrousos
ms.author: wiwagn
ms.date: 10/19/2018
ms.openlocfilehash: 6d318f4efc6958610947f164d6ca63634f3d7db5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777212"
---
# <a name="make-secure-net-microservices-and-web-applications"></a><span data-ttu-id="78b3a-103">Protección de microservicios y aplicaciones web .NET</span><span class="sxs-lookup"><span data-stu-id="78b3a-103">Make secure .NET Microservices and Web Applications</span></span>

<span data-ttu-id="78b3a-104">Hay tantos aspectos sobre la seguridad en los microservicios y las aplicaciones web que fácilmente se podrían dedicar al tema varios libros como este por lo que, en esta sección, nos centraremos en la autenticación, la autorización y los secretos de aplicación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-104">There are so many aspects about security in microservices and web applications that the topic could easy take several books like this one so, in this section, we'll focus on authentication, authorization, and application secrets.</span></span>

## <a name="implement-authentication-in-net-microservices-and-web-applications"></a><span data-ttu-id="78b3a-105">Implementación de la autenticación en microservicios y aplicaciones web .NET</span><span class="sxs-lookup"><span data-stu-id="78b3a-105">Implement authentication in .NET microservices and web applications</span></span>

<span data-ttu-id="78b3a-106">A menudo es necesario que los recursos y las API publicados por un servicio se limiten a determinados usuarios o clientes de confianza.</span><span class="sxs-lookup"><span data-stu-id="78b3a-106">It's often necessary for resources and APIs published by a service to be limited to certain trusted users or clients.</span></span> <span data-ttu-id="78b3a-107">El primer paso para tomar este tipo de decisiones de confianza en el nivel de API es la autenticación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-107">The first step to making these sorts of API-level trust decisions is authentication.</span></span> <span data-ttu-id="78b3a-108">La autenticación es el proceso de comprobar de forma fiable la identidad de un usuario.</span><span class="sxs-lookup"><span data-stu-id="78b3a-108">Authentication is the process of reliably verify a user’s identity.</span></span>

<span data-ttu-id="78b3a-109">En escenarios de microservicios, la autenticación suele controlarse de manera centralizada.</span><span class="sxs-lookup"><span data-stu-id="78b3a-109">In microservice scenarios, authentication is typically handled centrally.</span></span> <span data-ttu-id="78b3a-110">Si usa una puerta de enlace de API, esa puerta es un buen lugar para realizar la autenticación, como se muestra en la figura 9-1.</span><span class="sxs-lookup"><span data-stu-id="78b3a-110">If you're using an API Gateway, the gateway is a good place to authenticate, as shown in Figure 9-1.</span></span> <span data-ttu-id="78b3a-111">Si emplea este método, asegúrese de que no es posible ponerse en contacto directamente con los microservicios individuales (sin la puerta de enlace de API), a menos que haya aplicado seguridad adicional para autenticar si los mensajes provienen de la puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="78b3a-111">If you use this approach, make sure that the individual microservices cannot be reached directly (without the API Gateway) unless additional security is in place to authenticate messages whether they come from the gateway or not.</span></span>

![Diagrama en el que se muestra cómo interactúa la aplicación móvil cliente con el back-end.](./media/index/api-gateway-centralized-authentication.png)

<span data-ttu-id="78b3a-113">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="78b3a-113">**Figure 9-1**.</span></span> <span data-ttu-id="78b3a-114">Autenticación centralizada con una puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="78b3a-114">Centralized authentication with an API Gateway</span></span>

<span data-ttu-id="78b3a-115">Cuando la puerta de enlace de API centraliza la autenticación, agrega información de usuario al reenviar las solicitudes a los microservicios.</span><span class="sxs-lookup"><span data-stu-id="78b3a-115">When the API Gateway centralizes authentication, it adds user information when forwarding requests to the microservices.</span></span> <span data-ttu-id="78b3a-116">Si se puede tener acceso directamente a los servicios, entonces para la autenticación de los usuarios se puede usar un servicio de autenticación como Azure Active Directory o un microservicio de autenticación dedicado que actúe como un servicio de token de seguridad (STS).</span><span class="sxs-lookup"><span data-stu-id="78b3a-116">If services can be accessed directly, an authentication service like Azure Active Directory or a dedicated authentication microservice acting as a security token service (STS) can be used to authenticate users.</span></span> <span data-ttu-id="78b3a-117">Las decisiones de confianza se comparten entre los servicios con tokens de seguridad o cookies.</span><span class="sxs-lookup"><span data-stu-id="78b3a-117">Trust decisions are shared between services with security tokens or cookies.</span></span> <span data-ttu-id="78b3a-118">(Si es necesario, estos tokens se pueden compartir entre aplicaciones de ASP.NET Core mediante el [uso compartido de cookies](/aspnet/core/security/cookie-sharing)). Este patrón se ilustra en la figura 9-2.</span><span class="sxs-lookup"><span data-stu-id="78b3a-118">(These tokens can be shared between ASP.NET Core applications, if needed, by implementing [cookie sharing](/aspnet/core/security/cookie-sharing).) This pattern is illustrated in Figure 9-2.</span></span>

![Diagrama en el que se muestra la autenticación a través de microservicios de back-end.](./media/index/identity-microservice-authentication.png)

<span data-ttu-id="78b3a-120">**Figura 9-2**.</span><span class="sxs-lookup"><span data-stu-id="78b3a-120">**Figure 9-2**.</span></span> <span data-ttu-id="78b3a-121">Autenticación realizada por un microservicio de identidad; la confianza se comparte mediante un token de autorización.</span><span class="sxs-lookup"><span data-stu-id="78b3a-121">Authentication by identity microservice; trust is shared using an authorization token</span></span>

<span data-ttu-id="78b3a-122">Cuando se accede directamente a los microservicios, la confianza (que incluye la autenticación y la autorización) se controla mediante un token de seguridad emitido por un microservicio dedicado, que se comparte entre los microservicios.</span><span class="sxs-lookup"><span data-stu-id="78b3a-122">When microservices are accessed directly, trust, that includes authentication and authorization, is handled by a security token issued by a dedicated microservice, shared between microservices.</span></span>

### <a name="authenticate-with-aspnet-core-identity"></a><span data-ttu-id="78b3a-123">Autenticación con ASP.NET Core Identity</span><span class="sxs-lookup"><span data-stu-id="78b3a-123">Authenticate with ASP.NET Core Identity</span></span>

<span data-ttu-id="78b3a-124">El principal mecanismo de ASP.NET Core para identificar a los usuarios de una aplicación es el sistema de pertenencia [ASP.NET Core Identity](/aspnet/core/security/authentication/identity).</span><span class="sxs-lookup"><span data-stu-id="78b3a-124">The primary mechanism in ASP.NET Core for identifying an application’s users is the [ASP.NET Core Identity](/aspnet/core/security/authentication/identity) membership system.</span></span> <span data-ttu-id="78b3a-125">ASP.NET Core Identity almacena la información del usuario (incluida la información de inicio de sesión, los roles y las notificaciones) en un almacén de datos configurado por el desarrollador.</span><span class="sxs-lookup"><span data-stu-id="78b3a-125">ASP.NET Core Identity stores user information (including sign-in information, roles, and claims) in a data store configured by the developer.</span></span> <span data-ttu-id="78b3a-126">Normalmente, el almacén de datos de ASP.NET Core Identity es un almacén de Entity Framework incluido en el paquete `Microsoft.AspNetCore.Identity.EntityFrameworkCore`.</span><span class="sxs-lookup"><span data-stu-id="78b3a-126">Typically, the ASP.NET Core Identity data store is an Entity Framework store provided in the `Microsoft.AspNetCore.Identity.EntityFrameworkCore` package.</span></span> <span data-ttu-id="78b3a-127">Pero se pueden usar almacenes personalizados u otros paquetes de terceros para almacenar información de identidad en Table Storage de Azure, Cosmos DB u otras ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="78b3a-127">However, custom stores or other third-party packages can be used to store identity information in Azure Table Storage, CosmosDB, or other locations.</span></span>

<span data-ttu-id="78b3a-128">El código siguiente procede de la plantilla de proyecto de aplicación web de ASP.NET Core con la autenticación de cuentas de usuario individuales seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78b3a-128">The following code is taken from the ASP.NET Core Web Application project template with individual user account authentication selected.</span></span> <span data-ttu-id="78b3a-129">Muestra cómo configurar ASP.NET Core Identity mediante EntityFramework.Core en el método Startup.ConfigureServices.</span><span class="sxs-lookup"><span data-stu-id="78b3a-129">It shows how to configure ASP.NET Core Identity using EntityFramework.Core in the Startup.ConfigureServices method.</span></span>

```csharp
services.AddDbContext<ApplicationDbContext>(options =>
    options.UseSqlServer(Configuration.GetConnectionString("DefaultConnection")));
    services.AddIdentity<ApplicationUser, IdentityRole>()
        .AddEntityFrameworkStores<ApplicationDbContext>()
        .AddDefaultTokenProviders();
```

<span data-ttu-id="78b3a-130">Una vez configurado ASP.NET Core Identity, para habilitarlo llame a app.UseIdentity en el método `Startup.Configure` del servicio.</span><span class="sxs-lookup"><span data-stu-id="78b3a-130">Once ASP.NET Core Identity is configured, you enable it by calling app.UseIdentity in the service’s `Startup.Configure` method.</span></span>

<span data-ttu-id="78b3a-131">El uso de ASP.NET Core Identity permite varios escenarios:</span><span class="sxs-lookup"><span data-stu-id="78b3a-131">Using ASP.NET Core Identity enables several scenarios:</span></span>

- <span data-ttu-id="78b3a-132">Crear información de usuario con el tipo UserManager (userManager.CreateAsync).</span><span class="sxs-lookup"><span data-stu-id="78b3a-132">Create new user information using the UserManager type (userManager.CreateAsync).</span></span>

- <span data-ttu-id="78b3a-133">Autenticar a los usuarios con el tipo SignInManager.</span><span class="sxs-lookup"><span data-stu-id="78b3a-133">Authenticate users using the SignInManager type.</span></span> <span data-ttu-id="78b3a-134">Puede usar `signInManager.SignInAsync` para iniciar sesión directamente, o bien `signInManager.PasswordSignInAsync` para confirmar que la contraseña del usuario es correcta y, después, iniciar su sesión.</span><span class="sxs-lookup"><span data-stu-id="78b3a-134">You can use `signInManager.SignInAsync` to sign in directly, or `signInManager.PasswordSignInAsync` to confirm the user’s password is correct and then sign them in.</span></span>

- <span data-ttu-id="78b3a-135">Identificar a un usuario en función de la información almacenada en una cookie (que se lee mediante el software intermedio de ASP.NET Core Identity), de modo que las solicitudes posteriores desde un explorador incluyan la identidad y las notificaciones del usuario que ha iniciado sesión.</span><span class="sxs-lookup"><span data-stu-id="78b3a-135">Identify a user based on information stored in a cookie (which is read by ASP.NET Core Identity middleware) so that subsequent requests from a browser will include a signed-in user’s identity and claims.</span></span>

<span data-ttu-id="78b3a-136">ASP.NET Core Identity también es compatible con la [autenticación en dos fases](/aspnet/core/security/authentication/2fa).</span><span class="sxs-lookup"><span data-stu-id="78b3a-136">ASP.NET Core Identity also supports [two-factor authentication](/aspnet/core/security/authentication/2fa).</span></span>

<span data-ttu-id="78b3a-137">ASP.NET Core Identity es una solución recomendada para los escenarios de autenticación que usan un almacén de datos de usuario local y que conservan la identidad entre las solicitudes mediante el uso de cookies (como es habitual en las aplicaciones web MVC).</span><span class="sxs-lookup"><span data-stu-id="78b3a-137">For authentication scenarios that make use of a local user data store and that persist identity between requests using cookies (as is typical for MVC web applications), ASP.NET Core Identity is a recommended solution.</span></span>

### <a name="authenticate-with-external-providers"></a><span data-ttu-id="78b3a-138">Autenticación con proveedores externos</span><span class="sxs-lookup"><span data-stu-id="78b3a-138">Authenticate with external providers</span></span>

<span data-ttu-id="78b3a-139">ASP.NET Core también admite el uso de [proveedores de autenticación externos](/aspnet/core/security/authentication/social/) para permitir que los usuarios inicien sesión a través de flujos [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2).</span><span class="sxs-lookup"><span data-stu-id="78b3a-139">ASP.NET Core also supports using [external authentication providers](/aspnet/core/security/authentication/social/) to let users sign in via [OAuth 2.0](https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2) flows.</span></span> <span data-ttu-id="78b3a-140">Esto significa que los usuarios pueden iniciar sesión mediante los procesos de autenticación existentes de proveedores como Microsoft, Google, Facebook o Twitter, y asociar esas identidades con una identidad de ASP.NET Core en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-140">This means that users can sign in using existing authentication processes from providers like Microsoft, Google, Facebook, or Twitter and associate those identities with an ASP.NET Core identity in your application.</span></span>

<span data-ttu-id="78b3a-141">Para usar la autenticación externa, incluya el software intermedio de autenticación adecuado en la canalización de procesamiento de solicitudes HTTP de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-141">To use external authentication, you include the appropriate authentication middleware in your application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="78b3a-142">Este software intermedio es responsable de controlar las solicitudes para devolver las rutas URI desde el proveedor de autenticación, capturar información de identidad y hacer que esté disponible mediante el método SignInManager.GetExternalLoginInfo.</span><span class="sxs-lookup"><span data-stu-id="78b3a-142">This middleware is responsible for handling requests to return URI routes from the authentication provider, capturing identity information, and making it available via the SignInManager.GetExternalLoginInfo method.</span></span>

<span data-ttu-id="78b3a-143">En la tabla siguiente se muestran proveedores de autenticación externos populares y sus paquetes NuGet asociados:</span><span class="sxs-lookup"><span data-stu-id="78b3a-143">Popular external authentication providers and their associated NuGet packages are shown in the following table:</span></span>

| <span data-ttu-id="78b3a-144">**Proveedor**</span><span class="sxs-lookup"><span data-stu-id="78b3a-144">**Provider**</span></span>  | <span data-ttu-id="78b3a-145">**Paquete**</span><span class="sxs-lookup"><span data-stu-id="78b3a-145">**Package**</span></span>                                          |
| ------------- | ---------------------------------------------------- |
| <span data-ttu-id="78b3a-146">**Microsoft**</span><span class="sxs-lookup"><span data-stu-id="78b3a-146">**Microsoft**</span></span> | <span data-ttu-id="78b3a-147">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span><span class="sxs-lookup"><span data-stu-id="78b3a-147">**Microsoft.AspNetCore.Authentication.MicrosoftAccount**</span></span> |
| <span data-ttu-id="78b3a-148">**Google**</span><span class="sxs-lookup"><span data-stu-id="78b3a-148">**Google**</span></span>    | <span data-ttu-id="78b3a-149">**Microsoft.AspNetCore.Authentication.Google**</span><span class="sxs-lookup"><span data-stu-id="78b3a-149">**Microsoft.AspNetCore.Authentication.Google**</span></span>           |
| <span data-ttu-id="78b3a-150">**Facebook**</span><span class="sxs-lookup"><span data-stu-id="78b3a-150">**Facebook**</span></span>  | <span data-ttu-id="78b3a-151">**Microsoft.AspNetCore.Authentication.Facebook**</span><span class="sxs-lookup"><span data-stu-id="78b3a-151">**Microsoft.AspNetCore.Authentication.Facebook**</span></span>         |
| <span data-ttu-id="78b3a-152">**Twitter**</span><span class="sxs-lookup"><span data-stu-id="78b3a-152">**Twitter**</span></span>   | <span data-ttu-id="78b3a-153">**Microsoft.AspNetCore.Authentication.Twitter**</span><span class="sxs-lookup"><span data-stu-id="78b3a-153">**Microsoft.AspNetCore.Authentication.Twitter**</span></span>          |

<span data-ttu-id="78b3a-154">En todos los casos, el middleware se registra con una llamada a un método de registro similar a `app.Use{ExternalProvider}Authentication` en `Startup.Configure`.</span><span class="sxs-lookup"><span data-stu-id="78b3a-154">In all cases, the middleware is registered with a call to a registration method similar to `app.Use{ExternalProvider}Authentication` in `Startup.Configure`.</span></span> <span data-ttu-id="78b3a-155">Estos métodos de registro toman un objeto de opciones que contiene un identificador de aplicación e información secreta (una contraseña, por ejemplo), según requiera el proveedor.</span><span class="sxs-lookup"><span data-stu-id="78b3a-155">These registration methods take an options object that contains an application ID and secret information (a password, for instance), as needed by the provider.</span></span> <span data-ttu-id="78b3a-156">Los proveedores de autenticación externos requieren que la aplicación se registre (como se explica en la [documentación de ASP.NET Core](/aspnet/core/security/authentication/social/)) para que puedan informar al usuario sobre qué aplicación solicita acceso a su identidad.</span><span class="sxs-lookup"><span data-stu-id="78b3a-156">External authentication providers require the application to be registered (as explained in [ASP.NET Core documentation](/aspnet/core/security/authentication/social/)) so that they can inform the user what application is requesting access to their identity.</span></span>

<span data-ttu-id="78b3a-157">Una vez que se haya registrado el middleware en `Startup.Configure`, podrá pedirles a los usuarios que inicien sesión desde cualquier acción de controlador.</span><span class="sxs-lookup"><span data-stu-id="78b3a-157">Once the middleware is registered in `Startup.Configure`, you can prompt users to sign in from any controller action.</span></span> <span data-ttu-id="78b3a-158">Para ello, cree un objeto `AuthenticationProperties` que incluya el nombre del proveedor de autenticación y una dirección URL de redireccionamiento.</span><span class="sxs-lookup"><span data-stu-id="78b3a-158">To do this, you create an `AuthenticationProperties` object that includes the authentication provider’s name and a redirect URL.</span></span> <span data-ttu-id="78b3a-159">Después, devuelva una respuesta Challenge que pase el objeto `AuthenticationProperties`.</span><span class="sxs-lookup"><span data-stu-id="78b3a-159">You then return a Challenge response that passes the `AuthenticationProperties` object.</span></span> <span data-ttu-id="78b3a-160">El código siguiente muestra un ejemplo de esto.</span><span class="sxs-lookup"><span data-stu-id="78b3a-160">The following code shows an example of this.</span></span>

```csharp
var properties = _signInManager.ConfigureExternalAuthenticationProperties(provider,
    redirectUrl);
return Challenge(properties, provider);
```

<span data-ttu-id="78b3a-161">El parámetro redirectUrl incluye la dirección URL a la que el proveedor externo debe redirigir una vez que se ha autenticado el usuario.</span><span class="sxs-lookup"><span data-stu-id="78b3a-161">The redirectUrl parameter includes the URL that the external provider should redirect to once the user has authenticated.</span></span> <span data-ttu-id="78b3a-162">La dirección URL debe representar una acción que iniciará la sesión del usuario en función de información de identidad externa, como en el siguiente ejemplo simplificado:</span><span class="sxs-lookup"><span data-stu-id="78b3a-162">The URL should represent an action that will sign the user in based on external identity information, as in the following simplified example:</span></span>

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

<span data-ttu-id="78b3a-163">Si elige la opción de autenticación **Cuenta de usuario individual** al crear el proyecto de aplicación web ASP.NET Core en Visual Studio, todo el código necesario para iniciar sesión con un proveedor externo ya estará en el proyecto, como se muestra en la figura 9-3.</span><span class="sxs-lookup"><span data-stu-id="78b3a-163">If you choose the **Individual User Account** authentication option when you create the ASP.NET Core web application project in Visual Studio, all the code necessary to sign in with an external provider is already in the project, as shown in Figure 9-3.</span></span>

![Captura de pantalla del cuadro de diálogo Nueva aplicación web ASP.NET Core.](./media/index/select-external-authentication-option.png)

<span data-ttu-id="78b3a-165">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="78b3a-165">**Figure 9-3**.</span></span> <span data-ttu-id="78b3a-166">Proceso de selección de una opción para usar la autenticación externa al crear un proyecto de aplicación web.</span><span class="sxs-lookup"><span data-stu-id="78b3a-166">Selecting an option for using external authentication when creating a web application project</span></span>

<span data-ttu-id="78b3a-167">Además de los proveedores de autenticación externa mencionados anteriormente, hay disponibles paquetes de terceros que proporcionan software intermedio para el uso de muchos otros proveedores de autenticación externos.</span><span class="sxs-lookup"><span data-stu-id="78b3a-167">In addition to the external authentication providers listed previously, third-party packages are available that provide middleware for using many more external authentication providers.</span></span> <span data-ttu-id="78b3a-168">Para obtener una lista, vea el repositorio [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) en GitHub.</span><span class="sxs-lookup"><span data-stu-id="78b3a-168">For a list, see the [AspNet.Security.OAuth.Providers](https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src) repo on GitHub.</span></span>

<span data-ttu-id="78b3a-169">También puede crear middleware de autenticación externo propio para resolver alguna necesidad especial.</span><span class="sxs-lookup"><span data-stu-id="78b3a-169">You can also create your own external authentication middleware to solve some special need.</span></span>

### <a name="authenticate-with-bearer-tokens"></a><span data-ttu-id="78b3a-170">Autenticación con tokens de portador</span><span class="sxs-lookup"><span data-stu-id="78b3a-170">Authenticate with bearer tokens</span></span>

<span data-ttu-id="78b3a-171">La autenticación con ASP.NET Core Identity (o con Identity y proveedores de autenticación externos) funciona bien en muchos escenarios de aplicación web en los que es adecuado almacenar información de usuario en una cookie.</span><span class="sxs-lookup"><span data-stu-id="78b3a-171">Authenticating with ASP.NET Core Identity (or Identity plus external authentication providers) works well for many web application scenarios in which storing user information in a cookie is appropriate.</span></span> <span data-ttu-id="78b3a-172">En cambio, en otros escenarios las cookies no son una manera natural de conservar y transmitir datos.</span><span class="sxs-lookup"><span data-stu-id="78b3a-172">In other scenarios, though, cookies are not a natural means of persisting and transmitting data.</span></span>

<span data-ttu-id="78b3a-173">Por ejemplo, en una Web API de ASP.NET Core que expone puntos de conexión RESTful a los que podrían tener acceso aplicaciones de una sola página (SPA), clientes nativos o incluso otras Web API, normalmente le interesa usar la autenticación mediante token de portador.</span><span class="sxs-lookup"><span data-stu-id="78b3a-173">For example, in an ASP.NET Core Web API that exposes RESTful endpoints that might be accessed by Single Page Applications (SPAs), by native clients, or even by other Web APIs, you typically want to use bearer token authentication instead.</span></span> <span data-ttu-id="78b3a-174">Estos tipos de aplicaciones no funcionan con cookies, pero pueden recuperar fácilmente un token de portador e incluirlo en el encabezado de autorización de las solicitudes posteriores.</span><span class="sxs-lookup"><span data-stu-id="78b3a-174">These types of applications do not work with cookies, but can easily retrieve a bearer token and include it in the authorization header of subsequent requests.</span></span> <span data-ttu-id="78b3a-175">Con objeto de habilitar la autenticación mediante token, ASP.NET Core admite varias opciones para el uso de [OAuth 2.0](https://oauth.net/2/) y [OpenID Connect](https://openid.net/connect/).</span><span class="sxs-lookup"><span data-stu-id="78b3a-175">To enable token authentication, ASP.NET Core supports several options for using [OAuth 2.0](https://oauth.net/2/) and [OpenID Connect](https://openid.net/connect/).</span></span>

### <a name="authenticate-with-an-openid-connect-or-oauth-20-identity-provider"></a><span data-ttu-id="78b3a-176">Autenticación con un proveedor de identidad OpenID Connect u OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="78b3a-176">Authenticate with an OpenID Connect or OAuth 2.0 Identity provider</span></span>

<span data-ttu-id="78b3a-177">Si la información de usuario se almacena en Azure Active Directory u otra solución de identidad compatible con OpenID Connect u OAuth 2.0, puede usar el paquete **Microsoft.AspNetCore.Authentication.OpenIdConnect** para autenticarse con el flujo de trabajo de OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="78b3a-177">If user information is stored in Azure Active Directory or another identity solution that supports OpenID Connect or OAuth 2.0, you can use the **Microsoft.AspNetCore.Authentication.OpenIdConnect** package to authenticate using the OpenID Connect workflow.</span></span> <span data-ttu-id="78b3a-178">Por ejemplo, para autenticarse en el microservicio Identity.Api de eShopOnContainers, una aplicación web ASP.NET Core puede usar el middleware de ese paquete como se muestra en el siguiente ejemplo simplificado de `Startup.cs`:</span><span class="sxs-lookup"><span data-stu-id="78b3a-178">For example, to authenticate to the Identity.Api microservice in eShopOnContainers, an ASP.NET Core web application can use middleware from that package as shown in the following simplified example in `Startup.cs`:</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");
    var callBackUrl = Configuration.GetValue<string>("CallBackUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = OpenIdConnectDefaults.AuthenticationScheme;
    })
    .AddCookie()
    .AddOpenIdConnect(options =>
    {
        options.SignInScheme = CookieAuthenticationDefaults.AuthenticationScheme;
        options.Authority = identityUrl;
        options.SignedOutRedirectUri = callBackUrl;
        options.ClientSecret = "secret";
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

<span data-ttu-id="78b3a-179">Tenga en cuenta que, cuando se usa este flujo de trabajo, el software intermedio de ASP.NET Core Identity no es necesario, porque el servicio de identidad controla el almacenamiento y la autenticación de la información del usuario.</span><span class="sxs-lookup"><span data-stu-id="78b3a-179">Note that when you use this workflow, the ASP.NET Core Identity middleware is not needed, because all user information storage and authentication is handled by the Identity service.</span></span>

### <a name="issue-security-tokens-from-an-aspnet-core-service"></a><span data-ttu-id="78b3a-180">Emisión de tokens de seguridad desde un servicio de ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="78b3a-180">Issue security tokens from an ASP.NET Core service</span></span>

<span data-ttu-id="78b3a-181">Si prefiere emitir tokens de seguridad para los usuarios locales de ASP.NET Core Identity en lugar de usar un proveedor de identidades externo, puede aprovechar algunas buenas bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="78b3a-181">If you prefer to issue security tokens for local ASP.NET Core Identity users rather than using an external identity provider, you can take advantage of some good third-party libraries.</span></span>

<span data-ttu-id="78b3a-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) y [OpenIddict](https://github.com/openiddict/openiddict-core) son proveedores de OpenID Connect que se integran fácilmente con ASP.NET Core Identity y le permiten emitir tokens de seguridad desde un servicio de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="78b3a-182">[IdentityServer4](https://github.com/IdentityServer/IdentityServer4) and [OpenIddict](https://github.com/openiddict/openiddict-core) are OpenID Connect providers that integrate easily with ASP.NET Core Identity to let you issue security tokens from an ASP.NET Core service.</span></span> <span data-ttu-id="78b3a-183">En la [documentación de IdentityServer4](https://identityserver4.readthedocs.io/en/latest/) encontrará instrucciones detalladas para usar la biblioteca,</span><span class="sxs-lookup"><span data-stu-id="78b3a-183">The [IdentityServer4 documentation](https://identityserver4.readthedocs.io/en/latest/) has in-depth instructions for using the library.</span></span> <span data-ttu-id="78b3a-184">pero los pasos básicos para emitir tokens con IdentityServer4 son los que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-184">However, the basic steps to using IdentityServer4 to issue tokens are as follows.</span></span>

1. <span data-ttu-id="78b3a-185">Llame a app.UseIdentityServer en el método Startup.Configure para agregar IdentityServer4 a la canalización de procesamiento de solicitudes HTTP de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="78b3a-185">You call app.UseIdentityServer in the Startup.Configure method to add IdentityServer4 to the application’s HTTP request processing pipeline.</span></span> <span data-ttu-id="78b3a-186">Esto permite a la biblioteca atender las solicitudes a los puntos de conexión de OpenID Connect y OAuth2 como /connect/token.</span><span class="sxs-lookup"><span data-stu-id="78b3a-186">This lets the library serve requests to OpenID Connect and OAuth2 endpoints like /connect/token.</span></span>

2. <span data-ttu-id="78b3a-187">Configure IdentityServer4 en Startup.ConfigureServices mediante una llamada a services.AddIdentityServer.</span><span class="sxs-lookup"><span data-stu-id="78b3a-187">You configure IdentityServer4 in Startup.ConfigureServices by making a call to services.AddIdentityServer.</span></span>

3. <span data-ttu-id="78b3a-188">Para configurar el servidor de identidades, establezca los datos siguientes:</span><span class="sxs-lookup"><span data-stu-id="78b3a-188">You configure identity server by setting the following data:</span></span>

   - <span data-ttu-id="78b3a-189">Las [credenciales](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) que se van a usar para la firma.</span><span class="sxs-lookup"><span data-stu-id="78b3a-189">The [credentials](https://identityserver4.readthedocs.io/en/latest/topics/crypto.html) to use for signing.</span></span>

   - <span data-ttu-id="78b3a-190">Los [recursos de identidad y de API](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) a los que los usuarios podrían solicitar acceso:</span><span class="sxs-lookup"><span data-stu-id="78b3a-190">The [Identity and API resources](https://identityserver4.readthedocs.io/en/latest/topics/resources.html) that users might request access to:</span></span>

      - <span data-ttu-id="78b3a-191">Los recursos de API representan funciones o datos protegidos a los que los usuarios pueden tener acceso con un token de acceso.</span><span class="sxs-lookup"><span data-stu-id="78b3a-191">API resources represent protected data or functionality that a user can access with an access token.</span></span> <span data-ttu-id="78b3a-192">Un ejemplo de un recurso de API sería una API web (o un conjunto de API) que requiere autorización.</span><span class="sxs-lookup"><span data-stu-id="78b3a-192">An example of an API resource would be a web API (or set of APIs) that requires authorization.</span></span>

      - <span data-ttu-id="78b3a-193">Los recursos de identidad representan información (notificaciones) que se entregan a un cliente para identificar a un usuario.</span><span class="sxs-lookup"><span data-stu-id="78b3a-193">Identity resources represent information (claims) that are given to a client to identify a user.</span></span> <span data-ttu-id="78b3a-194">Las notificaciones pueden incluir el nombre de usuario, la dirección de correo electrónico, etc.</span><span class="sxs-lookup"><span data-stu-id="78b3a-194">The claims might include the user name, email address, and so on.</span></span>

   - <span data-ttu-id="78b3a-195">Los [clientes](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) que se conectarán para solicitar tokens.</span><span class="sxs-lookup"><span data-stu-id="78b3a-195">The [clients](https://identityserver4.readthedocs.io/en/latest/topics/clients.html) that will be connecting in order to request tokens.</span></span>

   - <span data-ttu-id="78b3a-196">El mecanismo de almacenamiento de la información de usuario, como [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) u otra alternativa.</span><span class="sxs-lookup"><span data-stu-id="78b3a-196">The storage mechanism for user information, such as [ASP.NET Core Identity](https://identityserver4.readthedocs.io/en/latest/quickstarts/0_overview.html) or an alternative.</span></span>

<span data-ttu-id="78b3a-197">Al especificar los clientes y los recursos que se van a usar en IdentityServer4, puede pasar una colección <xref:System.Collections.Generic.IEnumerable%601> del tipo adecuado a los métodos que toman almacenes de recursos o clientes en memoria.</span><span class="sxs-lookup"><span data-stu-id="78b3a-197">When you specify clients and resources for IdentityServer4 to use, you can pass an <xref:System.Collections.Generic.IEnumerable%601> collection of the appropriate type to methods that take in-memory client or resource stores.</span></span> <span data-ttu-id="78b3a-198">En escenarios más complejos, puede proporcionar tipos de proveedor de recursos o cliente mediante la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="78b3a-198">Or for more complex scenarios, you can provide client or resource provider types via Dependency Injection.</span></span>

<span data-ttu-id="78b3a-199">En el ejemplo siguiente se muestra el aspecto que podría tener una configuración para que IdentityServer4 use clientes y recursos en memoria proporcionados por un tipo IClientStore personalizado:</span><span class="sxs-lookup"><span data-stu-id="78b3a-199">A sample configuration for IdentityServer4 to use in-memory resources and clients provided by a custom IClientStore type might look like the following example:</span></span>

```csharp
// Add IdentityServer services
services.AddSingleton<IClientStore, CustomClientStore>();
services.AddIdentityServer()
    .AddSigningCredential("CN=sts")
    .AddInMemoryApiResources(MyApiResourceProvider.GetAllResources())
    .AddAspNetIdentity<ApplicationUser>();
```

### <a name="consume-security-tokens"></a><span data-ttu-id="78b3a-200">Consumo de tokens de seguridad</span><span class="sxs-lookup"><span data-stu-id="78b3a-200">Consume security tokens</span></span>

<span data-ttu-id="78b3a-201">La autenticación con un punto de conexión de OpenID Connect o mediante la emisión de tokens de seguridad propios se aplica a diversos escenarios.</span><span class="sxs-lookup"><span data-stu-id="78b3a-201">Authenticating against an OpenID Connect endpoint or issuing your own security tokens covers some scenarios.</span></span> <span data-ttu-id="78b3a-202">Pero ¿qué sucede si un servicio solo necesita limitar el acceso a los usuarios que tienen tokens de seguridad válidos proporcionados por otro servicio?</span><span class="sxs-lookup"><span data-stu-id="78b3a-202">But what about a service that simply needs to limit access to those users who have valid security tokens that were provided by a different service?</span></span>

<span data-ttu-id="78b3a-203">Para este escenario, el middleware de autenticación que controla los tokens JWT está disponible en el paquete **Microsoft.AspNetCore.Authentication.JwtBearer**.</span><span class="sxs-lookup"><span data-stu-id="78b3a-203">For that scenario, authentication middleware that handles JWT tokens is available in the **Microsoft.AspNetCore.Authentication.JwtBearer** package.</span></span> <span data-ttu-id="78b3a-204">JWT es el acrónimo de "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" y es un formato común de token de seguridad (definido en RFC 7519) para la comunicación de notificaciones de seguridad.</span><span class="sxs-lookup"><span data-stu-id="78b3a-204">JWT stands for "[JSON Web Token](https://tools.ietf.org/html/rfc7519)" and is a common security token format (defined by RFC 7519) for communicating security claims.</span></span> <span data-ttu-id="78b3a-205">Un ejemplo simplificado de cómo usar el middleware para consumir esos tokens podría ser similar a este fragmento de código, tomado del microservicio Ordering.Api de eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="78b3a-205">A simplified example of how to use middleware to consume such tokens might look like this code fragment, taken from the Ordering.Api microservice of eShopOnContainers.</span></span>

```csharp
// Startup.cs

public void Configure(IApplicationBuilder app, IHostingEnvironment env)
{
    //…
    // Configure the pipeline to use authentication
    app.UseAuthentication();
    //…
    app.UseMvc();
}

public void ConfigureServices(IServiceCollection services)
{
    var identityUrl = Configuration.GetValue<string>("IdentityUrl");

    // Add Authentication services

    services.AddAuthentication(options =>
    {
        options.DefaultAuthenticateScheme = JwtBearerDefaults.AuthenticationScheme;
        options.DefaultChallengeScheme = JwtBearerDefaults.AuthenticationScheme;

    }).AddJwtBearer(options =>
    {
        options.Authority = identityUrl;
        options.RequireHttpsMetadata = false;
        options.Audience = "orders";
    });
}
```

<span data-ttu-id="78b3a-206">Los parámetros de este uso son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="78b3a-206">The parameters in this usage are:</span></span>

- <span data-ttu-id="78b3a-207">`Audience` representa el receptor del token entrante o el recurso al que el token concede acceso.</span><span class="sxs-lookup"><span data-stu-id="78b3a-207">`Audience` represents the receiver of the incoming token or the resource that the token grants access to.</span></span> <span data-ttu-id="78b3a-208">Si el valor especificado en este parámetro no coincide con el parámetro del token, se rechazará el token.</span><span class="sxs-lookup"><span data-stu-id="78b3a-208">If the value specified in this parameter does not match the parameter in the token, the token will be rejected.</span></span>

- <span data-ttu-id="78b3a-209">`Authority` es la dirección del servidor de autenticación de emisión de tokens.</span><span class="sxs-lookup"><span data-stu-id="78b3a-209">`Authority` is the address of the token-issuing authentication server.</span></span> <span data-ttu-id="78b3a-210">El software intermedio de autenticación del portador de JWT usa este URI para obtener la clave pública que puede usarse para validar la firma del token.</span><span class="sxs-lookup"><span data-stu-id="78b3a-210">The JWT bearer authentication middleware uses this URI to get the public key that can be used to validate the token's signature.</span></span> <span data-ttu-id="78b3a-211">El middleware también confirma que el parámetro `iss` del token coincide con este URI.</span><span class="sxs-lookup"><span data-stu-id="78b3a-211">The middleware also confirms that the `iss` parameter in the token matches this URI.</span></span>

<span data-ttu-id="78b3a-212">Otro parámetro, `RequireHttpsMetadata`, resulta útil para la realización de pruebas; establézcalo en false para poder realizarlas en los entornos en los que no tiene certificados.</span><span class="sxs-lookup"><span data-stu-id="78b3a-212">Another parameter, `RequireHttpsMetadata`, is useful for testing purposes; you set this parameter to false so you can test in environments where you don't have certificates.</span></span> <span data-ttu-id="78b3a-213">En implementaciones reales, los tokens de portador de JWT siempre se deben pasar a través de HTTPS exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="78b3a-213">In real-world deployments, JWT bearer tokens should always be passed only over HTTPS.</span></span>

<span data-ttu-id="78b3a-214">Con este software intermedio, los tokens JWT se extraen automáticamente de los encabezados de autorización.</span><span class="sxs-lookup"><span data-stu-id="78b3a-214">With this middleware in place, JWT tokens are automatically extracted from authorization headers.</span></span> <span data-ttu-id="78b3a-215">Después, se deserializan, se validan (mediante los valores de los parámetros `Audience` y `Authority`) y se almacenan como información del usuario a la que se hará referencia más adelante a través de acciones de MVC o filtros de autorización.</span><span class="sxs-lookup"><span data-stu-id="78b3a-215">They are then deserialized, validated (using the values in the `Audience` and `Authority` parameters), and stored as user information to be referenced later by MVC actions or authorization filters.</span></span>

<span data-ttu-id="78b3a-216">El software intermedio de autenticación del portador de JWT también puede admitir escenarios más avanzados, como el uso de un certificado local para validar un token si la entidad no está disponible.</span><span class="sxs-lookup"><span data-stu-id="78b3a-216">The JWT bearer authentication middleware can also support more advanced scenarios, such as using a local certificate to validate a token if the authority is not available.</span></span> <span data-ttu-id="78b3a-217">En este escenario, puede especificar un objeto `TokenValidationParameters` en el objeto `JwtBearerOptions`.</span><span class="sxs-lookup"><span data-stu-id="78b3a-217">For this scenario, you can specify a `TokenValidationParameters` object in the `JwtBearerOptions` object.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="78b3a-218">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="78b3a-218">Additional resources</span></span>

- <span data-ttu-id="78b3a-219">**Uso compartido de cookies entre aplicaciones** </span><span class="sxs-lookup"><span data-stu-id="78b3a-219">**Sharing cookies between applications** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/cookie-sharing](/aspnet/core/security/cookie-sharing)

- <span data-ttu-id="78b3a-220">**Introducción a Identity** </span><span class="sxs-lookup"><span data-stu-id="78b3a-220">**Introduction to Identity** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/identity](/aspnet/core/security/authentication/identity)

- <span data-ttu-id="78b3a-221">**Rick Anderson. Autenticación en dos fases con SMS** </span><span class="sxs-lookup"><span data-stu-id="78b3a-221">**Rick Anderson. Two-factor authentication with SMS** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/2fa](/aspnet/core/security/authentication/2fa)

- <span data-ttu-id="78b3a-222">**Habilitación de la autenticación con Facebook, Google y otros proveedores externos** </span><span class="sxs-lookup"><span data-stu-id="78b3a-222">**Enabling authentication using Facebook, Google and other external providers** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/authentication/social/](/aspnet/core/security/authentication/social/)

- <span data-ttu-id="78b3a-223">**Michell Anicas. Una introducción a OAuth 2** </span><span class="sxs-lookup"><span data-stu-id="78b3a-223">**Michell Anicas. An Introduction to OAuth 2** </span></span>\
  <https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2>

- <span data-ttu-id="78b3a-224">**repositorio de GitHub para proveedores de OAuth de ASP.NET**</span><span class="sxs-lookup"><span data-stu-id="78b3a-224">**AspNet.Security.OAuth.Providers** (GitHub repo for ASP.NET OAuth providers) </span></span>\
  <https://github.com/aspnet-contrib/AspNet.Security.OAuth.Providers/tree/dev/src>

- <span data-ttu-id="78b3a-225">**IdentityServer4. Documentación oficial** </span><span class="sxs-lookup"><span data-stu-id="78b3a-225">**IdentityServer4. Official documentation** </span></span>\
  <https://identityserver4.readthedocs.io/en/latest/>

>[!div class="step-by-step"]
><span data-ttu-id="78b3a-226">[Anterior](../implement-resilient-applications/monitor-app-health.md)
>[Siguiente](authorization-net-microservices-web-applications.md)</span><span class="sxs-lookup"><span data-stu-id="78b3a-226">[Previous](../implement-resilient-applications/monitor-app-health.md)
[Next](authorization-net-microservices-web-applications.md)</span></span>
