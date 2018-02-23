---
title: "Implementación del patrón de interruptor"
description: "Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Implementación del patrón de interruptor"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 11/12/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 5d7db6899068f84f9165022cfbf17767a75e7db9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="94169-104">Implementación del patrón de interruptor</span><span class="sxs-lookup"><span data-stu-id="94169-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="94169-105">Tal y como se indicó anteriormente, debe controlar los errores que pueden comportar un tiempo variable de recuperación, como puede suceder al intentar conectarse a un recurso o servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="94169-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="94169-106">Controlar este tipo de error puede mejorar la estabilidad y la resistencia de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="94169-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="94169-107">En un entorno distribuido, las llamadas a servicios y recursos remotos pueden producir errores causados por errores transitorios, como tiempos de espera y conexiones de red lentas, o si los recursos van lentos o no están disponibles temporalmente.</span><span class="sxs-lookup"><span data-stu-id="94169-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="94169-108">Estos errores suelen corregirse solos pasados unos minutos y hay que tener una aplicación sólida en la nube preparada para controlarlos mediante el uso de una estrategia como el patrón de reintento.</span><span class="sxs-lookup"><span data-stu-id="94169-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="94169-109">Pero también puede haber situaciones en que los errores se deban a eventos imprevistos que pueden tardar mucho más tiempo en corregirse.</span><span class="sxs-lookup"><span data-stu-id="94169-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="94169-110">La gravedad de estos errores puede ir desde una pérdida parcial de conectividad hasta el fallo total del servicio.</span><span class="sxs-lookup"><span data-stu-id="94169-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="94169-111">En estas situaciones, no tiene sentido que una aplicación reintente continuamente una operación que es probable que no se lleve a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="94169-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="94169-112">Lo que debe hacer la aplicación es codificarse para aceptar que la operación ha fallado y controlar el error en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="94169-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="94169-113">El patrón de interruptor tiene una finalidad distinta a la del patrón de reintento.</span><span class="sxs-lookup"><span data-stu-id="94169-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="94169-114">El patrón de reintento permite que una aplicación reintente una operación con la expectativa de que finalmente se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="94169-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="94169-115">El patrón de interruptor impide que una aplicación realice una operación que es probable que falle.</span><span class="sxs-lookup"><span data-stu-id="94169-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="94169-116">Una aplicación puede combinar estos dos patrones utilizando el patrón de reintento para invocar una operación mediante un interruptor.</span><span class="sxs-lookup"><span data-stu-id="94169-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="94169-117">Pero la lógica de reintento debe ser sensible a las excepciones devueltas por el interruptor y debe dejar de intentar llevar a cabo la operación si el interruptor indica que un error no es transitorio.</span><span class="sxs-lookup"><span data-stu-id="94169-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="94169-118">Implementación de un patrón de interruptor con Polly</span><span class="sxs-lookup"><span data-stu-id="94169-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="94169-119">Al implementar los reintentos, en el caso de los interruptores se recomienda aprovechar bibliotecas .NET de eficacia probada, como Polly.</span><span class="sxs-lookup"><span data-stu-id="94169-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="94169-120">La aplicación eShopOnContainers utiliza la directiva de interruptor de Polly al implementar los reintentos de HTTP.</span><span class="sxs-lookup"><span data-stu-id="94169-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="94169-121">De hecho, la aplicación aplica las dos directivas a la clase de utilidad ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="94169-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="94169-122">Siempre que use un objeto del tipo ResilientHttpClient para las solicitudes HTTP (desde eShopOnContainers), va a aplicar esas dos directivas, aunque también puede agregar directivas adicionales.</span><span class="sxs-lookup"><span data-stu-id="94169-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="94169-123">En este caso, lo único que se agrega al código utilizado para los reintentos de llamada HTTP es el código en el que debe agregar la directiva de interruptor a la lista de directivas que se van a utilizar, como se muestra al final del código siguiente:</span><span class="sxs-lookup"><span data-stu-id="94169-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

