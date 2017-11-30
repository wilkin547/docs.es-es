---
title: "Implementar el patrón de disyuntor"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Implementar el patrón de disyuntor"
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 2a629e25a7565aaba156f68cf06d9a24b6c2b8b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="implementing-the-circuit-breaker-pattern"></a><span data-ttu-id="f503e-104">Implementar el patrón de disyuntor</span><span class="sxs-lookup"><span data-stu-id="f503e-104">Implementing the Circuit Breaker pattern</span></span>

<span data-ttu-id="f503e-105">Tal y como se indicó anteriormente, debe controlar los errores que pueden tardar una cantidad variable de tiempo de recuperación, como podría ocurrir al intentar conectarse a un recurso o servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="f503e-105">As noted earlier, you should handle faults that might take a variable amount of time to recover from, as might happen when you try to connect to a remote service or resource.</span></span> <span data-ttu-id="f503e-106">Control de este tipo de error puede mejorar la estabilidad y la resistencia de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f503e-106">Handling this type of fault can improve the stability and resiliency of an application.</span></span>

<span data-ttu-id="f503e-107">En un entorno distribuido, llamadas a servicios y recursos remotos pueden producir errores debido a errores transitorios, como conexiones de red lentas y tiempos de espera, o si se va recursos lenta o no están disponibles temporalmente.</span><span class="sxs-lookup"><span data-stu-id="f503e-107">In a distributed environment, calls to remote resources and services can fail due to transient faults, such as slow network connections and timeouts, or if resources are being slow or are temporarily unavailable.</span></span> <span data-ttu-id="f503e-108">Estos errores suelen corrigen por sí mismos después de unos minutos y una aplicación de nube sólidas debe estar preparada para controlarlos mediante el uso de una estrategia como en el patrón de reintento.</span><span class="sxs-lookup"><span data-stu-id="f503e-108">These faults typically correct themselves after a short time, and a robust cloud application should be prepared to handle them by using a strategy like the Retry pattern.</span></span>

<span data-ttu-id="f503e-109">Sin embargo, también puede haber situaciones donde los errores son debido a eventos imprevistos que pueden tardar mucho más tiempo en corregir.</span><span class="sxs-lookup"><span data-stu-id="f503e-109">However, there can also be situations where faults are due to unanticipated events that might take much longer to fix.</span></span> <span data-ttu-id="f503e-110">Estos errores pueden abarcar gravedad de una pérdida parcial de conectividad para el error completo de un servicio.</span><span class="sxs-lookup"><span data-stu-id="f503e-110">These faults can range in severity from a partial loss of connectivity to the complete failure of a service.</span></span> <span data-ttu-id="f503e-111">En estas situaciones, podría ser sentido para una aplicación para continuamente volver a intentar una operación que no es probable que lleve a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="f503e-111">In these situations, it might be pointless for an application to continually retry an operation that is unlikely to succeed.</span></span> <span data-ttu-id="f503e-112">En su lugar, se debe codificar la aplicación para que acepte que ha fallado la operación y controlar los errores en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="f503e-112">Instead, the application should be coded to accept that the operation has failed and handle the failure accordingly.</span></span>

