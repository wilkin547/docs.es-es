---
title: Cambios importantes en ASP.NET Core
titleSuffix: ''
description: Enumera los cambios importantes en ASP.NET Core.
ms.date: 07/17/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 1506e0aa27778d44497252231028689259f48896
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720246"
---
# <a name="aspnet-core-breaking-changes"></a>Cambios importantes en ASP.NET Core

ASP.NET Core proporciona las características de desarrollo de aplicaciones web que usa .NET Core.

En esta página se documentan los siguientes cambios importantes:

- [Se han quitado las API Antiforgery, CORS, Diagnostics, MVC y Routing obsoletas](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Autenticación: Google+ en desuso](#authentication-google-deprecated-and-replaced)
- [Autenticación: se ha quitado la propiedad HttpContext.Authentication](#authentication-httpcontextauthentication-property-removed)
- [Autenticación: se han reemplazado los tipos Newtonsoft.Json](#authentication-newtonsoftjson-types-replaced)
- [Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorización: la sobrecarga de AddAuthorization se ha movido a otro ensamblado](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorización: se ha quitado IAllowAnonymous de AuthorizationFilterContext.Filters](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorización: las implementaciones de IAuthorizationPolicyProvider requieren un método nuevo](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Autorización: El recurso en el enrutamiento de punto de conexión es HttpContext](#authorization-resource-in-endpoint-routing-is-httpcontext)
- [Azure: Paquetes de integración de Azure con prefijo de Microsoft quitados](#azure-microsoft-prefixed-azure-integration-packages-removed)
- [Los métodos de serialización BinaryFormatter están obsoletos y se prohíben en las aplicaciones ASP.NET](#binaryformatter-serialization-methods-are-obsolete-and-prohibited-in-aspnet-apps)
- [Blazor: espacio en blanco no significativo recortado de componentes en el tiempo de compilación](#blazor-insignificant-whitespace-trimmed-from-components-at-compile-time)
- [Blazor: Plataforma de destino de paquetes NuGet cambiada](#blazor-target-framework-of-nuget-packages-changed)
- [Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure](#caching-compactonmemorypressure-property-removed)
- [Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Almacenamiento en caché: los tipos "pubternal" de ResponseCaching se han cambiado a internal](#caching-responsecaching-pubternal-types-changed-to-internal)
- [Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [Extensiones: cambios en las referencias de paquetes que afectan a algunos paquetes NuGet](#extensions-package-reference-changes-affecting-some-nuget-packages)
- [Hospedaje: se ha quitado AspNetCoreModule V1 del conjunto de hospedaje de Windows](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hospedaje: el host genérico restringe la inserción del constructor de Startup](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hospedaje: redireccionamiento de HTTPS habilitado para aplicaciones fuera de proceso de IIS](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hospedaje: se han reemplazado los tipos IHostingEnvironment e IApplicationLifetime](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: los tipos BadHttpRequestException de Kestrel e IIS se han marcado como obsoletos y se han reemplazado](#http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced)
- [HTTP: los cambios de SameSite del explorador afectan a la autenticación](#http-browser-samesite-changes-impact-authentication)
- [HTTP: se ha quitado la extensibilidad de DefaultHttpContext](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: los campos HeaderNames se han cambiado a static readonly](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory](#http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes)
- [HTTP: cambios en la infraestructura del cuerpo de respuesta](#http-response-body-infrastructure-changes)
- [HTTP: se han cambiado algunos valores predeterminados de cookie de SameSite](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: se ha deshabilitado la E/S sincrónica de forma predeterminada](#http-synchronous-io-disabled-in-all-servers)
- [HttpSys: Deshabilitación predeterminada de la renegociación del certificado de cliente](#httpsys-client-certificate-renegotiation-disabled-by-default)
- [Identidad: se ha quitado la sobrecarga del método AddDefaultUI](#identity-adddefaultui-method-overload-removed)
- [Identidad: cambio de versión de arranque de IU](#identity-default-bootstrap-version-of-ui-changed)
- [Identidad: SignInAsync produce una excepción para la identidad no autenticada](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identidad: el constructor SignInManager acepta un nuevo parámetro](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identidad: la interfaz de usuario usa la característica de recursos web estáticos](#identity-ui-uses-static-web-assets-feature)
- [IIS: Mantenimiento de las cadenas de consulta de middleware de UrlRewrite](#iis-urlrewrite-middleware-query-strings-are-preserved)
- [Kestrel: cambios de configuración en tiempo de ejecución detectados de forma predeterminada](#kestrel-configuration-changes-at-run-time-detected-by-default)
- [Kestrel: se han quitado los adaptadores de conexión](#kestrel-connection-adapters-removed)
- [Kestrel: versiones del protocolo TLS admitidas de forma predeterminada cambiadas](#kestrel-default-supported-tls-protocol-versions-changed)
- [Kestrel: se ha quitado un ensamblado HTTPS vacío](#kestrel-empty-https-assembly-removed)
- [Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles](#kestrel-http2-disabled-over-tls-on-incompatible-windows-versions)
- [Kestrel: transporte de libuv marcado como obsoleto](#kestrel-libuv-transport-marked-as-obsolete)
- [Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: cambios en la capa de abstracción de transporte](#kestrel-transport-abstractions-removed-and-made-public)
- [Localización: API marcadas como obsoletas](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Localización: API "Pubternal" quitadas](#localization-pubternal-apis-removed)
- [Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes](#localization-obsolete-constructor-removed-in-request-localization-middleware)
- [Localización: se han eliminado la clase ResourceManagerWithCultureStringLocalizer y el miembro de interfaz WithCulture](#localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed)
- [Registro: la clase DebugLogger se ha convertido en interna](#logging-debuglogger-class-made-internal)
- [MVC: se ha quitado el sufijo Async de acción de controlador](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: herramienta de precompilación en desuso](#mvc-precompilation-tool-deprecated)
- [MVC: los tipos se han cambiado a internal](#mvc-pubternal-types-changed-to-internal)
- [MVC: se han quitado las correcciones de compatibilidad (shim) con la API web](#mvc-web-api-compatibility-shim-removed)
- [Razor: la compilación en tiempo de ejecución se ha movido a un paquete](#razor-runtime-compilation-moved-to-a-package)
- [Seguridad: Se ha quitado la codificación de nombre de cookie](#security-cookie-name-encoding-removed)
- [Seguridad: Se han actualizado las versiones del paquete NuGet IdentityModel](#security-identitymodel-nuget-package-versions-updated)
- [Estado de sesión: se han quitado las API obsoletas](#session-state-obsolete-apis-removed)
- [Marco compartido: eliminación de ensamblados de Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Marco compartido: se ha eliminado Microsoft.AspNetCore.All](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: se han quitado métodos de HubConnection](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: se han cambiado los constructores de HubConnectionContext](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: se ha cambiado el nombre del paquete de cliente de JavaScript](#signalr-javascript-client-package-name-changed)
- [SignalR: El protocolo de concentrador de MessagePack se ha migrado al paquete MessagePack 2.x](#signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package)
- [SignalR: se ha cambiado el tipo de opciones del protocolo de concentrador de MessagePack](#signalr-messagepack-hub-protocol-options-type-changed)
- [SignalR: API obsoletas](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SignalR: los métodos UseSignalR y UseConnections se han marcado como obsoletos](#signalr-usesignalr-and-useconnections-methods-removed)
- [SPA: cambio predeterminado de reserva de registrador de consola de SpaServices y NodeServices](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [SPA: SpaServices y NodeServices se han marcado como obsoletos](#spas-spaservices-and-nodeservices-marked-obsolete)
- [Archivos estáticos: tipo de contenido CSV cambiado a compatible con los estándares](#static-files-csv-content-type-changed-to-standards-compliant)
- [Marco de destino: no se admite .NET Framework](#target-framework-net-framework-support-dropped)

## <a name="aspnet-core-50"></a>ASP.NET Core 5.0

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

## <a name="aspnet-core-31"></a>ASP.NET Core 3.1

[!INCLUDE[HTTP: Browser SameSite changes impact authentication](~/includes/core-changes/aspnetcore/3.1/http-cookie-samesite-authn-impacts.md)]

***

## <a name="aspnet-core-30"></a>ASP.NET Core 3.0

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
