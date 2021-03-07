---
title: El bloque DAPR Publish & subscribe Building
description: Una descripción de la publicación DAPR & subscribe Building-Block y cómo aplicarla
author: edwinvw
ms.date: 02/07/2021
ms.openlocfilehash: 3d00c5a3171dd5a7287d07675f5a3742697e784b
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102401920"
---
# <a name="the-dapr-publish--subscribe-building-block"></a><span data-ttu-id="cdbbf-103">El bloque DAPR Publish & subscribe Building</span><span class="sxs-lookup"><span data-stu-id="cdbbf-103">The Dapr publish & subscribe building block</span></span>

<span data-ttu-id="cdbbf-104">El [patrón de publicación y suscripción](/azure/architecture/patterns/publisher-subscriber) (a menudo denominado "pub/sub") es un patrón de mensajería conocido y ampliamente utilizado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-104">The [Publish-Subscribe pattern](/azure/architecture/patterns/publisher-subscriber) (often referred to as "pub/sub") is a well-known and widely used messaging pattern.</span></span> <span data-ttu-id="cdbbf-105">Los arquitectos lo adoptan normalmente en aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-105">Architects commonly embrace it in distributed applications.</span></span> <span data-ttu-id="cdbbf-106">Sin embargo, la infraestructura para implementarla puede ser compleja.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-106">However, the plumbing to implement it can be complex.</span></span> <span data-ttu-id="cdbbf-107">A menudo hay diferencias de características sutiles entre distintos productos de mensajería.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-107">There are often subtle feature differences across different messaging products.</span></span> <span data-ttu-id="cdbbf-108">DAPR ofrece un bloque de creación que simplifica considerablemente la implementación de la funcionalidad de pub/sub.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-108">Dapr offers a building block that significantly simplifies implementing pub/sub functionality.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="cdbbf-109">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="cdbbf-109">What it solves</span></span>