<span data-ttu-id="f503e-113">El patrón de disyuntor tiene un propósito diferente que el patrón de reintento.</span><span class="sxs-lookup"><span data-stu-id="f503e-113">The Circuit Breaker pattern has a different purpose than the Retry pattern.</span></span> <span data-ttu-id="f503e-114">El patrón de reintento permite a una aplicación volver a intentar una operación de la expectativa de que finalmente se realizará correctamente la operación.</span><span class="sxs-lookup"><span data-stu-id="f503e-114">The Retry pattern enables an application to retry an operation in the expectation that the operation will eventually succeed.</span></span> <span data-ttu-id="f503e-115">El patrón de disyuntor impide que una aplicación realiza una operación que es probable que un error.</span><span class="sxs-lookup"><span data-stu-id="f503e-115">The Circuit Breaker pattern prevents an application from performing an operation that is likely to fail.</span></span> <span data-ttu-id="f503e-116">Una aplicación puede combinar estos dos modelos mediante el patrón de reintento para invocar una operación a través de un disyuntor.</span><span class="sxs-lookup"><span data-stu-id="f503e-116">An application can combine these two patterns by using the Retry pattern to invoke an operation through a circuit breaker.</span></span> <span data-ttu-id="f503e-117">Sin embargo, la lógica de reintento debe ser sensible a las excepciones devueltas por el disyuntor, y deben abandonar reintentos si el disyuntor indica que un error no es transitorio.</span><span class="sxs-lookup"><span data-stu-id="f503e-117">However, the retry logic should be sensitive to any exceptions returned by the circuit breaker, and it should abandon retry attempts if the circuit breaker indicates that a fault is not transient.</span></span>

## <a name="implementing-a-circuit-breaker-pattern-with-polly"></a><span data-ttu-id="f503e-118">Implementar un patrón de disyuntor con Polly</span><span class="sxs-lookup"><span data-stu-id="f503e-118">Implementing a Circuit Breaker pattern with Polly</span></span>

<span data-ttu-id="f503e-119">Como al implementar reintentos, el enfoque recomendado para los disyuntores consiste en aprovechar las ventajas de eficacia comprobadas de bibliotecas de .NET como Polly.</span><span class="sxs-lookup"><span data-stu-id="f503e-119">As when implementing retries, the recommended approach for circuit breakers is to take advantage of proven .NET libraries like Polly.</span></span>

<span data-ttu-id="f503e-120">La aplicación eShopOnContainers utiliza la directiva de disyuntor de Polly al implementar los reintentos HTTP.</span><span class="sxs-lookup"><span data-stu-id="f503e-120">The eShopOnContainers application uses the Polly Circuit Breaker policy when implementing HTTP retries.</span></span> <span data-ttu-id="f503e-121">De hecho, la aplicación aplica a las dos directivas a la clase de utilidad ResilientHttpClient.</span><span class="sxs-lookup"><span data-stu-id="f503e-121">In fact, the application applies both policies to the ResilientHttpClient utility class.</span></span> <span data-ttu-id="f503e-122">Siempre que se use un objeto de tipo ResilientHttpClient para las solicitudes HTTP (desde eShopOnContainers), que va a aplicar esas directivas de ambos, pero puede agregar directivas adicionales, demasiado.</span><span class="sxs-lookup"><span data-stu-id="f503e-122">Whenever you use an object of type ResilientHttpClient for HTTP requests (from eShopOnContainers), you will be applying both those policies, but you could add additional policies, too.</span></span>

<span data-ttu-id="f503e-123">El único que se agrega a continuación al código utilizado para los reintentos de llamada HTTP es el código que agrega la directiva de disyuntor a la lista de directivas que se va a usar, tal como se muestra al final del código siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503e-123">The only addition here to the code used for HTTP call retries is the code where you add the Circuit Breaker policy to the list of policies to use, as shown at the end of the following code:</span></span>

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

<span data-ttu-id="f503e-124">El código agrega una directiva para el contenedor de HTTP.</span><span class="sxs-lookup"><span data-stu-id="f503e-124">The code adds a policy to the HTTP wrapper.</span></span> <span data-ttu-id="f503e-125">Que la directiva define un disyuntor que se abre cuando el código detecta el número especificado de excepciones consecutivos (excepciones en una fila), como pasa en el parámetro exceptionsAllowedBeforeBreaking (5 en este caso).</span><span class="sxs-lookup"><span data-stu-id="f503e-125">That policy defines a circuit breaker that opens when the code detects the specified number of consecutive exceptions (exceptions in a row), as passed in the exceptionsAllowedBeforeBreaking parameter (5 in this case).</span></span> <span data-ttu-id="f503e-126">Una vez abierto el circuito, las solicitudes HTTP no funcionan, pero se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="f503e-126">When the circuit is open, HTTP requests do not work, but an exception is raised.</span></span>

