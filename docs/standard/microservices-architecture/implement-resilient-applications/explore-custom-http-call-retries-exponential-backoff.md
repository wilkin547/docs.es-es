---
title: Exploración de reintentos de llamada HTTP personalizados con retroceso exponencial
description: Obtenga información sobre cómo podría implementar, desde el principio, los reintentos de llamada HTTP con retroceso exponencial para controlar posibles escenarios de error de HTTP.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 06/08/2018
ms.openlocfilehash: c323b8c4e783ed18c601562cfb25e1ca4986d499
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2018
ms.locfileid: "37878752"
---
# <a name="explore-custom-http-call-retries-with-exponential-backoff"></a>Exploración de reintentos de llamada HTTP personalizados con retroceso exponencial

Para crear microservicios resistentes, debe controlar los posibles escenarios de error HTTP. Una manera de controlar esos errores, aunque no se recomienda, consiste en crear una implementación de reintentos propia con retroceso exponencial.

**Nota importante:** En esta sección se muestra cómo se puede crear código personalizado propio para implementar los reintentos de llamada HTTP. Pero no se recomienda hacerlo por su cuenta, sino usar mecanismos más eficaces y confiables, aunque más sencillos, como `HttpClientFactory` con Polly, disponible desde .NET Core 2.1. Esos enfoques recomendados se explican en las secciones siguientes. 

Como exploración inicial, se podría implementar código propio con una clase de utilidad para retroceso exponencial como en [RetryWithExponentialBackoff.cs](https://gist.github.com/CESARDELATORRE/6d7f647b29e55fdc219ee1fd2babb260), junto con código similar al siguiente (que también está disponible en este [repositorio de GitHub](https://gist.github.com/CESARDELATORRE/d80c6423a1aebaffaf387469f5194f5b)).

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

Usar este código en una aplicación de cliente C\# (otro microservicio de cliente API Web, una aplicación ASP.NET MVC o incluso una aplicación Xamarin C\#) es sencillo. En el ejemplo siguiente se muestra cómo hacerlo, mediante la clase HttpClient.

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

Recuerde que este código solo es adecuado como prueba de concepto. En las secciones siguientes se explica cómo usar enfoques más sofisticados, aunque más sencillos, con HttpClientFactory.
HttpClientFactory está disponible desde .NET Core 2.1, con bibliotecas de resistencia de eficacia probada, como Polly. 


>[!div class="step-by-step"]
[Anterior](implement-resilient-entity-framework-core-sql-connections.md)
[Siguiente](use-httpclientfactory-to-implement-resilient-http-requests.md)