<span data-ttu-id="cdbbf-110">La principal ventaja del patrón Publish-Subscribe es el **acoplamiento flexible**, que a veces se conoce como [desacoplamiento temporal](/azure/architecture/guide/technology-choices/messaging#decoupling).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-110">The primary advantage of the Publish-Subscribe pattern is **loose coupling**, sometimes referred to as [temporal decoupling](/azure/architecture/guide/technology-choices/messaging#decoupling).</span></span> <span data-ttu-id="cdbbf-111">El patrón desacopla los servicios que envían mensajes (los **publicadores**) de los servicios que consumen mensajes (los **suscriptores**).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-111">The pattern decouples services that send messages (the **publishers**) from services that consume messages (the **subscribers**).</span></span> <span data-ttu-id="cdbbf-112">Los publicadores y los suscriptores no se reconocen entre sí: ambos dependen de un agente de **mensajes** centralizado que distribuye los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-112">Both publishers and subscribers are unaware of each other - both are dependent on a centralized **message broker** that distributes the messages.</span></span>

<span data-ttu-id="cdbbf-113">En la figura 7-1 se muestra la arquitectura de alto nivel del patrón pub/sub.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-113">Figure 7-1 shows the high-level architecture of the pub/sub pattern.</span></span>

![El patrón pub/sub](./media/publish-subscribe/pub-sub-pattern.png)

<span data-ttu-id="cdbbf-115">**Figura 7-1**.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-115">**Figure 7-1**.</span></span> <span data-ttu-id="cdbbf-116">El patrón pub/sub.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-116">The pub/sub pattern.</span></span>

<span data-ttu-id="cdbbf-117">En la ilustración anterior, tenga en cuenta los pasos del patrón:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-117">From the previous figure, note the steps of the pattern:</span></span>

1. <span data-ttu-id="cdbbf-118">Los publicadores envían mensajes al agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-118">Publishers send messages to the message broker.</span></span>
1. <span data-ttu-id="cdbbf-119">Los suscriptores se enlazan a una suscripción en el agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-119">Subscribers bind to a subscription on the message broker.</span></span>
1. <span data-ttu-id="cdbbf-120">El agente de mensajes reenvía una copia del mensaje a las suscripciones interesadas.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-120">The message broker forwards a copy of the message to interested subscriptions.</span></span>
1. <span data-ttu-id="cdbbf-121">Los suscriptores consumen mensajes de sus suscripciones.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-121">Subscribers consume messages from their subscriptions.</span></span>

<span data-ttu-id="cdbbf-122">La mayoría de los agentes de mensajes encapsulan un mecanismo de puesta en cola que puede conservar los mensajes una vez recibidos.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-122">Most message brokers encapsulate a queueing mechanism that can persist messages once received.</span></span> <span data-ttu-id="cdbbf-123">Con él, el agente de mensajes garantiza la **durabilidad** almacenando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-123">With it, the message broker guarantees **durability** by storing the message.</span></span> <span data-ttu-id="cdbbf-124">No es necesario que los suscriptores estén disponibles de inmediato o incluso en línea cuando un publicador envía un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-124">Subscribers don't need to be immediately available or even online when a publisher sends a message.</span></span> <span data-ttu-id="cdbbf-125">Una vez disponible, el suscriptor recibe y procesa el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-125">Once available, the subscriber receives and processes the message.</span></span>  <span data-ttu-id="cdbbf-126">DAPR garantiza **una semántica al menos una vez** para la entrega de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-126">Dapr guarantees **At-Least-Once** semantics for message delivery.</span></span> <span data-ttu-id="cdbbf-127">Una vez que se publica un mensaje, se entregará al menos una vez a cualquier suscriptor interesado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-127">Once a message is published, it will be delivered at least once to any interested subscriber.</span></span>

 > <span data-ttu-id="cdbbf-128">Si el servicio solo puede procesar un mensaje una vez, deberá proporcionar una comprobación de [Idempotencia](/azure/architecture/microservices/design/api-design#idempotent-operations) para asegurarse de que el mismo mensaje no se procesa varias veces.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-128">If your service can only process a message once, you'll need to provide an [idempotency check](/azure/architecture/microservices/design/api-design#idempotent-operations) to ensure that the same message is not processed multiple times.</span></span> <span data-ttu-id="cdbbf-129">Aunque esta lógica se puede codificar, algunos agentes de mensajes, como Azure Service Bus, proporcionan capacidades de mensajería de *detección de duplicados* integrados.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-129">While such logic can be coded, some message brokers, such as Azure Service Bus, provide built-in *duplicate detection* messaging capabilities.</span></span>

<span data-ttu-id="cdbbf-130">Hay varios productos de agente de mensajes disponibles, tanto comerciales como de código abierto.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-130">There are several message broker products available - both commercially and open-source.</span></span> <span data-ttu-id="cdbbf-131">Cada una tiene ventajas y desventajas.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-131">Each has advantages and drawbacks.</span></span> <span data-ttu-id="cdbbf-132">Su trabajo es cumplir los requisitos del sistema con el agente adecuado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-132">Your job is to match your system requirements to the appropriate broker.</span></span> <span data-ttu-id="cdbbf-133">Una vez seleccionado, se recomienda desacoplar la aplicación de la fontanería del agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-133">Once selected, it's a best practice to decouple your application from message broker plumbing.</span></span> <span data-ttu-id="cdbbf-134">Para lograr esta funcionalidad, ajuste el agente dentro de una *abstracción*.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-134">You achieve this functionality by wrapping the broker inside an *abstraction*.</span></span> <span data-ttu-id="cdbbf-135">La abstracción encapsula la fontanería del mensaje y expone operaciones genéricas de pub/sub en el código.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-135">The abstraction encapsulates the message plumbing and exposes generic pub/sub operations to your code.</span></span> <span data-ttu-id="cdbbf-136">El código se comunica con la abstracción, no con el agente de mensajes real.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-136">Your code communicates with the abstraction, not the actual message broker.</span></span> <span data-ttu-id="cdbbf-137">A pesar de tomar una decisión acertada, tendrá que escribir y mantener la abstracción y su implementación subyacente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-137">While a wise decision, you'll have to write and maintain the abstraction and its underlying implementation.</span></span> <span data-ttu-id="cdbbf-138">Este enfoque requiere código personalizado que puede ser complejo, repetitivo y propenso a errores.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-138">This approach requires custom code that can be complex, repetitive, and error-prone.</span></span>

<span data-ttu-id="cdbbf-139">El bloque DAPR Publish & subscribe Building proporciona la abstracción de mensajería y la implementación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-139">The Dapr publish & subscribe building block provides the messaging abstraction and implementation out-of-the-box.</span></span> <span data-ttu-id="cdbbf-140">El código personalizado que habría tenido que escribir está precompilado y encapsulado en el bloque de creación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-140">The custom code you would have had to write is prebuilt and encapsulated inside the Dapr building block.</span></span> <span data-ttu-id="cdbbf-141">Se enlaza a él y se usa.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-141">You bind to it and consume it.</span></span> <span data-ttu-id="cdbbf-142">En lugar de escribir el código de la infraestructura de mensajería, usted y su equipo se centran en crear funciones empresariales que agregan valor a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-142">Instead of writing messaging plumbing code, you and your team focus on creating business functionality that adds value to your customers.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="cdbbf-143">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="cdbbf-143">How it works</span></span>

<span data-ttu-id="cdbbf-144">El bloque DAPR Publish & subscribe Building proporciona un marco de API independiente de la plataforma para enviar y recibir mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-144">The Dapr publish & subscribe building block provides a platform-agnostic API framework to send and receive messages.</span></span> <span data-ttu-id="cdbbf-145">Los servicios publican mensajes en un [tema](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions)con nombre.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-145">Your services publish messages to a named [topic](/azure/service-bus-messaging/service-bus-queues-topics-subscriptions#topics-and-subscriptions).</span></span> <span data-ttu-id="cdbbf-146">Los servicios se suscriben a un tema para consumir mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-146">Your services subscribe to a topic to consume messages.</span></span>

<span data-ttu-id="cdbbf-147">El servicio llama a la API pub/sub en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-147">The service calls the pub/sub API on the Dapr sidecar.</span></span> <span data-ttu-id="cdbbf-148">A continuación, el sidecar realiza las llamadas a un componente pub/sub de DAPR predefinido que encapsula un producto de agente de mensajes específico.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-148">The sidecar then makes calls into a pre-defined Dapr pub/sub component that encapsulates a specific message broker product.</span></span> <span data-ttu-id="cdbbf-149">En la figura 7-2 se muestra la pila de mensajería pub/sub de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-149">Figure 7-2 shows the Dapr pub/sub messaging stack.</span></span>

![La pila pub/sub](./media/publish-subscribe/pub-sub-buildingblock.png)

<span data-ttu-id="cdbbf-151">**Figura 7-2**.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-151">**Figure 7-2**.</span></span> <span data-ttu-id="cdbbf-152">La pila pub/sub de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-152">The Dapr pub/sub stack.</span></span>

<span data-ttu-id="cdbbf-153">El bloque DAPR Publish & subscribe Building se puede invocar de muchas maneras.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-153">The Dapr publish & subscribe building block can be invoked in many ways.</span></span>

<span data-ttu-id="cdbbf-154">En el nivel más bajo, cualquier plataforma de programación puede invocar el bloque de creación a través de HTTP o gRPC con la **API nativa de DAPR**.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-154">At the lowest level, any programming platform can invoke the building block over HTTP or gRPC using the **Dapr native API**.</span></span> <span data-ttu-id="cdbbf-155">Para publicar un mensaje, realice la siguiente llamada de API:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-155">To publish a message, you make the following API call:</span></span>

``` http
http://localhost:<dapr-port>/v1.0/publish/<pub-sub-name>/<topic>
```

<span data-ttu-id="cdbbf-156">Hay varios segmentos de dirección URL específicos de DAPR en la llamada anterior:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-156">There are several Dapr specific URL segments in the above call:</span></span>

- <span data-ttu-id="cdbbf-157">`<dapr-port>` proporciona el número de puerto en el que escucha el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-157">`<dapr-port>` provides the port number upon which the Dapr sidecar is listening.</span></span>
- <span data-ttu-id="cdbbf-158">`<pub-sub-name>` proporciona el nombre del componente pub/sub de DAPR seleccionado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-158">`<pub-sub-name>` provides the name of the selected Dapr pub/sub component.</span></span>
- <span data-ttu-id="cdbbf-159">`<topic>` proporciona el nombre del tema en el que se publica el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-159">`<topic>` provides the name of the topic to which the message is published.</span></span>

<span data-ttu-id="cdbbf-160">Con la herramienta de línea de comandos de *rizo* para publicar un mensaje, puede probarlo:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-160">Using the *curl* command-line tool to publish a message, you can try it out:</span></span>

``` curl
curl -X POST http://localhost:3500/v1.0/publish/pubsub/newOrder \
  -H "Content-Type: application/json" \
  -d '{ "orderId": "1234", "productId": "5678", "amount": 2 }'
```

<span data-ttu-id="cdbbf-161">Los mensajes se reciben Suscríbase a un tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-161">You receive messages by subscribing to a topic.</span></span> <span data-ttu-id="cdbbf-162">En el inicio, el tiempo de ejecución de DAPR llamará a la aplicación en un punto de conexión conocido para identificar y crear las suscripciones necesarias:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-162">At startup, the Dapr runtime will call the application on a well-known endpoint to identify and create the required subscriptions:</span></span>

``` http
http://localhost:<appPort>/dapr/subscribe
```

- <span data-ttu-id="cdbbf-163">`<appPort>` informa al sidecar de DAPR del puerto en el que escucha la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-163">`<appPort>` informs the Dapr sidecar of the port upon which the application is listening.</span></span>

<span data-ttu-id="cdbbf-164">Puede implementar este punto de conexión usted mismo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-164">You can implement this endpoint yourself.</span></span> <span data-ttu-id="cdbbf-165">Sin embargo, DAPR proporciona formas más intuitivas de implementarlo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-165">But Dapr provides more intuitive ways of implementing it.</span></span> <span data-ttu-id="cdbbf-166">Abordaremos esta funcionalidad más adelante en este capítulo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-166">We'll address this functionality later in this chapter.</span></span>

<span data-ttu-id="cdbbf-167">La respuesta de la llamada contiene una lista de temas a los que se suscribirán las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-167">The response from the call contains a list of topics to which the applications will subscribe.</span></span> <span data-ttu-id="cdbbf-168">Cada uno incluye un extremo al que llamar cuando el tema recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-168">Each includes an endpoint to call when the topic receives a message.</span></span> <span data-ttu-id="cdbbf-169">A continuación se muestra un ejemplo de una respuesta:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-169">Here's an example of a response:</span></span>

```json
[
  {
    "pubsubname": "pubsub",
    "topic": "newOrder",
    "route": "/orders"
  },
  {
    "pubsubname": "pubsub",
    "topic": "newProduct",
    "route": "/productCatalog/products"
  }
]
```

<span data-ttu-id="cdbbf-170">En la respuesta JSON, puede ver que la aplicación desea suscribirse a los temas `newOrder` y `newProduct` .</span><span class="sxs-lookup"><span data-stu-id="cdbbf-170">In the JSON response, you can see the application wants to subscribe to topics `newOrder` and `newProduct`.</span></span> <span data-ttu-id="cdbbf-171">Registra los puntos `/orders` de conexión y `/productCatalog/products` para cada uno de ellos, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-171">It registers the endpoints `/orders` and `/productCatalog/products` for each, respectively.</span></span> <span data-ttu-id="cdbbf-172">En ambas suscripciones, la aplicación se enlaza al componente DAPR denominado `pubsub` .</span><span class="sxs-lookup"><span data-stu-id="cdbbf-172">For both subscriptions, the application is binding to the Dapr component named `pubsub`.</span></span>

<span data-ttu-id="cdbbf-173">En la figura 7-3 se presenta el flujo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-173">Figure 7-3 presents the flow of the example.</span></span>

![Ejemplo de flujo de pub/sub con DAPR](media/publish-subscribe/pub-sub-flow.png)

<span data-ttu-id="cdbbf-175">**Figura 7-3**.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-175">**Figure 7-3**.</span></span> <span data-ttu-id="cdbbf-176">flujo pub/sub con DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-176">pub/sub flow with Dapr.</span></span>

<span data-ttu-id="cdbbf-177">En la ilustración anterior, tenga en cuenta el flujo:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-177">From the previous figure, note the flow:</span></span>

1. <span data-ttu-id="cdbbf-178">El sidecar de DAPR para el servicio B llama al `/dapr/subscribe` extremo del servicio b (el consumidor).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-178">The Dapr sidecar for Service B calls the `/dapr/subscribe` endpoint from Service B (the consumer).</span></span> <span data-ttu-id="cdbbf-179">El servicio responde con las suscripciones que desea crear.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-179">The service responds with the subscriptions it wants to create.</span></span>
1. <span data-ttu-id="cdbbf-180">El sidecar de DAPR para el servicio B crea las suscripciones solicitadas en el agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-180">The Dapr sidecar for Service B creates the requested subscriptions on the message broker.</span></span>
1. <span data-ttu-id="cdbbf-181">El servicio A publica un mensaje en el `/v1.0/publish/<pub-sub-name>/<topic>` punto de conexión en el servicio DAPR a sidecar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-181">Service A publishes a message at the `/v1.0/publish/<pub-sub-name>/<topic>` endpoint on the Dapr Service A sidecar.</span></span>
1. <span data-ttu-id="cdbbf-182">El servicio a sidecar publica el mensaje en el agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-182">The Service A sidecar publishes the message to the message broker.</span></span>
1. <span data-ttu-id="cdbbf-183">El agente de mensajes envía una copia del mensaje al sidecar del servicio B.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-183">The message broker sends a copy of the message to the Service B sidecar.</span></span>
1. <span data-ttu-id="cdbbf-184">El sidecar del servicio B llama al punto de conexión correspondiente a la suscripción (en este caso `/orders` ) del servicio b. El servicio responde con un código de Estado HTTP `200 OK` para que el sidecar considere que el mensaje se administra correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-184">The Service B sidecar calls the endpoint corresponding to the subscription (in this case `/orders`) on Service B. The service responds with an HTTP status-code `200 OK` so the sidecar will consider the message as being handled successfully.</span></span>

<span data-ttu-id="cdbbf-185">En el ejemplo, el mensaje se trata correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-185">In the example, the message is handled successfully.</span></span> <span data-ttu-id="cdbbf-186">Pero si algo va mal mientras el servicio B controla la solicitud, puede usar la respuesta para especificar lo que debe ocurrir con el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-186">But if something goes wrong while Service B is handling the request, it can use the response to specify what needs to happen with the message.</span></span> <span data-ttu-id="cdbbf-187">Cuando devuelve un código de Estado HTTP `404` , se registra un error y se quita el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-187">When it returns an HTTP status-code `404`, an error is logged and the message is dropped.</span></span> <span data-ttu-id="cdbbf-188">Con cualquier otro código de estado que sea `200` o `404` , se registra una advertencia y se vuelve a intentar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-188">With any other status-code than `200` or `404`, a warning is logged and the message is retried.</span></span> <span data-ttu-id="cdbbf-189">Como alternativa, el servicio B puede especificar explícitamente lo que debe ocurrir con el mensaje incluyendo una carga de JSON en el cuerpo de la respuesta:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-189">Alternatively, Service B can explicitly specify what needs to happen with the message by including a JSON payload in the body of the response:</span></span>

```json
{
  "status": "<status>"
}
```

<span data-ttu-id="cdbbf-190">En la tabla siguiente se muestran los `status` valores disponibles:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-190">The following table shows the available `status` values:</span></span>

| <span data-ttu-id="cdbbf-191">Estado</span><span class="sxs-lookup"><span data-stu-id="cdbbf-191">Status</span></span>           | <span data-ttu-id="cdbbf-192">Acción</span><span class="sxs-lookup"><span data-stu-id="cdbbf-192">Action</span></span>                                                       |
| ---------------- | ------------------------------------------------------------ |
| <span data-ttu-id="cdbbf-193">CORRECTA</span><span class="sxs-lookup"><span data-stu-id="cdbbf-193">SUCCESS</span></span>          | <span data-ttu-id="cdbbf-194">El mensaje se considera como procesado correctamente y se ha quitado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-194">The message is considered as processed successfully and dropped.</span></span> |
| <span data-ttu-id="cdbbf-195">REINTENTAR</span><span class="sxs-lookup"><span data-stu-id="cdbbf-195">RETRY</span></span>            | <span data-ttu-id="cdbbf-196">El mensaje se vuelve a intentar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-196">The message is retried.</span></span>                                      |
| <span data-ttu-id="cdbbf-197">DROP</span><span class="sxs-lookup"><span data-stu-id="cdbbf-197">DROP</span></span>             | <span data-ttu-id="cdbbf-198">Se registra una advertencia y se quita el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-198">A warning is logged and the message is dropped.</span></span>              |
| <span data-ttu-id="cdbbf-199">Cualquier otro Estado</span><span class="sxs-lookup"><span data-stu-id="cdbbf-199">Any other status</span></span> | <span data-ttu-id="cdbbf-200">El mensaje se vuelve a intentar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-200">The message is retried.</span></span>                                      |

### <a name="competing-consumers"></a><span data-ttu-id="cdbbf-201">Consumidores de la competencia</span><span class="sxs-lookup"><span data-stu-id="cdbbf-201">Competing consumers</span></span>

<span data-ttu-id="cdbbf-202">Al escalar horizontalmente una aplicación que se suscribe a un tema, debe tratar con los consumidores de la competencia.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-202">When scaling out an application that subscribes to a topic, you have to deal with competing consumers.</span></span> <span data-ttu-id="cdbbf-203">Solo una instancia de aplicación debe controlar un mensaje enviado al tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-203">Only one application instance should handle a message sent to the topic.</span></span> <span data-ttu-id="cdbbf-204">Afortunadamente, DAPR controla ese problema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-204">Luckily, Dapr handles that problem.</span></span> <span data-ttu-id="cdbbf-205">Cuando varias instancias de un servicio con el mismo identificador de aplicación se suscriben a un tema, DAPR entrega cada mensaje solo a uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-205">When multiple instances of a service with the same application-id subscribe to a topic, Dapr delivers each message to only one of them.</span></span>

### <a name="sdks"></a><span data-ttu-id="cdbbf-206">SDK</span><span class="sxs-lookup"><span data-stu-id="cdbbf-206">SDKs</span></span>

<span data-ttu-id="cdbbf-207">Realizar llamadas HTTP a las API de DAPR nativas requiere mucho tiempo y es abstracto.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-207">Making HTTP calls to the native Dapr APIs is time-consuming and abstract.</span></span> <span data-ttu-id="cdbbf-208">Las llamadas se diseñan en el nivel de HTTP y deberá controlar los problemas de fontanería, como la serialización y los códigos de respuesta HTTP.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-208">Your calls are crafted at the HTTP level, and you'll need to handle plumbing concerns such as serialization and HTTP response codes.</span></span> <span data-ttu-id="cdbbf-209">Afortunadamente, hay una forma más intuitiva.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-209">Fortunately, there's a more intuitive way.</span></span> <span data-ttu-id="cdbbf-210">DAPR proporciona varios SDK específicos del lenguaje para plataformas de desarrollo populares.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-210">Dapr provides several language-specific SDKs for popular development platforms.</span></span> <span data-ttu-id="cdbbf-211">En el momento de redactar este documento, vaya, Node.js, Python, .NET, Java y JavaScript están disponibles.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-211">At the time of this writing, Go, Node.js, Python, .NET, Java, and JavaScript are available.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="cdbbf-212">Uso del SDK de .NET para DAPR</span><span class="sxs-lookup"><span data-stu-id="cdbbf-212">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="cdbbf-213">Para los desarrolladores de .NET, el [SDK de .net para DAPR](https://www.nuget.org/packages/Dapr.Client) proporciona una manera más productiva de trabajar con DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-213">For .NET Developers, the [Dapr .NET SDK](https://www.nuget.org/packages/Dapr.Client) provides a more productive way of working with Dapr.</span></span> <span data-ttu-id="cdbbf-214">El SDK expone una `DaprClient` clase a través de la cual puede invocar directamente la funcionalidad de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-214">The SDK exposes a `DaprClient` class through which you can directly invoke Dapr functionality.</span></span> <span data-ttu-id="cdbbf-215">Es intuitivo y fácil de usar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-215">It's intuitive and easy to use.</span></span>

<span data-ttu-id="cdbbf-216">Para publicar un mensaje, `DaprClient` expone un `PublishEventAsync` método.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-216">To publish a message, the `DaprClient` exposes a `PublishEventAsync` method.</span></span>

```csharp
var data = new OrderData
{
  orderId = "123456",
  productId = "67890",
  amount = 2
};

var daprClient = new DaprClientBuilder().Build();

await daprClient.PublishEventAsync<OrderData>("pubsub", "newOrder", data);
```

- <span data-ttu-id="cdbbf-217">El primer argumento `pubsub` es el nombre del componente DAPR que proporciona la implementación del agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-217">The first argument `pubsub` is the name of the Dapr component that provides the message broker implementation.</span></span> <span data-ttu-id="cdbbf-218">Abordaremos los componentes más adelante en este capítulo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-218">We'll address components later in this chapter.</span></span>
- <span data-ttu-id="cdbbf-219">El segundo argumento `neworder` proporciona el nombre del tema al que se va a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-219">The second argument `neworder` provides the name of the topic to send the message to.</span></span>
- <span data-ttu-id="cdbbf-220">El tercer argumento es la carga del mensaje.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-220">The third argument is the payload of the message.</span></span>
- <span data-ttu-id="cdbbf-221">Puede especificar el tipo .NET del mensaje utilizando el parámetro de tipo genérico del método.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-221">You can specify the .NET type of the message using the generic type parameter of the method.</span></span>

<span data-ttu-id="cdbbf-222">Para recibir mensajes, debe enlazar un punto de conexión a una suscripción para un tema registrado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-222">To receive messages, you bind an endpoint to a subscription for a registered topic.</span></span> <span data-ttu-id="cdbbf-223">La biblioteca de AspNetCore para DAPR hace que sea trivial.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-223">The AspNetCore library for Dapr makes this trivial.</span></span> <span data-ttu-id="cdbbf-224">Por ejemplo, supongamos que tiene un método de acción ASP.NET WebAPI existente titulado `CreateOrder` :</span><span class="sxs-lookup"><span data-stu-id="cdbbf-224">Assume, for example, that you have an existing ASP.NET WebAPI action method entitled `CreateOrder`:</span></span>

```csharp
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

 > <span data-ttu-id="cdbbf-225">Debe agregar una referencia al paquete de NuGet [DAPR. AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) en el proyecto para consumir la integración de DAPR ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-225">You must add a reference to the [Dapr.AspNetCore](https://www.nuget.org/packages/Dapr.AspNetCore) NuGet package in your project to consume the Dapr ASP.NET Core integration.</span></span>

<span data-ttu-id="cdbbf-226">Para enlazar este método de acción a un tema, debe decorarlo con el `Topic` atributo:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-226">To bind this action method to a topic, you decorate it with the `Topic` attribute:</span></span>

```csharp
[Topic("pubsub", "newOrder")]
[HttpPost("/orders")]
public async Task<ActionResult> CreateOrder(Order order)
```

<span data-ttu-id="cdbbf-227">Se especifican dos elementos clave con este atributo:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-227">You specify two key elements with this attribute:</span></span>

- <span data-ttu-id="cdbbf-228">Componente pub/sub de DAPR de destino (en este caso `pubsub` ).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-228">The Dapr pub/sub component to target (in this case `pubsub`).</span></span>
- <span data-ttu-id="cdbbf-229">Tema al que se va a suscribir (en este caso `newOrder` ).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-229">The topic to subscribe to (in this case `newOrder`).</span></span>

<span data-ttu-id="cdbbf-230">A continuación, DAPR invoca ese método de acción a medida que recibe mensajes para ese tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-230">Dapr then invokes that action method as it receives messages for that topic.</span></span>

<span data-ttu-id="cdbbf-231">También necesitará habilitar ASP.NET Core para usar DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-231">You'll also need to enable ASP.NET Core to use Dapr.</span></span> <span data-ttu-id="cdbbf-232">El SDK de .NET para DAPR proporciona varios métodos de extensión que se pueden invocar en la `Startup` clase.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-232">The Dapr .NET SDK provides several extension methods that can be invoked in the `Startup` class.</span></span>

<span data-ttu-id="cdbbf-233">En el `ConfigureServices` método, debe agregar el siguiente método de extensión:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-233">In the `ConfigureServices` method, you must add the following extension method:</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    // ...
    services.AddControllers().AddDapr();
}
```

<span data-ttu-id="cdbbf-234">Al anexar el `AddDapr` método de extensión al `AddControllers` método de extensión, se registran los servicios necesarios para integrar DAPR en la canalización de MVC.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-234">Appending the `AddDapr` extension-method to the `AddControllers` extension-method registers the necessary services to integrate Dapr into the MVC pipeline.</span></span> <span data-ttu-id="cdbbf-235">También registra una `DaprClient` instancia en el contenedor de inserción de dependencias, que se puede insertar en cualquier parte del servicio.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-235">It also registers a `DaprClient` instance into the dependency injection container, which then can be injected anywhere into your service.</span></span>

<span data-ttu-id="cdbbf-236">En el `Configure` método, debe agregar los siguientes componentes de middleware para habilitar DAPR:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-236">In the `Configure` method, you must add the following middleware components to enable Dapr:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IWebHostEnvironment env)
{
    // ...
    app.UseCloudEvents();

    app.UseEndpoints(endpoints =>
    {
        endpoints.MapSubscribeHandler();
        // ...
    });
}
```

<span data-ttu-id="cdbbf-237">La llamada a `UseCloudEvents` agrega middleware de **CloudEvents** a la canalización de middleware ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-237">The call to `UseCloudEvents` adds **CloudEvents** middleware into to the ASP.NET Core middleware pipeline.</span></span> <span data-ttu-id="cdbbf-238">Este middleware desencapsulará las solicitudes que usan el formato estructurado CloudEvents, por lo que el método receptor puede leer la carga del evento directamente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-238">This middleware will unwrap requests that use the CloudEvents structured format, so the receiving method can read the event payload directly.</span></span>

> <span data-ttu-id="cdbbf-239">[CloudEvents](https://cloudevents.io/) es un formato de mensajería normalizado, que proporciona una manera común de describir la información de eventos entre plataformas.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-239">[CloudEvents](https://cloudevents.io/) is a standardized messaging format, providing a common way to describe event information across platforms.</span></span> <span data-ttu-id="cdbbf-240">DAPR adopta CloudEvents.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-240">Dapr embraces CloudEvents.</span></span> <span data-ttu-id="cdbbf-241">Para obtener más información sobre CloudEvents, consulte la [especificación de CloudEvents](https://github.com/cloudevents/spec/tree/v1.0).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-241">For more information about CloudEvents, see the [cloudevents specification](https://github.com/cloudevents/spec/tree/v1.0).</span></span>

<span data-ttu-id="cdbbf-242">La llamada a `MapSubscribeHandler` en la configuración de enrutamiento del punto de conexión agregará un punto de conexión de suscripción de DAPR a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-242">The call to `MapSubscribeHandler` in the endpoint routing configuration will add a Dapr subscribe endpoint to the application.</span></span> <span data-ttu-id="cdbbf-243">Este punto de conexión responderá a las solicitudes de `/dapr/subscribe` .</span><span class="sxs-lookup"><span data-stu-id="cdbbf-243">This endpoint will respond to requests on `/dapr/subscribe`.</span></span> <span data-ttu-id="cdbbf-244">Cuando se llama a este punto de conexión, buscará automáticamente todos los métodos de acción de WebAPI decorados con el `Topic` atributo e indicará a DAPR que cree suscripciones para ellos.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-244">When this endpoint is called, it will automatically find all WebAPI action methods decorated with the `Topic` attribute and instruct Dapr to create subscriptions for them.</span></span>

## <a name="pubsub-components"></a><span data-ttu-id="cdbbf-245">Componentes pub/sub</span><span class="sxs-lookup"><span data-stu-id="cdbbf-245">Pub/sub components</span></span>

<span data-ttu-id="cdbbf-246">Los [componentes pub/sub](https://github.com/dapr/components-contrib/tree/master/pubsub) de DAPR controlan el transporte real de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-246">Dapr [pub/sub components](https://github.com/dapr/components-contrib/tree/master/pubsub) handle the actual transport of the messages.</span></span> <span data-ttu-id="cdbbf-247">Hay varios disponibles.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-247">Several are available.</span></span> <span data-ttu-id="cdbbf-248">Cada encapsula un producto de agente de mensajes específico para implementar la funcionalidad pub/sub.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-248">Each encapsulates a specific message broker product to implement the pub/sub functionality.</span></span> <span data-ttu-id="cdbbf-249">En el momento de escribir este documento, los siguientes componentes pub/sub estaban disponibles:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-249">At the time of writing, the following pub/sub components were available:</span></span>

- <span data-ttu-id="cdbbf-250">Apache Kafka</span><span class="sxs-lookup"><span data-stu-id="cdbbf-250">Apache Kafka</span></span>
- <span data-ttu-id="cdbbf-251">Azure Event Hubs</span><span class="sxs-lookup"><span data-stu-id="cdbbf-251">Azure Event Hubs</span></span>
- <span data-ttu-id="cdbbf-252">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="cdbbf-252">Azure Service Bus</span></span>
- <span data-ttu-id="cdbbf-253">SNS/SQS DE AWS</span><span class="sxs-lookup"><span data-stu-id="cdbbf-253">AWS SNS/SQS</span></span>
- <span data-ttu-id="cdbbf-254">Pub/sub de GCP</span><span class="sxs-lookup"><span data-stu-id="cdbbf-254">GCP Pub/Sub</span></span>
- <span data-ttu-id="cdbbf-255">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="cdbbf-255">Hazelcast</span></span>
- <span data-ttu-id="cdbbf-256">MQTT</span><span class="sxs-lookup"><span data-stu-id="cdbbf-256">MQTT</span></span>
- <span data-ttu-id="cdbbf-257">NATS</span><span class="sxs-lookup"><span data-stu-id="cdbbf-257">NATS</span></span>
- <span data-ttu-id="cdbbf-258">Pulsar</span><span class="sxs-lookup"><span data-stu-id="cdbbf-258">Pulsar</span></span>
- <span data-ttu-id="cdbbf-259">RabbitMQ</span><span class="sxs-lookup"><span data-stu-id="cdbbf-259">RabbitMQ</span></span>
- <span data-ttu-id="cdbbf-260">Secuencias de Redis</span><span class="sxs-lookup"><span data-stu-id="cdbbf-260">Redis Streams</span></span>

> [!NOTE]
> <span data-ttu-id="cdbbf-261">La pila en la nube de Azure tiene la funcionalidad de mensajería (Azure Service Bus) y la disponibilidad de streaming de eventos (Azure Event hubs).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-261">The Azure cloud stack has both messaging functionality (Azure Service Bus) and event streaming (Azure Event Hub) availability.</span></span>

<span data-ttu-id="cdbbf-262">Estos componentes los crea la comunidad en un repositorio de componentes que se contrata [en github](https://github.com/dapr/components-contrib/tree/master/pubsub).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-262">These components are created by the community in a [component-contrib repository on GitHub](https://github.com/dapr/components-contrib/tree/master/pubsub).</span></span> <span data-ttu-id="cdbbf-263">Le recomendamos que escriba su propio componente DAPR para un agente de mensajes que todavía no se admite.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-263">You're encouraged to write your own Dapr component for a message broker that isn't yet supported.</span></span>

### <a name="configure-pubsub-components"></a><span data-ttu-id="cdbbf-264">Configurar componentes pub/sub</span><span class="sxs-lookup"><span data-stu-id="cdbbf-264">Configure pub/sub components</span></span>

<span data-ttu-id="cdbbf-265">Mediante el uso de un archivo de configuración DAPR, puede especificar los componentes pub/sub que se van a usar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-265">Using a Dapr configuration file, you can specify the pub/sub component(s) to use.</span></span> <span data-ttu-id="cdbbf-266">Esta configuración contiene varios campos.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-266">This configuration contains several fields.</span></span> <span data-ttu-id="cdbbf-267">El `name` campo especifica el componente pub/sub que quiere usar.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-267">The `name` field specifies the pub/sub component that you want to use.</span></span> <span data-ttu-id="cdbbf-268">Al enviar o recibir un mensaje, debe especificar este nombre (como vimos anteriormente en la `PublishEventAsync` firma del método).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-268">When sending or receiving a message, you need to specify this name (as you saw earlier in the `PublishEventAsync` method signature).</span></span>

<span data-ttu-id="cdbbf-269">A continuación se muestra un ejemplo de un archivo de configuración de DAPR para configurar un componente de agente de mensajes de RabbitMQ:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-269">Below you see an example of a Dapr configuration file for configuring a RabbitMQ message broker component:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub-rq
spec:
  type: pubsub.rabbitmq
  version: v1
  metadata:
  - name: host
    value: "amqp://localhost:5672"
  - name: durable
    value: true
```

<span data-ttu-id="cdbbf-270">En este ejemplo, puede ver que puede especificar cualquier configuración específica del agente de mensajes en el `metadata` bloque.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-270">In this example, you can see that you can specify any message broker-specific configuration in the `metadata` block.</span></span> <span data-ttu-id="cdbbf-271">En este caso, RabbitMQ se configura para crear colas duraderas.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-271">In this case, RabbitMQ is configured to create durable queues.</span></span> <span data-ttu-id="cdbbf-272">Pero el componente RabbitMQ tiene más opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-272">But the RabbitMQ component has more configuration options.</span></span> <span data-ttu-id="cdbbf-273">Cada una de las configuraciones de los componentes tendrá su propio conjunto de campos posibles.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-273">Each of the components' configuration will have its own set of possible fields.</span></span> <span data-ttu-id="cdbbf-274">Puede leer los campos que están disponibles en la documentación de cada [componente pub/sub](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-274">You can read which fields are available in the documentation of each [pub/sub component](https://docs.dapr.io/operations/components/setup-pubsub/supported-pubsub/).</span></span>

<span data-ttu-id="cdbbf-275">Junto a la manera programática de suscribirse a un tema desde el código, DAPR pub/sub también proporciona una manera declarativa de suscribirse a un tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-275">Next to the programmatic way of subscribing to a topic from code, Dapr pub/sub also provides a declarative way of subscribing to a topic.</span></span> <span data-ttu-id="cdbbf-276">Este enfoque quita la dependencia DAPR del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-276">This approach removes the Dapr dependency from the application code.</span></span> <span data-ttu-id="cdbbf-277">Por lo tanto, también permite que una aplicación existente se suscriba a temas sin realizar cambios en el código.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-277">Therefore, it also enables an existing application to subscribe to topics without any changes to the code.</span></span> <span data-ttu-id="cdbbf-278">En el ejemplo siguiente se muestra un archivo de configuración de DAPR para configurar una suscripción:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-278">The following example shows a Dapr configuration file for configuring a subscription:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Subscription
metadata:
  name: newOrder-subscription
spec:
  pubsubname: pubsub
  topic: newOrder
  route: /orders
scopes:
- ServiceB
- ServiceC
```

<span data-ttu-id="cdbbf-279">Tiene que especificar varios elementos con cada suscripción:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-279">You have to specify several elements with every subscription:</span></span>

- <span data-ttu-id="cdbbf-280">Nombre del componente pub/sub de DAPR que desea usar (en este caso `pubsub` ).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-280">The name of the Dapr pub/sub component you want to use (in this case `pubsub`).</span></span>
- <span data-ttu-id="cdbbf-281">Nombre del tema al que se va a suscribir (en este caso `newOrder` ).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-281">The name of the topic to subscribe to (in this case `newOrder`).</span></span>
- <span data-ttu-id="cdbbf-282">Operación de API que debe llamarse para este tema (en este caso `/orders` ).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-282">The API operation that needs to be called for this topic (in this case `/orders`).</span></span>
- <span data-ttu-id="cdbbf-283">El [ámbito](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) puede especificar qué servicios pueden publicar y suscribirse a un tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-283">The [scope](https://docs.dapr.io/developing-applications/building-blocks/pubsub/pubsub-scopes/) can specify which services can publish and subscribe to a topic.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="cdbbf-284">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="cdbbf-284">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="cdbbf-285">La aplicación [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) adjunta proporciona una arquitectura de referencia de un extremo a otro para crear una aplicación de microservicios que implementa DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-285">The accompanying [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr) app provides an end-to-end reference architecture for constructing a microservices application implementing Dapr.</span></span> <span data-ttu-id="cdbbf-286">eShopOnDapr es una evolución de la aplicación de [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainer) ampliamente popular, creada hace varios años.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-286">eShopOnDapr is an evolution of the widely popular [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainer) app, created several years ago.</span></span> <span data-ttu-id="cdbbf-287">Ambas versiones usan el patrón pub/sub para comunicar [eventos de integración](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) entre microservicios.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-287">Both versions use the pub/sub pattern for communicating [integration events](https://devblogs.microsoft.com/cesardelatorre/domain-events-vs-integration-events-in-domain-driven-design-and-microservices-architectures/#integration-events) across microservices.</span></span> <span data-ttu-id="cdbbf-288">Los eventos de integración incluyen:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-288">Integration events include:</span></span>

- <span data-ttu-id="cdbbf-289">Cuando un usuario desprotege una cesta de la compra.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-289">When a user checks-out a shopping basket.</span></span>
- <span data-ttu-id="cdbbf-290">Cuando un pago de un pedido se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-290">When a payment for an order has succeeded.</span></span>
- <span data-ttu-id="cdbbf-291">Cuando ha expirado el período de gracia de una compra.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-291">When the grace-period of a purchase has expired.</span></span>

<span data-ttu-id="cdbbf-292">Los eventos de eShopOnContainers se basan en la `IEventBus` interfaz siguiente:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-292">Eventing in eShopOnContainers is based on the following `IEventBus` interface:</span></span>

```csharp
public interface IEventBus
{
    void Publish(IntegrationEvent integrationEvent);

    void Subscribe<T, THandler>()
        where TEvent : IntegrationEvent
        where THandler : IIntegrationEventHandler<T>;
}
```

<span data-ttu-id="cdbbf-293">Las implementaciones concretas de esta interfaz existen en eShopOnContainers para RabbitMQ y Azure Service Bus.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-293">Concrete implementations of this interface exist in eShopOnContainers for both RabbitMQ and Azure Service Bus.</span></span> <span data-ttu-id="cdbbf-294">Cada implementación incluía una gran cantidad de código de fontanería personalizado que era complejo de comprender y difícil de mantener.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-294">Each implementation included a great deal of custom plumbing code that was complex to understand and difficult to maintain.</span></span>

<span data-ttu-id="cdbbf-295">El eShopOnDapr más reciente simplifica significativamente el comportamiento de pub/sub mediante DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-295">The newer eShopOnDapr significantly simplifies pub/sub behavior by using Dapr.</span></span> <span data-ttu-id="cdbbf-296">Por ejemplo, la `IEventBus` interfaz se ha reducido a un solo método:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-296">For example, the `IEventBus` interface was reduced to a single method:</span></span>

```csharp
public interface IEventBus
{
    Task PublishAsync(IntegrationEvent integrationEvent);
}
```

### <a name="publish-events"></a><span data-ttu-id="cdbbf-297">Publicación de eventos</span><span class="sxs-lookup"><span data-stu-id="cdbbf-297">Publish events</span></span>

<span data-ttu-id="cdbbf-298">En el eShopOnDapr actualizado, una sola `DaprEventBus` implementación puede admitir cualquier agente de mensajes compatible con DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-298">In the updated eShopOnDapr, a single `DaprEventBus` implementation can support any Dapr-supported message broker.</span></span> <span data-ttu-id="cdbbf-299">En el siguiente bloque de código se muestra el método de publicación simplificado.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-299">The following code block shows the simplified Publish method.</span></span> <span data-ttu-id="cdbbf-300">Observe cómo el `PublishAsync` método usa el cliente de DAPR para publicar un evento:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-300">Note how the `PublishAsync` method uses the Dapr client to publish an event:</span></span>

```csharp
public class DaprEventBus : IEventBus
{
    private const string PubSubName = "pubsub";

    private readonly DaprClient _daprClient;
    private readonly ILogger<DaprEventBus> _logger;

    public DaprEventBus(DaprClient daprClient, ILogger<DaprEventBus> logger)
    {
        _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
        _logger = logger ?? throw new ArgumentNullException(nameof(logger));
    }

    public async Task PublishAsync(IntegrationEvent integrationEvent)
    {
        var topicName = integrationEvent.GetType().Name;

        // Dapr uses System.Text.Json which does not support serialization of a
        // polymorphic type hierarchy by default. Using object as the type
        // parameter causes all properties to be serialized.
        await _daprClient.PublishEventAsync<object>(PubSubName, topicName, integrationEvent);
    }
}
```

<span data-ttu-id="cdbbf-301">Como puede ver en el fragmento de código, el nombre del tema se deriva del nombre del tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-301">As you can see in the code snippet, the topic name is derived from event type's name.</span></span> <span data-ttu-id="cdbbf-302">Dado que todos los servicios de eShop usan la `IEventBus` abstracción, DAPR required *no tiene ningún cambio* en el código de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-302">Because all eShop services use the `IEventBus` abstraction, retrofitting Dapr required *absolutely no change* to the mainline application code.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cdbbf-303">El SDK de DAPR usa `System.Text.Json` para serializar o deserializar los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-303">The Dapr SDK uses `System.Text.Json` to serialize/deserialize messages.</span></span> <span data-ttu-id="cdbbf-304">Sin embargo, `System.Text.Json` no serializa las propiedades de las clases derivadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-304">However, `System.Text.Json` doesn't serialize properties of derived classes by default.</span></span> <span data-ttu-id="cdbbf-305">En el código de eShop, a veces se declara un evento explícitamente como `IntegrationEvent` , la clase base para los eventos de integración.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-305">In the eShop code, an event is sometimes explicitly declared as an `IntegrationEvent`, the base class for integration events.</span></span> <span data-ttu-id="cdbbf-306">Esto se hace porque el tipo de evento concreto se determina dinámicamente en tiempo de ejecución en función de la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-306">This is done because the concrete event type is determined dynamically at run time based on business logic.</span></span> <span data-ttu-id="cdbbf-307">Como resultado, el evento se serializa utilizando la información de tipo de la clase base y no la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-307">As a result, the event is serialized using the type information of the base class and not the derived class.</span></span> <span data-ttu-id="cdbbf-308">Para forzar `System.Text.Json` la serialización de todas las propiedades de la clase derivada en este caso, el código utiliza `object` como parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-308">To force `System.Text.Json` to serialize all properties of the derived class in this case, the code uses `object` as the generic type parameter.</span></span> <span data-ttu-id="cdbbf-309">Para obtener más información, vea la [documentación de .net](../../standard/serialization/system-text-json-polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="cdbbf-309">For more information, see the [.NET documentation](../../standard/serialization/system-text-json-polymorphism.md).</span></span>

<span data-ttu-id="cdbbf-310">Con DAPR, el código de infraestructura se ha **simplificado drásticamente**.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-310">With Dapr, the infrastructure code is **dramatically simplified**.</span></span> <span data-ttu-id="cdbbf-311">No es necesario distinguir entre los distintos agentes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-311">It doesn't need to distinguish between the different message brokers.</span></span> <span data-ttu-id="cdbbf-312">DAPR proporciona esta abstracción para usted.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-312">Dapr provides this abstraction for you.</span></span> <span data-ttu-id="cdbbf-313">Y, si es necesario, puede intercambiar fácilmente agentes de mensajes o configurar varios componentes del agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-313">And if needed, you can easily swap out message brokers or configure multiple message broker components.</span></span>

### <a name="subscribe-to-events"></a><span data-ttu-id="cdbbf-314">Suscripción a los eventos</span><span class="sxs-lookup"><span data-stu-id="cdbbf-314">Subscribe to events</span></span>

<span data-ttu-id="cdbbf-315">La aplicación eShopOnContainers anterior contiene *SubscriptionManagers* para controlar la implementación de la suscripción para cada agente de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-315">The earlier eShopOnContainers app contains *SubscriptionManagers* to handle the subscription implementation for each message broker.</span></span> <span data-ttu-id="cdbbf-316">Cada administrador contiene código complejo específico del agente de mensajes para controlar los eventos de suscripción.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-316">Each manager contains complex message broker-specific code for handling subscription events.</span></span> <span data-ttu-id="cdbbf-317">Para recibir eventos, cada servicio tiene que registrar explícitamente un controlador para cada tipo de evento.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-317">To receive events, each service has to explicitly register a handler for each event-type.</span></span>

<span data-ttu-id="cdbbf-318">eShopOnDapr simplifica la fontanería de las suscripciones de eventos mediante el uso de bibliotecas de ASP.NET Core de DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-318">eShopOnDapr streamlines the plumbing for event subscriptions by using Dapr ASP.NET Core libraries.</span></span> <span data-ttu-id="cdbbf-319">Cada evento se controla mediante un método de acción en el controlador.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-319">Each event is handled by an action method in the controller.</span></span> <span data-ttu-id="cdbbf-320">Un `Topic` atributo decora el método de acción con el nombre del tema correspondiente al que suscribirse.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-320">A `Topic` attribute decorates the action method with the name of the corresponding topic to subscribe to.</span></span> <span data-ttu-id="cdbbf-321">A continuación se muestra un fragmento de código tomado de `PaymentService` :</span><span class="sxs-lookup"><span data-stu-id="cdbbf-321">Here's a code snippet taken from the `PaymentService`:</span></span>

```csharp
[Route("api/v1/[controller]")]
[ApiController]
public class IntegrationEventController : ControllerBase
{
    private const string DAPR_PUBSUB_NAME = "pubsub";

    private readonly IServiceProvider _serviceProvider;

    public IntegrationEventController(IServiceProvider serviceProvider)
    {
        _serviceProvider = serviceProvider;
    }

    [HttpPost("OrderStatusChangedToValidated")]
    [Topic(DAPR_PUBSUB_NAME, "OrderStatusChangedToValidatedIntegrationEvent")]
    public async Task OrderStarted(OrderStatusChangedToValidatedIntegrationEvent integrationEvent)
    {
        var handler = _serviceProvider.GetRequiredService<OrderStatusChangedToValidatedIntegrationEventHandler>();
        await handler.Handle(integrationEvent);
    }
}
```

<span data-ttu-id="cdbbf-322">En el `Topic` atributo, el nombre del tipo .net del evento se usa como el nombre del tema.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-322">In the `Topic` attribute, the name of the .NET type of the event is used as the topic name.</span></span> <span data-ttu-id="cdbbf-323">Para controlar el evento, se invoca un controlador de eventos que ya existía en la base de código eShopOnContainers anterior.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-323">For handling the event, an event handler that already existed in the earlier eShopOnContainers code base is invoked.</span></span> <span data-ttu-id="cdbbf-324">En el ejemplo anterior, los mensajes recibidos del `OrderStatusChangedToValidatedIntegrationEvent` tema invocan el `OrderStatusChangedToValidatedIntegrationEventHandler` controlador de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-324">In the previous example, messages received from the `OrderStatusChangedToValidatedIntegrationEvent` topic invoke the existing `OrderStatusChangedToValidatedIntegrationEventHandler` event-handler.</span></span> <span data-ttu-id="cdbbf-325">Dado que DAPR implementa la fontanería subyacente para las suscripciones y los agentes de mensajes, una gran cantidad de código original quedó obsoleta y se quitó del código base.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-325">Because Dapr implements the underlying plumbing for subscriptions and message brokers, a large amount of original code became obsolete and was removed from the code-base.</span></span> <span data-ttu-id="cdbbf-326">Gran parte de este código era complejo de entender y difícil de mantener.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-326">Much of this code was complex to understand and challenging to maintain.</span></span>

### <a name="use-pubsub-components"></a><span data-ttu-id="cdbbf-327">Uso de componentes pub/sub</span><span class="sxs-lookup"><span data-stu-id="cdbbf-327">Use pub/sub components</span></span>

<span data-ttu-id="cdbbf-328">En el repositorio de eShopOnDapr, una `deployment` carpeta contiene archivos para implementar la aplicación mediante diferentes modos de implementación: `Docker Compose` y `Kubernetes` .</span><span class="sxs-lookup"><span data-stu-id="cdbbf-328">Within the eShopOnDapr repository, a `deployment` folder contains files for deploying the application using different deployment modes: `Docker Compose` and `Kubernetes`.</span></span> <span data-ttu-id="cdbbf-329">`dapr`Existe una carpeta dentro de cada una de estas carpetas que contiene una `components` carpeta.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-329">A `dapr` folder exists within each of these folders that holds a `components` folder.</span></span> <span data-ttu-id="cdbbf-330">Esta carpeta contiene un archivo `eshop-pubsub.yaml` que contiene la configuración del componente pub/sub de DAPR que la aplicación usará para el comportamiento de pub/sub.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-330">This folder holds a file `eshop-pubsub.yaml` containing the configuration of the Dapr pub/sub component that the application will use for pub/sub behavior.</span></span> <span data-ttu-id="cdbbf-331">Como vio en los fragmentos de código anteriores, el nombre del componente pub/sub usado es `pubsub` .</span><span class="sxs-lookup"><span data-stu-id="cdbbf-331">As you saw in the earlier code snippets, the name of the pub/sub component used is `pubsub`.</span></span> <span data-ttu-id="cdbbf-332">Este es el contenido del `eshop-pubsub.yaml` archivo en la `deployment/compose/dapr/components` carpeta:</span><span class="sxs-lookup"><span data-stu-id="cdbbf-332">Here's the content of the `eshop-pubsub.yaml` file in the `deployment/compose/dapr/components` folder:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: default
spec:
  type: pubsub.nats
  version: v1
  metadata:
  - name: natsURL
    value: nats://demo.nats.io:4222
```

<span data-ttu-id="cdbbf-333">La configuración anterior especifica el [agente de mensajes de NAT](https://nats.io/) deseado para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-333">The preceding configuration specifies the desired [NATS message broker](https://nats.io/) for this example.</span></span> <span data-ttu-id="cdbbf-334">Para cambiar los agentes de mensajes, solo tiene que configurar un agente de mensajes diferente, como RabbitMQ o Azure Service Bus y actualizar el archivo YAML.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-334">To change message brokers, you need only to configure a different message broker, such as RabbitMQ or Azure Service Bus and update the yaml file.</span></span> <span data-ttu-id="cdbbf-335">Con DAPR, no se produce ningún cambio en el código de servicio principal al cambiar los agentes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-335">With Dapr, there are no changes to your mainline service code when switching message brokers.</span></span>

<span data-ttu-id="cdbbf-336">Por último, podría preguntar "¿por qué se necesitarían varios agentes de mensajes en una aplicación?".</span><span class="sxs-lookup"><span data-stu-id="cdbbf-336">Finally, you might ask, "Why would I need multiple message brokers in an application?".</span></span> <span data-ttu-id="cdbbf-337">Muchas veces, un sistema controlará las cargas de trabajo con características diferentes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-337">Many times a system will handle workloads with different characteristics.</span></span> <span data-ttu-id="cdbbf-338">Un evento se puede producir 10 veces al día, pero se produce otro evento 5.000 veces por segundo.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-338">One event may occur 10 times a day, but another event occurs 5,000 times per second.</span></span> <span data-ttu-id="cdbbf-339">Puede beneficiarse de la creación de particiones del tráfico de mensajería a diferentes agentes de mensajes.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-339">You may benefit by partitioning messaging traffic to different message brokers.</span></span> <span data-ttu-id="cdbbf-340">Con DAPR, puede agregar varias configuraciones de componente pub/sub, cada una con un nombre diferente.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-340">With Dapr, you can add multiple pub/sub component configurations, each with a different name.</span></span>

## <a name="summary"></a><span data-ttu-id="cdbbf-341">Resumen</span><span class="sxs-lookup"><span data-stu-id="cdbbf-341">Summary</span></span>

<span data-ttu-id="cdbbf-342">El patrón pub/sub le ayuda a desacoplar servicios en una aplicación distribuida.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-342">The pub/sub pattern helps you decouple services in a distributed application.</span></span> <span data-ttu-id="cdbbf-343">El bloque DAPR Publish & subscribe Building simplifica la implementación de este comportamiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-343">The Dapr publish & subscribe building block simplifies implementing this behavior in your application.</span></span>

<span data-ttu-id="cdbbf-344">A través de DAPR pub/sub, puede publicar mensajes en un *tema* específico.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-344">Through Dapr pub/sub, you can publish messages to a specific *topic*.</span></span> <span data-ttu-id="cdbbf-345">Además, el bloque de creación consultará el servicio para determinar a qué temas se va a suscribir.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-345">As well, the building block will query your service to determine which topic(s) to subscribe to.</span></span>

<span data-ttu-id="cdbbf-346">Puede usar DAPR pub/sub de forma nativa a través de HTTP o mediante uno de los SDK específicos del lenguaje, como el SDK de .NET para DAPR.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-346">You can use Dapr pub/sub natively over HTTP or by using one of the language-specific SDKs, such as the .NET SDK for Dapr.</span></span> <span data-ttu-id="cdbbf-347">El SDK de .NET se integra estrechamente con la plataforma de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-347">The .NET SDK tightly integrates with the ASP.NET core platform.</span></span>

<span data-ttu-id="cdbbf-348">Con DAPR, puede conectar un producto de agente de mensajes compatible con su aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-348">With Dapr, you can plug a supported message broker product into your application.</span></span> <span data-ttu-id="cdbbf-349">Después, puede intercambiar agentes de mensajes sin necesidad de realizar cambios en el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cdbbf-349">You can then swap message brokers without requiring code changes to your application.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="cdbbf-350">[Anterior](service-invocation.md)
> [Siguiente](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="cdbbf-350">[Previous](service-invocation.md)
[Next](bindings.md)</span></span>
