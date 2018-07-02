---
title: Implementación de reintentos de llamada HTTP personalizados con retroceso exponencial
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Implementación de reintentos de llamada HTTP personalizados con retroceso exponencial
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 77663f193b5f788ee07eba001306caed764ed253
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37104784"
---
# <a name="implementing-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="2cc7f-103">Implementación de reintentos de llamada HTTP personalizados con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="2cc7f-103">Implementing custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="2cc7f-104">Para crear microservicios resistentes, debe controlar los posibles escenarios de error HTTP.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-104">In order to create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="2cc7f-105">Por ello, puede crear su propia implementación de reintentos con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-105">For that purpose, you could create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="2cc7f-106">Además de controlar la falta de disponibilidad de recursos temporal, el retroceso exponencial también debe tener en cuenta que el proveedor de nube puede limitar la disponibilidad de recursos para impedir la sobrecarga de uso.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-106">In addition to handling temporal resource unavailability, the exponential backoff also needs to take into account that the cloud provider might throttle availability of resources to prevent usage overload.</span></span> <span data-ttu-id="2cc7f-107">Por ejemplo, el proveedor de nube podría considerar como un ataque de denegación de servicio ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) el hecho de crear demasiadas solicitudes de conexión muy rápidamente.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-107">For example, creating too many connection requests very quickly might be viewed as a Denial of Service ([DoS](https://en.wikipedia.org/wiki/Denial-of-service_attack)) attack by the cloud provider.</span></span> <span data-ttu-id="2cc7f-108">Como resultado, debe proporcionar un mecanismo para volver a escalar las solicitudes de conexión cuando se ha llegado a un umbral de capacidad.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-108">As a result, you need to provide a mechanism to scale back connection requests when a capacity threshold has been encountered.</span></span>

<span data-ttu-id="2cc7f-109">Como exploración inicial, podría implementar su propio código con una clase de utilidad para retroceso exponencial como [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), junto con código similar al siguiente (que también está disponible en un [repositorio de GitHub ](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span><span class="sxs-lookup"><span data-stu-id="2cc7f-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following (which is also available on a [GitHub repo](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).</span></span>

```csharp
public sealed class RetryWithExponentialBackoff
{
    private readonly int maxRetries, delayMilliseconds, maxDelayMilliseconds;

    public RetryWithExponentialBackoff(int maxRetries = 50,
        int delayMilliseconds = 200,
        int maxDelayMilliseconds = 2000)
    {
        this.maxRetries = maxRetries;
        this.delayMilliseconds = delayMilliseconds;
        this.maxDelayMilliseconds = maxDelayMilliseconds;
    }

    public async Task RunAsync(Func<Task> func)
    {
        ExponentialBackoff backoff = new ExponentialBackoff(this.maxRetries,
            this.delayMilliseconds,
            this.maxDelayMilliseconds);
        retry:
        try
        {
            await func();
        }
        catch (Exception ex) when (ex is TimeoutException ||
            ex is System.Net.Http.HttpRequestException)
        {
            Debug.WriteLine("Exception raised is: " +
                ex.GetType().ToString() +
                " –Message: " + ex.Message +
                " -- Inner Message: " +
                ex.InnerException.Message);
            await backoff.Delay();
            goto retry;
        }
    }
}

public struct ExponentialBackoff
{
    private readonly int m_maxRetries, m_delayMilliseconds, m_maxDelayMilliseconds;
    private int m_retries, m_pow;

    public ExponentialBackoff(int maxRetries, int delayMilliseconds,
        int maxDelayMilliseconds)
    {
        m_maxRetries = maxRetries;
        m_delayMilliseconds = delayMilliseconds;
        m_maxDelayMilliseconds = maxDelayMilliseconds;
        m_retries = 0;
        m_pow = 1;
    }

    public Task Delay()
    {
        if (m_retries == m_maxRetries)
        {
            throw new TimeoutException("Max retry attempts exceeded.");
        }
        ++m_retries;
        if (m_retries < 31)
        {
            m_pow = m_pow << 1; // m_pow = Pow(2, m_retries - 1)
        }
        int delay = Math.Min(m_delayMilliseconds * (m_pow - 1) / 2,
            m_maxDelayMilliseconds);
        return Task.Delay(delay);
    }
}
```

<span data-ttu-id="2cc7f-110">Usar este código en una aplicación de cliente C\# (otro microservicio de cliente API Web, una aplicación ASP.NET MVC o incluso una aplicación Xamarin C\#) es sencillo.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="2cc7f-111">En el ejemplo siguiente se muestra cómo hacerlo, mediante la clase HttpClient.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-111">The following example shows how, using the HttpClient class.</span></span>

```csharp
public async Task<Catalog> GetCatalogItems(int page,int take, int? brand, int? type)
{
    _apiClient = new HttpClient();
    var itemsQs = $"items?pageIndex={page}&pageSize={take}";
    var filterQs = "";
    var catalogUrl = $"{_remoteServiceBaseUrl}items{filterQs}?pageIndex={page}&pageSize={take}";
    var dataString = "";
    //
    // Using HttpClient with Retry and Exponential Backoff
    //
    var retry = new RetryWithExponentialBackoff();
    await retry.RunAsync(async () =>
    {
        // work with HttpClient call
        dataString = await _apiClient.GetStringAsync(catalogUrl);
    });
    return JsonConvert.DeserializeObject<Catalog>(dataString);
}
```

<span data-ttu-id="2cc7f-112">Sin embargo, este código es adecuado solo como prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-112">However, this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="2cc7f-113">En el tema siguiente se explica cómo usar bibliotecas más sofisticadas y probadas.</span><span class="sxs-lookup"><span data-stu-id="2cc7f-113">The next topic explains how to use more sophisticated and proven libraries.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="2cc7f-114">[Anterior](implement-resilient-entity-framework-core-sql-connections.md)
[Siguiente](implement-http-call-retries-exponential-backoff-polly.md)</span><span class="sxs-lookup"><span data-stu-id="2cc7f-114">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](implement-http-call-retries-exponential-backoff-polly.md)</span></span>
