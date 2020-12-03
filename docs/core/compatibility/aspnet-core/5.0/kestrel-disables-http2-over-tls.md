---
title: 'Cambio importante: Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760220"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a>Kestrel: Deshabilitación de HTTP/2 sobre TLS en versiones de Windows incompatibles

Para habilitar HTTP/2 sobre TLS (Seguridad de la capa de transporte) en Windows, deben cumplirse dos requisitos:

- Compatibilidad con ALPN (Negociación de protocolo de capa de aplicación), disponible a partir de Windows 8.1 y Windows Server 2012 R2.
- Un conjunto de cifrados compatible con HTTP/2, disponible a partir de Windows 10 y Windows Server 2016.

De este modo, el comportamiento de Kestrel cuando se configura HTTP/2 sobre TLS ha cambiado a:

- Cambio a la versión anterior `Http1` y registro de un mensaje en el nivel `Information` cuando [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) está establecido en `Http1AndHttp2`. `Http1AndHttp2` es el valor predeterminado en `ListenOptions.HttpProtocols`.
- Inicio de `NotSupportedException` cuando `ListenOptions.HttpProtocols` está establecido en `Http2`.

Para obtener información, vea el tema [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).

## <a name="version-introduced"></a>Versión introducida

ASP.NET Core 5.0 Preview 7

## <a name="old-behavior"></a>Comportamiento anterior

En la tabla siguiente se describe el comportamiento cuando se configura HTTP/2 sobre TLS.

| Protocolos | Windows 7,<br />Windows Server 2008 R2,<br />o versiones anteriores | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016,<br />o versiones más recientes |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Inicio de `NotSupportedException`                   | Error durante el protocolo de enlace TLS     | Error durante el protocolo de enlace TLS &ast;     | Sin errores |
| `Http1AndHttp2` | Cambio a la versión anterior `Http1`                    | Cambio a la versión anterior `Http1`     | Error durante el protocolo de enlace TLS &ast;     | Sin errores |

&ast; Configure los conjuntos de cifrado compatibles para habilitar estos escenarios.

## <a name="new-behavior"></a>Comportamiento nuevo

En la tabla siguiente se describe el comportamiento cuando se configura HTTP/2 sobre TLS.

| Protocolos | Windows 7,<br />Windows Server 2008 R2,<br />o versiones anteriores | Windows 8,<br />Windows Server 2012 | Windows 8.1,<br />Windows Server 2012 R2 | Windows 10,<br />Windows Server 2016,<br />o versiones más recientes |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | Inicio de `NotSupportedException`                   | Inicio de `NotSupportedException`     | Inicio de `NotSupportedException` &ast;&ast;     | Sin errores |
| `Http1AndHttp2` | Cambio a la versión anterior `Http1`                    | Cambio a la versión anterior `Http1`     | Cambio a la versión anterior `Http1` &ast;&ast;     | Sin errores |

&ast;&ast; Configure los conjuntos de cifrado compatibles y establezca el cambio de contexto de la aplicación `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` en `true` para habilitar estos escenarios.

## <a name="reason-for-change"></a>Motivo del cambio

Con este cambio, se garantiza que los errores de compatibilidad de HTTP/2 sobre TLS en versiones anteriores de Windows se detectan con la mayor claridad y rapidez posible.

## <a name="recommended-action"></a>Acción recomendada

Asegúrese de que HTTP/2 sobre TLS esté deshabilitado en versiones de Windows incompatibles. Windows 8.1 y Windows Server 2012 R2 son incompatibles, puesto que carecen de los cifrados necesarios de forma predeterminada. No obstante, es posible modificar los valores de configuración del equipo para que se usen cifrados compatibles con HTTP/2. Para obtener más información, vea [Conjuntos de cifrado TLS en Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1). Una vez configurado, se debe establecer el cambio de contexto de la aplicación `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` para habilitar HTTP/2 sobre TLS en Kestrel. Por ejemplo:

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

La compatibilidad subyacente no ha cambiado. Por ejemplo, HTTP/2 sobre TLS nunca ha funcionado en Windows 8 ni Windows Server 2012. Este cambio modifica el modo en el que se presentan los errores en estos escenarios no admitidos.

## <a name="affected-apis"></a>API afectadas

None

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
