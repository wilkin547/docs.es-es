---
title: El bloque de creación de invocación del servicio DAPR
description: Una descripción del bloque de creación de invocación de servicio, sus características, ventajas y cómo aplicarla
author: amolenk
ms.date: 02/07/2021
ms.openlocfilehash: 2b64aa1e9b079a3fefe120e687cd6d395981c633
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401842"
---
# <a name="the-dapr-service-invocation-building-block"></a><span data-ttu-id="932e0-103">El bloque de creación de invocación del servicio DAPR</span><span class="sxs-lookup"><span data-stu-id="932e0-103">The Dapr service invocation building block</span></span>

<span data-ttu-id="932e0-104">En un sistema distribuido, un servicio a menudo necesita comunicarse con otro para completar una operación empresarial.</span><span class="sxs-lookup"><span data-stu-id="932e0-104">Across a distributed system, one service often needs to communicate with another to complete a business operation.</span></span> <span data-ttu-id="932e0-105">El [bloque de creación de invocación del servicio DAPR](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) puede ayudar a simplificar la comunicación entre los servicios.</span><span class="sxs-lookup"><span data-stu-id="932e0-105">The [Dapr service invocation building block](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/) can help streamline the communication between services.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="932e0-106">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="932e0-106">What it solves</span></span>

<span data-ttu-id="932e0-107">Es posible que las llamadas entre los servicios de una aplicación distribuida parezcan sencillas, pero hay muchos desafíos.</span><span class="sxs-lookup"><span data-stu-id="932e0-107">Making calls between services in a distributed application may appear easy, but there are many challenges involved.</span></span> <span data-ttu-id="932e0-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="932e0-108">For example:</span></span>

- <span data-ttu-id="932e0-109">Dónde se encuentran los otros servicios.</span><span class="sxs-lookup"><span data-stu-id="932e0-109">Where the other services are located.</span></span>
- <span data-ttu-id="932e0-110">Cómo llamar a un servicio de forma segura, dada la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-110">How to call a service securely, given the service address.</span></span>
- <span data-ttu-id="932e0-111">Cómo controlar los reintentos cuando se producen [errores transitorios](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) de corta duración.</span><span class="sxs-lookup"><span data-stu-id="932e0-111">How to handle retries when short-lived [transient errors](/aspnet/aspnet/overview/developing-apps-with-windows-azure/building-real-world-cloud-apps-with-windows-azure/transient-fault-handling) occur.</span></span>

<span data-ttu-id="932e0-112">Por último, a medida que las aplicaciones distribuidas componen muchos servicios diferentes, la captura de información en los gráficos de llamadas de servicio es fundamental para diagnosticar los problemas de producción.</span><span class="sxs-lookup"><span data-stu-id="932e0-112">Lastly, as distributed applications compose many different services, capturing insights across service call graphs are critical to diagnosing production issues.</span></span>

<span data-ttu-id="932e0-113">El bloque de creación de invocación de servicio soluciona estos desafíos mediante el uso de un sidecar de DAPR como un [proxy inverso](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) para su servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-113">The service invocation building block addresses these challenges by using a Dapr sidecar as a [reverse proxy](https://kemptechnologies.com/reverse-proxy/reverse-proxy/) for your service.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="932e0-114">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="932e0-114">How it works</span></span>

<span data-ttu-id="932e0-115">Comencemos con un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="932e0-115">Let's start with an example.</span></span> <span data-ttu-id="932e0-116">Considere dos servicios, "servicio A" y "servicio B".</span><span class="sxs-lookup"><span data-stu-id="932e0-116">Consider two services, "Service A" and "Service B".</span></span> <span data-ttu-id="932e0-117">El servicio a necesita llamar a la `catalog/items` API en el servicio B. Aunque el servicio A podría tomar una dependencia del servicio B y realizar una llamada directa a él, el servicio A invoca la API de invocación del servicio en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-117">Service A needs to call the `catalog/items` API on Service B. While Service A could take a dependency on Service B and make a direct call to it, Service A instead invokes the service invocation API on the Dapr sidecar.</span></span> <span data-ttu-id="932e0-118">En la figura 6-1 se muestra la operación.</span><span class="sxs-lookup"><span data-stu-id="932e0-118">Figure 6-1 shows the operation.</span></span>

![Cómo funciona la invocación del servicio DAPR](./media/service-invocation/service-invocation-flow.png)

<span data-ttu-id="932e0-120">**Figura 6-1**.</span><span class="sxs-lookup"><span data-stu-id="932e0-120">**Figure 6-1**.</span></span> <span data-ttu-id="932e0-121">Cómo funciona la invocación del servicio DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-121">How Dapr service invocation works.</span></span>

<span data-ttu-id="932e0-122">Tenga en cuenta los pasos de la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="932e0-122">Note the steps from the previous figure:</span></span>

