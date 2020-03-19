---
ms.openlocfilehash: 958dede03e1c15f69f4ee676f13713ff43c29e96
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72393911"
---
### <a name="logging-debuglogger-class-made-internal"></a>Registro: la clase DebugLogger se ha convertido en interna

Antes de ASP.NET Core 3.0, el modificador de acceso de `DebugLogger` era `public`. En ASP.NET Core 3.0, el modificador de acceso se ha cambiado a `internal`.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="reason-for-change"></a>Motivo del cambio

El cambio se realiza para:

* Aplicar la coherencia con otras implementaciones de registrador como `ConsoleLogger`.
* Reducir la superficie de la API.

#### <a name="recommended-action"></a>Acción recomendada

Use el método de extensión <xref:Microsoft.Extensions.Logging.DebugLoggerFactoryExtensions.AddDebug%2A> de `ILoggingBuilder` para habilitar el registro de depuración. <xref:Microsoft.Extensions.Logging.Debug.DebugLoggerProvider> también sigue siendo `public` en caso de que el servicio se tenga que registrar de forma manual.

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

<xref:Microsoft.Extensions.Logging.Debug.DebugLogger?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.Extensions.Logging.Debug.DebugLogger`

-->
