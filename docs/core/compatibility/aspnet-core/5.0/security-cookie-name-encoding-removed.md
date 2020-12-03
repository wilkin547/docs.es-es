---
title: 'Cambio importante: Seguridad: Se ha quitado la codificación de nombre de cookie'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Seguridad: Se ha quitado la codificación de nombre de cookie'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 3cd40d2b04d0cdf0863e3a3fb6d790c2b35692bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760270"
---
# <a name="security-cookie-name-encoding-removed"></a>Seguridad: Se ha quitado la codificación de nombre de cookie

El [estándar de cookies de HTTP](https://tools.ietf.org/html/rfc6265#section-4.1.1) solo permite caracteres específicos en nombres y valores de cookies. Para admitir caracteres no permitidos, ASP.NET Core:

* Codifica cuando se crea una cookie de respuesta.
* Descodifica cuando se crea una cookie de solicitud.

En ASP.NET Core 5.0, este comportamiento de codificación ha cambiado en respuesta a un problema de seguridad.

Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#23578](https://github.com/dotnet/aspnetcore/issues/23578).

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 8)

## <a name="old-behavior"></a>Comportamiento anterior

Se codifican los nombres de las cookies de respuesta. Se descodifican los nombres de las cookies de solicitud.

## <a name="new-behavior"></a>Comportamiento nuevo

Se ha quitado la codificación y descodificación de los nombres de cookies. En el caso de las [versiones compatibles](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) de ASP.NET Core anteriores, el equipo planea mitigar el problema de descodificación en contexto. Además, al llamar a <xref:Microsoft.AspNetCore.Http.IResponseCookies.Append%2A?displayProperty=nameWithType> con un nombre de cookie no válido se inicia una excepción de tipo <xref:System.ArgumentException>. La codificación y la descodificación de valores de cookies permanecen sin cambios.

## <a name="reason-for-change"></a>Motivo del cambio

Se ha detectado un problema en [varios marcos web](https://github.com/advisories/GHSA-j6w9-fv6q-3q52). La codificación y la descodificación podrían permitir que un atacante omita una característica de seguridad llamada [prefijos de cookie](https://tools.ietf.org/html/draft-ietf-httpbis-cookie-prefixes-00) mediante la suplantación de prefijos reservados como `__Host-` con valores codificados como `__%48ost-`. El ataque requiere que una vulnerabilidad de seguridad inserte las cookies suplantadas, como una vulnerabilidad de scripts entre sitios (XSS), en el sitio web. Estos prefijos no se usan de forma predeterminada en ASP.NET Core ni en las bibliotecas o plantillas de `Microsoft.Owin`.

## <a name="recommended-action"></a>Acción recomendada

Si va a mover proyectos a ASP.NET Core 5.0 o una versión posterior, asegúrese de que los nombres de las cookies cumplen los [requisitos de especificación de tokens](https://tools.ietf.org/html/rfc2616#section-2.2): Los caracteres ASCII excluyen los controles y separadores `"(" | ")" | "<" | ">" | "@" | "," | ";" | ":" | "\" | <"> | "/" | "[" | "]" | "?" | "=" | "{" | "}" | SP | HT`. El uso de caracteres que no son ASCII en los nombres de cookies u otros encabezados HTTP puede producir una excepción del servidor o que el cliente pueda realizar una acción inadecuada de ida y vuelta.

## <a name="affected-apis"></a>API afectadas

- <xref:Microsoft.AspNetCore.Http.HttpRequest.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.HttpResponse.Cookies%2A?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinRequest.Cookies?displayProperty=nameWithType>
- <xref:Microsoft.Owin.IOwinResponse.Cookies?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.HttpRequest.Cookies`
- `Overload:Microsoft.AspNetCore.Http.HttpResponse.Cookies`
- `P:Microsoft.Owin.IOwinRequest.Cookies`
- `P:Microsoft.Owin.IOwinResponse.Cookies`

-->
