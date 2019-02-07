---
title: Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
description: Obtenga información sobre cómo controlar los errores HTTP con Polly y HttpClientFactory.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 01/07/2019
ms.openlocfilehash: d0c3042f2831e5f256f43e32e70645213054f247
ms.sourcegitcommit: dcc8feeff4718664087747529638ec9b47e65234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/31/2019
ms.locfileid: "55479651"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a>Implementación de reintentos de llamada HTTP con retroceso exponencial con HttpClientFactory y las directivas de Polly

El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como la biblioteca de código abierto [Polly](https://github.com/App-vNext/Polly).

Polly es una biblioteca de .NET que proporciona capacidades de resistencia y control de errores transitorios. Puede implementar esas funcionalidades mediante la aplicación de directivas de Polly como las de reintento, interruptor, aislamiento compartimentado, tiempo de espera y reserva. Polly tiene como destino .NET 4.x y la biblioteca 1.0 de .NET Standard (que es compatible con .NET Core).

Pero usar la biblioteca de Polly con código personalizado propio con HttpClient puede ser bastante complejo. En la versión original de eShopOnContainers, había un [bloque de creación ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/blob/master/src/BuildingBlocks/Resilience/Resilience.Http/ResilientHttpClient.cs) basado en Polly. Pero con el lanzamiento de HttpClientFactory, la comunicación HTTP resistente se ha convertido en mucho más fácil de implementar, por lo que ese bloque de creación ha quedado en desuso en eShopOnContainers. 

En los pasos siguientes se muestra cómo usar reintentos HTTP con Polly integrados en HttpClientFactory, que se explica en la sección anterior.

**Hacer referencia a los paquetes de ASP.NET Core 2.2**

`HttpClientFactory` está disponible desde .NET Core 2.1. Sin embargo, le recomendamos que use los últimos paquetes de ASP.NET Core 2.2 de NuGet en su proyecto. Normalmente se necesita el metapaquete `AspNetCore` y el paquete de extensión `Microsoft.Extensions.Http.Polly`.

**Configurar un cliente con la directiva de reintentos de Polly, en Startup**

Como se mostró en las secciones anteriores, tendrá que definir una configuración HttpClient cliente con nombre o tipo en el método Startup.ConfigureServices(...) estándar, pero ahora agregará código incremental en el que se especifica la directiva para los reintentos HTTP con retroceso exponencial, como se muestra a continuación:

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

El método **AddPolicyHandler()** es el que agrega las directivas a los objetos `HttpClient` que se van a usar. En este caso, se agrega una directiva de Polly para reintentos HTTP con retroceso exponencial.

Para tener un enfoque más modular, la directiva de reintentos HTTP se puede definir en un método independiente dentro del archivo `Startup.cs`, como se muestra en el código siguiente:

```csharp
static IAsyncPolicy<HttpResponseMessage> GetRetryPolicy()
{
    return HttpPolicyExtensions
        .HandleTransientHttpError()
        .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
        .WaitAndRetryAsync(6, retryAttempt => TimeSpan.FromSeconds(Math.Pow(2,
                                                                    retryAttempt)));
}
```

Con Polly, se puede definir una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error. En este caso, la directiva está configurada para intentar seis veces con un reintento exponencial, a partir de dos segundos. 

Por tanto, lo intentará seis veces y los segundos entre cada reintento serán exponenciales, a partir de dos segundos.

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a>Agregar una estrategia de vibración a la directiva de reintentos

Una directiva de reintentos normal puede afectar a su sistema en casos de escalabilidad y simultaneidad altas y de gran contención. Para gestionar los picos de reintentos similares procedentes de diferentes clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva o algoritmo de reintento. Esto puede mejorar el rendimiento general del sistema de un extremo a otro añadiendo aleatoriedad al retroceso exponencial. De esta forma, cuando surgen problemas, los picos se reparten. Al usar una directiva de Polly sin formato, el código para implementar la vibración podría parecerse al ejemplo siguiente:

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a>Recursos adicionales

- **Retry pattern (Patrón de reintento)**\
  [*https://docs.microsoft.com/azure/architecture/patterns/retry*](/azure/architecture/patterns/retry)

- **Polly y HttpClientFactory**\
  [*https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory*](https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory)

- **Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**\
  [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)

- **Marc Brooker. Jitter: Making Things Better With Randomness**\ (Vibración: hacer mejor las cosas gracias a la aleatoriedad)
  [*https://brooker.co.za/blog/2015/03/21/backoff.html*](https://brooker.co.za/blog/2015/03/21/backoff.html)

>[!div class="step-by-step"]
>[Anterior](explore-custom-http-call-retries-exponential-backoff.md)
>[Siguiente](implement-circuit-breaker-pattern.md)