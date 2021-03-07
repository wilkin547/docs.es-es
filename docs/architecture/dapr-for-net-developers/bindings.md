---
title: El bloque de creación de enlaces de DAPR
description: Descripción del bloque de creación de enlaces, sus características, ventajas y cómo aplicarlo
author: edwinvw
ms.date: 02/07/2021
ms.openlocfilehash: 757d2560016407119fe9244c100a971977852cc5
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401890"
---
# <a name="the-dapr-bindings-building-block"></a><span data-ttu-id="d309d-103">El bloque de creación de enlaces de DAPR</span><span class="sxs-lookup"><span data-stu-id="d309d-103">The Dapr bindings building block</span></span>

<span data-ttu-id="d309d-104">Las ofertas sin *servidor* basadas en la nube, como Azure functions y AWS lambda, han adquirido una adopción amplia en el espacio de la arquitectura distribuida.</span><span class="sxs-lookup"><span data-stu-id="d309d-104">Cloud-based *serverless* offerings, such as Azure Functions and AWS Lambda, have gained wide adoption across the distributed architecture space.</span></span> <span data-ttu-id="d309d-105">Entre muchas ventajas, permiten que un microservicio *controle eventos desde* o *invoquen eventos en* un sistema externo, lo que abstrae la complejidad subyacente y los problemas de establecimiento.</span><span class="sxs-lookup"><span data-stu-id="d309d-105">Among many benefits, they enable a microservice to *handle events from* or *invoke events in* an external system - abstracting away the underlying complexity and plumbing concerns.</span></span> <span data-ttu-id="d309d-106">Los recursos externos son muchos: incluyen almacenes de almacenamiento de los mismos, sistemas de mensajes y recursos Web, en diferentes plataformas y proveedores.</span><span class="sxs-lookup"><span data-stu-id="d309d-106">External resources are many: They include datastores, message systems, and web resources, across different platforms and vendors.</span></span> <span data-ttu-id="d309d-107">El [bloque de creación de enlaces DAPR](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) aporta estas mismas capacidades de enlace de recursos a la Doorstep de las aplicaciones DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-107">The [Dapr bindings building block](https://docs.dapr.io/developing-applications/building-blocks/bindings/bindings-overview/) brings these same resource binding capabilities to the doorstep of your Dapr applications.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="d309d-108">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="d309d-108">What it solves</span></span>

<span data-ttu-id="d309d-109">Los enlaces de recursos DAPR permiten a los servicios integrar las operaciones empresariales en los recursos externos fuera de la aplicación inmediata.</span><span class="sxs-lookup"><span data-stu-id="d309d-109">Dapr resource bindings enable your services to integrate business operations across external resources outside of the immediate application.</span></span> <span data-ttu-id="d309d-110">Un evento de un sistema externo podría desencadenar una operación en el servicio pasando información contextual.</span><span class="sxs-lookup"><span data-stu-id="d309d-110">An event from an external system could trigger an operation in your service passing in contextual information.</span></span> <span data-ttu-id="d309d-111">Después, el servicio podría expandir la operación desencadenando un evento en otro sistema externo, pasando la información de carga contextual.</span><span class="sxs-lookup"><span data-stu-id="d309d-111">Your service could then expand the operation by triggering an event in another external system, passing in contextual payload information.</span></span> <span data-ttu-id="d309d-112">El servicio se comunica sin necesidad de acoplamiento o reconocimiento del recurso externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-112">Your service communicates without coupling or awareness of the external resource.</span></span> <span data-ttu-id="d309d-113">La fontanería se encapsula dentro de los componentes de DAPR predefinidos.</span><span class="sxs-lookup"><span data-stu-id="d309d-113">The plumbing is encapsulated inside pre-defined Dapr components.</span></span> <span data-ttu-id="d309d-114">El componente DAPR que se va a usar puede intercambiarse fácilmente en tiempo de ejecución sin cambios de código.</span><span class="sxs-lookup"><span data-stu-id="d309d-114">The Dapr component to use can be easily swapped at runtime without code changes.</span></span>

<span data-ttu-id="d309d-115">Considere, por ejemplo, una cuenta de Twitter que desencadene un evento cada vez que un usuario Tweet una palabra clave.</span><span class="sxs-lookup"><span data-stu-id="d309d-115">Consider, for example, a Twitter account that triggers an event whenever a user tweets a keyword.</span></span> <span data-ttu-id="d309d-116">El servicio expone un controlador de eventos que recibe y procesa el tweet.</span><span class="sxs-lookup"><span data-stu-id="d309d-116">Your service exposes an event handler that receives and processes the tweet.</span></span> <span data-ttu-id="d309d-117">Una vez completado, el servicio desencadena un evento que invoca un servicio externo Twilio.</span><span class="sxs-lookup"><span data-stu-id="d309d-117">Once complete, your service triggers an event that invokes an external Twilio service.</span></span> <span data-ttu-id="d309d-118">Twilio envía un mensaje SMS que incluye el tweet.</span><span class="sxs-lookup"><span data-stu-id="d309d-118">Twilio sends an SMS message that includes the tweet.</span></span> <span data-ttu-id="d309d-119">En la figura 8-1 se muestra la arquitectura conceptual de esta operación.</span><span class="sxs-lookup"><span data-stu-id="d309d-119">Figure 8-1 show the conceptual architecture of this operation.</span></span>

