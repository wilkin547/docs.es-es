---
title: Valores de configuración de redes
description: Obtenga información sobre los valores del entorno de ejecución que configuran las redes para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998838"
---
# <a name="run-time-configuration-options-for-networking"></a>Opciones de configuración del entorno de ejecución para las redes

## <a name="http2-protocol"></a>Protocolo HTTP/2

- Configura si está habilitada la compatibilidad con el protocolo HTTP/2.
- Predeterminado: deshabilitado (`false`).
- Introducido en .NET Core 3.0.

| | Nombre de valor | Valores |
| - | - |
| **runtimeconfig.json** | `System.Net.Http.SocketsHttpHandler.Http2Support` | `false`: deshabilitado.<br/>`true`: habilitado. |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="sockets-http-handler"></a>Controlador HTTP de sockets

- Configura si las API de redes de alto nivel, como <xref:System.Net.Http.HttpClient>, usan <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> o la implementación de <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> basada en [libcurl](https://curl.haxx.se/libcurl/).
- Predeterminado: usar <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).
- Se puede configurar este valor mediante programación llamando al método <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Net.Http.UseSocketsHttpHandler` | `true`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`false`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>. |
| **Variable del entorno** | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | `1`: habilita el uso de <xref:System.Net.Http.SocketsHttpHandler>.<br/>`0`: habilita el uso de <xref:System.Net.Http.HttpClientHandler>. |