```csharp
public ResilientHttpClient CreateResilientHttpClient()
    => new ResilientHttpClient(CreatePolicies(), _logger);

private Policy[] CreatePolicies()
    => new Policy[]
    {
        Policy.Handle<HttpRequestException>()
            .WaitAndRetryAsync(
            // number of retries
            6,
            // exponential backofff
            retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt)),
            // on retry
            (exception, timeSpan, retryCount, context) =>
            {
                var msg = $"Retry {retryCount} implemented with Polly RetryPolicy " +
                    $"of {context.PolicyKey} " +
                    $"at {context.ExecutionKey}, " +
                    $"due to: {exception}.";
                _logger.LogWarning(msg);
                _logger.LogDebug(msg);
            }),
            Policy.Handle<HttpRequestException>()
                .CircuitBreakerAsync(
                    // number of exceptions before breaking circuit
                    5,
                    // time circuit opened before retry
                    TimeSpan.FromMinutes(1),
                    (exception, duration) =>
                    {
                        // on circuit opened
                        _logger.LogTrace("Circuit breaker opened");
                    },
                    () =>
                    {
                        // on circuit closed
                        _logger.LogTrace("Circuit breaker reset");
                    })
    };
}
```

<span data-ttu-id="94169-124">El código agrega una directiva al contenedor de HTTP.</span><span class="sxs-lookup"><span data-stu-id="94169-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="94169-125">Esa directiva define un interruptor que se abre cuando el código detecta el número especificado de excepciones consecutivas (excepciones seguidas), como sucede en el parámetro exceptionsAllowedBeforeBreaking (5 en este caso).</span><span class="sxs-lookup"><span data-stu-id="94169-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="94169-126">Una vez abierto el circuito, las solicitudes HTTP no funcionan, pero se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="94169-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="94169-127">Los interruptores también deben utilizarse para redirigir las solicitudes a una infraestructura de reserva siempre que tenga problemas en un recurso concreto que se implemente en un entorno distinto al de la aplicación o del servicio del cliente que realiza la llamada HTTP.</span><span class="sxs-lookup"><span data-stu-id="94169-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="94169-128">De este modo, si se produce una interrupción en el centro de datos que afecta solo a los microservicios de back-end, pero no a las aplicaciones cliente, estas aplicaciones pueden redirigir a los servicios de reserva.</span><span class="sxs-lookup"><span data-stu-id="94169-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="94169-129">Polly está creando una directiva nueva para automatizar este escenario de [directiva de conmutación por error](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy).</span><span class="sxs-lookup"><span data-stu-id="94169-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="94169-130">Todas estas características sirven para los casos en que administre la conmutación por error desde el código .NET, y no cuando Azure los administra automáticamente por usted, con la transparencia de ubicación.</span><span class="sxs-lookup"><span data-stu-id="94169-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="94169-131">Uso de la clase de utilidad ResilientHttpClient desde eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="94169-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="94169-132">La clase de utilidad ResilientHttpClient se utiliza de forma similar a cómo se utiliza la clase .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="94169-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="94169-133">En el ejemplo siguiente de la aplicación web MVC de eShopOnContainers (la clase de agente OrderingService utilizada por OrderController), el objeto ResilientHttpClient se aplica mediante el parámetro httpClient del constructor.</span><span class="sxs-lookup"><span data-stu-id="94169-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="94169-134">A continuación, el objeto se usa para realizar solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="94169-134">Then the object is used to perform HTTP requests.</span></span>

```csharp
public class OrderingService : IOrderingService
{
    private IHttpClient _apiClient;
    private readonly string _remoteServiceBaseUrl;
    private readonly IOptionsSnapshot<AppSettings> _settings;
    private readonly IHttpContextAccessor _httpContextAccesor;

    public OrderingService(IOptionsSnapshot<AppSettings> settings,
        IHttpContextAccessor httpContextAccesor,
        IHttpClient httpClient)
    {
        _remoteServiceBaseUrl = $"{settings.Value.OrderingUrl}/api/v1/orders";
        _settings = settings;
        _httpContextAccesor = httpContextAccesor;
        _apiClient = httpClient;
    }

    async public Task<List<Order>> GetMyOrders(ApplicationUser user)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        var ordersUrl = _remoteServiceBaseUrl;
        var dataString = await _apiClient.GetStringAsync(ordersUrl);
        var response = JsonConvert.DeserializeObject<List<Order>>(dataString);
        return response;
    }

    // Other methods ...
    async public Task CreateOrder(Order order)
    {
        var context = _httpContextAccesor.HttpContext;
        var token = await context.Authentication.GetTokenAsync("access_token");
        _apiClient.Inst.DefaultRequestHeaders.Authorization = new
            System.Net.Http.Headers.AuthenticationHeaderValue("Bearer", token);
        _apiClient.Inst.DefaultRequestHeaders.Add("x-requestid",
            order.RequestId.ToString());
        var ordersUrl = $"{_remoteServiceBaseUrl}/new";
        order.CardTypeId = 1;
        order.CardExpirationApiFormat();
        SetFakeIdToProducts(order);
        var response = await _apiClient.PostAsync(ordersUrl, order);
        response.EnsureSuccessStatusCode();
    }
}
```