![Enlace de entrada](media/bindings/bindings-architecture.png)

<span data-ttu-id="d309d-121">**Figura 8-1**.</span><span class="sxs-lookup"><span data-stu-id="d309d-121">**Figure 8-1**.</span></span> <span data-ttu-id="d309d-122">Arquitectura conceptual de un enlace de recursos DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-122">Conceptual architecture of a Dapr resource binding.</span></span>

<span data-ttu-id="d309d-123">A primera vista, el comportamiento del enlace de recursos puede ser similar al [patrón de publicación/suscripción](publish-subscribe.md) descrito anteriormente en este libro.</span><span class="sxs-lookup"><span data-stu-id="d309d-123">At first glance, resource binding behavior may appear similar to the [Publish/Subscribe pattern](publish-subscribe.md) described earlier in this book.</span></span> <span data-ttu-id="d309d-124">Aunque comparten similitudes, hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="d309d-124">While they share similarities, there are differences.</span></span> <span data-ttu-id="d309d-125">La publicación o suscripción se centra en la comunicación asincrónica entre DAPR Services.</span><span class="sxs-lookup"><span data-stu-id="d309d-125">Publish/subscribe focuses on asynchronous communication between Dapr services.</span></span> <span data-ttu-id="d309d-126">El enlace de recursos tiene un ámbito mucho más amplio.</span><span class="sxs-lookup"><span data-stu-id="d309d-126">Resource binding has a much wider scope.</span></span> <span data-ttu-id="d309d-127">Se centra en la interoperabilidad del sistema entre las plataformas de software.</span><span class="sxs-lookup"><span data-stu-id="d309d-127">It focuses on system interoperability across software platforms.</span></span> <span data-ttu-id="d309d-128">Intercambio de información entre aplicaciones, almacenes de datos y servicios dispares fuera de la aplicación de microservicios.</span><span class="sxs-lookup"><span data-stu-id="d309d-128">Exchanging information between disparate applications, datastores, and services outside your microservice application.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d309d-129">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="d309d-129">How it works</span></span>

<span data-ttu-id="d309d-130">El enlace de recursos DAPR comienza con un archivo de configuración de componentes.</span><span class="sxs-lookup"><span data-stu-id="d309d-130">Dapr resource binding starts with a component configuration file.</span></span> <span data-ttu-id="d309d-131">Este archivo YAML describe el tipo de recurso al que se enlazará junto con sus valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d309d-131">This YAML file describes the type of resource to which you'll bind along with its configuration settings.</span></span> <span data-ttu-id="d309d-132">Una vez configurado, el servicio puede recibir eventos del recurso o desencadenar eventos en él.</span><span class="sxs-lookup"><span data-stu-id="d309d-132">Once configured, your service can receive events from the resource or trigger events on it.</span></span>

> [!NOTE]
> <span data-ttu-id="d309d-133">Las configuraciones de enlace se presentan en detalle más adelante en la sección *componentes* .</span><span class="sxs-lookup"><span data-stu-id="d309d-133">Binding configurations are presented in detail later in the *Components* section.</span></span>

### <a name="input-bindings"></a><span data-ttu-id="d309d-134">Enlaces de entrada</span><span class="sxs-lookup"><span data-stu-id="d309d-134">Input bindings</span></span>

<span data-ttu-id="d309d-135">Los enlaces de entrada desencadenan el código con eventos entrantes de recursos externos.</span><span class="sxs-lookup"><span data-stu-id="d309d-135">Input bindings trigger your code with incoming events from external resources.</span></span> <span data-ttu-id="d309d-136">Para recibir eventos y datos, se registra un punto de conexión público desde el servicio que se convierte en el *controlador de eventos*.</span><span class="sxs-lookup"><span data-stu-id="d309d-136">To receive events and data, you register a public endpoint from your service that becomes the *event handler*.</span></span> <span data-ttu-id="d309d-137">En la figura 8-2 se muestra el flujo:</span><span class="sxs-lookup"><span data-stu-id="d309d-137">Figure 8-2 shows the flow:</span></span>

![DAPR flujo de enlace de entrada](media/bindings/input-binding-flow.png)

<span data-ttu-id="d309d-139">**Figura 8-2**.</span><span class="sxs-lookup"><span data-stu-id="d309d-139">**Figure 8-2**.</span></span> <span data-ttu-id="d309d-140">Flujo de enlace de entrada DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-140">Dapr input binding flow.</span></span>

<span data-ttu-id="d309d-141">En la figura 8,2 se describen los pasos para recibir eventos de una cuenta de Twitter externa:</span><span class="sxs-lookup"><span data-stu-id="d309d-141">Figure 8.2 describes the steps for receiving events from an external Twitter account:</span></span>

