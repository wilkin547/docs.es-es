---
title: Implementación de reintentos de llamada HTTP con retroceso exponencial con Polly
description: Obtenga información sobre cómo controlar los errores HTTP con Polly e IHttpClientFactory.
ms.date: 01/13/2021
ms.openlocfilehash: 8cffc644d73eaec5019e00c6a83de8635b569cde
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189055"
---
# <a name="implement-http-call-retries-with-exponential-backoff-with-ihttpclientfactory-and-polly-policies"></a><span data-ttu-id="4c8be-103">Implementación de reintentos de llamada HTTP con retroceso exponencial con IHttpClientFactory y las directivas de Polly</span><span class="sxs-lookup"><span data-stu-id="4c8be-103">Implement HTTP call retries with exponential backoff with IHttpClientFactory and Polly policies</span></span>

<span data-ttu-id="4c8be-104">El enfoque recomendado para los reintentos con retroceso exponencial consiste en aprovechar las ventajas de las bibliotecas de .NET más avanzadas como la biblioteca de código abierto [Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="4c8be-104">The recommended approach for retries with exponential backoff is to take advantage of more advanced .NET libraries like the open-source [Polly library](https://github.com/App-vNext/Polly).</span></span>

<span data-ttu-id="4c8be-105">Polly es una biblioteca de .NET que proporciona capacidades de resistencia y control de errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="4c8be-105">Polly is a .NET library that provides resilience and transient-fault handling capabilities.</span></span> <span data-ttu-id="4c8be-106">Puede implementar esas funcionalidades mediante la aplicación de directivas de Polly como las de reintento, interruptor, aislamiento compartimentado, tiempo de espera y reserva.</span><span class="sxs-lookup"><span data-stu-id="4c8be-106">You can implement those capabilities by applying Polly policies such as Retry, Circuit Breaker, Bulkhead Isolation, Timeout, and Fallback.</span></span> <span data-ttu-id="4c8be-107">Polly tiene como destino .NET Framework 4.x y .NET Standard 1.0, 1.1 y 2.0 (que admite .NET Core y versiones posteriores).</span><span class="sxs-lookup"><span data-stu-id="4c8be-107">Polly targets .NET Framework 4.x and .NET Standard 1.0, 1.1, and 2.0 (which supports .NET Core and later).</span></span>

<span data-ttu-id="4c8be-108">En los pasos siguientes se muestra cómo usar reintentos HTTP con Polly integrados en `IHttpClientFactory`, que se explica en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="4c8be-108">The following steps show how you can use Http retries with Polly integrated into `IHttpClientFactory`, which is explained in the previous section.</span></span>

<span data-ttu-id="4c8be-109">**Referencias a los paquetes de ASP.NET Core 3.1**</span><span class="sxs-lookup"><span data-stu-id="4c8be-109">**Reference the ASP.NET Core 3.1 packages**</span></span>

<span data-ttu-id="4c8be-110">`IHttpClientFactory` está disponible desde .NET Core 2.1, pero, a pesar de ello, le recomendamos que use los últimos paquetes de ASP.NET Core 3.1 de NuGet en su proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c8be-110">`IHttpClientFactory` is available since .NET Core 2.1 however we recommend you to use the latest ASP.NET Core 3.1 packages from NuGet in your project.</span></span> <span data-ttu-id="4c8be-111">Normalmente también es necesario hacer referencia al paquete de extensión `Microsoft.Extensions.Http.Polly`.</span><span class="sxs-lookup"><span data-stu-id="4c8be-111">You typically also need to reference the extension package `Microsoft.Extensions.Http.Polly`.</span></span>

<span data-ttu-id="4c8be-112">**Configurar un cliente con la directiva de reintentos de Polly, en Startup**</span><span class="sxs-lookup"><span data-stu-id="4c8be-112">**Configure a client with Polly's Retry policy, in Startup**</span></span>

<span data-ttu-id="4c8be-113">Como se mostró en las secciones anteriores, tendrá que definir una configuración HttpClient cliente con nombre o tipo en el método Startup.ConfigureServices(...) estándar, pero ahora agregará código incremental en el que se especifica la directiva para los reintentos HTTP con retroceso exponencial, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="4c8be-113">As shown in previous sections, you need to define a named or typed client HttpClient configuration in your standard Startup.ConfigureServices(...) method, but now, you add incremental code specifying the policy for the Http retries with exponential backoff, as below:</span></span>

```csharp
//ConfigureServices()  - Startup.cs
services.AddHttpClient<IBasketService, BasketService>()
        .SetHandlerLifetime(TimeSpan.FromMinutes(5))  //Set lifetime to five minutes
        .AddPolicyHandler(GetRetryPolicy());
```

<span data-ttu-id="4c8be-114">El método **AddPolicyHandler()** es el que agrega las directivas a los objetos `HttpClient` que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="4c8be-114">The **AddPolicyHandler()** method is what adds policies to the `HttpClient` objects you'll use.</span></span> <span data-ttu-id="4c8be-115">En este caso, se agrega una directiva de Polly para reintentos HTTP con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="4c8be-115">In this case, it's adding a Polly's policy for Http Retries with exponential backoff.</span></span>

<span data-ttu-id="4c8be-116">Para tener un enfoque más modular, la directiva de reintentos HTTP se puede definir en un método independiente dentro del archivo `Startup.cs`, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c8be-116">To have a more modular approach, the Http Retry Policy can be defined in a separate method within the `Startup.cs` file, as shown in the following code:</span></span>

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

<span data-ttu-id="4c8be-117">Con Polly, se puede definir una directiva de reintentos con el número de reintentos, la configuración de retroceso exponencial y las acciones necesarias cuando se produce una excepción de HTTP, como registrar el error.</span><span class="sxs-lookup"><span data-stu-id="4c8be-117">With Polly, you can define a Retry policy with the number of retries, the exponential backoff configuration, and the actions to take when there's an HTTP exception, such as logging the error.</span></span> <span data-ttu-id="4c8be-118">En este caso, la directiva está configurada para intentar seis veces con un reintento exponencial, a partir de dos segundos.</span><span class="sxs-lookup"><span data-stu-id="4c8be-118">In this case, the policy is configured to try six times with an exponential retry, starting at two seconds.</span></span>

## <a name="add-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="4c8be-119">Agregar una estrategia de vibración a la directiva de reintentos</span><span class="sxs-lookup"><span data-stu-id="4c8be-119">Add a jitter strategy to the retry policy</span></span>

<span data-ttu-id="4c8be-120">Una directiva de reintentos normal puede afectar a su sistema en casos de escalabilidad y simultaneidad altas y de gran contención.</span><span class="sxs-lookup"><span data-stu-id="4c8be-120">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="4c8be-121">Para gestionar los picos de reintentos similares procedentes de diferentes clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva o algoritmo de reintento.</span><span class="sxs-lookup"><span data-stu-id="4c8be-121">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="4c8be-122">Esto puede mejorar el rendimiento general del sistema de un extremo a otro añadiendo aleatoriedad al retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="4c8be-122">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="4c8be-123">De esta forma, cuando surgen problemas, los picos se reparten.</span><span class="sxs-lookup"><span data-stu-id="4c8be-123">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="4c8be-124">El principio que rige esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c8be-124">The principle is illustrated by the following example:</span></span>

```csharp
Random jitterer = new Random();
var retryWithJitterPolicy = HttpPolicyExtensions
    .HandleTransientHttpError()
    .OrResult(msg => msg.StatusCode == System.Net.HttpStatusCode.NotFound)
    .WaitAndRetryAsync(6,    // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))  
                      + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

<span data-ttu-id="4c8be-125">Polly proporciona algoritmos de vibración listos para la producción a través del sitio web del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4c8be-125">Polly provides production-ready jitter algorithms via the project website.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4c8be-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4c8be-126">Additional resources</span></span>

- <span data-ttu-id="4c8be-127">**Patrón de reintento**</span><span class="sxs-lookup"><span data-stu-id="4c8be-127">**Retry pattern**</span></span>  
  [https://docs.microsoft.com/azure/architecture/patterns/retry](/azure/architecture/patterns/retry)

- <span data-ttu-id="4c8be-128">**Polly e IHttpClientFactory**</span><span class="sxs-lookup"><span data-stu-id="4c8be-128">**Polly and IHttpClientFactory**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Polly-and-HttpClientFactory>

- <span data-ttu-id="4c8be-129">**Polly (.NET resilience and transient-fault-handling library) (Polly [Biblioteca de control de errores transitorios y resistencia de .NET])**</span><span class="sxs-lookup"><span data-stu-id="4c8be-129">**Polly (.NET resilience and transient-fault-handling library)**</span></span>  
  <https://github.com/App-vNext/Polly>

- <span data-ttu-id="4c8be-130">**Polly: reintentar con vibración**</span><span class="sxs-lookup"><span data-stu-id="4c8be-130">**Polly: Retry with Jitter**</span></span>  
  <https://github.com/App-vNext/Polly/wiki/Retry-with-jitter>

- <span data-ttu-id="4c8be-131">**Marc Brooker. Jitter: Making Things Better With Randomness** (Vibración: hacer mejor las cosas gracias a la aleatoriedad)</span><span class="sxs-lookup"><span data-stu-id="4c8be-131">**Marc Brooker. Jitter: Making Things Better With Randomness**</span></span>  
  <https://brooker.co.za/blog/2015/03/21/backoff.html>

>[!div class="step-by-step"]
><span data-ttu-id="4c8be-132">[Anterior](use-httpclientfactory-to-implement-resilient-http-requests.md)
>[Siguiente](implement-circuit-breaker-pattern.md)</span><span class="sxs-lookup"><span data-stu-id="4c8be-132">[Previous](use-httpclientfactory-to-implement-resilient-http-requests.md)
[Next](implement-circuit-breaker-pattern.md)</span></span>