1. <span data-ttu-id="932e0-123">El servicio A realiza una llamada al `catalog/items` punto de conexión en el servicio B mediante la invocación de la API de invocación del servicio en el servicio a sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-123">Service A makes a call to the `catalog/items` endpoint in Service B by invoking the service invocation API on the Service A sidecar.</span></span>

    > [!NOTE]
    > <span data-ttu-id="932e0-124">El sidecar usa un mecanismo de resolución de nombres conectable para resolver la dirección del servicio B. En el modo autohospedado, DAPR usa [MDN](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) para encontrarlo.</span><span class="sxs-lookup"><span data-stu-id="932e0-124">The sidecar uses a pluggable name resolution mechanism to resolve the address of Service B. In self-hosted mode, Dapr uses [mDNS](https://www.ionos.com/digitalguide/server/know-how/multicast-dns/) to find it.</span></span> <span data-ttu-id="932e0-125">Cuando se ejecuta en modo Kubernetes, el servicio DNS de Kubernetes determina la dirección.</span><span class="sxs-lookup"><span data-stu-id="932e0-125">When running in Kubernetes mode, the Kubernetes DNS service determines the address.</span></span>  

1. <span data-ttu-id="932e0-126">El servicio un sidecar reenvía la solicitud al sidecar del servicio B.</span><span class="sxs-lookup"><span data-stu-id="932e0-126">The Service A sidecar forwards the request to the Service B sidecar.</span></span>

1. <span data-ttu-id="932e0-127">El sidecar del servicio B realiza la `catalog/items` solicitud real contra la API del servicio b.</span><span class="sxs-lookup"><span data-stu-id="932e0-127">The Service B sidecar makes the actual `catalog/items` request against the Service B API.</span></span>

1. <span data-ttu-id="932e0-128">El servicio B ejecuta la solicitud y devuelve una respuesta a su sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-128">Service B executes the request and returns a response back to its sidecar.</span></span>

1. <span data-ttu-id="932e0-129">El servicio B sidecar reenvía la respuesta al servicio a sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-129">The Service B sidecar forwards the response back to the Service A sidecar.</span></span>

1. <span data-ttu-id="932e0-130">El servicio A sidecar devuelve la respuesta al servicio a.</span><span class="sxs-lookup"><span data-stu-id="932e0-130">The Service A sidecar returns the response back to Service A.</span></span>

<span data-ttu-id="932e0-131">Dado que las llamadas fluyen a través de sidecar, DAPR puede inyectar algunos comportamientos de corte transversal útiles:</span><span class="sxs-lookup"><span data-stu-id="932e0-131">Because the calls flow through sidecars, Dapr can inject some useful cross-cutting behaviors:</span></span>

- <span data-ttu-id="932e0-132">Reintentar llamadas automáticamente en caso de error.</span><span class="sxs-lookup"><span data-stu-id="932e0-132">Automatically retry calls upon failure.</span></span>
- <span data-ttu-id="932e0-133">Realizar llamadas entre servicios seguros con autenticación mutua (mTLS), incluida la sustitución automática de certificados.</span><span class="sxs-lookup"><span data-stu-id="932e0-133">Make calls between services secure with mutual (mTLS) authentication, including automatic certificate rollover.</span></span>
- <span data-ttu-id="932e0-134">Controlar qué operaciones pueden realizar los clientes mediante directivas de control de acceso.</span><span class="sxs-lookup"><span data-stu-id="932e0-134">Control what operations clients can do using access control policies.</span></span>
- <span data-ttu-id="932e0-135">Capture los seguimientos y las métricas de todas las llamadas entre servicios para proporcionar información y diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="932e0-135">Capture traces and metrics for all calls between services to provide insights and diagnostics.</span></span>

<span data-ttu-id="932e0-136">Cualquier aplicación puede invocar un sidecar de DAPR mediante la API de **invocación** nativa integrada en DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-136">Any application can invoke a Dapr sidecar by using the native **invoke** API built into Dapr.</span></span> <span data-ttu-id="932e0-137">Se puede llamar a la API con HTTP o gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-137">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="932e0-138">Use la siguiente dirección URL para llamar a la API HTTP:</span><span class="sxs-lookup"><span data-stu-id="932e0-138">Use the following URL to call the HTTP API:</span></span>

``` http
http://localhost:<dapr-port>/v1.0/invoke/<application-id>/method/<method-name>
```

- <span data-ttu-id="932e0-139">`<dapr-port>` el puerto HTTP en el que escucha DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-139">`<dapr-port>` the HTTP port that Dapr is listening on.</span></span>
- <span data-ttu-id="932e0-140">`<application-id>` IDENTIFICADOR de la aplicación del servicio que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="932e0-140">`<application-id>` application ID of the service to call.</span></span>
- <span data-ttu-id="932e0-141">`<method-name>` nombre del método que se va a invocar en el servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="932e0-141">`<method-name>` name of the method to invoke on the remote service.</span></span>

<span data-ttu-id="932e0-142">En el ejemplo siguiente, se realiza una llamada a *rizo* en el `catalog/items` punto de conexión "Get" de `Service B` :</span><span class="sxs-lookup"><span data-stu-id="932e0-142">In the following example, a *curl* call is made to the `catalog/items` 'GET' endpoint of `Service B`:</span></span>

```console
curl http://localhost:3500/v1.0/invoke/serviceb/method/catalog/items
```

> [!NOTE]
> <span data-ttu-id="932e0-143">Las API de DAPR habilitan cualquier pila de aplicaciones que admita HTTP o gRPC para usar los bloques de creación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-143">The Dapr APIs enable any application stack that supports HTTP or gRPC to use Dapr building blocks.</span></span> <span data-ttu-id="932e0-144">Por lo tanto, el bloque de creación de invocación del servicio puede actuar como un puente entre los protocolos.</span><span class="sxs-lookup"><span data-stu-id="932e0-144">Therefore, the service invocation building block can act as a bridge between protocols.</span></span> <span data-ttu-id="932e0-145">Los servicios pueden comunicarse entre sí mediante HTTP, gRPC o una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="932e0-145">Services can communicate with each other using HTTP, gRPC or a combination of both.</span></span>

<span data-ttu-id="932e0-146">En la sección siguiente, aprenderá a usar el SDK de .NET para simplificar las llamadas de invocación de servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-146">In the next section, you'll learn how to use the .NET SDK to simplify service invocation calls.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="932e0-147">Uso del SDK de .NET para DAPR</span><span class="sxs-lookup"><span data-stu-id="932e0-147">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="932e0-148">El [SDK de .net](https://github.com/dapr/dotnet-sdk) para DAPR proporciona a los desarrolladores de .net una forma intuitiva y específica del lenguaje de interactuar con DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-148">The Dapr [.NET SDK](https://github.com/dapr/dotnet-sdk) provides .NET developers with an intuitive and language-specific way to interact with Dapr.</span></span> <span data-ttu-id="932e0-149">El SDK ofrece a los desarrolladores tres maneras de realizar llamadas de invocación del servicio remoto:</span><span class="sxs-lookup"><span data-stu-id="932e0-149">The SDK offers developers three ways of making remote service invocation calls:</span></span>

1. <span data-ttu-id="932e0-150">Invocar servicios HTTP mediante HttpClient</span><span class="sxs-lookup"><span data-stu-id="932e0-150">Invoke HTTP services using HttpClient</span></span>
1. <span data-ttu-id="932e0-151">Invocar servicios HTTP mediante DaprClient</span><span class="sxs-lookup"><span data-stu-id="932e0-151">Invoke HTTP services using DaprClient</span></span>
1. <span data-ttu-id="932e0-152">Invocar servicios gRPC mediante DaprClient</span><span class="sxs-lookup"><span data-stu-id="932e0-152">Invoke gRPC services using DaprClient</span></span>

### <a name="invoke-http-services-using-httpclient"></a><span data-ttu-id="932e0-153">Invocar servicios HTTP mediante HttpClient</span><span class="sxs-lookup"><span data-stu-id="932e0-153">Invoke HTTP services using HttpClient</span></span>

<span data-ttu-id="932e0-154">La mejor manera de llamar a un punto de conexión HTTP es usar la integración enriquecida de DAPR con `HttpClient` .</span><span class="sxs-lookup"><span data-stu-id="932e0-154">The preferred way to call an HTTP endpoint is to use Dapr's rich integration with `HttpClient`.</span></span> <span data-ttu-id="932e0-155">En el ejemplo siguiente se envía un pedido llamando al `submit` método de la `orderservice` aplicación:</span><span class="sxs-lookup"><span data-stu-id="932e0-155">The following example submits an order by calling the `submit` method of the `orderservice` application:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient();
await httpClient.PostAsJsonAsync("http://orderservice/submit", order);
```

<span data-ttu-id="932e0-156">En el ejemplo, `DaprClient.CreateHttpClient` devuelve una `HttpClient` instancia de que se usa para realizar la invocación del servicio DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-156">In the example, `DaprClient.CreateHttpClient` returns an `HttpClient` instance that is used to perform Dapr service invocation.</span></span> <span data-ttu-id="932e0-157">El devuelto `HttpClient` utiliza un controlador de mensajes DAPR especial que reescribe los URI de las solicitudes salientes.</span><span class="sxs-lookup"><span data-stu-id="932e0-157">The returned `HttpClient` uses a special Dapr message handler that rewrites URIs of outgoing requests.</span></span> <span data-ttu-id="932e0-158">El nombre de host se interpreta como el identificador de la aplicación del servicio al que se va a llamar.</span><span class="sxs-lookup"><span data-stu-id="932e0-158">The host name is interpreted as the application ID of the service to call.</span></span> <span data-ttu-id="932e0-159">La solicitud reescrita que se está llamando realmente es:</span><span class="sxs-lookup"><span data-stu-id="932e0-159">The rewritten request that's actually being called is:</span></span>

```http
http://127.0.0.1:3500/v1/invoke/orderservice/method/submit
```

<span data-ttu-id="932e0-160">En este ejemplo se usa el valor predeterminado para el punto de conexión HTTP DAPR, que es `http://127.0.0.1:<dapr-http-port>/` .</span><span class="sxs-lookup"><span data-stu-id="932e0-160">This example uses the default value for the Dapr HTTP endpoint, which is `http://127.0.0.1:<dapr-http-port>/`.</span></span> <span data-ttu-id="932e0-161">El valor de `dapr-http-port` se toma de la `DAPR_HTTP_PORT` variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="932e0-161">The value of `dapr-http-port` is taken from the `DAPR_HTTP_PORT` environment variable.</span></span> <span data-ttu-id="932e0-162">Si no se establece, se usa el número de puerto predeterminado `3500` .</span><span class="sxs-lookup"><span data-stu-id="932e0-162">If it's not set, the default port number `3500` is used.</span></span>

<span data-ttu-id="932e0-163">Como alternativa, puede configurar un punto de conexión personalizado en la llamada a `DaprClient.CreateHttpClient` :</span><span class="sxs-lookup"><span data-stu-id="932e0-163">Alternatively, you can configure a custom endpoint in the call to `DaprClient.CreateHttpClient`:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient(daprEndpoint = "localhost:4000");
```

<span data-ttu-id="932e0-164">También puede establecer directamente la dirección base especificando el identificador de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="932e0-164">You can also directly set the base address by specifying the application ID.</span></span> <span data-ttu-id="932e0-165">Esto hace posible el uso de URI relativos al realizar una llamada:</span><span class="sxs-lookup"><span data-stu-id="932e0-165">This makes it possible to use relative URIs when making a call:</span></span>

```csharp
var httpClient = DaprClient.CreateHttpClient("orderservice");
await httpClient.PostAsJsonAsync("/submit");
```

<span data-ttu-id="932e0-166">El `HttpClient` objeto está pensado para tener una duración prolongada.</span><span class="sxs-lookup"><span data-stu-id="932e0-166">The `HttpClient` object is intended to be long-lived.</span></span> <span data-ttu-id="932e0-167">Una sola `HttpClient` instancia se puede reutilizar durante la vigencia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="932e0-167">A single `HttpClient` instance can be reused for the lifetime of the application.</span></span> <span data-ttu-id="932e0-168">En el escenario siguiente se muestra cómo una `OrderServiceClient` clase vuelve a usar una instancia de DAPR `HttpClient` :</span><span class="sxs-lookup"><span data-stu-id="932e0-168">The next scenario demonstrates how an `OrderServiceClient` class reuses a Dapr `HttpClient` instance:</span></span>  

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddSingleton<IOrderServiceClient, OrderServiceClient>(
        _ => new OrderServiceClient(DaprClient.CreateInvokeHttpClient("orderservice")));
}
```

<span data-ttu-id="932e0-169">En el fragmento de código anterior, `OrderServiceClient` se registra como singleton con el sistema de inserción de dependencias ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="932e0-169">In the snippet above, the `OrderServiceClient` is registered as a singleton with the ASP.NET Core dependency injection system.</span></span> <span data-ttu-id="932e0-170">Un generador de implementación crea una nueva `HttpClient` instancia de mediante una llamada a `DaprClient.CreateInvokeHttpClient` .</span><span class="sxs-lookup"><span data-stu-id="932e0-170">An implementation factory creates a new `HttpClient` instance by calling `DaprClient.CreateInvokeHttpClient`.</span></span> <span data-ttu-id="932e0-171">A continuación, usa el recién creado `HttpClient` para crear instancias del `OrderServiceClient` objeto.</span><span class="sxs-lookup"><span data-stu-id="932e0-171">It then uses the newly created `HttpClient` to instantiate the `OrderServiceClient` object.</span></span> <span data-ttu-id="932e0-172">Al registrar `OrderServiceClient` como singleton, se volverá a usar durante la vigencia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="932e0-172">By registering the `OrderServiceClient` as a singleton, it will be reused for the lifetime of the application.</span></span>

<span data-ttu-id="932e0-173">El `OrderServiceClient` propio no tiene código específico de DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-173">The `OrderServiceClient` itself has no Dapr-specific code.</span></span> <span data-ttu-id="932e0-174">Aunque la invocación del servicio DAPR se usa en el capó, puede tratar el HttpClient de DAPR como cualquier otro HttpClient:</span><span class="sxs-lookup"><span data-stu-id="932e0-174">Even though Dapr service invocation is used under the hood, you can treat the Dapr HttpClient like any other HttpClient:</span></span>

```csharp
public class OrderServiceClient : IOrderServiceClient
{
    private readonly HttpClient _httpClient;

    public OrderServiceClient(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public async Task SubmitOrder(Order order)
    {
        var response = await _httpClient.PostAsJsonAsync("submit", order);
        response.EnsureSuccessStatusCode();
    }
}
```

<span data-ttu-id="932e0-175">El uso de la clase HttpClient con la invocación del servicio DAPR tiene muchas ventajas:</span><span class="sxs-lookup"><span data-stu-id="932e0-175">Using the HttpClient class with Dapr service invocation has many benefits:</span></span>

- <span data-ttu-id="932e0-176">HttpClient es una clase conocida que muchos desarrolladores ya usan en su código.</span><span class="sxs-lookup"><span data-stu-id="932e0-176">HttpClient is a well-known class that many developers already use in their code.</span></span> <span data-ttu-id="932e0-177">El uso de HttpClient para la invocación del servicio DAPR permite a los desarrolladores reutilizar sus conocimientos existentes.</span><span class="sxs-lookup"><span data-stu-id="932e0-177">Using HttpClient for Dapr service invocation allows developers to reuse their existing skills.</span></span>
- <span data-ttu-id="932e0-178">HttpClient admite escenarios avanzados, como encabezados personalizados, y control total sobre los mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="932e0-178">HttpClient supports advanced scenarios, such as custom headers, and full control over request and response messages.</span></span>
- <span data-ttu-id="932e0-179">En .NET 5, HttpClient admite la serialización y deserialización automáticas mediante System.Text.Jsen.</span><span class="sxs-lookup"><span data-stu-id="932e0-179">In .NET 5, HttpClient supports automatic serialization and deserialization using System.Text.Json.</span></span>
- <span data-ttu-id="932e0-180">HttpClient se integra con muchos marcos y bibliotecas existentes [, como ajustar,](https://github.com/reactiveui/refit) [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage)y [Polly](https://github.com/App-vNext/Polly).</span><span class="sxs-lookup"><span data-stu-id="932e0-180">HttpClient integrates with many existing frameworks and libraries, such as [Refit](https://github.com/reactiveui/refit), [RestSharp](https://restsharp.dev/getting-started/getting-started.html#basic-usage), and [Polly](https://github.com/App-vNext/Polly).</span></span>

### <a name="invoke-http-services-using-daprclient"></a><span data-ttu-id="932e0-181">Invocar servicios HTTP mediante DaprClient</span><span class="sxs-lookup"><span data-stu-id="932e0-181">Invoke HTTP services using DaprClient</span></span>

<span data-ttu-id="932e0-182">Aunque HttpClient es la manera preferida de invocar servicios mediante la semántica de HTTP, también puede usar la `DaprClient.InvokeMethodAsync` familia de métodos.</span><span class="sxs-lookup"><span data-stu-id="932e0-182">While HttpClient is the preferred way to invoke services using HTTP semantics, you can also use the `DaprClient.InvokeMethodAsync` family of methods.</span></span> <span data-ttu-id="932e0-183">En el ejemplo siguiente se envía un pedido llamando al `submit` método de la `orderservice` aplicación:</span><span class="sxs-lookup"><span data-stu-id="932e0-183">The following example submits an order by calling the `submit` method of the `orderservice` application:</span></span>

``` csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation =
        await daprClient.InvokeMethodAsync<Order, OrderConfirmation>(
            "orderservice", "submit", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

<span data-ttu-id="932e0-184">El tercer argumento, un `order` objeto, se serializa internamente (con `System.Text.JsonSerializer` ) y se envía como la carga de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="932e0-184">The third argument, an `order` object, is serialized internally (with `System.Text.JsonSerializer`) and sent as the request payload.</span></span> <span data-ttu-id="932e0-185">El SDK de .NET se encarga de la llamada al sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-185">The .NET SDK takes care of the call to the sidecar.</span></span> <span data-ttu-id="932e0-186">También deserializa la respuesta a un `OrderConfirmation` objeto.</span><span class="sxs-lookup"><span data-stu-id="932e0-186">It also deserializes the response to an `OrderConfirmation` object.</span></span> <span data-ttu-id="932e0-187">Dado que no se especifica ningún método HTTP, la solicitud se ejecuta como HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="932e0-187">Because no HTTP method is specified, the request is executed as an HTTP POST.</span></span>

<span data-ttu-id="932e0-188">En el ejemplo siguiente se muestra cómo puede realizar una solicitud HTTP GET especificando `HttpMethod` :</span><span class="sxs-lookup"><span data-stu-id="932e0-188">The next example demonstrates how you can make an HTTP GET request by specifying the `HttpMethod`:</span></span>

```csharp
var catalogItems = await daprClient.InvokeMethodAsync<IEnumerable<CatalogItem>>(HttpMethod.Get, "catalogservice", "items");
```

<span data-ttu-id="932e0-189">En algunos escenarios, puede que necesite más control sobre el mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="932e0-189">For some scenarios, you may require more control over the request message.</span></span> <span data-ttu-id="932e0-190">Por ejemplo, si necesita especificar encabezados de solicitud o si desea utilizar un serializador personalizado para la carga útil.</span><span class="sxs-lookup"><span data-stu-id="932e0-190">For example, when you need to specify request headers, or you want to use a custom serializer for the payload.</span></span> <span data-ttu-id="932e0-191">`DaprClient.CreateInvokeMethodRequest` crea un `HttpRequestMessage` .</span><span class="sxs-lookup"><span data-stu-id="932e0-191">`DaprClient.CreateInvokeMethodRequest` creates an `HttpRequestMessage`.</span></span> <span data-ttu-id="932e0-192">En el ejemplo siguiente se muestra cómo agregar un encabezado de autorización HTTP a un mensaje de solicitud:</span><span class="sxs-lookup"><span data-stu-id="932e0-192">The following example demonstrates how to add an HTTP authorization header to a request message:</span></span>

```csharp
var request = daprClient.CreateInvokeMethodRequest("orderservice", "submit", order);
request.Headers.Authorization = new AuthenticationHeaderValue("bearer", token);
```

<span data-ttu-id="932e0-193">`HttpRequestMessage`Ahora tiene las siguientes propiedades establecidas:</span><span class="sxs-lookup"><span data-stu-id="932e0-193">The `HttpRequestMessage` now has the following properties set:</span></span>

- <span data-ttu-id="932e0-194">Dirección URL = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`</span><span class="sxs-lookup"><span data-stu-id="932e0-194">Url = `http://127.0.0.1:3500/v1.0/invoke/orderservice/method/submit`</span></span>
- <span data-ttu-id="932e0-195">HttpMethod = POST</span><span class="sxs-lookup"><span data-stu-id="932e0-195">HttpMethod = POST</span></span>
- <span data-ttu-id="932e0-196">Content =  `JsonContent` objeto que contiene la serialización JSON `order`</span><span class="sxs-lookup"><span data-stu-id="932e0-196">Content =  `JsonContent` object containing the JSON-serialized `order`</span></span>
- <span data-ttu-id="932e0-197">Headers. Authorization = "Bearer \<token> "</span><span class="sxs-lookup"><span data-stu-id="932e0-197">Headers.Authorization = "bearer \<token>"</span></span>

<span data-ttu-id="932e0-198">Una vez que haya configurado la solicitud de la forma que desee, use `DaprClient.InvokeMethodAsync` para enviarla:</span><span class="sxs-lookup"><span data-stu-id="932e0-198">Once you've got the request set up the way you want, use `DaprClient.InvokeMethodAsync` to send it:</span></span>

```csharp
var orderConfirmation = await daprClient.InvokeMethodAsync<OrderConfirmation>(request);
```

<span data-ttu-id="932e0-199">`DaprClient.InvokeMethodAsync` deserializa la respuesta a un `OrderConfirmation` objeto si la solicitud se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="932e0-199">`DaprClient.InvokeMethodAsync` deserializes the response to an `OrderConfirmation` object if the request is successful.</span></span> <span data-ttu-id="932e0-200">Como alternativa, puede usar `DaprClient.InvokeMethodWithResponseAsync` para obtener acceso completo al subyacente `HttpResponseMessage` :</span><span class="sxs-lookup"><span data-stu-id="932e0-200">Alternatively, you can use `DaprClient.InvokeMethodWithResponseAsync` to get full access to the underlying `HttpResponseMessage`:</span></span>

```csharp
var response = await daprClient.InvokeMethodWithResponseAsync(request);
response.EnsureSuccessStatusCode();

var orderConfirmation = response.Content.ReadFromJsonAsync<OrderConfirmation>();
```

> [!NOTE]
> <span data-ttu-id="932e0-201">En el caso de las llamadas de invocación de servicio mediante HTTP, merece la pena considerar el uso de la integración de HttpClient de DAPR presentada en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="932e0-201">For service invocation calls using HTTP, it's worth considering using the Dapr HttpClient integration presented in the previous section.</span></span> <span data-ttu-id="932e0-202">El uso de HttpClient ofrece ventajas adicionales, como la integración con Marcos y bibliotecas existentes.</span><span class="sxs-lookup"><span data-stu-id="932e0-202">Using HttpClient gives you additional benefits such as integration with existing frameworks and libraries.</span></span>

### <a name="invoke-grpc-services-using-daprclient"></a><span data-ttu-id="932e0-203">Invocar servicios gRPC mediante DaprClient</span><span class="sxs-lookup"><span data-stu-id="932e0-203">Invoke gRPC services using DaprClient</span></span>

<span data-ttu-id="932e0-204">DaprClient proporciona una familia de `InvokeMethodGrpcAsync` métodos para llamar a puntos de conexión de gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-204">DaprClient provides a family of `InvokeMethodGrpcAsync` methods for calling gRPC endpoints.</span></span> <span data-ttu-id="932e0-205">La principal diferencia con los métodos HTTP es el uso de un serializador protobuf en lugar de JSON.</span><span class="sxs-lookup"><span data-stu-id="932e0-205">The main difference with the HTTP methods is the use of a Protobuf serializer instead of JSON.</span></span> <span data-ttu-id="932e0-206">En el ejemplo siguiente se invoca el `submitOrder` método de `orderservice` sobre gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-206">The following example invokes the `submitOrder` method of the `orderservice` over gRPC.</span></span>

```csharp
var daprClient = new DaprClientBuilder().Build();
try
{
    var confirmation = await daprClient.InvokeMethodGrpcAsync<Order, OrderConfirmation>("orderservice", "submitOrder", order);
}
catch (InvocationException ex)
{
    // Handle error
}
```

<span data-ttu-id="932e0-207">En el ejemplo anterior, DaprClient serializa el objeto especificado `order` mediante [protobuf](https://developers.google.com/protocol-buffers) y usa el resultado como el cuerpo de la solicitud gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-207">In the example above, DaprClient serializes the given `order` object using [Protobuf](https://developers.google.com/protocol-buffers) and uses the result as the gRPC request body.</span></span> <span data-ttu-id="932e0-208">Del mismo modo, el cuerpo de la respuesta se protobuf deserializa y se devuelve al autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="932e0-208">Likewise, the response body is Protobuf deserialized and returned to the caller.</span></span> <span data-ttu-id="932e0-209">Protobuf suele proporcionar un mejor rendimiento que las cargas de JSON usadas en la invocación del servicio HTTP.</span><span class="sxs-lookup"><span data-stu-id="932e0-209">Protobuf typically provides better performance than the JSON payloads used in HTTP service invocation.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="932e0-210">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="932e0-210">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="932e0-211">La arquitectura de referencia de microservicios de [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) original de Microsoft usaba una combinación de servicios http/Rest y gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-211">The original [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) microservice reference architecture from Microsoft used a mix of HTTP/REST and gRPC services.</span></span> <span data-ttu-id="932e0-212">El uso de gRPC se limitó a la comunicación entre un [servicio de agregador](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) y servicios back-end básicos.</span><span class="sxs-lookup"><span data-stu-id="932e0-212">The use of gRPC was limited to communication between an [aggregator service](../cloud-native/service-to-service-communication.md#service-aggregator-pattern) and core back-end services.</span></span> <span data-ttu-id="932e0-213">En la figura 6-2 se muestra la arquitectura:</span><span class="sxs-lookup"><span data-stu-id="932e0-213">Figure 6-2 show the architecture:</span></span>

![llamadas a gRPC y HTTP/REST en eShopOnContainers](./media/service-invocation/eshop-on-containers.png)

<span data-ttu-id="932e0-215">**Figura 6-2**.</span><span class="sxs-lookup"><span data-stu-id="932e0-215">**Figure 6-2**.</span></span> <span data-ttu-id="932e0-216">llamadas a gRPC y HTTP/REST en eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="932e0-216">gRPC and HTTP/REST calls in eShopOnContainers.</span></span>

<span data-ttu-id="932e0-217">Tenga en cuenta los pasos de la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="932e0-217">Note the steps from the previous figure:</span></span>

1. <span data-ttu-id="932e0-218">El front-end llama a la [puerta de enlace de API](/azure/architecture/microservices/design/gateway) mediante http/REST.</span><span class="sxs-lookup"><span data-stu-id="932e0-218">The front end calls the [API gateway](/azure/architecture/microservices/design/gateway) using HTTP/REST.</span></span>

1. <span data-ttu-id="932e0-219">La puerta de enlace de API reenvía las solicitudes [CRUD](https://www.sumologic.com/glossary/crud/) (creación, lectura, actualización y eliminación) sencillas directamente a un servicio back-end básico mediante http/REST.</span><span class="sxs-lookup"><span data-stu-id="932e0-219">The API gateway forwards simple [CRUD](https://www.sumologic.com/glossary/crud/) (Create, Read, Update, Delete) requests directly to a core back-end service using HTTP/REST.</span></span>

1. <span data-ttu-id="932e0-220">La puerta de enlace de API reenvía las solicitudes complejas que implican llamadas coordinadas a varios servicios de back-end al servicio de agregador de la compra Web.</span><span class="sxs-lookup"><span data-stu-id="932e0-220">The API gateway forwards complex requests that involve coordinated calls to multiple back-end services to the web shopping aggregator service.</span></span>

1. <span data-ttu-id="932e0-221">El servicio Aggregator usa gRPC para llamar a los servicios back-end básicos.</span><span class="sxs-lookup"><span data-stu-id="932e0-221">The aggregator service uses gRPC to call core back-end services.</span></span>

<span data-ttu-id="932e0-222">En la implementación de eShopOnDapr actualizada recientemente, se agregan DAPR sidecar a los servicios y a la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="932e0-222">In the recently updated eShopOnDapr implementation, Dapr sidecars are added to the services and API gateway.</span></span> <span data-ttu-id="932e0-223">En la figura 6-3 se muestra la arquitectura actualizada:</span><span class="sxs-lookup"><span data-stu-id="932e0-223">Figure 6-3 show the updated architecture:</span></span>

![llamadas a gRPC y HTTP/REST con sidecar en eShopOnContainers](./media/service-invocation/eshop-on-dapr.png)

<span data-ttu-id="932e0-225">**Figura 6-3**.</span><span class="sxs-lookup"><span data-stu-id="932e0-225">**Figure 6-3**.</span></span> <span data-ttu-id="932e0-226">Arquitectura de eShop actualizada mediante DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-226">Updated eShop architecture using Dapr.</span></span>

<span data-ttu-id="932e0-227">Tenga en cuenta los pasos actualizados de la ilustración anterior:</span><span class="sxs-lookup"><span data-stu-id="932e0-227">Note the updated steps from the previous figure:</span></span>

1. <span data-ttu-id="932e0-228">El front-end todavía usa HTTP/REST para llamar a la puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="932e0-228">The front end still uses HTTP/REST to call the API gateway.</span></span>

1. <span data-ttu-id="932e0-229">La puerta de enlace de API reenvía las solicitudes HTTP a su sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-229">The API gateway forwards HTTP requests to its Dapr sidecar.</span></span>

1. <span data-ttu-id="932e0-230">La puerta de enlace de API sidecar envía la solicitud al sidecar del servicio back-end o del agregador.</span><span class="sxs-lookup"><span data-stu-id="932e0-230">The API gateway sidecar sends the request to the sidecar of the aggregator or back-end service.</span></span>

1. <span data-ttu-id="932e0-231">El servicio Aggregator usa el SDK de .NET de DAPR para llamar a servicios de back-end a través de su arquitectura de sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-231">The aggregator service uses the Dapr .NET SDK to call back-end services through their sidecar architecture.</span></span>

<span data-ttu-id="932e0-232">DAPR implementa llamadas entre sidecar con gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-232">Dapr implements calls between sidecars with gRPC.</span></span> <span data-ttu-id="932e0-233">Por tanto, incluso si está invocando un servicio remoto con la semántica HTTP/REST, una parte del transporte se sigue implementando mediante gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-233">So even if you're invoking a remote service with HTTP/REST semantics, a part of the transport is still implemented using gRPC.</span></span>

<span data-ttu-id="932e0-234">La aplicación de referencia eShopOnDapr se beneficia del bloque de creación de invocación del servicio DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-234">The eShopOnDapr reference application benefits from the Dapr service invocation building block.</span></span> <span data-ttu-id="932e0-235">Entre las ventajas se incluyen la detección de servicios, la mTLS automática y la observación.</span><span class="sxs-lookup"><span data-stu-id="932e0-235">The benefits include service discovery, automatic mTLS, and observability.</span></span>

### <a name="forward-http-requests-using-envoy-and-dapr"></a><span data-ttu-id="932e0-236">Reenviar solicitudes HTTP mediante envío y DAPR</span><span class="sxs-lookup"><span data-stu-id="932e0-236">Forward HTTP requests using Envoy and Dapr</span></span>

<span data-ttu-id="932e0-237">Tanto la aplicación de eShop original como la actualizada aprovechan el [proxy de envío](https://www.envoyproxy.io/) como puerta de enlace de API.</span><span class="sxs-lookup"><span data-stu-id="932e0-237">Both the original and updated eShop application leverage the [Envoy proxy](https://www.envoyproxy.io/) as an API gateway.</span></span> <span data-ttu-id="932e0-238">El envío es un proxy de código abierto y un bus de comunicación que es popular en aplicaciones distribuidas modernas.</span><span class="sxs-lookup"><span data-stu-id="932e0-238">Envoy is an open-source proxy and communication bus that is popular across modern distributed applications.</span></span> <span data-ttu-id="932e0-239">A partir de Lyft, el envío es propiedad de la [base informática nativa](https://www.cncf.io/)de la nube y la mantiene.</span><span class="sxs-lookup"><span data-stu-id="932e0-239">Originating from Lyft, Envoy is owned and maintained by the [Cloud-Native Computing Foundation](https://www.cncf.io/).</span></span>

<span data-ttu-id="932e0-240">En la implementación de eShopOnContainers original, la puerta de enlace de API de envío reenvió las solicitudes HTTP entrantes directamente al agregador o a los servicios back-end.</span><span class="sxs-lookup"><span data-stu-id="932e0-240">In the original eShopOnContainers implementation, the Envoy API gateway forwarded incoming HTTP requests directly to aggregator or back-end services.</span></span> <span data-ttu-id="932e0-241">En el nuevo eShopOnDapr, el proxy de envío reenvía la solicitud a un sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-241">In the new eShopOnDapr, the Envoy proxy forwards the request to a Dapr sidecar.</span></span> <span data-ttu-id="932e0-242">El sidecar proporciona invocación de servicio, mTLS y observabilidad.</span><span class="sxs-lookup"><span data-stu-id="932e0-242">The sidecar provides service invocation, mTLS, and observability.</span></span>

<span data-ttu-id="932e0-243">Los envíos se configuran mediante un archivo de definición de YAML para controlar el comportamiento del proxy.</span><span class="sxs-lookup"><span data-stu-id="932e0-243">Envoy is configured using a YAML definition file to control the proxy's behavior.</span></span> <span data-ttu-id="932e0-244">Para permitir que el envío reenvíe las solicitudes HTTP a un contenedor de DAPR sidecar, `dapr` se agrega un clúster a la configuración.</span><span class="sxs-lookup"><span data-stu-id="932e0-244">To enable Envoy to forward HTTP requests to a Dapr sidecar container, a `dapr` cluster is added to the configuration.</span></span> <span data-ttu-id="932e0-245">La configuración del clúster contiene un host que apunta al puerto HTTP en el que escucha el sidecar de DAPR:</span><span class="sxs-lookup"><span data-stu-id="932e0-245">The cluster configuration contains a host that points to the HTTP port on which the Dapr sidecar is listening:</span></span>

``` yaml
clusters:
- name: dapr
  connect_timeout: 0.25s
  type: strict_dns
  hosts:
  - socket_address:
    address: 127.0.0.1
    port_value: 3500
```

<span data-ttu-id="932e0-246">La configuración de rutas de envío se actualiza para reescribir las solicitudes entrantes como llamadas al sidecar DAPR (preste especial atención al `prefix_rewrite` par clave-valor):</span><span class="sxs-lookup"><span data-stu-id="932e0-246">The Envoy routes configuration is updated to rewrite incoming requests as calls to the Dapr sidecar (pay close attention to the `prefix_rewrite` key/value pair):</span></span>

``` yaml
- name: "c-short"
  match:
    prefix: "/c/"
  route:
    auto_host_rewrite: true
    prefix_rewrite: "/v1.0/invoke/catalog-api/method/"
    cluster: dapr
```

<span data-ttu-id="932e0-247">Considere un escenario en el que el cliente front-end desea recuperar una lista de elementos de catálogo.</span><span class="sxs-lookup"><span data-stu-id="932e0-247">Consider a scenario where the front-end client wants to retrieve a list of catalog items.</span></span> <span data-ttu-id="932e0-248">La API de catálogo proporciona un punto de conexión para obtener los elementos de catálogo:</span><span class="sxs-lookup"><span data-stu-id="932e0-248">The Catalog API provides an endpoint for getting the catalog items:</span></span>

``` csharp
[Route("api/v1/[controller]")]
[ApiController]
public class CatalogController : ControllerBase
{
    [HttpGet("items")]
    public async Task<IActionResult> ItemsAsync(
        [FromQuery] int pageSize = 10,
        [FromQuery] int pageIndex = 0)
    {
        // ...
    }
```

<span data-ttu-id="932e0-249">En primer lugar, el front-end realiza una llamada HTTP directa a la puerta de enlace de API de envío.</span><span class="sxs-lookup"><span data-stu-id="932e0-249">First, the front end makes a direct HTTP call to the Envoy API gateway.</span></span>

```
GET http://<api-gateway>/c/api/v1/catalog/items?pageSize=20
```

<span data-ttu-id="932e0-250">El proxy de envío coincide con la ruta, vuelve a escribir la solicitud HTTP y la reenvía a la `invoke` API de su sidecar de DAPR:</span><span class="sxs-lookup"><span data-stu-id="932e0-250">The Envoy proxy matches the route, rewrites the HTTP request, and forwards it to the `invoke` API of its Dapr sidecar:</span></span>

```
GET http://127.0.0.1:3500/v1.0/invoke/catalog-api/method/api/v1/catalog/items?pageSize=20
```

<span data-ttu-id="932e0-251">El sidecar controla la detección de servicios y enruta la solicitud al servicio de catálogo API sidecar.</span><span class="sxs-lookup"><span data-stu-id="932e0-251">The sidecar handles service discovery and routes the request to the Catalog API sidecar.</span></span> <span data-ttu-id="932e0-252">Por último, el sidecar llama a la API de catálogo para ejecutar la solicitud, capturar los elementos del catálogo y devolver una respuesta:</span><span class="sxs-lookup"><span data-stu-id="932e0-252">Finally, the sidecar calls the Catalog API to execute the request, fetch catalog items, and return a response:</span></span>

```
GET http://localhost/api/v1/catalog/items?pageSize=20
```

### <a name="make-aggregated-service-calls-using-the-net-sdk"></a><span data-ttu-id="932e0-253">Realizar llamadas de servicio agregadas mediante el SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="932e0-253">Make aggregated service calls using the .NET SDK</span></span>

<span data-ttu-id="932e0-254">La mayoría de las llamadas del front-end de eShop son llamadas CRUD simples.</span><span class="sxs-lookup"><span data-stu-id="932e0-254">Most calls from the eShop front end are simple CRUD calls.</span></span> <span data-ttu-id="932e0-255">La puerta de enlace de API los reenvía a un único servicio para su procesamiento.</span><span class="sxs-lookup"><span data-stu-id="932e0-255">The API gateway forwards them to a single service for processing.</span></span> <span data-ttu-id="932e0-256">Sin embargo, algunos escenarios requieren varios servicios back-end para que funcionen de forma conjunta para completar una solicitud.</span><span class="sxs-lookup"><span data-stu-id="932e0-256">Some scenarios, however, require multiple back-end services to work together to complete a request.</span></span> <span data-ttu-id="932e0-257">Para estas llamadas más complejas, eShop usa el servicio de agregador de la compra web para mediar el flujo de trabajo entre varios servicios.</span><span class="sxs-lookup"><span data-stu-id="932e0-257">For these more complex calls, eShop uses the web shopping aggregator service to mediate the workflow across multiple services.</span></span> <span data-ttu-id="932e0-258">En la figura 6-4 se muestra la secuencia de procesamiento de agregar un elemento a la cesta de la compra:</span><span class="sxs-lookup"><span data-stu-id="932e0-258">Figure 6-4 show the processing sequence of adding an item to your shopping basket:</span></span>

![Diagrama de la secuencia de actualización de la cesta](./media/service-invocation/complex-call.png)

<span data-ttu-id="932e0-260">**Figura 6-4**.</span><span class="sxs-lookup"><span data-stu-id="932e0-260">**Figure 6-4**.</span></span> <span data-ttu-id="932e0-261">Actualizar la secuencia de la cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="932e0-261">Update shopping basket sequence.</span></span>

<span data-ttu-id="932e0-262">El servicio de agregación recupera primero los elementos de catálogo de la API de catálogo.</span><span class="sxs-lookup"><span data-stu-id="932e0-262">The aggregator service first retrieves catalog items from the Catalog API.</span></span> <span data-ttu-id="932e0-263">Después, valida la disponibilidad y los precios de los elementos.</span><span class="sxs-lookup"><span data-stu-id="932e0-263">It then validates item availability and pricing.</span></span> <span data-ttu-id="932e0-264">Por último, el servicio agregador guarda la cesta de la compra actualizada llamando a la API basket.</span><span class="sxs-lookup"><span data-stu-id="932e0-264">Finally, the aggregator service saves the updated shopping basket by calling the Basket API.</span></span>

<span data-ttu-id="932e0-265">El servicio agregador contiene un `BasketController` que proporciona un punto de conexión para actualizar la cesta de la compra:</span><span class="sxs-lookup"><span data-stu-id="932e0-265">The aggregator service contains a `BasketController` that provides an endpoint for updating the shopping basket:</span></span>

``` csharp
[Route("api/v1/[controller]")]
[Authorize]
[ApiController]
public class BasketController : ControllerBase
{
    private readonly ICatalogService _catalog;
    private readonly IBasketService _basket;

    [HttpPost]
    [HttpPut]
    public async Task<ActionResult<BasketData>> UpdateAllBasketAsync(
        [FromBody] UpdateBasketRequest data, [FromHeader] string authorization)
    {
        // Get the item details from the catalog API.
        var catalogItems = await _catalog.GetCatalogItemsAsync(
            data.Items.Select(x => x.ProductId));

        // Check item availability and prices; store results in basket object.
        var basket = CreateValidatedBasket(data, catalogItems);

        // Save the shopping basket.
        await _basket.UpdateAsync(basket, authorization);

        return basket;
    }

    // ...
}
```

<span data-ttu-id="932e0-266">El `UpdateAllBasketAsync` método obtiene el encabezado *Authorization* de la solicitud entrante mediante un `FromHeader` atributo.</span><span class="sxs-lookup"><span data-stu-id="932e0-266">The `UpdateAllBasketAsync` method gets the *Authorization* header of the incoming request using a `FromHeader` attribute.</span></span> <span data-ttu-id="932e0-267">El encabezado *Authorization* contiene el token de acceso que se necesita para llamar a servicios back-end protegidos.</span><span class="sxs-lookup"><span data-stu-id="932e0-267">The *Authorization* header contains the access token that is needed to call protected back-end services.</span></span>

<span data-ttu-id="932e0-268">Después de recibir una solicitud para actualizar la cesta, el servicio agregador llama a la API de catálogo para obtener los detalles del elemento.</span><span class="sxs-lookup"><span data-stu-id="932e0-268">After receiving a request to update the basket, the aggregator service calls the Catalog API to get the item details.</span></span> <span data-ttu-id="932e0-269">El controlador de cesta utiliza un objeto insertado `ICatalogService` para hacer esa llamada y comunicarse con la API de catálogo.</span><span class="sxs-lookup"><span data-stu-id="932e0-269">The Basket controller uses an injected `ICatalogService` object to make that call and communicate with the Catalog API.</span></span> <span data-ttu-id="932e0-270">La implementación original de la interfaz usó gRPC para hacer la llamada.</span><span class="sxs-lookup"><span data-stu-id="932e0-270">The original implementation of the interface used gRPC to make the call.</span></span> <span data-ttu-id="932e0-271">La implementación actualizada usa la invocación del servicio DAPR con compatibilidad con HttpClient:</span><span class="sxs-lookup"><span data-stu-id="932e0-271">The updated implementation uses Dapr service invocation with HttpClient support:</span></span>

``` csharp
public class CatalogService : ICatalogService
{
    private readonly HttpClient _httpClient;

    public CatalogService(HttpClient httpClient)
    {
        _httpClient = httpClient ?? throw new ArgumentNullException(nameof(httpClient));
    }

    public Task<IEnumerable<CatalogItem>> GetCatalogItemsAsync(IEnumerable<int> ids)
    {
        var requestUri = $"api/v1/catalog/items?ids={string.Join(",", ids)}";

        return _httpClient.GetFromJsonAsync<IEnumerable<CatalogItem>>(requestUri);
    }

    // ...
}
```

<span data-ttu-id="932e0-272">Observe cómo no se requiere ningún código específico de DAPR para realizar la llamada de invocación del servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-272">Notice how no Dapr specific code is required to make the service invocation call.</span></span> <span data-ttu-id="932e0-273">Toda la comunicación se realiza mediante el objeto HttpClient estándar.</span><span class="sxs-lookup"><span data-stu-id="932e0-273">All communication is done using the standard HttpClient object.</span></span>

<span data-ttu-id="932e0-274">El HttpClient de DAPR se inserta en la `CatalogService` clase en el `Startup.ConfigureServices` método:</span><span class="sxs-lookup"><span data-stu-id="932e0-274">The Dapr HttpClient is injected into the `CatalogService` class in the `Startup.ConfigureServices` method:</span></span>

```csharp
services.AddSingleton<ICatalogService, CatalogService>(
    _ => new CatalogService(DaprClient.CreateInvokeHttpClient("catalog-api")));
```

<span data-ttu-id="932e0-275">La otra llamada realizada por el servicio Aggregator es a la API basket.</span><span class="sxs-lookup"><span data-stu-id="932e0-275">The other call made by the aggregator service is to the Basket API.</span></span> <span data-ttu-id="932e0-276">Solo permite solicitudes autorizadas.</span><span class="sxs-lookup"><span data-stu-id="932e0-276">It only allows authorized requests.</span></span> <span data-ttu-id="932e0-277">El token de acceso se pasa en un encabezado de solicitud de *autorización* para asegurarse de que la llamada se realiza correctamente:</span><span class="sxs-lookup"><span data-stu-id="932e0-277">The access token is passed along in an *Authorization* request header to ensure the call succeeds:</span></span>

``` csharp
public class BasketService : IBasketService
{
    public Task UpdateAsync(BasketData currentBasket, string accessToken)
    {
        var request = new HttpRequestMessage(HttpMethod.Post, "api/v1/basket")
        {
            Content = JsonContent.Create(currentBasket)
        };
        request.Headers.Authorization = new AuthenticationHeaderValue(accessToken);

        var response = await _httpClient.SendAsync(request);
        response.EnsureSuccessStatusCode();
    }

    // ...
}
```

<span data-ttu-id="932e0-278">En este ejemplo, solo se usa la funcionalidad HttpClient estándar para llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-278">In this example too, only standard HttpClient functionality is used to call the service.</span></span> <span data-ttu-id="932e0-279">Esto permite a los desarrolladores que ya están familiarizados con HttpClient reutilicen sus conocimientos existentes.</span><span class="sxs-lookup"><span data-stu-id="932e0-279">This allows developers who are already familiar with HttpClient to reuse their existing skills.</span></span> <span data-ttu-id="932e0-280">Incluso permite que el código HttpClient existente use la invocación del servicio DAPR sin realizar ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="932e0-280">It even enables existing HttpClient code to use Dapr service invocation without making any changes.</span></span>

## <a name="summary"></a><span data-ttu-id="932e0-281">Resumen</span><span class="sxs-lookup"><span data-stu-id="932e0-281">Summary</span></span>

<span data-ttu-id="932e0-282">En este capítulo, ha aprendido sobre el bloque de creación de invocación del servicio.</span><span class="sxs-lookup"><span data-stu-id="932e0-282">In this chapter, you learned about the service invocation building block.</span></span> <span data-ttu-id="932e0-283">Vio cómo invocar métodos remotos realizando llamadas HTTP directas al sidecar de DAPR y usando el SDK de .NET para DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-283">You saw how to invoke remote methods both by making direct HTTP calls to the Dapr sidecar, and by using the Dapr .NET SDK.</span></span>

<span data-ttu-id="932e0-284">El SDK de .NET para DAPR proporciona varias maneras de invocar métodos remotos.</span><span class="sxs-lookup"><span data-stu-id="932e0-284">The Dapr .NET SDK provides multiple ways to invoke remote methods.</span></span> <span data-ttu-id="932e0-285">La compatibilidad con HttpClient es ideal para los desarrolladores que desean reutilizar los conocimientos existentes y es compatible con muchos marcos y bibliotecas existentes.</span><span class="sxs-lookup"><span data-stu-id="932e0-285">HttpClient support is great for developers wanting to reuse existing skills and is compatible with many existing frameworks and libraries.</span></span> <span data-ttu-id="932e0-286">DaprClient ofrece compatibilidad para usar directamente la API de invocación del servicio DAPR mediante la semántica HTTP o gRPC.</span><span class="sxs-lookup"><span data-stu-id="932e0-286">DaprClient offers support for directly using the Dapr service invocation API using either HTTP or gRPC semantics.</span></span>

<span data-ttu-id="932e0-287">La arquitectura de referencia de eShopOnDapr muestra cómo se moderniza la solución eShopOnContainers original mediante la invocación del servicio DAPR.</span><span class="sxs-lookup"><span data-stu-id="932e0-287">The eShopOnDapr reference architecture shows how the original eShopOnContainers solution is modernized by using Dapr service invocation.</span></span> <span data-ttu-id="932e0-288">Agregar DAPR a eShop proporciona ventajas como los reintentos automáticos, el cifrado de mensajes mediante mTLS y una mejor observación.</span><span class="sxs-lookup"><span data-stu-id="932e0-288">Adding Dapr to eShop provides benefits such as automatic retries, message encryption using mTLS, and improved observability.</span></span>

### <a name="references"></a><span data-ttu-id="932e0-289">Referencias</span><span class="sxs-lookup"><span data-stu-id="932e0-289">References</span></span>

- [<span data-ttu-id="932e0-290">Bloque de creación de invocación del servicio DAPR</span><span class="sxs-lookup"><span data-stu-id="932e0-290">Dapr service invocation building block</span></span>](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/)

- [<span data-ttu-id="932e0-291">Supervisión de aplicaciones nativas distribuidas en la nube</span><span class="sxs-lookup"><span data-stu-id="932e0-291">Monitoring distributed cloud-native applications</span></span>](../cloud-native/observability-patterns.md)

> [!div class="step-by-step"]
> <span data-ttu-id="932e0-292">[Anterior](state-management.md)
> [Siguiente](publish-subscribe.md)</span><span class="sxs-lookup"><span data-stu-id="932e0-292">[Previous](state-management.md)
[Next](publish-subscribe.md)</span></span>