1. <span data-ttu-id="d309d-142">El sidecar de DAPR lee el archivo de configuración de enlace y se suscribe al evento especificado para el recurso externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-142">The Dapr sidecar reads the binding configuration file and subscribes to the event specified for the external resource.</span></span> <span data-ttu-id="d309d-143">En el ejemplo, el origen del evento es una cuenta de Twitter.</span><span class="sxs-lookup"><span data-stu-id="d309d-143">In the example, the event source is a Twitter account.</span></span>
1. <span data-ttu-id="d309d-144">Cuando se publica un tweet coincidente en Twitter, el componente de enlace que se ejecuta en el sidecar de DAPR lo recoge y desencadena un evento.</span><span class="sxs-lookup"><span data-stu-id="d309d-144">When a matching Tweet is published on Twitter, the binding component running in the Dapr sidecar picks it up and triggers an event.</span></span>
1. <span data-ttu-id="d309d-145">El sidecar de DAPR invoca el punto de conexión (es decir, el controlador de eventos) configurado para el enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-145">The Dapr sidecar invokes the endpoint (that is, event handler) configured for the binding.</span></span> <span data-ttu-id="d309d-146">En el ejemplo, el servicio escucha una solicitud HTTP POST en el `/tweet` extremo en el puerto 6000.</span><span class="sxs-lookup"><span data-stu-id="d309d-146">In the example, the service listens for an HTTP POST on the `/tweet` endpoint on port 6000.</span></span> <span data-ttu-id="d309d-147">Dado que se trata de una operación POST de HTTP, la carga de JSON para el evento se pasa en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d309d-147">Because it's an HTTP POST operation, the JSON payload for the event is passed in the request body.</span></span>
1. <span data-ttu-id="d309d-148">Después de controlar el evento, el servicio devuelve un código de Estado HTTP `200 OK` .</span><span class="sxs-lookup"><span data-stu-id="d309d-148">After handling the event, the service returns an HTTP status code `200 OK`.</span></span>

<span data-ttu-id="d309d-149">El siguiente controlador de ASP.NET Core proporciona un ejemplo de cómo controlar un evento desencadenado por el enlace de Twitter:</span><span class="sxs-lookup"><span data-stu-id="d309d-149">The following ASP.NET Core controller provides an example of handling an event triggered by the Twitter binding:</span></span>

```csharp
[ApiController]
public class SomeController : ControllerBase
{
    public class TwitterTweet
    {
        [JsonPropertyName("id_str")]
        public string ID {get; set; }

        [JsonPropertyName("text")]
        public string Text {get; set; }
    }

    [HttpPost("/tweet")]
    public ActionResult Post(TwitterTweet tweet)
    {
        // Handle tweet
        Console.WriteLine("Tweet received: {0}: {1}", tweet.ID, tweet.Text);

        // ...

        // Acknowledge message
        return Ok();
    }
}
```

<span data-ttu-id="d309d-150">Si la operación debe generar un error, se devolverá el código de Estado HTTP de nivel 400 o 500 adecuado.</span><span class="sxs-lookup"><span data-stu-id="d309d-150">If the operation should error, you would return the appropriate 400 or 500 level HTTP status code.</span></span> <span data-ttu-id="d309d-151">En el caso de los enlaces que incluyen garantías de *entrega una vez como mínimo* , el sidecar de DAPR volverá a intentar el desencadenador.</span><span class="sxs-lookup"><span data-stu-id="d309d-151">For bindings that feature *at-least-once-delivery* guarantees, the Dapr sidecar will retry the trigger.</span></span> <span data-ttu-id="d309d-152">Consulte [documentación de DAPR para enlaces de recursos] [1] para ver si ofrecen garantías de entrega *al menos una vez* o *exactamente una vez* .</span><span class="sxs-lookup"><span data-stu-id="d309d-152">Check out [Dapr documentation for resource bindings][1] to see whether they offer *at-least-once* or *exactly-once* delivery guarantees.</span></span>

### <a name="output-bindings"></a><span data-ttu-id="d309d-153">Enlaces de salida</span><span class="sxs-lookup"><span data-stu-id="d309d-153">Output bindings</span></span>

<span data-ttu-id="d309d-154">DAPR también incluye capacidades de *enlace de salida* .</span><span class="sxs-lookup"><span data-stu-id="d309d-154">Dapr also includes *output binding* capabilities.</span></span> <span data-ttu-id="d309d-155">Permiten que el servicio desencadene un evento que invoca un recurso externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-155">They enable your service to trigger an event that invokes an external resource.</span></span> <span data-ttu-id="d309d-156">De nuevo, empieza por configurar un archivo de configuración de enlace YAML que describe el enlace de salida.</span><span class="sxs-lookup"><span data-stu-id="d309d-156">Again, you start by configuring a binding configuration YAML file that describes the output binding.</span></span> <span data-ttu-id="d309d-157">Una vez en su lugar, se desencadena un evento que invoca la API de enlaces en el sidecar de DAPR de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d309d-157">Once in place, you trigger an event that invokes the bindings API on the Dapr sidecar of your application.</span></span> <span data-ttu-id="d309d-158">En la figura 8-3 se muestra el flujo de un enlace de salida:</span><span class="sxs-lookup"><span data-stu-id="d309d-158">Figure 8-3 shows the flow of an output binding:</span></span>

