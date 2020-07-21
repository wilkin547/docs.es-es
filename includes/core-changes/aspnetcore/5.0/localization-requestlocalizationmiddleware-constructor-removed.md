---
ms.openlocfilehash: db941229e02064ee856829417d6762aa17b0b926
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309171"
---
### <a name="localization-obsolete-constructor-removed-in-request-localization-middleware"></a>Localización: Se ha quitado el constructor obsoleto en el middleware de localización de solicitudes

El constructor <xref:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware> que carece de un parámetro <xref:Microsoft.Extensions.Logging.ILoggerFactory> se ha marcado como obsoleto [en esta confirmación](https://github.com/dotnet/aspnetcore/commit/ba8c6ccf6fd3eeb7fc42a159d362b15eae4fb3a0). En ASP.NET Core 5.0 se ha quitado el constructor obsoleto. Para obtener información, vea [dotnet/aspnetcore#23785](https://github.com/dotnet/aspnetcore/issues/23785).

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

#### <a name="old-behavior"></a>Comportamiento anterior

El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` existe.

#### <a name="new-behavior"></a>Comportamiento nuevo

El constructor obsoleto `RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions<RequestLocalizationOptions>)` no existe.

#### <a name="reason-for-change"></a>Motivo del cambio

Este cambio garantiza que el middleware de localización de solicitudes siempre tenga acceso a un registrador.

#### <a name="recommended-action"></a>Acción recomendada

Cuando se construye manualmente una instancia de `RequestLocalizationMiddleware`, se pasa una instancia de `ILoggerFactory` en el constructor. Si en ese contexto no hay una instancia de `ILoggerFactory` válida disponible, considere la posibilidad de pasar una instancia de <xref:Microsoft.Extensions.Logging.Abstractions.NullLoggerFactory> al constructor de middleware.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

[RequestLocalizationMiddleware.ctor(RequestDelegate, IOptions\<RequestLocalizationOptions>)](/dotnet/api/microsoft.aspnetcore.localization.requestlocalizationmiddleware.-ctor?view=aspnetcore-3.1#Microsoft_AspNetCore_Localization_RequestLocalizationMiddleware__ctor_Microsoft_AspNetCore_Http_RequestDelegate_Microsoft_Extensions_Options_IOptions_Microsoft_AspNetCore_Builder_RequestLocalizationOptions__)

<!--

#### Affected APIs

`M:Microsoft.AspNetCore.Localization.RequestLocalizationMiddleware.#ctor(Microsoft.AspNetCore.Http.RequestDelegate,Microsoft.Extensions.Options.IOptions{Microsoft.AspNetCore.Builder.RequestLocalizationOptions})`

-->
