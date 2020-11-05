---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188307"
---
# <a name="run-time-configuration-options-for-networking"></a>Opciones de configuración del entorno de ejecución para las redes

## <a name="http2-protocol"></a>Protocolo HTTP/2

- Configura si está habilitada la compatibilidad con el protocolo HTTP/2.

- Introducido en .NET Core 3.0.

- Solo para .NET Core 3.0: Si se omite esta configuración, la compatibilidad con el protocolo HTTP/2 está deshabilitada. Esto es equivalente a establecer el valor en `false`.

- .NET Core 3.1, y .NET 5 y versiones posteriores: si se omite esta configuración, se habilita la compatibilidad con el protocolo HTTP/2. Esto es equivalente a establecer el valor en `true`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Configura si <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o pilas de protocolo HTTP anteriores (<xref:System.Net.Http.WinHttpHandler> en Windows y `CurlHandler`, una clase interna implementada sobre [libcurl](https://curl.haxx.se/libcurl/), en Linux).

  > [!NOTE]
  > Es posible que esté usando las API para redes de alto nivel en lugar de crear directamente instancias de la clase <xref:System.Net.Http.HttpClientHandler>. Este valor también afecta a la pila del protocolo HTTP que usan las API para redes de alto nivel, como <xref:System.Net.Http.HttpClient> y [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).

- Si se omite este valor, <xref:System.Net.Http.HttpClientHandler> utiliza <xref:System.Net.Http.SocketsHttpHandler>. Esto es equivalente a establecer el valor en `true`.

- Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`false`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`0`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux |

> [!NOTE]
> A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.

## <a name="latin1-headers-net-core-31-only"></a>Encabezados Latin1 (solo .NET Core 3.1)

- Este modificador permite relajar la validación de encabezados HTTP y habilita <xref:System.Net.Http.SocketsHttpHandler> para enviar caracteres codificados mediante ISO-8859-1 (Latin-1) en los encabezados.

- Si se omite esta configuración, un intento de enviar un carácter que no sea ASCII iniciará una excepción <xref:System.Net.Http.HttpRequestException>. Esto es equivalente a establecer el valor en `false`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | `0`: deshabilitado.<br/>`1`: habilitado. |

> [!NOTE]
> Esta opción solo está disponible en .NET Core 3.1 desde la versión 3.1.9, y no en versiones anteriores o posteriores. En .NET 5 se recomienda usar <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.