<span data-ttu-id="f503e-127">Los disyuntores también debe utilizarse para redirigir las solicitudes a una infraestructura de reserva si es posible que tenga problemas en un recurso concreto que se implementa en un entorno diferente de la aplicación cliente o servicio que realiza la llamada HTTP.</span><span class="sxs-lookup"><span data-stu-id="f503e-127">Circuit breakers should also be used to redirect requests to a fallback infrastructure if you might have issues in a particular resource that is deployed in a different environment than the client application or service that is performing the HTTP call.</span></span> <span data-ttu-id="f503e-128">De este modo, si se produce una interrupción en el centro de datos que afecta solo la microservicios de back-end, pero no las aplicaciones de cliente, las aplicaciones cliente pueden redirigir a los servicios de reserva.</span><span class="sxs-lookup"><span data-stu-id="f503e-128">That way, if there is an outage in the datacenter that impacts only your backend microservices but not your client applications, the client applications can redirect to the fallback services.</span></span> <span data-ttu-id="f503e-129">Polly está planeando una directiva nueva para automatizar esta tarea, [directiva de conmutación por error](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) escenario.</span><span class="sxs-lookup"><span data-stu-id="f503e-129">Polly is planning a new policy to automate this [failover policy](https://github.com/App-vNext/Polly/wiki/Polly-Roadmap#failover-policy) scenario.</span></span>

<span data-ttu-id="f503e-130">Por supuesto, todas esas características están en los casos donde está administrando la conmutación por error desde dentro del código. NET, en lugar de tener que administran automáticamente para Azure, con transparencia de ubicación.</span><span class="sxs-lookup"><span data-stu-id="f503e-130">Of course, all those features are for cases where you are managing the failover from within the .NET code, as opposed to having it managed automatically for you by Azure, with location transparency.</span></span>

## <a name="using-the-resilienthttpclient-utility-class-from-eshoponcontainers"></a><span data-ttu-id="f503e-131">Uso de la clase de utilidad ResilientHttpClient desde eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f503e-131">Using the ResilientHttpClient utility class from eShopOnContainers</span></span>

<span data-ttu-id="f503e-132">Utilice la clase de utilidad ResilientHttpClient de forma similar a cómo utilizar la clase .NET HttpClient.</span><span class="sxs-lookup"><span data-stu-id="f503e-132">You use the ResilientHttpClient utility class in a way similar to how you use the .NET HttpClient class.</span></span> <span data-ttu-id="f503e-133">En el ejemplo siguiente de la aplicación web MVC de eShopOnContainers (la clase de agente OrderingService utilizada por OrderController), el objeto ResilientHttpClient se aplica a través del parámetro httpClient del constructor.</span><span class="sxs-lookup"><span data-stu-id="f503e-133">In the following example from the eShopOnContainers MVC web application (the OrderingService agent class used by OrderController), the ResilientHttpClient object is injected through the httpClient parameter of the constructor.</span></span> <span data-ttu-id="f503e-134">A continuación, el objeto se usa para realizar solicitudes HTTP.</span><span class="sxs-lookup"><span data-stu-id="f503e-134">Then the object is used to perform HTTP requests.</span></span>

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

<span data-ttu-id="f503e-135">Cada vez que la \_se utiliza el objeto de miembro apiClient, usa internamente la clase contenedora con Polly policiesؙ: la directiva de reintentos, la directiva de disyuntor y cualquier otra directiva que desea aplicar de la colección de directivas de Polly.</span><span class="sxs-lookup"><span data-stu-id="f503e-135">Whenever the \_apiClient member object is used, it internally uses the wrapper class with Polly policiesؙ—the Retry policy, the Circuit Breaker policy, and any other policy that you might want to apply from the Polly policies collection.</span></span>

## <a name="testing-retries-in-eshoponcontainers"></a><span data-ttu-id="f503e-136">Probar los reintentos en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f503e-136">Testing retries in eShopOnContainers</span></span>

<span data-ttu-id="f503e-137">Cada vez que inicia la solución eShopOnContainers en un host Docker, debe iniciar varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="f503e-137">Whenever you start the eShopOnContainers solution in a Docker host, it needs to start multiple containers.</span></span> <span data-ttu-id="f503e-138">Algunos de los contenedores son más lentos iniciar e inicializar, al igual que el contenedor de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f503e-138">Some of the containers are slower to start and initialize, like the SQL Server container.</span></span> <span data-ttu-id="f503e-139">Esto es especialmente cierto en la primera vez que implemente la aplicación eShopOnContainers en Docker, porque es necesario configurar las imágenes y la base de datos.</span><span class="sxs-lookup"><span data-stu-id="f503e-139">This is especially true the first time you deploy the eShopOnContainers application into Docker, because it needs to set up the images and the database.</span></span> <span data-ttu-id="f503e-140">El hecho de que algunos contenedores de inician con una velocidad superior otros pueden provocar el resto de los servicios inicialmente iniciar excepciones de HTTP, incluso si configura las dependencias entre los contenedores en la redacción docker nivel, como se explica en las secciones anteriores.</span><span class="sxs-lookup"><span data-stu-id="f503e-140">The fact that some containers start slower than others can cause the rest of the services to initially throw HTTP exceptions, even if you set dependencies between containers at the docker-compose level, as explained in previous sections.</span></span> <span data-ttu-id="f503e-141">Los docker-crear dependencias entre los contenedores son simplemente en el nivel de proceso.</span><span class="sxs-lookup"><span data-stu-id="f503e-141">Those docker-compose dependencies between containers are just at the process level.</span></span> <span data-ttu-id="f503e-142">Se puede iniciar el proceso de punto de entrada del contenedor, pero SQL Server podrían no estar preparado para las consultas.</span><span class="sxs-lookup"><span data-stu-id="f503e-142">The container’s entry point process might be started, but SQL Server might not be ready for queries.</span></span> <span data-ttu-id="f503e-143">El resultado puede ser una cascada de errores y la aplicación puede obtener una excepción al intentar utilizar dicho contenedor determinado.</span><span class="sxs-lookup"><span data-stu-id="f503e-143">The result can be a cascade of errors, and the application can get an exception when trying to consume that particular container.</span></span>

<span data-ttu-id="f503e-144">También puede ver este tipo de error en el inicio cuando la aplicación se implementa en la nube.</span><span class="sxs-lookup"><span data-stu-id="f503e-144">You might also see this type of error on startup when the application is deploying to the cloud.</span></span> <span data-ttu-id="f503e-145">En ese caso, orchestrators podría ser mover contenedores de un nodo o la máquina virtual a otra (que es, a partir de las nuevas instancias) cuando el número de contenedores de equilibrio en todos los nodos del clúster.</span><span class="sxs-lookup"><span data-stu-id="f503e-145">In that case, orchestrators might be moving containers from one node or VM to another (that is, starting new instances) when balancing the number of containers across the cluster’s nodes.</span></span>

<span data-ttu-id="f503e-146">La manera eShopOnContainers soluciona este problema es mediante el patrón de reintento que se mostrados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="f503e-146">The way eShopOnContainers solves this issue is by using the Retry pattern we illustrated earlier.</span></span> <span data-ttu-id="f503e-147">También es ¿por qué, al comienzo de la solución, podría obtener seguimientos del registro o advertencias similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503e-147">It is also why, when starting the solution, you might get log traces or warnings like the following:</span></span>

> <span data-ttu-id="f503e-148">"**Reintento 1 implementa con RetryPolicy de Polly**, debido a que: System.Net.Http.HttpRequestException: se produjo un error al enviar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f503e-148">"**Retry 1 implemented with Polly's RetryPolicy**, due to: System.Net.Http.HttpRequestException: An error occurred while sending the request.</span></span><span data-ttu-id="f503e-149"> ---&gt;System.Net.Http.CurlException: No se pudo conectar al servidor\\n en System.Net.Http.CurlHandler.ThrowIfCURLEError (error CURLcode)\\n en \[... \].</span><span class="sxs-lookup"><span data-stu-id="f503e-149"> ---&gt; System.Net.Http.CurlException: Couldn't connect to server\\n at System.Net.Http.CurlHandler.ThrowIfCURLEError(CURLcode error)\\n at \[...\].</span></span>

## <a name="testing-the-circuit-breaker-in-eshoponcontainers"></a><span data-ttu-id="f503e-150">Probar el disyuntor en eShopOnContainers</span><span class="sxs-lookup"><span data-stu-id="f503e-150">Testing the circuit breaker in eShopOnContainers</span></span>

<span data-ttu-id="f503e-151">Hay varias maneras de poder abrir el circuito y probarlo con eShopOnContainers.</span><span class="sxs-lookup"><span data-stu-id="f503e-151">There are a few ways you can open the circuit and test it with eShopOnContainers.</span></span>

<span data-ttu-id="f503e-152">Una opción consiste en reducir el número permitido de reintentos en 1 en la directiva de disyuntor y volver a implementar la solución completa en Docker.</span><span class="sxs-lookup"><span data-stu-id="f503e-152">One option is to lower the allowed number of retries to 1 in the circuit breaker policy and redeploy the whole solution into Docker.</span></span> <span data-ttu-id="f503e-153">Con un reintento único, hay una gran probabilidad de que una solicitud HTTP se producirá un error durante la implementación, el disyuntor se abrirá y se produce un error.</span><span class="sxs-lookup"><span data-stu-id="f503e-153">With a single retry, there is a good chance that an HTTP request will fail during deployment, the circuit breaker will open, and you get an error.</span></span>

<span data-ttu-id="f503e-154">Otra opción es usar middleware personalizado que se implementa en la ordenación microservicio.</span><span class="sxs-lookup"><span data-stu-id="f503e-154">Another option is to use custom middleware that is implemented in the ordering microservice.</span></span> <span data-ttu-id="f503e-155">Cuando se habilita este middleware, detecta todas las solicitudes HTTP y devuelve el código de estado 500.</span><span class="sxs-lookup"><span data-stu-id="f503e-155">When this middleware is enabled, it catches all HTTP requests and returns status code 500.</span></span> <span data-ttu-id="f503e-156">Puede habilitar el middleware realizando una solicitud GET al error del URI, similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503e-156">You can enable the middleware by making a GET request to the failing URI, like the following:</span></span>

-   <span data-ttu-id="f503e-157">GET/error</span><span class="sxs-lookup"><span data-stu-id="f503e-157">GET /failing</span></span>

<span data-ttu-id="f503e-158">Esta solicitud devuelve el estado actual del middleware de.</span><span class="sxs-lookup"><span data-stu-id="f503e-158">This request returns the current state of the middleware.</span></span> <span data-ttu-id="f503e-159">Si está habilitado el software intermedio, la solicitud devuelve el código de estado 500.</span><span class="sxs-lookup"><span data-stu-id="f503e-159">If the middleware is enabled, the request return status code 500.</span></span> <span data-ttu-id="f503e-160">Si se deshabilita el software intermedio, no hay ninguna respuesta.</span><span class="sxs-lookup"><span data-stu-id="f503e-160">If the middleware is disabled, there is no response.</span></span>

-   <span data-ttu-id="f503e-161">GET/errores? habilitar</span><span class="sxs-lookup"><span data-stu-id="f503e-161">GET /failing?enable</span></span>

<span data-ttu-id="f503e-162">Esta solicitud habilita el middleware.</span><span class="sxs-lookup"><span data-stu-id="f503e-162">This request enables the middleware.</span></span>

-   <span data-ttu-id="f503e-163">GET/errores? deshabilitar</span><span class="sxs-lookup"><span data-stu-id="f503e-163">GET /failing?disable</span></span>

<span data-ttu-id="f503e-164">Esta solicitud deshabilita el middleware.</span><span class="sxs-lookup"><span data-stu-id="f503e-164">This request disables the middleware.</span></span>

<span data-ttu-id="f503e-165">Por ejemplo, una vez que se ejecuta la aplicación, puede habilitar el middleware realizando una solicitud usando el siguiente URI en cualquier explorador.</span><span class="sxs-lookup"><span data-stu-id="f503e-165">For instance, once the application is running, you can enable the middleware by making a request using the following URI in any browser.</span></span> <span data-ttu-id="f503e-166">Tenga en cuenta que la ordenación microservicio utiliza el puerto 5102.</span><span class="sxs-lookup"><span data-stu-id="f503e-166">Note that the ordering microservice uses port 5102.</span></span>

<span data-ttu-id="f503e-167">http://localhost:5102 / errores? habilitar</span><span class="sxs-lookup"><span data-stu-id="f503e-167">http://localhost:5102/failing?enable</span></span>

<span data-ttu-id="f503e-168">A continuación, puede comprobar el estado usando el URI [http://localhost:5102 / errores](http://localhost:5100/failing), tal y como se muestra en la figura 10-4.</span><span class="sxs-lookup"><span data-stu-id="f503e-168">You can then check the status using the URI [http://localhost:5102/failing](http://localhost:5100/failing), as shown in Figure 10-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="f503e-169">**Figura 10-4**.</span><span class="sxs-lookup"><span data-stu-id="f503e-169">**Figure 10-4**.</span></span> <span data-ttu-id="f503e-170">Simular un error con middleware ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f503e-170">Simulating a failure with ASP.NET middleware</span></span>

<span data-ttu-id="f503e-171">En este momento, la ordenación responde de microservicio con código de estado 500 cada vez que se llama a invocarlo.</span><span class="sxs-lookup"><span data-stu-id="f503e-171">At this point, the ordering microservice responds with status code 500 whenever you call invoke it.</span></span>

<span data-ttu-id="f503e-172">Una vez que se está ejecutando el software intermedio, puede intentar realizar un pedido de la aplicación web MVC.</span><span class="sxs-lookup"><span data-stu-id="f503e-172">Once the middleware is running, you can try making an order from the MVC web application.</span></span> <span data-ttu-id="f503e-173">Debido al error de las solicitudes, se abrirá el circuito.</span><span class="sxs-lookup"><span data-stu-id="f503e-173">Because the requests fails, the circuit will open.</span></span>

<span data-ttu-id="f503e-174">En el ejemplo siguiente, puede ver que la aplicación web MVC tiene una instrucción catch bloquear en la lógica para realizar un pedido.</span><span class="sxs-lookup"><span data-stu-id="f503e-174">In the following example, you can see that the MVC web application has a catch block in the logic for placing an order.</span></span> <span data-ttu-id="f503e-175">Si el código detecta una excepción de circuito abierto, muestra al usuario un mensaje descriptivo que les indica que esperar.</span><span class="sxs-lookup"><span data-stu-id="f503e-175">If the code catches an open-circuit exception, it shows the user a friendly message telling them to wait.</span></span>

```csharp
[HttpPost]
public async Task<IActionResult> Create(Order model, string action)
{
    try
    {
        if (ModelState.IsValid)
        {
            var user = _appUserParser.Parse(HttpContext.User);
            await _orderSvc.CreateOrder(model);
            //Redirect to historic list.
            return RedirectToAction("Index");
        }
    }
    catch(BrokenCircuitException ex)
    {
        ModelState.AddModelError("Error",
            "It was not possible to create a new order, please try later on");
    }
    return View(model);
}
```

<span data-ttu-id="f503e-176">Este es un resumen.</span><span class="sxs-lookup"><span data-stu-id="f503e-176">Here’s a summary.</span></span> <span data-ttu-id="f503e-177">La directiva de reintentos prueba varias veces para que la solicitud HTTP y obtiene errores HTTP.</span><span class="sxs-lookup"><span data-stu-id="f503e-177">The Retry policy tries several times to make the HTTP request and gets HTTP errors.</span></span> <span data-ttu-id="f503e-178">Cuando el número de intentos alcanza el número máximo establecido para la directiva de disyuntor (en este caso, 5), la aplicación produce una BrokenCircuitException.</span><span class="sxs-lookup"><span data-stu-id="f503e-178">When the number of tries reaches the maximum number set for the Circuit Breaker policy (in this case, 5), the application throws a BrokenCircuitException.</span></span> <span data-ttu-id="f503e-179">El resultado es un mensaje descriptivo, como se muestra en la figura 10-5.</span><span class="sxs-lookup"><span data-stu-id="f503e-179">The result is a friendly message, as shown in Figure 10-5.</span></span>

![](./media/image5.png)

<span data-ttu-id="f503e-180">**Figura 5-10**.</span><span class="sxs-lookup"><span data-stu-id="f503e-180">**Figure 10-5**.</span></span> <span data-ttu-id="f503e-181">Disyuntor devolviendo un error en la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f503e-181">Circuit breaker returning an error to the UI</span></span>

<span data-ttu-id="f503e-182">Puede implementar una lógica diferente para cuando se abra el circuito.</span><span class="sxs-lookup"><span data-stu-id="f503e-182">You can implement different logic for when to open the circuit.</span></span> <span data-ttu-id="f503e-183">O bien puede intentar una solicitud HTTP con un microservicio de back-end diferente si hay un centro de datos de reserva o el sistema back-end redundante.</span><span class="sxs-lookup"><span data-stu-id="f503e-183">Or you can try an HTTP request against a different back-end microservice if there is a fallback datacenter or redundant back-end system.</span></span>

<span data-ttu-id="f503e-184">Por último, otra posibilidad de que el CircuitBreakerPolicy es usar aíslan (lo que obliga a abrir y mantiene abierto el circuito) y restablecimiento (que se cierra nuevo).</span><span class="sxs-lookup"><span data-stu-id="f503e-184">Finally, another possibility for the CircuitBreakerPolicy is to use Isolate (which forces open and holds open the circuit) and Reset (which closes it again).</span></span> <span data-ttu-id="f503e-185">Puede utilizarse para crear un punto de conexión HTTP de utilidad que invoca a aislar y restablecimiento directamente en la directiva.</span><span class="sxs-lookup"><span data-stu-id="f503e-185">These could be used to build a utility HTTP endpoint that invokes Isolate and Reset directly on the policy.</span></span> <span data-ttu-id="f503e-186">Este tipo de extremo HTTP también podría usarse, protegida adecuadamente, en el entorno de producción para aislar temporalmente un sistema de nivel inferior, como cuando desee actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="f503e-186">Such an HTTP endpoint could also be used, suitably secured, in production for temporarily isolating a downstream system, such as when you want to upgrade it.</span></span> <span data-ttu-id="f503e-187">O bien, podría viaje el circuito manualmente para proteger un sistema de nivel inferior que sospecha que se produzca un error.</span><span class="sxs-lookup"><span data-stu-id="f503e-187">Or it could trip the circuit manually to protect a downstream system you suspect to be faulting.</span></span>

## <a name="adding-a-jitter-strategy-to-the-retry-policy"></a><span data-ttu-id="f503e-188">Agregar una estrategia de vibración a la directiva de reintentos</span><span class="sxs-lookup"><span data-stu-id="f503e-188">Adding a jitter strategy to the retry policy</span></span>

<span data-ttu-id="f503e-189">Una directiva de reintentos regular puede afectar a su sistema en los casos de escalabilidad y alta simultaneidad y en elevada contención.</span><span class="sxs-lookup"><span data-stu-id="f503e-189">A regular Retry policy can impact your system in cases of high concurrency and scalability and under high contention.</span></span> <span data-ttu-id="f503e-190">Para superar los picos de reintentos similar procedentes de muchos clientes en caso de interrupciones parciales, una buena solución es agregar una estrategia de vibración a la directiva de algoritmo de reintento.</span><span class="sxs-lookup"><span data-stu-id="f503e-190">To overcome peaks of similar retries coming from many clients in case of partial outages, a good workaround is to add a jitter strategy to the retry algorithm/policy.</span></span> <span data-ttu-id="f503e-191">Esto puede mejorar el rendimiento general del sistema to-end mediante la adición de aleatoriedad al retroceso exponencial.</span><span class="sxs-lookup"><span data-stu-id="f503e-191">This can improve the overall performance of the end-to-end system by adding randomness to the exponential backoff.</span></span> <span data-ttu-id="f503e-192">Esto se extiende los picos cuando surgen problemas.</span><span class="sxs-lookup"><span data-stu-id="f503e-192">This spreads out the spikes when issues arise.</span></span> <span data-ttu-id="f503e-193">Cuando usas Polly, código para implementar la vibración podría ser similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f503e-193">When you use Polly, code to implement jitter could look like the following example:</span></span>

```csharp
Random jitterer = new Random();
Policy.Handle<HttpResponseException>() // etc
    .WaitAndRetry(5, // exponential back-off plus some jitter
        retryAttempt => TimeSpan.FromSeconds(Math.Pow(2, retryAttempt))
            + TimeSpan.FromMilliseconds(jitterer.Next(0, 100))
    );
```

## <a name="additional-resources"></a><span data-ttu-id="f503e-194">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f503e-194">Additional resources</span></span>

-   <span data-ttu-id="f503e-195">**Vuelva a intentar patrón**
    [*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span><span class="sxs-lookup"><span data-stu-id="f503e-195">**Retry pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/retry*](https://docs.microsoft.com/azure/architecture/patterns/retry)</span></span>

-   <span data-ttu-id="f503e-196">**Resistencia de conexión** (Entity Framework Core) [ *https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span><span class="sxs-lookup"><span data-stu-id="f503e-196">**Connection Resiliency** (Entity Framework Core) [*https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency*](https://docs.microsoft.com/ef/core/miscellaneous/connection-resiliency)</span></span>

-   <span data-ttu-id="f503e-197">**Polly** (resistencia de .NET y la biblioteca de control de errores transitorios) [ *https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span><span class="sxs-lookup"><span data-stu-id="f503e-197">**Polly** (.NET resilience and transient-fault-handling library) [*https://github.com/App-vNext/Polly*](https://github.com/App-vNext/Polly)</span></span>

-   <span data-ttu-id="f503e-198">**Patrón de disyuntor**
    [*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span><span class="sxs-lookup"><span data-stu-id="f503e-198">**Circuit Breaker pattern**
[*https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker*](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)</span></span>

-   <span data-ttu-id="f503e-199">**Marc Saavedra. Vibración: Hacer cosas mejor con aleatoriedad** https://brooker.co.za/blog/2015/03/21/backoff.html</span><span class="sxs-lookup"><span data-stu-id="f503e-199">**Marc Brooker. Jitter: Making Things Better With Randomness** https://brooker.co.za/blog/2015/03/21/backoff.html</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f503e-200">[Anterior] (implement-http-call-retries-exponential-backoff-polly.md) [siguiente] (aplicación-monitor-health.md)</span><span class="sxs-lookup"><span data-stu-id="f503e-200">[Previous] (implement-http-call-retries-exponential-backoff-polly.md) [Next] (monitor-app-health.md)</span></span>