![Flujo de enlace de salida de DAPR](media/bindings/output-binding-flow.png)

<span data-ttu-id="d309d-160">**Figura 8-3**.</span><span class="sxs-lookup"><span data-stu-id="d309d-160">**Figure 8-3**.</span></span> <span data-ttu-id="d309d-161">Flujo de enlace de salida de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-161">Dapr output binding flow.</span></span>

1. <span data-ttu-id="d309d-162">El sidecar de DAPR lee el archivo de configuración de enlace con la información sobre cómo conectarse al recurso externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-162">The Dapr sidecar reads the binding configuration file with the information on how to connect to the external resource.</span></span> <span data-ttu-id="d309d-163">En el ejemplo, el recurso externo es una cuenta de SMS de Twilio.</span><span class="sxs-lookup"><span data-stu-id="d309d-163">In the example, the external resource is a Twilio SMS account.</span></span>
1. <span data-ttu-id="d309d-164">La aplicación invoca el `/v1.0/bindings/sms` punto de conexión en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-164">Your application invokes the `/v1.0/bindings/sms` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="d309d-165">En este caso, usa HTTP POST para invocar la API.</span><span class="sxs-lookup"><span data-stu-id="d309d-165">In this case, it uses an HTTP POST to invoke the API.</span></span> <span data-ttu-id="d309d-166">También es posible usar gRPC.</span><span class="sxs-lookup"><span data-stu-id="d309d-166">It's also possible to use gRPC.</span></span>
1. <span data-ttu-id="d309d-167">El componente de enlace que se ejecuta en el sidecar de DAPR llama al sistema de mensajería externo para enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="d309d-167">The binding component running in the Dapr sidecar calls the external messaging system to send the message.</span></span> <span data-ttu-id="d309d-168">El mensaje contendrá la carga que se pasa en la solicitud POST.</span><span class="sxs-lookup"><span data-stu-id="d309d-168">The message will contain the payload passed in the POST request.</span></span>

<span data-ttu-id="d309d-169">Por ejemplo, puede invocar un enlace de salida mediante la invocación de la API de DAPR con rizo:</span><span class="sxs-lookup"><span data-stu-id="d309d-169">As an example, you can invoke an output binding by invoking the Dapr API using curl:</span></span>

```console
curl -X POST http://localhost:3500/v1.0/bindings/sms \
  -H "Content-Type: application/json" \
  -d '{
        "data": "Welcome to this awesome service",
        "metadata": {
          "toNumber": "555-3277"
        },
        "operation": "create"
      }'
```

<span data-ttu-id="d309d-170">Tenga en cuenta que el puerto HTTP es el mismo que el usado por el sidecar DAPR (en este caso, el puerto HTTP predeterminado DAPR `3500` ).</span><span class="sxs-lookup"><span data-stu-id="d309d-170">Note that the HTTP port is the same as used by the Dapr sidecar (in this case, the default Dapr HTTP port `3500`).</span></span>

<span data-ttu-id="d309d-171">La estructura de la carga (es decir, el mensaje enviado) variará según el enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-171">The structure of the payload (that is, message sent) will vary per binding.</span></span> <span data-ttu-id="d309d-172">En el ejemplo anterior, la carga útil contiene un `data` elemento con un mensaje.</span><span class="sxs-lookup"><span data-stu-id="d309d-172">In the example above, the payload contains a `data` element with a message.</span></span> <span data-ttu-id="d309d-173">Los enlaces a otros tipos de recursos externos pueden ser diferentes, especialmente para los metadatos que se envían.</span><span class="sxs-lookup"><span data-stu-id="d309d-173">Bindings to other types of external resources can be different, especially for the metadata that is sent.</span></span> <span data-ttu-id="d309d-174">Cada carga útil también debe contener un `operation` campo, que define la operación que se ejecutará en el enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-174">Each payload must also contain an `operation` field, that defines the operation the binding will execute.</span></span> <span data-ttu-id="d309d-175">En el ejemplo anterior se especifica una `create` operación que crea el mensaje SMS.</span><span class="sxs-lookup"><span data-stu-id="d309d-175">The above example specifies a `create` operation that creates the SMS message.</span></span> <span data-ttu-id="d309d-176">Entre las operaciones comunes se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d309d-176">Common operations include:</span></span>

