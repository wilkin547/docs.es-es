---
title: Exploración de reintentos de llamada HTTP personalizados con retroceso exponencial
description: Obtenga información sobre cómo podría implementar, desde el principio, los reintentos de llamada HTTP con retroceso exponencial para controlar posibles escenarios de error de HTTP.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/16/2018
ms.openlocfilehash: fdbc09cddde34cb8897e1d5b105cb15c863b59ce
ms.sourcegitcommit: 542aa405b295955eb055765f33723cb8b588d0d0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2019
ms.locfileid: "54362254"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a><span data-ttu-id="6a0f6-103">Exploración de reintentos de llamada HTTP personalizados con retroceso exponencial</span><span class="sxs-lookup"><span data-stu-id="6a0f6-103">Explore custom HTTP call retries with exponential backoff</span></span>

<span data-ttu-id="6a0f6-104">Para crear microservicios resistentes, debe controlar los posibles escenarios de error HTTP.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-104">To create resilient microservices, you need to handle possible HTTP failure scenarios.</span></span> <span data-ttu-id="6a0f6-105">Una manera de controlar esos errores, aunque no se recomienda, consiste en crear una implementación de reintentos propia con retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-105">One way of handling those failures, although not recommended, is to create your own implementation of retries with exponential backoff.</span></span>

<span data-ttu-id="6a0f6-106">**Nota importante:** En esta sección se muestra cómo se puede crear código personalizado propio para implementar los reintentos de llamada HTTP.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-106">**Important note:** This section shows you how you could create your own custom code to implement HTTP call retries.</span></span> <span data-ttu-id="6a0f6-107">Pero no se recomienda hacerlo por su cuenta, sino usar mecanismos más eficaces y confiables, aunque más sencillos, como `HttpClientFactory` con Polly, disponible desde .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-107">However, it isn't recommended to do it on your own but to use more powerful and reliable while simpler to use mechanisms, such as `HttpClientFactory` with Polly, available since .NET Core 2.1.</span></span> <span data-ttu-id="6a0f6-108">Esos enfoques recomendados se explican en las secciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-108">Those recommended approaches are explained in the next sections.</span></span>

<span data-ttu-id="6a0f6-109">Como exploración inicial, podría implementar su propio código con una clase de utilidad para retroceso exponencial como [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), junto con código similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-109">As an initial exploration, you could implement your own code with a utility class for exponential backoff as in [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), plus code like the following.</span></span>

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

<span data-ttu-id="6a0f6-110">Usar este código en una aplicación de cliente C\# (otro microservicio de cliente API Web, una aplicación ASP.NET MVC o incluso una aplicación Xamarin C\#) es sencillo.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-110">Using this code in a client C\# application (another Web API client microservice, an ASP.NET MVC application, or even a C\# Xamarin application) is straightforward.</span></span> <span data-ttu-id="6a0f6-111">En el ejemplo siguiente se muestra cómo hacerlo, mediante la clase HttpClient.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-111">The following example shows how, using the HttpClient class.</span></span>

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

<span data-ttu-id="6a0f6-112">Recuerde que este código solo es adecuado como prueba de concepto.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-112">Remember that this code is suitable only as a proof of concept.</span></span> <span data-ttu-id="6a0f6-113">En las secciones siguientes se explica cómo usar enfoques más sofisticados, aunque más sencillos, con HttpClientFactory.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-113">The next sections explain how to use more sophisticated approaches while simpler, by using HttpClientFactory.</span></span> <span data-ttu-id="6a0f6-114">HttpClientFactory está disponible desde .NET Core 2.1, con bibliotecas de resistencia de eficacia probada, como Polly.</span><span class="sxs-lookup"><span data-stu-id="6a0f6-114">HttpClientFactory is available since .NET Core 2.1, with proven resiliency libraries like Polly.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6a0f6-115">[Anterior](implement-resilient-entity-framework-core-sql-connections.md)
>[Siguiente](use-httpclientfactory-to-implement-resilient-http-requests.md)</span><span class="sxs-lookup"><span data-stu-id="6a0f6-115">[Previous](implement-resilient-entity-framework-core-sql-connections.md)
[Next](use-httpclientfactory-to-implement-resilient-http-requests.md)</span></span>