<span data-ttu-id="94169-135">Cada vez que se utiliza el objeto de miembro \_apiClient, se usa internamente la clase contenedora con las directivas de Polly: la directiva de reintentos, la directiva de interruptor y cualquier otra directiva de Polly que quiera aplicar.</span><span class="sxs-lookup"><span data-stu-id="94169-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="94169-136">Pruebas de los reintentos en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="94169-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="94169-137">Cada vez que inicie la solución eShopOnContainers en un host Docker, debe iniciar varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="94169-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="94169-138">Algunos de los contenedores tardan más en iniciarse e inicializarse, como el contenedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="94169-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="94169-139">Esto sucede especialmente la primera vez que implementa la aplicación eShopOnContainers en Docker, porque las imágenes y la base de datos se tienen que configurar.</span><span class="sxs-lookup"><span data-stu-id="94169-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="94169-140">El hecho de que algunos contenedores se inicien más lentamente que otros puede provocar que el resto de servicios lancen inicialmente excepciones HTTP, aunque configure las dependencias entre contenedores en el nivel de Docker Compose, como se ha explicado en las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="94169-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="94169-141">Las dependencias de Docker Compose entre contenedores solo se dan en el nivel de proceso.</span><span class="sxs-lookup"><span data-stu-id="94169-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="94169-142">El proceso de punto de entrada del contenedor se puede iniciar, pero podría ser que SQL Server no estuviera listo para las consultas.</span><span class="sxs-lookup"><span data-stu-id="94169-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="94169-143">El resultado puede ser una cascada de errores y la aplicación puede obtener una excepción al intentar utilizar dicho contenedor.</span><span class="sxs-lookup"><span data-stu-id="94169-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="94169-144">Este tipo de error también puede darse en el inicio, cuando la aplicación se está implementando en la nube.</span><span class="sxs-lookup"><span data-stu-id="94169-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="94169-145">En ese caso, podría ser que los orquestadores movieran los contenedores de un nodo o máquina virtual a otro (iniciando así nuevas instancias) al repartir equitativamente los contenedores entre los nodos de clúster.</span><span class="sxs-lookup"><span data-stu-id="94169-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="94169-146">La forma que tiene eShopOnContainers de solucionar este problema es utilizar el patrón de reintento que hemos mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="94169-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="94169-147">Este es también el motivo por el cual, al iniciar la solución, puede ser que reciba seguimientos del registro o advertencias como las siguientes:</span><span class="sxs-lookup"><span data-stu-id="94169-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="94169-148">"**Reintento 1 implementado con RetryPolicy de Polly**, en que: System.Net.Http.HttpRequestException: error al enviar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="94169-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="94169-149"> ---&gt; System.Net.Http.CurlException: no se pudo conectar al servidor\\n en System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n en \[...\].</span><span class="sxs-lookup"><span data-stu-id="94169-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="94169-150">Prueba del interruptor en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="94169-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="94169-151">Hay varias formas de abrir el circuito y probarlo con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="94169-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="94169-152">Una opción es reducir el número permitido de reintentos a 1 en la directiva del interruptor y volver a implementar la solución completa en Docker.</span><span class="sxs-lookup"><span data-stu-id="94169-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="94169-153">Con un solo reintento, hay una gran probabilidad de que una solicitud HTTP falle durante la implementación, el interruptor se abra y se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="94169-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="94169-154">Otra opción consiste en usar un middleware personalizado que se implemente en el microservicio `Basket`.</span><span class="sxs-lookup"><span data-stu-id="94169-154">Another option is to use custom middleware that is implemented in the `Basket` microservice.</span></span> <span data-ttu-id="94169-155">Al habilitar este middleware, detecta todas las solicitudes HTTP y devuelve el código de estado 500.</span><span class="sxs-lookup"><span data-stu-id="94169-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="94169-156">Para habilitar el middleware, envíe una solicitud GET al URI que falla, de forma similar a esta:</span><span class="sxs-lookup"><span data-stu-id="94169-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="94169-157">GET /failing</span><span class="sxs-lookup"><span data-stu-id="94169-157">GET /failing</span></span>