- <span data-ttu-id="d309d-177">create</span><span class="sxs-lookup"><span data-stu-id="d309d-177">create</span></span>
- <span data-ttu-id="d309d-178">get</span><span class="sxs-lookup"><span data-stu-id="d309d-178">get</span></span>
- <span data-ttu-id="d309d-179">delete</span><span class="sxs-lookup"><span data-stu-id="d309d-179">delete</span></span>
- <span data-ttu-id="d309d-180">list</span><span class="sxs-lookup"><span data-stu-id="d309d-180">list</span></span>

<span data-ttu-id="d309d-181">Es el autor del enlace qué operaciones admite el enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-181">It's up to the author of the binding which operations the binding supports.</span></span> <span data-ttu-id="d309d-182">La documentación de cada enlace describe las operaciones disponibles y cómo invocarlas.</span><span class="sxs-lookup"><span data-stu-id="d309d-182">The documentation for each binding describes the available operations and how to invoke them.</span></span>

## <a name="using-the-dapr-net-sdk"></a><span data-ttu-id="d309d-183">Uso del SDK de .NET de DAPR</span><span class="sxs-lookup"><span data-stu-id="d309d-183">Using the Dapr .NET SDK</span></span>

<span data-ttu-id="d309d-184">El SDK de .NET para DAPR proporciona compatibilidad específica del lenguaje para los desarrolladores de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d309d-184">The Dapr .NET SDK provides language-specific support for .NET Core developers.</span></span> <span data-ttu-id="d309d-185">En el ejemplo siguiente, la llamada a `HttpClient.PostAsync()` se reemplaza con el `DaprClient.InvokeBindingAsync()` método.</span><span class="sxs-lookup"><span data-stu-id="d309d-185">In the following example, the call to the `HttpClient.PostAsync()` is replaced with the `DaprClient.InvokeBindingAsync()` method.</span></span> <span data-ttu-id="d309d-186">Este método especializado simplifica la invocación de un enlace de salida configurado:</span><span class="sxs-lookup"><span data-stu-id="d309d-186">This specialized method simplifies invoking a configured output binding:</span></span>

```csharp
private async Task SendSMSAsync([FromServices] DaprClient daprClient)
{
    var message = "Welcome to this awesome service";
    var metadata = new Dictionary<string, string>
    {
      { "toNumber", "555-3277" }
    };
    await daprClient.InvokeBindingAsync("sms", "create", message, metadata);
}
```

<span data-ttu-id="d309d-187">El método espera los `metadata` valores y `message` .</span><span class="sxs-lookup"><span data-stu-id="d309d-187">The method expects the `metadata` and `message` values.</span></span>

<span data-ttu-id="d309d-188">Cuando se usa para invocar un enlace, `DaprClient` usa gRPC para llamar a la API de DAPR en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-188">When used to invoke a binding, the `DaprClient` uses gRPC to call the Dapr API on the Dapr sidecar.</span></span>

## <a name="binding-components"></a><span data-ttu-id="d309d-189">Enlazar componentes</span><span class="sxs-lookup"><span data-stu-id="d309d-189">Binding components</span></span>

