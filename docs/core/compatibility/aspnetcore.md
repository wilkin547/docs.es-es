---
title: Cambios importantes en ASP.NET Core
titleSuffix: ''
description: Enumera los cambios importantes en ASP.NET Core.
ms.date: 09/09/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 2af0cc6721b66b1d07b196e4ba330f8425c14752
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022992"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="d6069-103">Cambios importantes en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="d6069-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="d6069-104">ASP.NET Core proporciona las características de desarrollo de aplicaciones web que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d6069-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="d6069-105">Seleccione uno de los siguientes vínculos para conocer los cambios importantes en una versión específica:</span><span class="sxs-lookup"><span data-stu-id="d6069-105">Select one of the following links for breaking changes in a specific version:</span></span>

* [<span data-ttu-id="d6069-106">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="d6069-106">ASP.NET Core 5.0</span></span>](#aspnet-core-50)
* [<span data-ttu-id="d6069-107">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d6069-107">ASP.NET Core 3.1</span></span>](#aspnet-core-31)
* [<span data-ttu-id="d6069-108">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d6069-108">ASP.NET Core 3.0</span></span>](#aspnet-core-30)

<span data-ttu-id="d6069-109">En esta página se documentan los siguientes cambios importantes en ASP.NET Core 3.0, 3.1 y 5.0:</span><span class="sxs-lookup"><span data-stu-id="d6069-109">The following breaking changes in ASP.NET Core 3.0, 3.1, and 5.0 are documented on this page:</span></span>

- [<span data-ttu-id="d6069-110">Se han quitado las API Antiforgery, CORS, Diagnostics, MVC y Routing obsoletas</span><span class="sxs-lookup"><span data-stu-id="d6069-110">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="d6069-111">Autenticación: Google+ en desuso</span><span class="sxs-lookup"><span data-stu-id="d6069-111">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="d6069-112">Autenticación: se ha quitado la propiedad HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="d6069-112">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="d6069-113">Autenticación: se han reemplazado los tipos Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="d6069-113">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="d6069-114">Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler</span><span class="sxs-lookup"><span data-stu-id="d6069-114">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="d6069-115">Autorización: la sobrecarga de AddAuthorization se ha movido a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="d6069-115">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="d6069-116">Autorización: se ha quitado IAllowAnonymous de AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="d6069-116">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="d6069-117">Autorización: las implementaciones de IAuthorizationPolicyProvider requieren un método nuevo</span><span class="sxs-lookup"><span data-stu-id="d6069-117">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="d6069-118">Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext</span><span class="sxs-lookup"><span data-stu-id="d6069-118">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="d6069-119">Azure: Paquetes de integración de Azure con prefijo de Microsoft quitados</span><span class="sxs-lookup"><span data-stu-id="d6069-119">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="d6069-120">Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d6069-120">BinaryFormatter serialization methods are obsolete and prohibited in ASP.NET apps</span></span>](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [<span data-ttu-id="d6069-121">Blazor: espacio en blanco no significativo recortado de componentes en el tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="d6069-121">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="d6069-122">Blazor: Plataforma de destino de paquetes NuGet cambiada</span><span class="sxs-lookup"><span data-stu-id="d6069-122">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="d6069-123">Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="d6069-123">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="d6069-124">Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient</span><span class="sxs-lookup"><span data-stu-id="d6069-124">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="d6069-125">Almacenamiento en caché: los tipos "pubternal" de ResponseCaching se han cambiado a internal</span><span class="sxs-lookup"><span data-stu-id="d6069-125">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="d6069-126">Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="d6069-126">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="d6069-127">Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="d6069-127">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="d6069-128">Hospedaje: se ha quitado AspNetCoreModule V1 del conjunto de hospedaje de Windows</span><span class="sxs-lookup"><span data-stu-id="d6069-128">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="d6069-129">Hospedaje: el host genérico restringe la inserción del constructor de Startup</span><span class="sxs-lookup"><span data-stu-id="d6069-129">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="d6069-130">Hospedaje: redireccionamiento de HTTPS habilitado para aplicaciones fuera de proceso de IIS</span><span class="sxs-lookup"><span data-stu-id="d6069-130">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="d6069-131">Hospedaje: se han reemplazado los tipos IHostingEnvironment e IApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="d6069-131">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="d6069-132">Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="d6069-132">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="d6069-133">HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado</span><span class="sxs-lookup"><span data-stu-id="d6069-133">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="d6069-134">HTTP: los cambios de SameSite del explorador afectan a la autenticación</span><span class="sxs-lookup"><span data-stu-id="d6069-134">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="d6069-135">HTTP: se ha quitado la extensibilidad de DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="d6069-135">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="d6069-136">HTTP: los campos HeaderNames se han cambiado a static readonly</span><span class="sxs-lookup"><span data-stu-id="d6069-136">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="d6069-137">HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="d6069-137">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="d6069-138">HTTP: cambios en la infraestructura del cuerpo de respuesta</span><span class="sxs-lookup"><span data-stu-id="d6069-138">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="d6069-139">HTTP: se han cambiado algunos valores predeterminados de cookie de SameSite</span><span class="sxs-lookup"><span data-stu-id="d6069-139">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="d6069-140">HTTP: se ha deshabilitado la E/S sincrónica de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="d6069-140">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="d6069-141">HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="d6069-141">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="d6069-142">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="d6069-142">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="d6069-143">Identidad: cambio de versión de arranque de IU</span><span class="sxs-lookup"><span data-stu-id="d6069-143">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="d6069-144">Identidad: SignInAsync produce una excepción para la identidad no autenticada</span><span class="sxs-lookup"><span data-stu-id="d6069-144">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="d6069-145">Identidad: el constructor SignInManager acepta un nuevo parámetro</span><span class="sxs-lookup"><span data-stu-id="d6069-145">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="d6069-146">Identidad: la interfaz de usuario usa la característica de recursos web estáticos</span><span class="sxs-lookup"><span data-stu-id="d6069-146">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="d6069-147">IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="d6069-147">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="d6069-148">Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="d6069-148">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="d6069-149">Kestrel: se han quitado los adaptadores de conexión</span><span class="sxs-lookup"><span data-stu-id="d6069-149">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="d6069-150">Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas</span><span class="sxs-lookup"><span data-stu-id="d6069-150">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="d6069-151">Kestrel: se ha quitado un ensamblado HTTPS vacío</span><span class="sxs-lookup"><span data-stu-id="d6069-151">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="d6069-152">Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles</span><span class="sxs-lookup"><span data-stu-id="d6069-152">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="d6069-153">Kestrel: transporte de libuv marcado como obsoleto</span><span class="sxs-lookup"><span data-stu-id="d6069-153">Kestrel: Libuv transport marked as obsolete</span></span>](#kestrel-libuv-transport-marked-as-obsolete)
- [<span data-ttu-id="d6069-154">Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación</span><span class="sxs-lookup"><span data-stu-id="d6069-154">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="d6069-155">Kestrel: cambios en la capa de abstracción de transporte</span><span class="sxs-lookup"><span data-stu-id="d6069-155">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="d6069-156">Localización: API marcadas como obsoletas</span><span class="sxs-lookup"><span data-stu-id="d6069-156">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="d6069-157">Localización: API "Pubternal" quitadas</span><span class="sxs-lookup"><span data-stu-id="d6069-157">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="d6069-158">Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes</span><span class="sxs-lookup"><span data-stu-id="d6069-158">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="d6069-159">Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture</span><span class="sxs-lookup"><span data-stu-id="d6069-159">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="d6069-160">Registro: la clase DebugLogger se ha convertido en interna</span><span class="sxs-lookup"><span data-stu-id="d6069-160">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="d6069-161">Middleware: página de errores de la base de datos marcada como obsoleta</span><span class="sxs-lookup"><span data-stu-id="d6069-161">Middleware: Database error page marked as obsolete</span></span>](#middleware-database-error-page-marked-as-obsolete)
- [<span data-ttu-id="d6069-162">Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador</span><span class="sxs-lookup"><span data-stu-id="d6069-162">Middleware: Exception Handler Middleware throws original exception if handler not found</span></span>](#middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found)
- [<span data-ttu-id="d6069-163">MVC: se ha quitado el sufijo Async de acción de controlador</span><span class="sxs-lookup"><span data-stu-id="d6069-163">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="d6069-164">MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="d6069-164">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="d6069-165">MVC: herramienta de precompilación en desuso</span><span class="sxs-lookup"><span data-stu-id="d6069-165">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="d6069-166">MVC: los tipos se han cambiado a internal</span><span class="sxs-lookup"><span data-stu-id="d6069-166">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="d6069-167">MVC: se han quitado las correcciones de compatibilidad (shim) con la API web</span><span class="sxs-lookup"><span data-stu-id="d6069-167">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="d6069-168">Razor: API RazorTemplateEngine eliminada</span><span class="sxs-lookup"><span data-stu-id="d6069-168">Razor: RazorTemplateEngine API removed</span></span>](#razor-razortemplateengine-api-removed)
- [<span data-ttu-id="d6069-169">Razor: la compilación en tiempo de ejecución se ha movido a un paquete</span><span class="sxs-lookup"><span data-stu-id="d6069-169">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="d6069-170">Seguridad: Se ha quitado la codificación de nombre de cookie</span><span class="sxs-lookup"><span data-stu-id="d6069-170">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="d6069-171">Seguridad: Se han actualizado las versiones del paquete NuGet IdentityModel</span><span class="sxs-lookup"><span data-stu-id="d6069-171">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="d6069-172">Estado de sesión: se han quitado las API obsoletas</span><span class="sxs-lookup"><span data-stu-id="d6069-172">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="d6069-173">Marco compartido: eliminación de ensamblados de Microsoft.AspNetCore.App</span><span class="sxs-lookup"><span data-stu-id="d6069-173">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="d6069-174">Marco compartido: se ha eliminado Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="d6069-174">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="d6069-175">SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="d6069-175">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="d6069-176">SignalR: se han quitado métodos de HubConnection</span><span class="sxs-lookup"><span data-stu-id="d6069-176">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="d6069-177">SignalR: se han cambiado los constructores de HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="d6069-177">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="d6069-178">SignalR: se ha cambiado el nombre del paquete de cliente de JavaScript</span><span class="sxs-lookup"><span data-stu-id="d6069-178">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="d6069-179">SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="d6069-179">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="d6069-180">SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack</span><span class="sxs-lookup"><span data-stu-id="d6069-180">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="d6069-181">SignalR: API obsoletas</span><span class="sxs-lookup"><span data-stu-id="d6069-181">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="d6069-182">SignalR: los métodos UseSignalR y UseConnections se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="d6069-182">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="d6069-183">SPA: cambio predeterminado de reserva de registrador de consola de SpaServices y NodeServices</span><span class="sxs-lookup"><span data-stu-id="d6069-183">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="d6069-184">SPA: SpaServices y NodeServices se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="d6069-184">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="d6069-185">Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares</span><span class="sxs-lookup"><span data-stu-id="d6069-185">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="d6069-186">Marco de destino: no se admite .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d6069-186">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="d6069-187">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="d6069-187">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

***

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

***

[!INCLUDE [binaryformatter-serialization-obsolete](../../../includes/core-changes/corefx/5.0/binaryformatter-serialization-obsolete.md)]

***

[!INCLUDE[Blazor: Insignificant whitespace trimmed from components at compile time](~/includes/core-changes/aspnetcore/5.0/blazor-components-trim-insignificant-whitespace.md)]

***

[!INCLUDE[Blazor: Target framework of NuGet packages changed](~/includes/core-changes/aspnetcore/5.0/blazor-packages-target-framework-changed.md)]

***

[!INCLUDE[Extensions: Package reference changes](~/includes/core-changes/aspnetcore/5.0/extensions-package-reference-changes.md)]

***

[!INCLUDE[HTTP: HttpClient instances created by IHttpClientFactory log integer status codes](~/includes/core-changes/aspnetcore/5.0/http-httpclient-instances-log-integer-status-codes.md)]

***

[!INCLUDE[HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced](~/includes/core-changes/aspnetcore/5.0/http-badhttprequestexception-obsolete.md)]

***

[!INCLUDE[HttpSys: Client certificate renegotiation disabled by default](~/includes/core-changes/aspnetcore/5.0/httpsys-client-certificate-renegotiation-disabled-by-default.md)]

***

[!INCLUDE[IIS: UrlRewrite middleware query strings are preserved](~/includes/core-changes/aspnetcore/5.0/iis-urlrewrite-middleware-query-strings-are-preserved.md)]

***

[!INCLUDE[Kestrel: Configuration changes at run time detected by default](~/includes/core-changes/aspnetcore/5.0/kestrel-configuration-changes-at-run-time-detected-by-default.md)]

***
[!INCLUDE[Kestrel: Default supported TLS protocol versions changed](~/includes/core-changes/aspnetcore/5.0/kestrel-default-supported-tls-protocol-versions-changed.md)]

***

[!INCLUDE[Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions](~/includes/core-changes/aspnetcore/5.0/kestrel-disables-http2-over-tls.md)]

***

[!INCLUDE[Kestrel: Libuv transport marked as obsolete](~/includes/core-changes/aspnetcore/5.0/kestrel-libuv-transport-obsolete.md)]

***

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

***

[!INCLUDE[Middleware: Database error page marked as obsolete](~/includes/core-changes/aspnetcore/5.0/middleware-database-error-page-obsolete.md)]

***

[!INCLUDE[Middleware: Exception Handler Middleware throws original exception if handler not found](~/includes/core-changes/aspnetcore/5.0/middleware-exception-handler-throws-original-exception.md)]

***

[!INCLUDE[Security: Cookie name encoding removed](~/includes/core-changes/aspnetcore/5.0/security-cookie-name-encoding-removed.md)]

***

[!INCLUDE[Security: IdentityModel NuGet package versions updated](~/includes/core-changes/aspnetcore/5.0/security-identitymodel-nuget-package-versions-updated.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-package.md)]

***

[!INCLUDE[SignalR: MessagePack Hub Protocol options type changed](~/includes/core-changes/aspnetcore/5.0/signalr-messagepack-hub-protocol-options-changed.md)]

***

[!INCLUDE[SignalR: UseSignalR and UseConnections methods removed](~/includes/core-changes/aspnetcore/5.0/signalr-usesignalr-useconnections-removed.md)]

***

[!INCLUDE[Static files: CSV content type changed to standards-compliant](~/includes/core-changes/aspnetcore/5.0/static-files-csv-content-type-changed.md)]

***

## <a name="aspnet-core-31"></a><span data-ttu-id="d6069-188">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d6069-188">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="d6069-189">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="d6069-189">ASP.NET Core 3.0</span></span>

[!INCLUDE[Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed](~/includes/core-changes/aspnetcore/3.0/obsolete-apis-removed.md)]

***

[!INCLUDE[Authentication: Google+ deprecation](~/includes/core-changes/aspnetcore/3.0/authn-google-plus-authn-changes.md)]

***

[!INCLUDE[Authentication: HttpContext.Authentication property removed](~/includes/core-changes/aspnetcore/3.0/authn-httpcontext-property-removed.md)]

***

[!INCLUDE[Authentication: Newtonsoft.Json types replaced](~/includes/core-changes/aspnetcore/3.0/authn-apis-json-types.md)]

***

[!INCLUDE[Authentication: OAuthHandler ExchangeCodeAsync signature changed](~/includes/core-changes/aspnetcore/3.0/authn-exchangecodeasync-signature-change.md)]

***

[!INCLUDE[Authorization: AddAuthorization overload assembly change](~/includes/core-changes/aspnetcore/3.0/authz-assembly-change.md)]

***

[!INCLUDE[Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters](~/includes/core-changes/aspnetcore/3.0/authz-iallowanonymous-removed-from-collection.md)]

***

[!INCLUDE[Authorization: IAuthorizationPolicyProvider implementations require new method](~/includes/core-changes/aspnetcore/3.0/authz-iauthzpolicyprovider-new-method.md)]

***

[!INCLUDE[Caching: CompactOnMemoryPressure property removed](~/includes/core-changes/aspnetcore/3.0/caching-memory-property-removed.md)]

***

[!INCLUDE[Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package](~/includes/core-changes/aspnetcore/3.0/caching-new-sqlclient-package.md)]

***

[!INCLUDE[Caching: ResponseCaching types changed to internal](~/includes/core-changes/aspnetcore/3.0/caching-response-pubternal-to-internal.md)]

***

[!INCLUDE[Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs](~/includes/core-changes/aspnetcore/3.0/dataprotection-azstorage-using-azstorage-apis.md)]

***

[!INCLUDE[Hosting: ANCM version 1 removed from hosting bundle](~/includes/core-changes/aspnetcore/3.0/hosting-ancmv1-hosting-bundle-removal.md)]

***

[!INCLUDE[Hosting: Generic host restriction on Startup constructor injection](~/includes/core-changes/aspnetcore/3.0/hosting-generic-host-startup-ctor-restriction.md)]

***

[!INCLUDE[Hosting: HTTPS redirection enabled for IIS OutOfProcess](~/includes/core-changes/aspnetcore/3.0/hosting-https-redirection-iis-outofprocess.md)]

***

[!INCLUDE[Hosting: IHostingEnvironment and IApplicationLifetime types replaced](~/includes/core-changes/aspnetcore/3.0/hosting-ihostingenv-iapplifetime-types-replaced.md)]

***

[!INCLUDE[Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies](~/includes/core-changes/aspnetcore/3.0/hosting-objectpoolprovider-webhostbuilder-dependencies.md)]

***

[!INCLUDE[HTTP: DefaultHttpContext extensibility removed](~/includes/core-changes/aspnetcore/3.0/http-defaulthttpcontext-extensibility-removed.md)]

***

[!INCLUDE[HTTP: HeaderNames fields changed to static readonly](~/includes/core-changes/aspnetcore/3.0/http-headernames-constants-staticreadonly.md)]

***

[!INCLUDE[HTTP: Response body infrastructure changes](~/includes/core-changes/aspnetcore/3.0/http-response-body-changes.md)]

***

[!INCLUDE[HTTP: Some cookie SameSite default values changed](~/includes/core-changes/aspnetcore/3.0/http-cookie-samesite-defaults-change.md)]

***

[!INCLUDE[HTTP: Synchronous IO disabled by default](~/includes/core-changes/aspnetcore/3.0/http-synchronous-io-disabled.md)]

***

[!INCLUDE[Identity: AddDefaultUI method overload removed](~/includes/core-changes/aspnetcore/3.0/identity-ui-adddefaultui-overload-removed.md)]

***

[!INCLUDE[Identity: UI Bootstrap version change](~/includes/core-changes/aspnetcore/3.0/identity-ui-bootstrap-version.md)]

***

[!INCLUDE[Identity: SignInAsync throws exception for unauthenticated identity](~/includes/core-changes/aspnetcore/3.0/identity-signinasync-throws-exception.md)]

***

[!INCLUDE[Identity: SignInManager constructor accepts new parameter](~/includes/core-changes/aspnetcore/3.0/identity-signinmanager-ctor-parameter.md)]

***

[!INCLUDE[Identity: UI uses static web assets feature](~/includes/core-changes/aspnetcore/3.0/identity-ui-static-web-assets.md)]

***

[!INCLUDE[Kestrel: Connection adapters removed](~/includes/core-changes/aspnetcore/3.0/kestrel-connection-adapters-removed.md)]

***

[!INCLUDE[Kestrel: Empty HTTPS assembly removed](~/includes/core-changes/aspnetcore/3.0/kestrel-empty-assembly-removed.md)]

***

[!INCLUDE[Kestrel: Request trailer headers moved to new collection](~/includes/core-changes/aspnetcore/3.0/kestrel-request-trailer-headers.md)]

***

[!INCLUDE[Kestrel: Transport abstraction layer changes](~/includes/core-changes/aspnetcore/3.0/kestrel-transport-abstractions.md)]

***

[!INCLUDE[Localization: APIs marked obsolete](~/includes/core-changes/aspnetcore/3.0/localization-apis-marked-obsolete.md)]

***

[!INCLUDE[Logging: DebugLogger class made internal](~/includes/core-changes/aspnetcore/3.0/logging-debuglogger-to-internal.md)]

***

[!INCLUDE[MVC: Controller action Async suffix removed](~/includes/core-changes/aspnetcore/3.0/mvc-action-async-suffix-trimmed.md)]

***

[!INCLUDE[MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core](~/includes/core-changes/aspnetcore/3.0/mvc-jsonresult-moved.md)]

***

[!INCLUDE[MVC: Precompilation tool deprecated](~/includes/core-changes/aspnetcore/3.0/mvc-precompilation-tool-deprecated.md)]

***

[!INCLUDE[MVC: Types changed to internal](~/includes/core-changes/aspnetcore/3.0/mvc-pubternal-to-internal.md)]

***

[!INCLUDE[MVC: Web API compatibility shim removed](~/includes/core-changes/aspnetcore/3.0/mvc-webapi-compat-shim-removed.md)]

***

[!INCLUDE[Razor: RazorTemplatEengine API removed](~/includes/core-changes/aspnetcore/3.0/razor-razortemplateengine-api-removed.md)]

***

[!INCLUDE[Razor: Runtime compilation moved to a package](~/includes/core-changes/aspnetcore/3.0/razor-runtime-compilation-package.md)]

***

[!INCLUDE[Session state: Obsolete APIs removed](~/includes/core-changes/aspnetcore/3.0/session-obsolete-apis-removed.md)]

***

[!INCLUDE[Shared framework: Assembly removal from Microsoft.AspNetCore.App](~/includes/core-changes/aspnetcore/3.0/sharedfx-app-shared-framework-assemblies.md)]

***

[!INCLUDE[Shared framework: Microsoft.AspNetCore.All removed](~/includes/core-changes/aspnetcore/3.0/sharedfx-all-framework-removed.md)]

***

[!INCLUDE[SignalR: HandshakeProtocol.SuccessHandshakeData replaced](~/includes/core-changes/aspnetcore/3.0/signalr-successhandshakedata-replaced.md)]

***

[!INCLUDE[SignalR: HubConnection methods removed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnection-methods-removed.md)]

***

[!INCLUDE[SignalR: HubConnectionContext constructors changed](~/includes/core-changes/aspnetcore/3.0/signalr-hubconnectioncontext-ctors.md)]

***

[!INCLUDE[SignalR: JavaScript client package name change](~/includes/core-changes/aspnetcore/3.0/signalr-js-client-package-name.md)]

***

[!INCLUDE[SignalR: Obsolete APIs](~/includes/core-changes/aspnetcore/3.0/signalr-obsolete-apis.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices marked obsolete](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-obsolete.md)]

***

[!INCLUDE[SPAs: SpaServices and NodeServices console logger fallback default change](~/includes/core-changes/aspnetcore/3.0/spas-spaservices-nodeservices-fallback.md)]

***

[!INCLUDE[Target framework: .NET Framework not supported](~/includes/core-changes/aspnetcore/3.0/targetfx-netfx-tfm-support.md)]

***
