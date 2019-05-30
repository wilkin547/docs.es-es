---
title: Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
description: Obtenga información sobre cómo controlar los errores HTTP con Polly y HttpClientFactory.
ms.date: 01/07/2019
ms.openlocfilehash: 9ffb0d918dc2efdc41d6c2db2e2141d14061b687
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053115"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-httpclientfactory-and-polly-policies"></a><span data-ttu-id="7a130-103">Implementación de reintentos de llamada HTTP con retroceso exponencial con HttpClientFactory y las directivas de Polly</span><span class="sxs-lookup"><span data-stu-id="7a130-103">Implement HTTP call retries with exponential backoff with HttpClientFactory and Polly policies</span></span>

<span data-ttu-id="7a130-104">El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como la biblioteca de código abierto [Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="7a130-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="7a130-105">Polly es una biblioteca de .NET que proporciona capacidades de resistencia y control de errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="7a130-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="7a130-106">Puede implementar esas funcionalidades mediante la aplicación de directivas de Polly como las de reintento, interruptor, aislamiento compartimentado, tiempo de espera y reserva.</span><span class="sxs-lookup"><span data-stu-id="7a130-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="7a130-107">Polly tiene como destino .NET 4.x y la biblioteca 1.0 de .NET Standard (que es compatible con .NET Core).</span><span class="sxs-lookup"><span data-stu-id="7a130-107">Polly targets .NET 4.x and the .NET Standard Library 1.0 (which supports .NET Core).</span></span>

<span data-ttu-id="7a130-108">Pero usar la biblioteca de Polly con código personalizado propio con HttpClient puede ser bastante complejo.</span><span class="sxs-lookup"><span data-stu-id="7a130-108">However, using Polly’s library with your own custom code with HttpClient can be significantly complex.</span></span> <span data-ttu-id="7a130-109">En la versión original de eShopOnContainers, había un [bloque de creación ResilientHttpClient](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) basado en Polly.</span><span class="sxs-lookup"><span data-stu-id="7a130-109">In the original version of eShopOnContainers, there was a [ResilientHttpClient building-block](https://github.com/dotnet-architecture/eShopOnContainers/commit/0c317d56f3c8937f6823cf1b45f5683397274815#diff-e6532e623eb606a0f8568663403e3a10) based on Polly.</span></span> <span data-ttu-id="7a130-110">Pero con el lanzamiento de [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md), la comunicación HTTP resistente se ha convertido en mucho más fácil de implementar, por lo que ese bloque de creación ha quedado en desuso en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="7a130-110">But with the release of [HttpClientFactory](use-httpclientfactory-to-implement-resilient-http-requests.md), resilient HTTP communication has become much simpler to implement, so that building-block was deprecated from eShopOnContainers.</span></span> 

<span data-ttu-id="7a130-111">En los pasos siguientes se muestra cómo usar reintentos HTTP con Polly integrados en HttpClientFactory, que se explica en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="7a130-111">The following steps show how you can use Http retries with Polly integrated into HttpClientFactory, which is explained in the previous section.</span></span>

<span data-ttu-id="7a130-112">**Hacer referencia a los paquetes de ASP.NET Core 2.2**</span><span class="sxs-lookup"><span data-stu-id="7a130-112">**Reference the ASP.NET Core 2.2 packages**</span></span>

<span data-ttu-id="7a130-113">`HttpClientFactory` está disponible desde .NET Core 2.1. Sin embargo, le recomendamos que use los últimos paquetes de ASP.NET Core 2.2 de NuGet en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="7a130-113">`HttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 2.2 packages from NuGet in your project.</span></span> <span data-ttu-id="7a130-114">Normalmente se necesita el metapaquete `AspNetCore` y el paquete de extensión `Microsoft.Extensions.Http.Polly`.</span><span class="sxs-lookup"><span data-stu-id="7a130-114">You typically need the `AspNetCore` metapackage, and the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="7a130-115">**Configurar un cliente con la directiva de reintentos de Polly, en Startup**</span><span class="sxs-lookup"><span data-stu-id="7a130-115">**Configure a client with Polly’s Retry policy, in Startup**</span></span>

<span data-ttu-id="7a130-116">Como se mostró en las secciones anteriores, tendrá que definir una configuración HttpClient cliente con nombre o tipo en el método Startup.ConfigureServices(...) estándar, pero ahora agregará código incremental en el que se especifica la directiva para los reintentos HTTP con retroceso exponencial, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="7a130-116">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="7a130-117">El método **AddPolicyHandler()** es el que agrega las directivas a los objetos `HttpClient` que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="7a130-117">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="7a130-118">En este caso, se agrega una directiva de Polly para reintentos HTTP con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="7a130-118">In this case, it's adding a Polly’s policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="7a130-119">Para tener un enfoque más modular, la directiva de reintentos HTTP se puede definir en un método independiente dentro del archivo `Startup.cs`, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a130-119">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

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

<span data-ttu-id="7a130-120">Con Polly, se puede definir una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error.</span><span class="sxs-lookup"><span data-stu-id="7a130-120">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="7a130-121">En este caso, la directiva está configurada para intentar seis veces con un reintento exponencial, a partir de dos segundos.</span><span class="sxs-lookup"><span data-stu-id="7a130-121">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span> 

<span data-ttu-id="7a130-122">Por tanto, lo intentará seis veces y los segundos entre cada reintento serán exponenciales, a partir de dos segundos.</span><span class="sxs-lookup"><span data-stu-id="7a130-122">so it will try six times and the seconds between each retry will be exponential, starting on two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="7a130-123">Agregar una estrategia de vibración a la directiva de reintentos</span><span class="sxs-lookup"><span data-stu-id="7a130-123">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="7a130-124">Una directiva de reintentos normal puede afectar a su sistema en casos de escalabilidad y simultaneidad altas y de gran contención.</span><span class="sxs-lookup"><span data-stu-id="7a130-124">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="7a130-125">Para gestionar los picos de reintentos similares procedentes de diferentes clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva o algoritmo de reintento.</span><span class="sxs-lookup"><span data-stu-id="7a130-125">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="7a130-126">Esto puede mejorar el rendimiento general del sistema de un extremo a otro añadiendo aleatoriedad al retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="7a130-126">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="7a130-127">De esta forma, cuando surgen problemas, los picos se reparten.</span><span class="sxs-lookup"><span data-stu-id="7a130-127">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="7a130-128">Al usar una directiva de Polly sin formato, el código para implementar la vibración podría parecerse al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a130-128">When you use a plain Polly policy, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random(); 
Policy
  .Handle<HttpResponseException>() // etc
  .WaitAndRetry(5,    // exponential back-off plus some jitter
      retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                    + TimeSpan.FromMilliseconds(jitterer.Next(0, 100)) 
  );
```

## <a name="additional-resources"></a><span data-ttu-id="7a130-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7a130-129">Additional resources</span></span>

- <span data-ttu-id="7a130-130">**Retry pattern (Patrón de reintento)** \\</span><span class="sxs-lookup"><span data-stu-id="7a130-130">**Retry pattern**\\</span></span>
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="7a130-131">**Polly y HttpClientFactory**\\</span><span class="sxs-lookup"><span data-stu-id="7a130-131">**Polly and HttpClientFactory**\\</span></span>
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- <span data-ttu-id="7a130-132">**Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])** \\</span><span class="sxs-lookup"><span data-stu-id="7a130-132">**Polly (.NET resilience and transient-fault-handling library)**\\</span></span>
  <https://github.com/App-vNext/Polly>

- <span data-ttu-id="7a130-133">**Marc Brooker. Jitter: Making Things Better With Randomness**\ (Vibración: hacer mejor las cosas gracias a la aleatoriedad)</span><span class="sxs-lookup"><span data-stu-id="7a130-133">**Marc Brooker. Jitter: Making Things Better With Randomness**\\</span></span>
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
><span data-ttu-id="7a130-134">[Anterior](explore-custom-http-call-retries-exponential-backoff.md)
>[Siguiente](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="7a130-134">[Previous](explore-custom-http-call-retries-exponential-backoff.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