<span data-ttu-id="94169-158">Esta solicitud devuelve el estado actual del middleware.</span><span class="sxs-lookup"><span data-stu-id="94169-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="94169-159">Si el middleware está habilitado, la solicitud devuelve el código de estado 500.</span><span class="sxs-lookup"><span data-stu-id="94169-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="94169-160">Si el middleware está deshabilitado, no se emite ninguna respuesta.</span><span class="sxs-lookup"><span data-stu-id="94169-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="94169-161">GET /failing?enable</span><span class="sxs-lookup"><span data-stu-id="94169-161">GET /failing?enable</span></span>

<span data-ttu-id="94169-162">Esta solicitud habilita el middleware.</span><span class="sxs-lookup"><span data-stu-id="94169-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="94169-163">GET /failing?disable</span><span class="sxs-lookup"><span data-stu-id="94169-163">GET /failing?disable</span></span>

<span data-ttu-id="94169-164">Esta solicitud deshabilita el middleware.</span><span class="sxs-lookup"><span data-stu-id="94169-164">This request disables the middleware.</span></span>

<span data-ttu-id="94169-165">Por ejemplo, cuando la aplicación se está ejecutando, puede habilitar el middleware realizando una solicitud con el siguiente URI en cualquier explorador.</span><span class="sxs-lookup"><span data-stu-id="94169-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="94169-166">Tenga en cuenta que el microservicio de ordenación utiliza el puerto 5103.</span><span class="sxs-lookup"><span data-stu-id="94169-166">Note that the ordering microservice uses port 5103.</span></span>

<span data-ttu-id="94169-167">http://localhost:5103/failing?enable</span><span class="sxs-lookup"><span data-stu-id="94169-167">http://localhost:5103/failing?enable</span></span>

