---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6b5e03b127f95911b712b66c0be8a4f5a2929fc2
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761946"
---
# <a name="run-time-configuration-options-for-networking"></a>Opciones de configuración del entorno de ejecución para las redes

## <a name="http2-protocol"></a>Protocolo HTTP/2

- Configura si está habilitada la compatibilidad con el protocolo HTTP/2.

- Si se omite esta configuración, la compatibilidad con el protocolo HTTP/2 está deshabilitada. Esto es equivalente a establecer el valor en `false`.

- Introducido en .NET Core 3.0.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="usesocketshttphandler"></a>UseSocketsHttpHandler

- Configura si <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> usa <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o pilas de protocolo HTTP anteriores (<xref:System.Net.Http.WinHttpHandler> en Windows y `CurlHandler`, una clase interna implementada sobre [libcurl](https://curl.haxx.se/libcurl/), en Linux).

  > [!NOTE]
  > Es posible que esté usando las API para redes de alto nivel en lugar de crear directamente instancias de la clase <xref:System.Net.Http.HttpClientHandler>. Este valor también afecta a la pila del protocolo HTTP que usan las API para redes de alto nivel, como <xref:System.Net.Http.HttpClient> y [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).

- Si se omite este valor, <xref:System.Net.Http.HttpClientHandler> utiliza <xref:System.Net.Http.SocketsHttpHandler>. Esto es equivalente a establecer el valor en `true`.

- Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`false`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`0`: habilita el uso de <xref:System.Net.Http.WinHttpHandler> en Windows o [libcurl](https://curl.haxx.se/libcurl/) en Linux |

> [!NOTE]
> A partir de .NET 5, la configuración `System.Net.Http.UseSocketsHttpHandler` ya no está disponible.
