---
title: IdentityServer para aplicaciones nativas en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | IdentityServer
ms.date: 05/13/2020
ms.openlocfilehash: bdf193aac348b54f2ebf5b537beef5d61a1d5a1e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91163835"
---
# <a name="identityserver-for-cloud-native-applications"></a><span data-ttu-id="7d346-103">IdentityServer para aplicaciones nativas para la nube</span><span class="sxs-lookup"><span data-stu-id="7d346-103">IdentityServer for cloud-native applications</span></span>

<span data-ttu-id="7d346-104">IdentityServer es un servidor de autenticación de código abierto que implementa los estándares OpenID Connect (OIDC) y OAuth 2,0 para ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="7d346-104">IdentityServer is an open-source authentication server that implements OpenID Connect (OIDC) and OAuth 2.0 standards for ASP.NET Core.</span></span> <span data-ttu-id="7d346-105">Está diseñado para proporcionar una manera común de autenticar las solicitudes en todas las aplicaciones, tanto si son puntos de conexión Web, nativos, móviles o de API.</span><span class="sxs-lookup"><span data-stu-id="7d346-105">It's designed to provide a common way to authenticate requests to all of your applications, whether they're web, native, mobile, or API endpoints.</span></span> <span data-ttu-id="7d346-106">IdentityServer se puede usar para implementar el inicio de sesión único (SSO) para varias aplicaciones y tipos de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7d346-106">IdentityServer can be used to implement Single Sign-On (SSO) for multiple applications and application types.</span></span> <span data-ttu-id="7d346-107">Se puede usar para autenticar a los usuarios reales mediante formularios de inicio de sesión e interfaces de usuario similares, así como la autenticación basada en servicio que normalmente implica la emisión, comprobación y renovación de tokens sin ninguna interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="7d346-107">It can be used to authenticate actual users via sign-in forms and similar user interfaces as well as service-based authentication that typically involves token issuance, verification, and renewal without any user interface.</span></span> <span data-ttu-id="7d346-108">IdentityServer está diseñado para ser una solución personalizable.</span><span class="sxs-lookup"><span data-stu-id="7d346-108">IdentityServer is designed to be a customizable solution.</span></span> <span data-ttu-id="7d346-109">Normalmente, cada instancia está personalizada para adaptarse a las necesidades de una organización o un conjunto de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7d346-109">Each instance is typically customized to suit an individual organization and/or set of applications' needs.</span></span>

## <a name="common-web-app-scenarios"></a><span data-ttu-id="7d346-110">Escenarios comunes de aplicaciones Web</span><span class="sxs-lookup"><span data-stu-id="7d346-110">Common web app scenarios</span></span>

<span data-ttu-id="7d346-111">Normalmente, las aplicaciones deben admitir algunos o todos los escenarios siguientes:</span><span class="sxs-lookup"><span data-stu-id="7d346-111">Typically, applications need to support some or all of the following scenarios:</span></span>

- <span data-ttu-id="7d346-112">Usuarios humanos que acceden a aplicaciones web con un explorador.</span><span class="sxs-lookup"><span data-stu-id="7d346-112">Human users accessing web applications with a browser.</span></span>
- <span data-ttu-id="7d346-113">Usuarios humanos que acceden a las API Web de back-end desde aplicaciones basadas en explorador.</span><span class="sxs-lookup"><span data-stu-id="7d346-113">Human users accessing back-end Web APIs from browser-based apps.</span></span>
- <span data-ttu-id="7d346-114">Usuarios humanos de clientes móviles o nativos que acceden a las API Web de back-end.</span><span class="sxs-lookup"><span data-stu-id="7d346-114">Human users on mobile/native clients accessing back-end Web APIs.</span></span>
- <span data-ttu-id="7d346-115">Otras aplicaciones que acceden a las API Web de back-end (sin una interfaz de usuario o usuario activa).</span><span class="sxs-lookup"><span data-stu-id="7d346-115">Other applications accessing back-end Web APIs (without an active user or user interface).</span></span>
- <span data-ttu-id="7d346-116">Cualquier aplicación puede necesitar interactuar con otras API Web, usando su propia identidad o delegando la identidad del usuario.</span><span class="sxs-lookup"><span data-stu-id="7d346-116">Any application may need to interact with other Web APIs, using its own identity or delegating to the user's identity.</span></span>

![Escenarios y tipos de aplicación](./media/application-types.png)

