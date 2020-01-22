---
title: 'Cambios importantes en ASP.NET Core: .NET Core'
description: Enumera los cambios importantes en ASP.NET Core.
ms.date: 01/10/2020
author: scottaddie
ms.author: scaddie
ms.openlocfilehash: 261788722e09a6fa5b9427b5a220b69a2367b751
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116587"
---
# <a name="aspnet-core-breaking-changes"></a>Cambios importantes en ASP.NET Core

ASP.NET Core proporciona las características de desarrollo de aplicaciones web que usa .NET Core.

En esta página se documentan los siguientes cambios importantes:

- [HTTP: los cambios de SameSite del explorador afectan a la autenticación](#http-browser-samesite-changes-impact-authentication)
- [Se han quitado las API Antiforgery, CORS, Diagnostics, MVC y Routing obsoletas](#obsolete-antiforgery-cors-diagnostics-mvc-and-routing-apis-removed)
- [Autenticación: Google+ en desuso](#authentication-google-deprecated-and-replaced)
- [Autenticación: se ha quitado la propiedad HttpContext.Authentication](#authentication-httpcontextauthentication-property-removed)
- [Autenticación: se han reemplazado los tipos Newtonsoft.Json](#authentication-newtonsoftjson-types-replaced)
- [Autenticación: se ha cambiado la firma ExchangeCodeAsync de OAuthHandler](#authentication-oauthhandler-exchangecodeasync-signature-changed)
- [Autorización: la sobrecarga de AddAuthorization se ha movido a otro ensamblado](#authorization-addauthorization-overload-moved-to-different-assembly)
- [Autorización: se ha quitado IAllowAnonymous de AuthorizationFilterContext.Filters](#authorization-iallowanonymous-removed-from-authorizationfiltercontextfilters)
- [Autorización: las implementaciones de IAuthorizationPolicyProvider requieren un método nuevo](#authorization-iauthorizationpolicyprovider-implementations-require-new-method)
- [Almacenamiento en caché: se ha quitado la propiedad CompactOnMemoryPressure](#caching-compactonmemorypressure-property-removed)
- [Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient](#caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package)
- [Almacenamiento en caché: los tipos "pubternal" de ResponseCaching se han cambiado a internal](#caching-responsecaching-pubternal-types-changed-to-internal)
- [Protección de datos: DataProtection.AzureStorage usa API nuevas de Azure Storage](#data-protection-dataprotectionazurestorage-uses-new-azure-storage-apis)
- [Hospedaje: se ha quitado AspNetCoreModule V1 del conjunto de hospedaje de Windows](#hosting-aspnetcoremodule-v1-removed-from-windows-hosting-bundle)
- [Hospedaje: el host genérico restringe la inserción del constructor de Startup](#hosting-generic-host-restricts-startup-constructor-injection)
- [Hospedaje: redireccionamiento de HTTPS habilitado para aplicaciones fuera de proceso de IIS](#hosting-https-redirection-enabled-for-iis-out-of-process-apps)
- [Hospedaje: se han reemplazado los tipos IHostingEnvironment e IApplicationLifetime](#hosting-ihostingenvironment-and-iapplicationlifetime-types-marked-obsolete-and-replaced)
- [Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder](#hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies)
- [HTTP: se ha quitado la extensibilidad de DefaultHttpContext](#http-defaulthttpcontext-extensibility-removed)
- [HTTP: los campos HeaderNames se han cambiado a static readonly](#http-headernames-constants-changed-to-static-readonly)
- [HTTP: cambios en la infraestructura del cuerpo de respuesta](#http-response-body-infrastructure-changes)
- [HTTP: se han cambiado algunos valores predeterminados de cookie de SameSite](#http-some-cookie-samesite-defaults-changed-to-none)
- [HTTP: se ha deshabilitado la E/S sincrónica de forma predeterminada](#http-synchronous-io-disabled-in-all-servers)
- [Identidad: se ha quitado la sobrecarga del método AddDefaultUI](#identity-adddefaultui-method-overload-removed)
- [Identidad: cambio de versión de arranque de IU](#identity-default-bootstrap-version-of-ui-changed)
- [Identidad: SignInAsync produce una excepción para la identidad no autenticada](#identity-signinasync-throws-exception-for-unauthenticated-identity)
- [Identidad: el constructor SignInManager acepta un nuevo parámetro](#identity-signinmanager-constructor-accepts-new-parameter)
- [Identidad: la interfaz de usuario usa la característica de recursos web estáticos](#identity-ui-uses-static-web-assets-feature)
- [Kestrel: se han quitado los adaptadores de conexión](#kestrel-connection-adapters-removed)
- [Kestrel: se ha quitado un ensamblado HTTPS vacío](#kestrel-empty-https-assembly-removed)
- [Kestrel: se han movido los encabezados de finalizador de solicitud a una nueva recopilación](#kestrel-request-trailer-headers-moved-to-new-collection)
- [Kestrel: cambios en la capa de abstracción de transporte](#kestrel-transport-abstractions-removed-and-made-public)
- [Localización: API marcadas como obsoletas](#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete)
- [Registro: la clase DebugLogger se ha convertido en interna](#logging-debuglogger-class-made-internal)
- [MVC: se ha quitado el sufijo Async de acción de controlador](#mvc-async-suffix-trimmed-from-controller-action-names)
- [MVC: JsonResult se ha trasladado a Microsoft.AspNetCore.Mvc.Core](#mvc-jsonresult-moved-to-microsoftaspnetcoremvccore)
- [MVC: herramienta de precompilación en desuso](#mvc-precompilation-tool-deprecated)
- [MVC: los tipos se han cambiado a internal](#mvc-pubternal-types-changed-to-internal)
- [MVC: se han quitado las correcciones de compatibilidad (shim) con la API web](#mvc-web-api-compatibility-shim-removed)
- [Razor: la compilación en tiempo de ejecución se ha movido a un paquete](#razor-runtime-compilation-moved-to-a-package)
- [Estado de sesión: se han quitado las API obsoletas](#session-state-obsolete-apis-removed)
- [Marco compartido: eliminación de ensamblados de Microsoft.AspNetCore.App](#shared-framework-assemblies-removed-from-microsoftaspnetcoreapp)
- [Marco compartido: se ha eliminado Microsoft.AspNetCore.All](#shared-framework-removed-microsoftaspnetcoreall)
- [SignalR: se ha reemplazado HandshakeProtocol.SuccessHandshakeData](#signalr-handshakeprotocolsuccesshandshakedata-replaced)
- [SignalR: se han quitado métodos de HubConnection](#signalr-hubconnection-resetsendping-and-resettimeout-methods-removed)
- [SignalR: se han cambiado los constructores de HubConnectionContext](#signalr-hubconnectioncontext-constructors-changed)
- [SignalR: se ha cambiado el nombre del paquete de cliente de JavaScript](#signalr-javascript-client-package-name-changed)
- [SignalR: API obsoletas](#signalr-usesignalr-and-useconnections-methods-marked-obsolete)
- [SPA: SpaServices y NodeServices se han marcado como obsoletos](#spas-spaservices-and-nodeservices-marked-obsolete)
- [SPA: cambio predeterminado de reserva de registrador de consola de SpaServices y NodeServices](#spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger)
- [Marco de destino: no se admite .NET Framework](#target-framework-net-framework-support-dropped)

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