<span data-ttu-id="94169-168">A continuación, puede comprobar el estado usando el URI [http://localhost:5103/failing](http://localhost:5103/failing), como se muestra en la Figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="94169-168">You can then check the status using the URI [http://localhost:5103/failing](http://localhost:5103/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="94169-169">**Figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="94169-169">**Figure 10-4**.</span></span> <span data-ttu-id="94169-170">Comprobación del estado del middleware ASP.NET "Error": en este caso, deshabilitado</span><span class="sxs-lookup"><span data-stu-id="94169-170">Checking the state of the “Failing” ASP.NET middleware – In this case, disabled.</span></span> 

<span data-ttu-id="94169-171">En este punto, el microservicio de la cesta responde con el código de estado 500 siempre que su llamada lo invoque.</span><span class="sxs-lookup"><span data-stu-id="94169-171">At this point, the Basket microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="94169-172">Cuando se esté ejecutando el middleware, puede intentar realizar un pedido desde la aplicación web MVC.</span><span class="sxs-lookup"><span data-stu-id="94169-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="94169-173">Como el error falla, el circuito se abre.</span><span class="sxs-lookup"><span data-stu-id="94169-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="94169-174">En el ejemplo siguiente, la aplicación web MVC presenta un bloque catch en la lógica para realizar un pedido.</span><span class="sxs-lookup"><span data-stu-id="94169-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="94169-175">Si el código detecta una excepción de circuito abierto, muestra un mensaje descriptivo al usuario en que se le indica que espere.</span><span class="sxs-lookup"><span data-stu-id="94169-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
public class CartController : Controller
{
    //…
    public async Task<IActionResult> Index()
    {
        try
        {
            //… Other code
        }
        catch (BrokenCircuitException)
        {
            // Catches error when Basket.api is in circuit-opened mode                 
            HandleBrokenCircuitException();
        }
        return View();
    }       

    private void HandleBrokenCircuitException()
    {
        TempData["BasketInoperativeMsg"] = "Basket Service is inoperative, please try later on. (Business message due to Circuit-Breaker)";
    }
}
```

<span data-ttu-id="94169-176">Aquí tiene un resumen.</span><span class="sxs-lookup"><span data-stu-id="94169-176">Here’s a summary.</span></span> <span data-ttu-id="94169-177">La directiva de reintentos intenta realizar la solicitud HTTP varias veces y obtiene errores HTTP.</span><span class="sxs-lookup"><span data-stu-id="94169-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="94169-178">Cuando el número de intentos alcanza el número máximo establecido para la directiva del interruptor (en este caso, 5), la aplicación emite la excepción BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="94169-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="94169-179">El resultado es un mensaje descriptivo, como el que se muestra en la Figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="94169-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="94169-180">**Figura 10-5**.</span><span class="sxs-lookup"><span data-stu-id="94169-180">**Figure 10-5**.</span></span> <span data-ttu-id="94169-181">Interruptor que devuelve un error en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="94169-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="94169-182">Puede implementar una lógica que indique cuándo se debe abrir el circuito.</span><span class="sxs-lookup"><span data-stu-id="94169-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="94169-183">También puede probar una solicitud HTTP en un microservicio de back-end distinto si se dispone de un centro de datos de reserva o un sistema back-end redundante.</span><span class="sxs-lookup"><span data-stu-id="94169-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="94169-184">Por último, otra posibilidad de CircuitBreakerPolicy es utilizar Aislar (que fuerza y mantiene la apertura del circuito) y Restablecer (que lo cierra de nuevo).</span><span class="sxs-lookup"><span data-stu-id="94169-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="94169-185">Estas características se pueden utilizar para crear un punto de conexión HTTP de utilidad que invoque Aislar y Restablecer directamente en la directiva.</span><span class="sxs-lookup"><span data-stu-id="94169-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="94169-186">Este tipo de punto de conexión HTTP, protegido adecuadamente, también se puede usar en el entorno de producción para aislar temporalmente un sistema de nivel inferior, como cuando quiere actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="94169-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="94169-187">También puede activar el circuito manualmente para proteger un sistema de nivel inferior que le parezca que está fallando.</span><span class="sxs-lookup"><span data-stu-id="94169-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="94169-188">Agregar una estrategia de vibración a la directiva de reintentos</span><span class="sxs-lookup"><span data-stu-id="94169-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="94169-189">Una directiva de reintentos normal puede afectar a su sistema en casos de escalabilidad y simultaneidad altas y de gran contención.</span><span class="sxs-lookup"><span data-stu-id="94169-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="94169-190">Para gestionar los picos de reintentos similares procedentes de diferentes clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva o algoritmo de reintento.</span><span class="sxs-lookup"><span data-stu-id="94169-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="94169-191">Esto puede mejorar el rendimiento general del sistema de un extremo a otro añadiendo aleatoriedad al retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="94169-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="94169-192">De esta forma, cuando surgen problemas, los picos se reparten.</span><span class="sxs-lookup"><span data-stu-id="94169-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="94169-193">Al utilizar Polly, el código para implementar la vibración puede parecerse a este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="94169-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="94169-194">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="94169-194">Additional resources</span></span>

-   <span data-ttu-id="94169-195">**Patrón de reintento**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="94169-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="94169-196">**Resistencia de conexión** (núcleo del marco de entidad) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="94169-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="94169-197">**Polly** (biblioteca de control de errores transitorios y resistencia .NET) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="94169-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="94169-198">**Patrón de interruptor**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="94169-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="94169-199">**Marc Brooker. Jitter: Making Things Better With Randomness** (Vibración: hacer mejor las cosas gracias a la aleatoriedad) https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="94169-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="94169-200">[Anterior] (implement-http-call-retries-exponential-backoff-polly.md) [Siguiente] (monitor-app-health.md)</span><span class="sxs-lookup"><span data-stu-id="94169-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