<span data-ttu-id="7d346-118">**Figura 8-1**.</span><span class="sxs-lookup"><span data-stu-id="7d346-118">**Figure 8-1**.</span></span> <span data-ttu-id="7d346-119">Tipos y escenarios de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7d346-119">Application types and scenarios.</span></span>

<span data-ttu-id="7d346-120">En cada uno de estos escenarios, la funcionalidad expuesta debe protegerse contra el uso no autorizado.</span><span class="sxs-lookup"><span data-stu-id="7d346-120">In each of these scenarios, the exposed functionality needs to be secured against unauthorized use.</span></span> <span data-ttu-id="7d346-121">Como mínimo, normalmente esto requiere la autenticación del usuario o la entidad de seguridad que realiza una solicitud para un recurso.</span><span class="sxs-lookup"><span data-stu-id="7d346-121">At a minimum, this typically requires authenticating the user or principal making a request for a resource.</span></span> <span data-ttu-id="7d346-122">Esta autenticación puede usar uno de varios protocolos comunes, como SAML2p, WS-FED o OpenID Connect.</span><span class="sxs-lookup"><span data-stu-id="7d346-122">This authentication may use one of several common protocols such as SAML2p, WS-Fed, or OpenID Connect.</span></span> <span data-ttu-id="7d346-123">La comunicación con las API normalmente usa el protocolo OAuth2 y su compatibilidad con los tokens de seguridad.</span><span class="sxs-lookup"><span data-stu-id="7d346-123">Communicating with APIs typically uses the OAuth2 protocol and its support for security tokens.</span></span> <span data-ttu-id="7d346-124">La separación de estas cuestiones críticas de seguridad transversales y sus detalles de implementación de las propias aplicaciones garantiza la coherencia y mejora la seguridad y el mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="7d346-124">Separating these critical cross-cutting security concerns and their implementation details from the applications themselves ensures consistency and improves security and maintainability.</span></span> <span data-ttu-id="7d346-125">El outsourcing de estos problemas con un producto dedicado, como IdentityServer, ayuda a la necesidad de que cada aplicación resuelva estos problemas por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="7d346-125">Outsourcing these concerns to a dedicated product like IdentityServer helps the requirement for every application to solve these problems itself.</span></span>

