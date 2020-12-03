---
title: 'Cambio importante: Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 8801d3e6950d66fd9f24e051fd8729c50eb0b282
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760252"
---
# <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a>Middleware: El middleware del controlador de excepciones produce una excepción original si no se encuentra el controlador

En las versiones anteriores a ASP.NET Core 5.0, el [middleware del controlador de excepciones](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) ejecuta el controlador de excepciones configurado cuando se produce una excepción. Si no se encuentra el controlador de excepciones configurado mediante <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath>, se genera una respuesta HTTP 404. La respuesta es engañosa porque:

* Parece un error del usuario.
* Oculta el hecho de que se ha producido una excepción en el servidor.

Para solucionar este error engañoso en ASP.NET Core 5.0, el middleware del controlador de excepciones (`ExceptionHandlerMiddleware`) produce la excepción original si no se encuentra el controlador de excepciones. Como resultado, el servidor genera una respuesta HTTP 500. La respuesta será más fácil de examinar en los registros del servidor en el momento de depurar el error que se ha producido.

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).

## <a name="version-introduced"></a>Versión introducida

5.0 RC 1

## <a name="old-behavior"></a>Comportamiento anterior

El middleware del controlador de excepciones produce una respuesta HTTP 404 si no se encuentra el controlador de excepciones configurado.

## <a name="new-behavior"></a>Comportamiento nuevo

El middleware del controlador de excepciones produce la excepción original si no se encuentra el controlador de excepciones configurado.

## <a name="reason-for-change"></a>Motivo del cambio

El error HTTP 404 no indica claramente que se ha producido una excepción en el servidor. Este cambio produce un error HTTP 500 para que sea obvio que:

* El problema no se debe a un error del usuario.
* Se ha encontrado una excepción en el servidor.

## <a name="recommended-action"></a>Acción recomendada

No hay cambios en la API. Todas las aplicaciones existentes se seguirán compilando y ejecutando. El servidor controla la excepción generada. Por ejemplo, [Kestrel](/aspnet/core/fundamentals/servers/kestrel) o [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) convierten la excepción en una respuesta de error HTTP 500.

## <a name="affected-apis"></a>API afectadas

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
