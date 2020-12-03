---
title: 'Cambio importante: HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 964c0a65a07816acea8016d42a66a6bf84aba7c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760100"
---
# <a name="http-httpclient-instances-created-by-ihttpclientfactory-log-integer-status-codes"></a>HTTP: instancias de HttpClient creadas por códigos de estado enteros del registro de IHttpClientFactory

Instancias de <xref:System.Net.Http.HttpClient> creadas como enteros por códigos de estado HTTP del registro de <xref:System.Net.Http.IHttpClientFactory>, en lugar de con nombres de código de estado.

## <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 1)

## <a name="old-behavior"></a>Comportamiento anterior

El registro usa las descripciones textuales de los códigos de estado HTTP. Considere los siguientes mensajes de registro:

```output
Received HTTP response after 56.0044ms - OK
End processing HTTP request after 70.0862ms - OK
```

## <a name="new-behavior"></a>Comportamiento nuevo

El registro usa los valores enteros de los códigos de estado HTTP. Considere los siguientes mensajes de registro:

```output
Received HTTP response after 56.0044ms - 200
End processing HTTP request after 70.0862ms - 200
```

## <a name="reason-for-change"></a>Motivo del cambio

El comportamiento original de este registro es incoherente con otras partes de ASP.NET Core que siempre han usado valores enteros. La incoherencia hace que los registros resulten difíciles de consultar a través de sistemas de registro estructurados, como [Elasticsearch](https://www.elastic.co/elasticsearch/). Para obtener más contexto, vea [dotnet/extensions#1549](https://github.com/dotnet/extensions/issues/1549).

El uso de valores enteros es más flexible que el uso de texto, ya que permite realizar consultas en intervalos de valores.

Se consideró la posibilidad de agregar otro valor de registro para capturar el código de estado entero. Desafortunadamente, al hacerlo, se introduciría otra incoherencia con el resto de ASP.NET Core. El registro de HttpClient y el registro de HTTP de servidor/hospedaje ya usan el mismo nombre de clave de `StatusCode`.

## <a name="recommended-action"></a>Acción recomendada

La mejor opción consiste en actualizar las consultas de registros para usar los valores enteros de los códigos de estado. Esta opción puede hacer que sea algo difícil escribir consultas en varias versiones de ASP.NET Core. Aun así, el uso de enteros para este propósito es mucho más flexible para la consulta de registros.

Si necesita forzar la compatibilidad con el comportamiento anterior y usar códigos de estado textuales, reemplace el registro de `IHttpClientFactory` por el suyo propio:

1. Copie las versiones de .NET Core 3.1 de las siguientes clases en el proyecto:

    * [LoggingHttpMessageHandlerBuilderFilter](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandlerBuilderFilter.cs)
    * [LoggingHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingHttpMessageHandler.cs)
    * [LoggingScopeHttpMessageHandler](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/LoggingScopeHttpMessageHandler.cs)
    * [HttpHeadersLogValue](https://github.com/dotnet/extensions/blob/release/3.1/src/HttpClientFactory/Http/src/Logging/HttpHeadersLogValue.cs)

1. Cambie el nombre de las clases para evitar conflictos con tipos públicos en el paquete NuGet de [Microsoft.Extensions.Http](https://www.nuget.org/packages/Microsoft.Extensions.Http).

1. Reemplace la implementación integrada de `LoggingHttpMessageHandlerBuilderFilter` por la suya propia en el método `Startup.ConfigureServices` del proyecto. Por ejemplo:

    ```csharp
    public void ConfigureServices(IServiceCollection services)
    {
        // Other service registrations go first. Code omitted for brevity.

        // Place the following after all AddHttpClient registrations.
        services.RemoveAll<IHttpMessageHandlerBuilderFilter>();

        services.AddSingleton<IHttpMessageHandlerBuilderFilter,
                              MyLoggingHttpMessageHandlerBuilderFilter>();
    }
    ```

## <a name="affected-apis"></a>API afectadas

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType>

<!--

### Category

ASP.NET Core

### Affected APIs

`T:System.Net.Http.HttpClient`

-->
