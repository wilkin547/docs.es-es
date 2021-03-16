---
title: 'Cambio importante: API obsoletas y quitadas'
description: Obtenga información sobre el cambio importante en ASP.NET Core 6.0 titulado API obsoletas y quitadas
author: scottaddie
ms.author: scaddie
ms.date: 02/16/2021
ms.openlocfilehash: 4a4819247b7e6bb957f643b457e651cca5b4e703
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102108424"
---
# <a name="obsoleted-and-removed-apis"></a>API obsoletas y quitadas

En ASP.NET Core 6.0 (versión preliminar 1), varias API se han quitado o se han marcado como obsoletas.

## <a name="version-introduced"></a>Versión introducida

6.0 (versión preliminar 1)

## <a name="old-behavior"></a>Comportamiento anterior

En ASP.NET Core 5.0, las API no se quitaron ni se marcaron como obsoletas.

## <a name="new-behavior"></a>Comportamiento nuevo

En ASP.NET Core 6.0, las API se han quitado o se han marcado como obsoletas.

## <a name="reason-for-change"></a>Motivo del cambio

Las API ya no se usan o bien ya no funcionan.

## <a name="recommended-action"></a>Acción recomendada

Use las API de reemplazo recomendadas.

## <a name="affected-apis"></a>API afectadas

* Se ha quitado [Microsoft.AspNetCore.Http.Connections.ParseResponse](/dotnet/api/microsoft.aspnetcore.http.connections.negotiateprotocol.parseresponse?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Http_Connections_NegotiateProtocol_ParseResponse_System_IO_Stream_). En su lugar, use <xref:Microsoft.AspNetCore.Http.Connections.NegotiateProtocol.ParseResponse(System.ReadOnlySpan{System.Byte})?displayProperty=nameWithType>.
* Se ha quitado [Microsoft.AspNetCore.SignalR.HubInvocationContext](/dotnet/api/microsoft.aspnetcore.signalr.hubinvocationcontext.-ctor?view=aspnetcore-5.0&preserve-view=true#Microsoft_AspNetCore_SignalR_HubInvocationContext__ctor_Microsoft_AspNetCore_SignalR_HubCallerContext_System_String_System_Object___). En su lugar, use <xref:Microsoft.AspNetCore.SignalR.HubInvocationContext.%23ctor(Microsoft.AspNetCore.SignalR.HubCallerContext,System.IServiceProvider,Microsoft.AspNetCore.SignalR.Hub,System.Reflection.MethodInfo,System.Collections.Generic.IReadOnlyList{System.Object})?displayProperty=nameWithType>.
* Se ha quitado [Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature](/dotnet/api/microsoft.aspnetcore.http.features.ihttpbufferingfeature?view=aspnetcore-3.1&preserve-view=true). En su lugar, use <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseBodyFeature?displayProperty=nameWithType>.
* Se ha quitado [Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature](/dotnet/api/microsoft.aspnetcore.http.features.ihttpsendfilefeature?view=aspnetcore-3.1&preserve-view=true). En su lugar, use <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseBodyFeature?displayProperty=nameWithType>.
* Se ha quitado el constructor sin argumentos de [Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext](/dotnet/api/microsoft.aspnetcore.staticfiles.staticfileresponsecontext.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_StaticFiles_StaticFileResponseContext__ctor). En su lugar, use <xref:Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext.%23ctor(Microsoft.AspNetCore.Http.HttpContext,Microsoft.Extensions.FileProviders.IFileInfo)?displayProperty=nameWithType>.
* Se ha quitado el constructor [Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor](/dotnet/api/microsoft.aspnetcore.mvc.infrastructure.objectresultexecutor.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_Infrastructure_ObjectResultExecutor__ctor_Microsoft_AspNetCore_Mvc_Infrastructure_OutputFormatterSelector_Microsoft_AspNetCore_Mvc_Infrastructure_IHttpResponseStreamWriterFactory_Microsoft_Extensions_Logging_ILoggerFactory_). En su lugar, use <xref:Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor.%23ctor(Microsoft.AspNetCore.Mvc.Infrastructure.OutputFormatterSelector,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory,Microsoft.Extensions.Logging.ILoggerFactory,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcOptions})?displayProperty=nameWithType>.
* Se ha quitado [Microsoft.AspNetCore.Mvc.ModelBinding.ValidationAllowShortCircuitingValidationWhenNoValidatorsArePresent](/dotnet/api/microsoft.aspnetcore.mvc.modelbinding.validation.validationvisitor.allowshortcircuitingvalidationwhennovalidatorsarepresent?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_ModelBinding_Validation_ValidationVisitor_AllowShortCircuitingValidationWhenNoValidatorsArePresent).
* Se ha quitado [Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor](/dotnet/api/microsoft.aspnetcore.mvc.viewfeatures.viewcomponentresultexecutor.-ctor?view=aspnetcore-3.1&preserve-view=true#Microsoft_AspNetCore_Mvc_ViewFeatures_ViewComponentResultExecutor__ctor_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Mvc_MvcViewOptions__Microsoft_Extensions_Logging_ILoggerFactory_System_Text_Encodings_Web_HtmlEncoder_Microsoft_AspNetCore_Mvc_ModelBinding_IModelMetadataProvider_Microsoft_AspNetCore_Mvc_ViewFeatures_ITempDataDictionaryFactory_). En su lugar, use <xref:Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor.%23ctor(Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcViewOptions},Microsoft.Extensions.Logging.ILoggerFactory,System.Text.Encodings.Web.HtmlEncoder,Microsoft.AspNetCore.Mvc.ModelBinding.IModelMetadataProvider,Microsoft.AspNetCore.Mvc.ViewFeatures.ITempDataDictionaryFactory,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory)?displayProperty=nameWithType>.
* [CompatibilityVersion](/dotnet/api/microsoft.aspnetcore.mvc.compatibilityversion?view=aspnetcore-3.1&preserve-view=true) ha quedado obsoleta.

<!--

## Category

ASP.NET Core

## Affected APIs

- `M:Microsoft.AspNetCore.Http.Connections.NegotiateProtocol.ParseResponse(System.IO.Stream)`
- `M:Microsoft.AspNetCore.SignalR.HubInvocationContext.#ctor(Microsoft.AspNetCore.SignalR.HubCallerContext,System.String,System.Object[])`
- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`
- `M:Microsoft.AspNetCore.StaticFiles.StaticFileResponseContext.#ctor`
- `M:Microsoft.AspNetCore.Mvc.Infrastructure.ObjectResultExecutor.#ctor(Microsoft.AspNetCore.Mvc.Infrastructure.OutputFormatterSelector,Microsoft.AspNetCore.Mvc.Infrastructure.IHttpResponseStreamWriterFactory,Microsoft.Extensions.Logging.ILoggerFactory)`
- `Overload:Microsoft.AspNetCore.Mvc.ModelBinding.Validation.ValidationVisitor.AllowShortCircuitingValidationWhenNoValidatorsArePresent`
- `M:Microsoft.AspNetCore.Mvc.ViewFeatures.ViewComponentResultExecutor.#ctor(Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Mvc.MvcViewOptions},Microsoft.Extensions.Logging.ILoggerFactory,System.Text.Encodings.Web.HtmlEncoder,Microsoft.AspNetCore.Mvc.ModelBinding.IModelMetadataProvider,Microsoft.AspNetCore.Mvc.ViewFeatures.ITempDataDictionaryFactory)`
- `T:Microsoft.AspNetCore.Mvc.CompatibilityVersion`

-->
