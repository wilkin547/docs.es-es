---
title: Cambios importantes en ASP.NET Core
titleSuffix: ''
description: Enumera los cambios importantes en ASP.NET Core.
ms.date: 07/15/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: cea6771afdc05edc525e7d35f530f42e7b3bc1fa
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441952"
---
# <a name="aspnet-core-breaking-changes"></a><span data-ttu-id="6631a-103">Cambios importantes en ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="6631a-103">ASP.NET Core breaking changes</span></span>

<span data-ttu-id="6631a-104">ASP.NET Core proporciona las características de desarrollo de aplicaciones web que usa .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6631a-104">ASP.NET Core provides the web app development features used by .NET Core.</span></span>

<span data-ttu-id="6631a-105">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="6631a-105">The following breaking changes are documented on this page:</span></span>

- [<span data-ttu-id="6631a-106">Se han quitado las API Antiforgery, CORS, Diagnostics, MVC y Routing obsoletas</span><span class="sxs-lookup"><span data-stu-id="6631a-106">Obsolete Antiforgery, CORS, Diagnostics, MVC, and Routing APIs removed</span></span>](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [<span data-ttu-id="6631a-107">Autenticación: Google+ en desuso</span><span class="sxs-lookup"><span data-stu-id="6631a-107">Authentication: Google+ deprecation</span></span>](#authentication-google-deprecated-and-replaced)
- [<span data-ttu-id="6631a-108">Autenticación: se ha quitado la propiedad HttpContext.Authentication</span><span class="sxs-lookup"><span data-stu-id="6631a-108">Authentication: HttpContext.Authentication property removed</span></span>](#authentication-httpcontextauthentication-property-removed)
- [<span data-ttu-id="6631a-109">Autenticación: se han reemplazado los tipos Newtonsoft.Json</span><span class="sxs-lookup"><span data-stu-id="6631a-109">Authentication: Newtonsoft.Json types replaced</span></span>](#authentication-newtonsoftjson-types-replaced)
- [<span data-ttu-id="6631a-110">Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler</span><span class="sxs-lookup"><span data-stu-id="6631a-110">Authentication: OAuthHandler ExchangeCodeAsync signature changed</span></span>](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [<span data-ttu-id="6631a-111">Autorización: la sobrecarga de AddAuthorization se ha movido a otro ensamblado</span><span class="sxs-lookup"><span data-stu-id="6631a-111">Authorization: AddAuthorization overload moved to different assembly</span></span>](#authorization-addauthorization-overload-moved-to-different-assembly)
- [<span data-ttu-id="6631a-112">Autorización: se ha quitado IAllowAnonymous de AuthorizationFilterContext.Filters</span><span class="sxs-lookup"><span data-stu-id="6631a-112">Authorization: IAllowAnonymous removed from AuthorizationFilterContext.Filters</span></span>](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [<span data-ttu-id="6631a-113">Autorización: las implementaciones de IAuthorizationPolicyProvider requieren un método nuevo</span><span class="sxs-lookup"><span data-stu-id="6631a-113">Authorization: IAuthorizationPolicyProvider implementations require new method</span></span>](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [<span data-ttu-id="6631a-114">Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext</span><span class="sxs-lookup"><span data-stu-id="6631a-114">Authorization: Resource in endpoint routing is HttpContext</span></span>](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [<span data-ttu-id="6631a-115">Azure: Paquetes de integración de Azure con prefijo de Microsoft quitados</span><span class="sxs-lookup"><span data-stu-id="6631a-115">Azure: Microsoft-prefixed Azure integration packages removed</span></span>](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [<span data-ttu-id="6631a-116">Blazor: espacio en blanco no significativo recortado de componentes en el tiempo de compilación</span><span class="sxs-lookup"><span data-stu-id="6631a-116">Blazor: Insignificant whitespace trimmed from components at compile time</span></span>](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [<span data-ttu-id="6631a-117">Blazor: Plataforma de destino de paquetes NuGet cambiada</span><span class="sxs-lookup"><span data-stu-id="6631a-117">Blazor: Target framework of NuGet packages changed</span></span>](#blazor-target-framework-of-nuget-packages-changed)
- [<span data-ttu-id="6631a-118">Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure</span><span class="sxs-lookup"><span data-stu-id="6631a-118">Caching: CompactOnMemoryPressure property removed</span></span>](#caching-compactonmemorypressure-property-removed)
- [<span data-ttu-id="6631a-119">Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient</span><span class="sxs-lookup"><span data-stu-id="6631a-119">Caching: Microsoft.Extensions.Caching.SqlServer uses new SqlClient package</span></span>](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [<span data-ttu-id="6631a-120">Almacenamiento en caché: los tipos "pubternal" de ResponseCaching se han cambiado a internal</span><span class="sxs-lookup"><span data-stu-id="6631a-120">Caching: ResponseCaching "pubternal" types changed to internal</span></span>](#caching-responsecaching-pubternal-types-changed-to-internal)
- [<span data-ttu-id="6631a-121">Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage</span><span class="sxs-lookup"><span data-stu-id="6631a-121">Data Protection: DataProtection.AzureStorage uses new Azure Storage APIs</span></span>](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [<span data-ttu-id="6631a-122">Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="6631a-122">Extensions: Package reference changes affecting some NuGet packages</span></span>](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [<span data-ttu-id="6631a-123">Hospedaje: se ha quitado AspNetCoreModule V1 del conjunto de hospedaje de Windows</span><span class="sxs-lookup"><span data-stu-id="6631a-123">Hosting: AspNetCoreModule V1 removed from Windows Hosting Bundle</span></span>](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [<span data-ttu-id="6631a-124">Hospedaje: el host genérico restringe la inserción del constructor de Startup</span><span class="sxs-lookup"><span data-stu-id="6631a-124">Hosting: Generic host restricts Startup constructor injection</span></span>](#hosting-generic-host-restricts-startup-constructor-injection)
- [<span data-ttu-id="6631a-125">Hospedaje: redireccionamiento de HTTPS habilitado para aplicaciones fuera de proceso de IIS</span><span class="sxs-lookup"><span data-stu-id="6631a-125">Hosting: HTTPS redirection enabled for IIS out-of-process apps</span></span>](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [<span data-ttu-id="6631a-126">Hospedaje: se han reemplazado los tipos IHostingEnvironment e IApplicationLifetime</span><span class="sxs-lookup"><span data-stu-id="6631a-126">Hosting: IHostingEnvironment and IApplicationLifetime types replaced</span></span>](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="6631a-127">Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="6631a-127">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [<span data-ttu-id="6631a-128">HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado</span><span class="sxs-lookup"><span data-stu-id="6631a-128">HTTP: Kestrel and IIS BadHttpRequestException types marked obsolete and replaced</span></span>](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [<span data-ttu-id="6631a-129">HTTP: los cambios de SameSite del explorador afectan a la autenticación</span><span class="sxs-lookup"><span data-stu-id="6631a-129">HTTP: Browser SameSite changes impact authentication</span></span>](#http-browser-samesite-changes-impact-authentication)
- [<span data-ttu-id="6631a-130">HTTP: se ha quitado la extensibilidad de DefaultHttpContext</span><span class="sxs-lookup"><span data-stu-id="6631a-130">HTTP: DefaultHttpContext extensibility removed</span></span>](#http-defaulthttpcontext-extensibility-removed)
- [<span data-ttu-id="6631a-131">HTTP: los campos HeaderNames se han cambiado a static readonly</span><span class="sxs-lookup"><span data-stu-id="6631a-131">HTTP: HeaderNames fields changed to static readonly</span></span>](#http-headernames-constants-changed-to-static-readonly)
- [<span data-ttu-id="6631a-132">HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory</span><span class="sxs-lookup"><span data-stu-id="6631a-132">HTTP: HttpClient instances created by IHttpClientFactory log integer status codes</span></span>](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [<span data-ttu-id="6631a-133">HTTP: cambios en la infraestructura del cuerpo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6631a-133">HTTP: Response body infrastructure changes</span></span>](#http-response-body-infrastructure-changes)
- [<span data-ttu-id="6631a-134">HTTP: se han cambiado algunos valores predeterminados de cookie de SameSite</span><span class="sxs-lookup"><span data-stu-id="6631a-134">HTTP: Some cookie SameSite default values changed</span></span>](#http-some-cookie-samesite-defaults-changed-to-none)
- [<span data-ttu-id="6631a-135">HTTP: se ha deshabilitado la E/S sincrónica de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="6631a-135">HTTP: Synchronous IO disabled by default</span></span>](#http-synchronous-io-disabled-in-all-servers)
- [<span data-ttu-id="6631a-136">HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="6631a-136">HttpSys: Client certificate renegotiation disabled by default</span></span>](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [<span data-ttu-id="6631a-137">Identidad: se ha quitado la sobrecarga del método AddDefaultUI</span><span class="sxs-lookup"><span data-stu-id="6631a-137">Identity: AddDefaultUI method overload removed</span></span>](#identity-adddefaultui-method-overload-removed)
- [<span data-ttu-id="6631a-138">Identidad: cambio de versión de arranque de IU</span><span class="sxs-lookup"><span data-stu-id="6631a-138">Identity: UI Bootstrap version change</span></span>](#identity-default-bootstrap-version-of-ui-changed)
- [<span data-ttu-id="6631a-139">Identidad: SignInAsync produce una excepción para la identidad no autenticada</span><span class="sxs-lookup"><span data-stu-id="6631a-139">Identity: SignInAsync throws exception for unauthenticated identity</span></span>](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [<span data-ttu-id="6631a-140">Identidad: el constructor SignInManager acepta un nuevo parámetro</span><span class="sxs-lookup"><span data-stu-id="6631a-140">Identity: SignInManager constructor accepts new parameter</span></span>](#identity-signinmanager-constructor-accepts-new-parameter)
- [<span data-ttu-id="6631a-141">Identidad: la interfaz de usuario usa la característica de recursos web estáticos</span><span class="sxs-lookup"><span data-stu-id="6631a-141">Identity: UI uses static web assets feature</span></span>](#identity-ui-uses-static-web-assets-feature)
- [<span data-ttu-id="6631a-142">IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite</span><span class="sxs-lookup"><span data-stu-id="6631a-142">IIS: UrlRewrite middleware query strings are preserved</span></span>](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [<span data-ttu-id="6631a-143">Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="6631a-143">Kestrel: Configuration changes at run time detected by default</span></span>](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [<span data-ttu-id="6631a-144">Kestrel: se han quitado los adaptadores de conexión</span><span class="sxs-lookup"><span data-stu-id="6631a-144">Kestrel: Connection adapters removed</span></span>](#kestrel-connection-adapters-removed)
- [<span data-ttu-id="6631a-145">Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas</span><span class="sxs-lookup"><span data-stu-id="6631a-145">Kestrel: Default supported TLS protocol versions changed</span></span>](#kestrel-default-supported-tls-protocol-versions-changed)
- [<span data-ttu-id="6631a-146">Kestrel: se ha quitado un ensamblado HTTPS vacío</span><span class="sxs-lookup"><span data-stu-id="6631a-146">Kestrel: Empty HTTPS assembly removed</span></span>](#kestrel-empty-https-assembly-removed)
- [<span data-ttu-id="6631a-147">Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles</span><span class="sxs-lookup"><span data-stu-id="6631a-147">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [<span data-ttu-id="6631a-148">Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación</span><span class="sxs-lookup"><span data-stu-id="6631a-148">Kestrel: Request trailer headers moved to new collection</span></span>](#kestrel-request-trailer-headers-moved-to-new-collection)
- [<span data-ttu-id="6631a-149">Kestrel: cambios en la capa de abstracción de transporte</span><span class="sxs-lookup"><span data-stu-id="6631a-149">Kestrel: Transport abstraction layer changes</span></span>](#kestrel-transport-abstractions-removed-and-made-public)
- [<span data-ttu-id="6631a-150">Localización: API marcadas como obsoletas</span><span class="sxs-lookup"><span data-stu-id="6631a-150">Localization: APIs marked obsolete</span></span>](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [<span data-ttu-id="6631a-151">Localización: API "Pubternal" quitadas</span><span class="sxs-lookup"><span data-stu-id="6631a-151">Localization: "Pubternal" APIs removed</span></span>](#localization-pubternal-apis-removed)
- [<span data-ttu-id="6631a-152">Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes</span><span class="sxs-lookup"><span data-stu-id="6631a-152">Localization: Obsolete constructor removed in request localization middleware</span></span>](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [<span data-ttu-id="6631a-153">Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture</span><span class="sxs-lookup"><span data-stu-id="6631a-153">Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed</span></span>](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [<span data-ttu-id="6631a-154">Registro: la clase DebugLogger se ha convertido en interna</span><span class="sxs-lookup"><span data-stu-id="6631a-154">Logging: DebugLogger class made internal</span></span>](#logging-debuglogger-class-made-internal)
- [<span data-ttu-id="6631a-155">MVC: se ha quitado el sufijo Async de acción de controlador</span><span class="sxs-lookup"><span data-stu-id="6631a-155">MVC: Controller action Async suffix removed</span></span>](#mvc-async-suffix-trimmed-from-controller-action-names)
- [<span data-ttu-id="6631a-156">MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core</span><span class="sxs-lookup"><span data-stu-id="6631a-156">MVC: JsonResult moved to Microsoft.AspNetCore.Mvc.Core</span></span>](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [<span data-ttu-id="6631a-157">MVC: herramienta de precompilación en desuso</span><span class="sxs-lookup"><span data-stu-id="6631a-157">MVC: Precompilation tool deprecated</span></span>](#mvc-precompilation-tool-deprecated)
- [<span data-ttu-id="6631a-158">MVC: los tipos se han cambiado a internal</span><span class="sxs-lookup"><span data-stu-id="6631a-158">MVC: Types changed to internal</span></span>](#mvc-pubternal-types-changed-to-internal)
- [<span data-ttu-id="6631a-159">MVC: se han quitado las correcciones de compatibilidad (shim) con la API web</span><span class="sxs-lookup"><span data-stu-id="6631a-159">MVC: Web API compatibility shim removed</span></span>](#mvc-web-api-compatibility-shim-removed)
- [<span data-ttu-id="6631a-160">Razor: la compilación en tiempo de ejecución se ha movido a un paquete</span><span class="sxs-lookup"><span data-stu-id="6631a-160">Razor: Runtime compilation moved to a package</span></span>](#razor-runtime-compilation-moved-to-a-package)
- [<span data-ttu-id="6631a-161">Seguridad: Se ha quitado la codificación de nombre de cookie</span><span class="sxs-lookup"><span data-stu-id="6631a-161">Security: Cookie name encoding removed</span></span>](#security-cookie-name-encoding-removed)
- [<span data-ttu-id="6631a-162">Seguridad: Se han actualizado las versiones del paquete NuGet IdentityModel</span><span class="sxs-lookup"><span data-stu-id="6631a-162">Security: IdentityModel NuGet package versions updated</span></span>](#security-identitymodel-nuget-package-versions-updated)
- [<span data-ttu-id="6631a-163">Estado de sesión: se han quitado las API obsoletas</span><span class="sxs-lookup"><span data-stu-id="6631a-163">Session state: Obsolete APIs removed</span></span>](#session-state-obsolete-apis-removed)
- [<span data-ttu-id="6631a-164">Marco compartido: eliminación de ensamblados de Microsoft.AspNetCore.App</span><span class="sxs-lookup"><span data-stu-id="6631a-164">Shared framework: Assembly removal from Microsoft.AspNetCore.App</span></span>](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [<span data-ttu-id="6631a-165">Marco compartido: se ha eliminado Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="6631a-165">Shared framework: Microsoft.AspNetCore.All removed</span></span>](#shared-framework-removed-microsoftaspnetcoreall)
- [<span data-ttu-id="6631a-166">SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData</span><span class="sxs-lookup"><span data-stu-id="6631a-166">SignalR: HandshakeProtocol.SuccessHandshakeData replaced</span></span>](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [<span data-ttu-id="6631a-167">SignalR: se han quitado métodos de HubConnection</span><span class="sxs-lookup"><span data-stu-id="6631a-167">SignalR: HubConnection methods removed</span></span>](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [<span data-ttu-id="6631a-168">SignalR: se han cambiado los constructores de HubConnectionContext</span><span class="sxs-lookup"><span data-stu-id="6631a-168">SignalR: HubConnectionContext constructors changed</span></span>](#signalr-hubconnectioncontext-constructors-changed)
- [<span data-ttu-id="6631a-169">SignalR: se ha cambiado el nombre del paquete de cliente de JavaScript</span><span class="sxs-lookup"><span data-stu-id="6631a-169">SignalR: JavaScript client package name change</span></span>](#signalr-javascript-client-package-name-changed)
- [<span data-ttu-id="6631a-170">SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x</span><span class="sxs-lookup"><span data-stu-id="6631a-170">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [<span data-ttu-id="6631a-171">SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack</span><span class="sxs-lookup"><span data-stu-id="6631a-171">SignalR: MessagePack Hub Protocol options type changed</span></span>](#signalr-messagepack-hub-protocol-options-type-changed)
- [<span data-ttu-id="6631a-172">SignalR: API obsoletas</span><span class="sxs-lookup"><span data-stu-id="6631a-172">SignalR: Obsolete APIs</span></span>](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [<span data-ttu-id="6631a-173">SignalR: los métodos UseSignalR y UseConnections se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="6631a-173">SignalR: UseSignalR and UseConnections methods removed</span></span>](#signalr-usesignalr-and-useconnections-methods-removed)
- [<span data-ttu-id="6631a-174">SPA: cambio predeterminado de reserva de registrador de consola de SpaServices y NodeServices</span><span class="sxs-lookup"><span data-stu-id="6631a-174">SPAs: SpaServices and NodeServices console logger fallback default change</span></span>](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [<span data-ttu-id="6631a-175">SPA: SpaServices y NodeServices se han marcado como obsoletos</span><span class="sxs-lookup"><span data-stu-id="6631a-175">SPAs: SpaServices and NodeServices marked obsolete</span></span>](#spas-spaservices-and-nodeservices-marked-obsolete)
- [<span data-ttu-id="6631a-176">Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares</span><span class="sxs-lookup"><span data-stu-id="6631a-176">Static files: CSV content type changed to standards-compliant</span></span>](#static-files-csv-content-type-changed-to-standards-compliant)
- [<span data-ttu-id="6631a-177">Marco de destino: no se admite .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6631a-177">Target framework: .NET Framework not supported</span></span>](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a><span data-ttu-id="6631a-178">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="6631a-178">ASP.NET Core 5.0</span></span>

[!INCLUDE[Authorization: Resource in endpoint routing is HttpContext](~/includes/core-changes/aspnetcore/5.0/authorization-resource-in-endpoint-routing.md)]

***

[!INCLUDE[Azure: Microsoft-prefixed Azure integration packages removed](~/includes/core-changes/aspnetcore/5.0/azure-integration-packages-removed.md)]

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

[!INCLUDE[Localization: "Pubternal" APIs removed](~/includes/core-changes/aspnetcore/5.0/localization-pubternal-apis-removed.md)]

***

[!INCLUDE[Localization: Obsolete constructor removed in request localization middleware](~/includes/core-changes/aspnetcore/5.0/localization-requestlocalizationmiddleware-constructor-removed.md)]

***

[!INCLUDE[Localization: ResourceManagerWithCultureStringLocalizer class and WithCulture interface member removed](~/includes/core-changes/aspnetcore/5.0/localization-members-removed.md)]

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

## <a name="aspnet-core-31"></a><span data-ttu-id="6631a-179">ASP.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6631a-179">ASP.NET Core 3.1</span></span>

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a><span data-ttu-id="6631a-180">ASP.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6631a-180">ASP.NET Core 3.0</span></span>

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