<span data-ttu-id="7d346-126">IdentityServer proporciona middleware que se ejecuta dentro de una aplicación ASP.NET Core y agrega compatibilidad con OpenID Connect y OAuth2 (consulte las [Especificaciones admitidas](https://docs.identityserver.io/en/latest/intro/specs.html)).</span><span class="sxs-lookup"><span data-stu-id="7d346-126">IdentityServer provides middleware that runs within an ASP.NET Core application and adds support for OpenID Connect and OAuth2 (see [supported specifications](https://docs.identityserver.io/en/latest/intro/specs.html)).</span></span> <span data-ttu-id="7d346-127">Las organizaciones crearían su propia aplicación ASP.NET Core con middleware IdentityServer para que actúe como STS para todos sus protocolos de seguridad basados en tokens.</span><span class="sxs-lookup"><span data-stu-id="7d346-127">Organizations would create their own ASP.NET Core app using IdentityServer middleware to act as the STS for all of their token-based security protocols.</span></span> <span data-ttu-id="7d346-128">El middleware IdentityServer expone puntos de conexión para admitir la funcionalidad estándar, como:</span><span class="sxs-lookup"><span data-stu-id="7d346-128">The IdentityServer middleware exposes endpoints to support standard functionality, including:</span></span>

- <span data-ttu-id="7d346-129">Autorizar (autenticar al usuario final)</span><span class="sxs-lookup"><span data-stu-id="7d346-129">Authorize (authenticate the end user)</span></span>
- <span data-ttu-id="7d346-130">Token (solicitar un token mediante programación)</span><span class="sxs-lookup"><span data-stu-id="7d346-130">Token (request a token programmatically)</span></span>
- <span data-ttu-id="7d346-131">Detección (metadatos sobre el servidor)</span><span class="sxs-lookup"><span data-stu-id="7d346-131">Discovery (metadata about the server)</span></span>
- <span data-ttu-id="7d346-132">Información de usuario (obtener información de usuario con un token de acceso válido)</span><span class="sxs-lookup"><span data-stu-id="7d346-132">User Info (get user information with a valid access token)</span></span>
- <span data-ttu-id="7d346-133">Autorización de dispositivo (se usa para iniciar la autorización de flujo de dispositivo)</span><span class="sxs-lookup"><span data-stu-id="7d346-133">Device Authorization (used to start device flow authorization)</span></span>
- <span data-ttu-id="7d346-134">Introspección (validación de token)</span><span class="sxs-lookup"><span data-stu-id="7d346-134">Introspection (token validation)</span></span>
- <span data-ttu-id="7d346-135">Revocación (revocación de tokens)</span><span class="sxs-lookup"><span data-stu-id="7d346-135">Revocation (token revocation)</span></span>
- <span data-ttu-id="7d346-136">Finalizar sesión (desencadenar el cierre de sesión único en todas las aplicaciones)</span><span class="sxs-lookup"><span data-stu-id="7d346-136">End Session (trigger single sign-out across all apps)</span></span>

## <a name="getting-started"></a><span data-ttu-id="7d346-137">Introducción</span><span class="sxs-lookup"><span data-stu-id="7d346-137">Getting started</span></span>

<span data-ttu-id="7d346-138">IdentityServer4 es de código abierto y está disponible para su uso.</span><span class="sxs-lookup"><span data-stu-id="7d346-138">IdentityServer4 is open-source and free to use.</span></span> <span data-ttu-id="7d346-139">Puede agregarlo a las aplicaciones mediante sus paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="7d346-139">You can add it to your applications using its NuGet packages.</span></span> <span data-ttu-id="7d346-140">El paquete principal es [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) que se ha descargado más de 4 millones veces.</span><span class="sxs-lookup"><span data-stu-id="7d346-140">The main package is [IdentityServer4](https://www.nuget.org/packages/IdentityServer4/) that has been downloaded over four million times.</span></span> <span data-ttu-id="7d346-141">El paquete base no incluye ningún código de interfaz de usuario y solo admite en la configuración de memoria.</span><span class="sxs-lookup"><span data-stu-id="7d346-141">The base package doesn't include any user interface code and only supports in memory configuration.</span></span> <span data-ttu-id="7d346-142">Para usarlo con una base de datos, también querrá un proveedor de datos como [IdentityServer4. EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) que usa Entity Framework Core para almacenar la configuración y los datos operativos de IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="7d346-142">To use it with a database, you'll also want a data provider like [IdentityServer4.EntityFramework](https://www.nuget.org/packages/IdentityServer4.EntityFramework) that uses Entity Framework Core to store configuration and operational data for IdentityServer.</span></span> <span data-ttu-id="7d346-143">Para la interfaz de usuario, puede copiar archivos del repositorio de la interfaz de usuario de [Inicio rápido](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) en la aplicación ASP.net Core MVC para agregar compatibilidad para iniciar sesión y cerrar sesión con middleware IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="7d346-143">For user interface, you can copy files from the [Quickstart UI repository](https://github.com/IdentityServer/IdentityServer4.Quickstart.UI) into your ASP.NET Core MVC application to add support for sign in and sign out using IdentityServer middleware.</span></span>

## <a name="configuration"></a><span data-ttu-id="7d346-144">Configuración</span><span class="sxs-lookup"><span data-stu-id="7d346-144">Configuration</span></span>

<span data-ttu-id="7d346-145">IdentityServer admite distintos tipos de protocolos y proveedores de autenticación social que se pueden configurar como parte de cada instalación personalizada.</span><span class="sxs-lookup"><span data-stu-id="7d346-145">IdentityServer supports different kinds of protocols and social authentication providers that can be configured as part of each custom installation.</span></span> <span data-ttu-id="7d346-146">Esto se hace normalmente en la clase de la aplicación ASP.NET Core `Startup` en el `ConfigureServices` método.</span><span class="sxs-lookup"><span data-stu-id="7d346-146">This is typically done in the ASP.NET Core application's `Startup` class in the `ConfigureServices` method.</span></span> <span data-ttu-id="7d346-147">La configuración implica especificar los protocolos admitidos y las rutas de acceso a los servidores y extremos que se usarán.</span><span class="sxs-lookup"><span data-stu-id="7d346-147">The configuration involves specifying the supported protocols and the paths to the servers and endpoints that will be used.</span></span> <span data-ttu-id="7d346-148">En la figura 8-2 se muestra una configuración de ejemplo tomada del proyecto de IU de inicio rápido de IdentityServer4:</span><span class="sxs-lookup"><span data-stu-id="7d346-148">Figure 8-2 shows an example configuration taken from the IdentityServer4 Quickstart UI project:</span></span>

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddMvc();

        // some details omitted
        services.AddIdentityServer();

          services.AddAuthentication()
            .AddGoogle("Google", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;

                options.ClientId = "<insert here>";
                options.ClientSecret = "<insert here>";
            })
            .AddOpenIdConnect("demoidsrv", "IdentityServer", options =>
            {
                options.SignInScheme = IdentityServerConstants.ExternalCookieAuthenticationScheme;
                options.SignOutScheme = IdentityServerConstants.SignoutScheme;

                options.Authority = "https://demo.identityserver.io/";
                options.ClientId = "implicit";
                options.ResponseType = "id_token";
                options.SaveTokens = true;
                options.CallbackPath = new PathString("/signin-idsrv");
                options.SignedOutCallbackPath = new PathString("/signout-callback-idsrv");
                options.RemoteSignOutPath = new PathString("/signout-idsrv");

                options.TokenValidationParameters = new TokenValidationParameters
                {
                    NameClaimType = "name",
                    RoleClaimType = "role"
                };
            });
    }
}
```

<span data-ttu-id="7d346-149">**Figura 8-2**.</span><span class="sxs-lookup"><span data-stu-id="7d346-149">**Figure 8-2**.</span></span> <span data-ttu-id="7d346-150">Configuración de IdentityServer.</span><span class="sxs-lookup"><span data-stu-id="7d346-150">Configuring IdentityServer.</span></span>

<span data-ttu-id="7d346-151">IdentityServer también hospeda un sitio de demostración público que se puede usar para probar diversos protocolos y configuraciones.</span><span class="sxs-lookup"><span data-stu-id="7d346-151">IdentityServer also hosts a public demo site that can be used to test various protocols and configurations.</span></span> <span data-ttu-id="7d346-152">Se encuentra en [https://demo.identityserver.io/](https://demo.identityserver.io/) e incluye información sobre cómo configurar su comportamiento en función del que `client_id` se le proporciona.</span><span class="sxs-lookup"><span data-stu-id="7d346-152">It's located at [https://demo.identityserver.io/](https://demo.identityserver.io/) and includes information on how to configure its behavior based on the `client_id` provided to it.</span></span>

## <a name="javascript-clients"></a><span data-ttu-id="7d346-153">Clientes de JavaScript</span><span class="sxs-lookup"><span data-stu-id="7d346-153">JavaScript clients</span></span>

<span data-ttu-id="7d346-154">Muchas aplicaciones nativas en la nube aprovechan las API del lado servidor y las aplicaciones de página única de cliente enriquecidas (Spa) en el front-end.</span><span class="sxs-lookup"><span data-stu-id="7d346-154">Many cloud-native applications leverage server-side APIs and rich client single page applications (SPAs) on the front end.</span></span> <span data-ttu-id="7d346-155">IdentityServer envía un [cliente de JavaScript](https://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) ( `oidc-client.js` ) a través de NPM que se puede Agregar a Spa para permitirles usar IdentityServer para el inicio de sesión, el cierre de sesión y la autenticación basada en tokens de las API Web.</span><span class="sxs-lookup"><span data-stu-id="7d346-155">IdentityServer ships a [JavaScript client](https://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html) (`oidc-client.js`) via NPM that can be added to SPAs to enable them to use IdentityServer for sign in, sign out, and token-based authentication of web APIs.</span></span>

## <a name="references"></a><span data-ttu-id="7d346-156">Referencias</span><span class="sxs-lookup"><span data-stu-id="7d346-156">References</span></span>

- [<span data-ttu-id="7d346-157">Documentación de IdentityServer</span><span class="sxs-lookup"><span data-stu-id="7d346-157">IdentityServer documentation</span></span>](https://docs.identityserver.io/en/latest/)
- [<span data-ttu-id="7d346-158">Tipos de aplicación</span><span class="sxs-lookup"><span data-stu-id="7d346-158">Application types</span></span>](/azure/active-directory/develop/app-types)
- [<span data-ttu-id="7d346-159">Cliente OIDC de JavaScript</span><span class="sxs-lookup"><span data-stu-id="7d346-159">JavaScript OIDC client</span></span>](https://docs.identityserver.io/en/latest/quickstarts/4_javascript_client.html)

>[!div class="step-by-step"]
><span data-ttu-id="7d346-160">[Anterior](azure-active-directory.md)
>[Siguiente](security.md)</span><span class="sxs-lookup"><span data-stu-id="7d346-160">[Previous](azure-active-directory.md)
[Next](security.md)</span></span>