<span data-ttu-id="d309d-190">En el capó, los enlaces de recursos se implementan con componentes de enlace DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-190">Under the hood, resource bindings are implemented with Dapr binding components.</span></span> <span data-ttu-id="d309d-191">Los aporta la comunidad y están escritos en Go.</span><span class="sxs-lookup"><span data-stu-id="d309d-191">They're contributed by the community and written in Go.</span></span> <span data-ttu-id="d309d-192">Si tiene que integrarse con un recurso externo para el que aún no existe ningún enlace DAPR, puede crearlo usted mismo.</span><span class="sxs-lookup"><span data-stu-id="d309d-192">If you need to integrate with an external resource for which no Dapr binding exists yet, you can create it yourself.</span></span> <span data-ttu-id="d309d-193">Consulte el [repositorio de componentes de DAPR-entrib](https://github.com/dapr/components-contrib) para ver cómo puede contribuir con un enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-193">Check out the [Dapr components-contrib repo](https://github.com/dapr/components-contrib) to see how you can contribute a binding.</span></span>

> [!NOTE]
> <span data-ttu-id="d309d-194">DAPR y todos sus componentes se escriben en el lenguaje [Golang](https://golang.org/) (Go).</span><span class="sxs-lookup"><span data-stu-id="d309d-194">Dapr and all of its components are written in the [Golang](https://golang.org/) (Go) language.</span></span> <span data-ttu-id="d309d-195">Go se considera una plataforma moderna de programación nativa en la nube.</span><span class="sxs-lookup"><span data-stu-id="d309d-195">Go is considered a modern, cloud-native programming platform.</span></span>

<span data-ttu-id="d309d-196">Los enlaces se configuran mediante un archivo de configuración YAML.</span><span class="sxs-lookup"><span data-stu-id="d309d-196">You configure bindings using a YAML configuration file.</span></span> <span data-ttu-id="d309d-197">A continuación se muestra un ejemplo de configuración para el enlace de Twitter:</span><span class="sxs-lookup"><span data-stu-id="d309d-197">Here's an example configuration for the Twitter binding:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: twitter-mention
  namespace: default
spec:
  type: bindings.twitter
  version: v1
  metadata:
  - name: consumerKey
    value: "****" # twitter api consumer key, required
  - name: consumerSecret
    value: "****" # twitter api consumer secret, required
  - name: accessToken
    value: "****" # twitter api access token, required
  - name: accessSecret
    value: "****" # twitter api access secret, required
  - name: query
    value: "dapr" # your search query, required
```

<span data-ttu-id="d309d-198">Cada configuración de enlace contiene un `metadata` elemento general con `name` un `namespace` campo y.</span><span class="sxs-lookup"><span data-stu-id="d309d-198">Each binding configuration contains a general `metadata` element with a `name` and `namespace` field.</span></span> <span data-ttu-id="d309d-199">DAPR determinará el punto de conexión para invocar su servicio según el `name` campo configurado.</span><span class="sxs-lookup"><span data-stu-id="d309d-199">Dapr will determine the endpoint to invoke your service based upon the configured `name` field.</span></span> <span data-ttu-id="d309d-200">En el ejemplo anterior, DAPR invocará el método anotado con `/twitter-mention` en el servicio cuando se produce un evento.</span><span class="sxs-lookup"><span data-stu-id="d309d-200">In the above example, Dapr will invoke the method annotated with `/twitter-mention` in your service when an event occurs.</span></span>

<span data-ttu-id="d309d-201">En el `spec` elemento, especifique el `type` del enlace junto con el enlace específico `metadata` .</span><span class="sxs-lookup"><span data-stu-id="d309d-201">In the `spec` element, you specify the `type` of the binding along with binding specific `metadata`.</span></span> <span data-ttu-id="d309d-202">En el ejemplo se especifican las credenciales para acceder a una cuenta de Twitter mediante su API.</span><span class="sxs-lookup"><span data-stu-id="d309d-202">The example specifies credentials for accessing a Twitter account using its API.</span></span> <span data-ttu-id="d309d-203">Los metadatos pueden diferir entre los enlaces de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="d309d-203">The metadata can differ between input and output bindings.</span></span> <span data-ttu-id="d309d-204">Por ejemplo, para usar Twitter como enlace de entrada, debe especificar el texto que se va a buscar en los tweets mediante el `query` campo.</span><span class="sxs-lookup"><span data-stu-id="d309d-204">For example, to use Twitter as an input binding, you need to specify the text to search for in tweets using the `query` field.</span></span> <span data-ttu-id="d309d-205">Cada vez que se envía un tweet coincidente, el sidecar de DAPR invocará el `/twitter-mention` punto de conexión en el servicio.</span><span class="sxs-lookup"><span data-stu-id="d309d-205">Every time a matching tweet is sent, the Dapr sidecar will invoke the `/twitter-mention` endpoint on the service.</span></span> <span data-ttu-id="d309d-206">También proporcionará el contenido del Tweet.</span><span class="sxs-lookup"><span data-stu-id="d309d-206">It will also deliver the contents of the tweet.</span></span>

<span data-ttu-id="d309d-207">Se puede configurar un enlace para la entrada, la salida o ambos.</span><span class="sxs-lookup"><span data-stu-id="d309d-207">A binding can be configured for input, output, or both.</span></span> <span data-ttu-id="d309d-208">Curiosamente, el enlace no especifica explícitamente la configuración de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="d309d-208">Interestingly, the binding doesn't explicitly specify input or output configuration.</span></span> <span data-ttu-id="d309d-209">En su lugar, la dirección se deduce por el uso del enlace junto con los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="d309d-209">Instead, the direction is inferred by the usage of the binding along with configuration values.</span></span>

<span data-ttu-id="d309d-210">La [documentación de DAPR para los enlaces de recursos] [1] proporciona una lista completa de los enlaces disponibles y sus valores de configuración específicos.</span><span class="sxs-lookup"><span data-stu-id="d309d-210">The [Dapr documentation for resource bindings][1] provides a complete list of the available bindings and their specific configuration settings.</span></span>

### <a name="cron-binding"></a><span data-ttu-id="d309d-211">Enlace cron</span><span class="sxs-lookup"><span data-stu-id="d309d-211">Cron binding</span></span>

<span data-ttu-id="d309d-212">Preste mucha atención al enlace cron de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-212">Pay close attention to Dapr's Cron binding.</span></span> <span data-ttu-id="d309d-213">No se suscribe a eventos de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-213">It doesn't subscribe to events from an external system.</span></span> <span data-ttu-id="d309d-214">En su lugar, este enlace utiliza una programación de intervalo configurable para desencadenar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d309d-214">Instead, this binding uses a configurable interval schedule to trigger your application.</span></span> <span data-ttu-id="d309d-215">El enlace proporciona una manera sencilla de implementar un trabajador en segundo plano para reactivarse y realizar algún trabajo a intervalos regulares, sin necesidad de implementar un bucle interminable con un retraso configurable.</span><span class="sxs-lookup"><span data-stu-id="d309d-215">The binding provides a simple way to implement a background worker to wake up and do some work at a regular interval, without the need to implement an endless loop with a configurable delay.</span></span> <span data-ttu-id="d309d-216">Este es un ejemplo de una configuración de enlace cron:</span><span class="sxs-lookup"><span data-stu-id="d309d-216">Here's an example of a Cron binding configuration:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: checkOrderBacklog
  namespace: default
spec:
  type: bindings.cron
  version: v1
  metadata:
  - name: schedule
    value: "@every 30m"
```

<span data-ttu-id="d309d-217">En este ejemplo, DAPR desencadena un servicio mediante la invocación del `/checkOrderBacklog` punto de conexión cada 30 minutos.</span><span class="sxs-lookup"><span data-stu-id="d309d-217">In this example, Dapr triggers a service by invoking the `/checkOrderBacklog` endpoint every 30 minutes.</span></span> <span data-ttu-id="d309d-218">Hay varios patrones disponibles para especificar el `schedule` valor.</span><span class="sxs-lookup"><span data-stu-id="d309d-218">There are several patterns available for specifying the `schedule` value.</span></span> <span data-ttu-id="d309d-219">Para obtener más información, consulte la [documentación de enlace de cron](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/).</span><span class="sxs-lookup"><span data-stu-id="d309d-219">For more information, see the [Cron binding documentation](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/cron/).</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="d309d-220">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="d309d-220">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="d309d-221">La aplicación de referencia eShopOnDapr adjunta implementa un ejemplo de enlace de salida.</span><span class="sxs-lookup"><span data-stu-id="d309d-221">The accompanying eShopOnDapr reference application implements an output binding example.</span></span> <span data-ttu-id="d309d-222">Desencadena el enlace de [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) de DAPR para enviar un correo electrónico al usuario cuando se coloca un nuevo pedido.</span><span class="sxs-lookup"><span data-stu-id="d309d-222">It triggers the Dapr [SendGrid](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/sendgrid/) binding to send a user an email when a new order is placed.</span></span> <span data-ttu-id="d309d-223">Puede encontrar este enlace en el `eshop-email.yaml` archivo de la carpeta componentes:</span><span class="sxs-lookup"><span data-stu-id="d309d-223">You can find this binding in the `eshop-email.yaml` file in the components folder:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: sendmail
  namespace: eshop
spec:
  type: bindings.twilio.sendgrid
  version: v1
  metadata:
  - name: apiKey
    secretKeyRef:
      name: sendGridAPIKey
auth:
  secretStore: eshop-secretstore
```

<span data-ttu-id="d309d-224">Esta configuración usa el componente de enlace [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) .</span><span class="sxs-lookup"><span data-stu-id="d309d-224">This configuration uses the [Twilio SendGrid](https://github.com/dapr/components-contrib/tree/master/bindings/twilio) binding component.</span></span> <span data-ttu-id="d309d-225">Observe cómo la clave de API para conectarse al servicio consume una referencia secreta de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-225">Note how the API key for connecting to the service consumes a Dapr secret reference.</span></span> <span data-ttu-id="d309d-226">Este enfoque mantiene los secretos fuera del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d309d-226">This approach keeps secrets outside of the configuration file.</span></span> <span data-ttu-id="d309d-227">Lea el [capítulo](secrets.md) sobre el bloque de creación de secretos para obtener más información sobre los secretos de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-227">Read the [secrets building block chapter](secrets.md) to learn more about Dapr secrets.</span></span>

<span data-ttu-id="d309d-228">La configuración de enlace especifica un componente de enlace que se puede invocar mediante el `/sendmail` punto de conexión en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-228">The binding configuration specifies a binding component that can be invoked using the `/sendmail` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="d309d-229">A continuación se muestra un fragmento de código en el que se envía un correo electrónico cada vez que se inicia un pedido:</span><span class="sxs-lookup"><span data-stu-id="d309d-229">Here's a code snippet in which an email is sent whenever an order is started:</span></span>

```csharp
public Task Handle(OrderStartedDomainEvent notification, CancellationToken cancellationToken)
{
    var string message = CreateEmailBody(notification);
    var metadata = new Dictionary<string, string>
    {
        {"emailFrom", "eShopOn@dapr.io"},
        {"emailTo", notification.UserName},
        {"subject", $"Your eShopOnDapr order #{notification.Order.Id}"}
    };
    return _daprClient.InvokeBindingAsync("sendmail", "create", message, metadata, cancellationToken);
}
```

<span data-ttu-id="d309d-230">Como puede ver en este ejemplo, `message` contiene el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d309d-230">As you can see in this example, `message` contains the message body.</span></span> <span data-ttu-id="d309d-231">El `CreateEmailBody` método simplemente da formato a una cadena con el texto del cuerpo.</span><span class="sxs-lookup"><span data-stu-id="d309d-231">The `CreateEmailBody` method simply formats a string with the body text.</span></span> <span data-ttu-id="d309d-232">`metadata`Especifica el remitente de correo electrónico, el destinatario y el asunto del mensaje de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="d309d-232">The `metadata` specifies the email sender, recipient, and the subject for the email message.</span></span> <span data-ttu-id="d309d-233">Si estos valores son estáticos, también se pueden incluir en los campos de metadatos del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="d309d-233">If these values are static, they can also be included in the metadata fields in the configuration file.</span></span> <span data-ttu-id="d309d-234">El nombre del enlace que se va a invocar es `sendmail` y la operación es `create` .</span><span class="sxs-lookup"><span data-stu-id="d309d-234">The name of the binding to invoke is `sendmail` and the operation is `create`.</span></span>

## <a name="summary"></a><span data-ttu-id="d309d-235">Resumen</span><span class="sxs-lookup"><span data-stu-id="d309d-235">Summary</span></span>

<span data-ttu-id="d309d-236">Los enlaces de recursos DAPR permiten la integración con distintos sistemas y recursos externos sin tener que tomar dependencias en sus bibliotecas o SDK.</span><span class="sxs-lookup"><span data-stu-id="d309d-236">Dapr resource bindings enable you to integrate with different external resources and systems without taking dependencies on their libraries or SDKs.</span></span> <span data-ttu-id="d309d-237">Estos sistemas externos no tienen por qué ser sistemas de mensajería como un bus de servicio o un agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="d309d-237">These external systems don't necessarily have to be messaging systems like a service bus or message broker.</span></span> <span data-ttu-id="d309d-238">Los enlaces también existen para almacenes de almacén de y recursos web como Twitter o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d309d-238">Bindings also exist for datastores and web resources like Twitter or SendGrid.</span></span>

<span data-ttu-id="d309d-239">Los enlaces de entrada (o desencadenadores) reaccionan a los eventos que se producen en un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-239">Input bindings (or triggers) react to events occurring in an external system.</span></span> <span data-ttu-id="d309d-240">Invocan los puntos de conexión HTTP públicos preconfigurados en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d309d-240">They invoke the public HTTP endpoints pre-configured in your application.</span></span> <span data-ttu-id="d309d-241">DAPR usa el nombre del enlace en la configuración para determinar el punto de conexión al que llamar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d309d-241">Dapr uses the name of the binding in the configuration to determine the endpoint to call in your application.</span></span>

<span data-ttu-id="d309d-242">Los enlaces de salida enviarán mensajes a un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="d309d-242">Output bindings will send messages to an external system.</span></span> <span data-ttu-id="d309d-243">Desencadena un enlace de salida mediante una solicitud HTTP POST en el `/v1.0/bindings/<binding-name>` punto de conexión en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-243">You trigger an output binding by doing an HTTP POST on the `/v1.0/bindings/<binding-name>` endpoint on the Dapr sidecar.</span></span> <span data-ttu-id="d309d-244">También puede usar gRPC para invocar el enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-244">You can also use gRPC to invoke the binding.</span></span> <span data-ttu-id="d309d-245">El SDK de .NET ofrece un `InvokeBindingAsync` método para invocar enlaces de DAPR con gRPC.</span><span class="sxs-lookup"><span data-stu-id="d309d-245">The .NET SDK offers a `InvokeBindingAsync` method to invoke Dapr bindings using gRPC.</span></span>

<span data-ttu-id="d309d-246">Un enlace se implementa con un componente DAPR.</span><span class="sxs-lookup"><span data-stu-id="d309d-246">You implement a binding with a Dapr component.</span></span> <span data-ttu-id="d309d-247">Estos componentes son aportados por la comunidad.</span><span class="sxs-lookup"><span data-stu-id="d309d-247">These components are contributed by the community.</span></span> <span data-ttu-id="d309d-248">La configuración de cada componente de enlace tiene metadatos específicos para el sistema externo que abstrae.</span><span class="sxs-lookup"><span data-stu-id="d309d-248">Each binding component's configuration has metadata that is specific for the external system it abstracts.</span></span> <span data-ttu-id="d309d-249">Además, los comandos que admite y la estructura de la carga variarán en función del componente de enlace.</span><span class="sxs-lookup"><span data-stu-id="d309d-249">Also, the commands it supports and the structure of the payload will differ per binding component.</span></span>

### <a name="references"></a><span data-ttu-id="d309d-250">Referencias</span><span class="sxs-lookup"><span data-stu-id="d309d-250">References</span></span>

- [<span data-ttu-id="d309d-251">Documentación de DAPR para enlaces de recursos</span><span class="sxs-lookup"><span data-stu-id="d309d-251">Dapr documentation for resource bindings</span></span>](https://docs.dapr.io/operations/components/setup-bindings/supported-bindings/)

>[!div class="step-by-step"]
><span data-ttu-id="d309d-252">[Anterior](publish-subscribe.md)
>[Siguiente](observability.md)</span><span class="sxs-lookup"><span data-stu-id="d309d-252">[Previous](publish-subscribe.md)
[Next](observability.md)</span></span>
