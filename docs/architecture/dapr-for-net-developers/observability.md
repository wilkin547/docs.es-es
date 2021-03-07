---
title: El bloque de creación de observación de DAPR
description: Una descripción del bloque de creación de observación, sus características, ventajas y cómo aplicarla
author: edwinvw
ms.date: 02/07/2021
ms.reviewer: robvet
ms.openlocfilehash: c7c941625f5867ad58eee602bfc42183bee87183
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401872"
---
# <a name="the-dapr-observability-building-block"></a><span data-ttu-id="4524d-103">El bloque de creación de observación de DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-103">The Dapr observability building block</span></span>

<span data-ttu-id="4524d-104">Los sistemas distribuidos modernos son complejos.</span><span class="sxs-lookup"><span data-stu-id="4524d-104">Modern distributed systems are complex.</span></span> <span data-ttu-id="4524d-105">Comienza con servicios pequeños, que se pueden implementar de forma independiente y de acoplamiento flexible.</span><span class="sxs-lookup"><span data-stu-id="4524d-105">You start with small, loosely coupled, independently deployable services.</span></span> <span data-ttu-id="4524d-106">Estos servicios cruzan los límites del proceso y del servidor.</span><span class="sxs-lookup"><span data-stu-id="4524d-106">These services cross process and server boundaries.</span></span> <span data-ttu-id="4524d-107">A continuación, usan diferentes tipos de servicios de respaldo de infraestructura (bases de datos, agentes de mensajes y almacenes de claves).</span><span class="sxs-lookup"><span data-stu-id="4524d-107">They then consume different kinds of infrastructure backing services (databases, message brokers, key vaults).</span></span> <span data-ttu-id="4524d-108">Por último, estos fragmentos dispares se componen juntos para formar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-108">Finally, these disparate pieces compose together to form an application.</span></span>

<span data-ttu-id="4524d-109">Con tantas partes desplazadas independientes, ¿cómo puede tener sentido de lo que está ocurriendo?</span><span class="sxs-lookup"><span data-stu-id="4524d-109">With so many separate, moving parts, how do you make sense of what is going on?</span></span> <span data-ttu-id="4524d-110">Desafortunadamente, los enfoques de supervisión heredados del pasado no son suficientes.</span><span class="sxs-lookup"><span data-stu-id="4524d-110">Unfortunately, legacy monitoring approaches from the past aren't enough.</span></span> <span data-ttu-id="4524d-111">En su lugar, el sistema debe ser **observable** de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="4524d-111">Instead, the system must be **observable** from end-to-end.</span></span> <span data-ttu-id="4524d-112">Las prácticas de [observación](../cloud-native/observability-patterns.md) modernas proporcionan visibilidad e información sobre el estado de la aplicación en todo momento.</span><span class="sxs-lookup"><span data-stu-id="4524d-112">Modern [observability](../cloud-native/observability-patterns.md) practices provide visibility and insight into the health of the application at all times.</span></span> <span data-ttu-id="4524d-113">Permiten deducir el estado interno observando la salida.</span><span class="sxs-lookup"><span data-stu-id="4524d-113">They enable you to infer the internal state by observing the output.</span></span> <span data-ttu-id="4524d-114">La observación es obligatoria para la supervisión y solución de problemas de las aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="4524d-114">Observability is mandatory for monitoring and troubleshooting distributed applications.</span></span>

<span data-ttu-id="4524d-115">La información del sistema que se usa para obtener observación se conoce como **telemetría**.</span><span class="sxs-lookup"><span data-stu-id="4524d-115">The system information used to gain observability is referred to as **telemetry**.</span></span> <span data-ttu-id="4524d-116">Se puede dividir en cuatro amplias categorías:</span><span class="sxs-lookup"><span data-stu-id="4524d-116">It can be divided into four broad categories:</span></span>

1. <span data-ttu-id="4524d-117">La **traza distribuida** proporciona información sobre el tráfico entre servicios y servicios implicados en las transacciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="4524d-117">**Distributed tracing** provides insight into the traffic between services and services involved in distributed transactions.</span></span>
1. <span data-ttu-id="4524d-118">**Métricas** proporciona información sobre el rendimiento de un servicio y su consumo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4524d-118">**Metrics** provides insight into the performance of a service and its resource consumption.</span></span>
1. <span data-ttu-id="4524d-119">El **registro** proporciona información sobre cómo se ejecuta el código y si se han producido errores.</span><span class="sxs-lookup"><span data-stu-id="4524d-119">**Logging** provides insight into how the code is executing and if errors have occurred.</span></span>
1. <span data-ttu-id="4524d-120">Los puntos de conexión de **mantenimiento** proporcionan una visión general de la disponibilidad de un servicio.</span><span class="sxs-lookup"><span data-stu-id="4524d-120">**Health** endpoints provide insight into the availability of a service.</span></span>

<span data-ttu-id="4524d-121">La profundidad de la telemetría viene determinada por las características de observación de una plataforma de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-121">The depth of telemetry is determined by the observability features of an application platform.</span></span> <span data-ttu-id="4524d-122">Tenga en cuenta la nube de Azure.</span><span class="sxs-lookup"><span data-stu-id="4524d-122">Consider the Azure cloud.</span></span> <span data-ttu-id="4524d-123">Proporciona una experiencia de telemetría enriquecida que incluye todas las categorías de telemetría.</span><span class="sxs-lookup"><span data-stu-id="4524d-123">It provides a rich telemetry experience that includes all of the telemetry categories.</span></span> <span data-ttu-id="4524d-124">Sin ninguna configuración, la mayoría de los servicios IaaS y PaaS de Azure propagan y publican la telemetría en el servicio [aplicación de Azure Insights](/azure/azure-monitor/app/app-insights-overview) .</span><span class="sxs-lookup"><span data-stu-id="4524d-124">Without any configuration, most Azure IaaS and PaaS services propagate and publish telemetry to the [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) service.</span></span> <span data-ttu-id="4524d-125">Application Insights presenta el registro del sistema, el seguimiento y las áreas problemáticas con paneles muy visuales.</span><span class="sxs-lookup"><span data-stu-id="4524d-125">Application Insights presents system logging, tracing, and problem areas with highly visual dashboards.</span></span> <span data-ttu-id="4524d-126">Incluso puede representar un diagrama que muestre las dependencias entre servicios en función de su comunicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-126">It can even render a diagram showing the dependencies between services based on their communication.</span></span>

<span data-ttu-id="4524d-127">Sin embargo, ¿qué ocurre si una aplicación no puede usar los recursos de PaaS y IaaS de Azure?</span><span class="sxs-lookup"><span data-stu-id="4524d-127">However, what if an application can't use Azure PaaS and IaaS resources?</span></span> <span data-ttu-id="4524d-128">¿Todavía es posible aprovechar la experiencia de telemetría enriquecida de Application Insights?</span><span class="sxs-lookup"><span data-stu-id="4524d-128">Is it still possible to take advantage of the rich telemetry experience of Application Insights?</span></span> <span data-ttu-id="4524d-129">La respuesta es sí.</span><span class="sxs-lookup"><span data-stu-id="4524d-129">The answer is yes.</span></span> <span data-ttu-id="4524d-130">Una aplicación que no es de Azure puede importar bibliotecas, agregar configuración e instrumentar código para emitir la telemetría para Aplicación de Azure información.</span><span class="sxs-lookup"><span data-stu-id="4524d-130">A non-Azure application can import libraries, add configuration, and instrument code to emit telemetry to Azure Application Insights.</span></span> <span data-ttu-id="4524d-131">Sin embargo, este enfoque **acopla estrechamente** la aplicación a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="4524d-131">However, this approach **tightly couples** the application to Application Insights.</span></span> <span data-ttu-id="4524d-132">Mover la aplicación a otra plataforma de supervisión podría implicar una refactorización costosa.</span><span class="sxs-lookup"><span data-stu-id="4524d-132">Moving the app to a different monitoring platform could involve expensive refactoring.</span></span> <span data-ttu-id="4524d-133">¿No sería genial evitar el acoplamiento estrecho y consumir la utilidad de observación fuera del código?</span><span class="sxs-lookup"><span data-stu-id="4524d-133">Wouldn't it be great to avoid tight coupling and consume observability outside of the code?</span></span>

<span data-ttu-id="4524d-134">Con DAPR, puede.</span><span class="sxs-lookup"><span data-stu-id="4524d-134">With Dapr, you can.</span></span> <span data-ttu-id="4524d-135">Echemos un vistazo a cómo DAPR puede Agregar observación a nuestras aplicaciones distribuidas.</span><span class="sxs-lookup"><span data-stu-id="4524d-135">Let's look at how Dapr can add observability to our distributed applications.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="4524d-136">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="4524d-136">What it solves</span></span>

<span data-ttu-id="4524d-137">El bloque de creación de observación DAPR desacopla la observación de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-137">The Dapr observability building block decouples observability from the application.</span></span> <span data-ttu-id="4524d-138">Captura automáticamente el tráfico generado por los DAPR sidecar y los servicios del sistema DAPR que componen el plano de control DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-138">It automatically captures traffic generated by Dapr sidecars and Dapr system services that make up the Dapr control plane.</span></span> <span data-ttu-id="4524d-139">El bloque correlaciona el tráfico de una única operación que abarca varios servicios.</span><span class="sxs-lookup"><span data-stu-id="4524d-139">The block correlates traffic from a single operation that spans multiple services.</span></span> <span data-ttu-id="4524d-140">También expone las métricas de rendimiento, la utilización de recursos y el estado del sistema.</span><span class="sxs-lookup"><span data-stu-id="4524d-140">It also exposes performance metrics, resource utilization, and the health of the system.</span></span> <span data-ttu-id="4524d-141">La telemetría se publica en formatos de estándar abierto, lo que permite introducir información en el back-end de supervisión de su elección.</span><span class="sxs-lookup"><span data-stu-id="4524d-141">Telemetry is published in open-standard formats enabling information to be fed into your monitoring back end of choice.</span></span> <span data-ttu-id="4524d-142">Allí, la información se puede visualizar, consultar y analizar.</span><span class="sxs-lookup"><span data-stu-id="4524d-142">There, the information can be visualized, queried, and analyzed.</span></span>

<span data-ttu-id="4524d-143">A medida que DAPR abstrae el establecimiento, la aplicación no es consciente de cómo se implementa la observación.</span><span class="sxs-lookup"><span data-stu-id="4524d-143">As Dapr abstracts away the plumbing, the application is unaware of how observability is implemented.</span></span> <span data-ttu-id="4524d-144">No es necesario hacer referencia a las bibliotecas ni implementar código de instrumentación personalizado.</span><span class="sxs-lookup"><span data-stu-id="4524d-144">There's no need to reference libraries or implement custom instrumentation code.</span></span> <span data-ttu-id="4524d-145">DAPR permite al desarrollador centrarse en la creación de lógica de negocios y no en la estructura de observación.</span><span class="sxs-lookup"><span data-stu-id="4524d-145">Dapr allows the developer to focus on building business logic and not observability plumbing.</span></span> <span data-ttu-id="4524d-146">La observación se configura en el nivel de DAPR y es coherente en todos los servicios, incluso cuando se crean en distintos equipos y se crea con diferentes pilas tecnológicas.</span><span class="sxs-lookup"><span data-stu-id="4524d-146">Observability is configured at the Dapr level and is consistent across services, even when created by different teams, and built with different technology stacks.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="4524d-147">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="4524d-147">How it works</span></span>

<span data-ttu-id="4524d-148">La [arquitectura sidecar](dapr-at-20000-feet.md#sidecar-architecture) de DAPR permite características de observación integradas.</span><span class="sxs-lookup"><span data-stu-id="4524d-148">Dapr's [sidecar architecture](dapr-at-20000-feet.md#sidecar-architecture) enables built-in observability features.</span></span> <span data-ttu-id="4524d-149">A medida que los servicios se comunican, DAPR sidecar interceptan el tráfico y extraen la información de seguimiento, métricas y registro.</span><span class="sxs-lookup"><span data-stu-id="4524d-149">As services communicate, Dapr sidecars intercept the traffic and extract tracing, metrics, and logging information.</span></span> <span data-ttu-id="4524d-150">La telemetría se publica en un formato estándar abierto.</span><span class="sxs-lookup"><span data-stu-id="4524d-150">Telemetry is published in an open standards format.</span></span> <span data-ttu-id="4524d-151">De forma predeterminada, DAPR admite [OpenTelemetry](https://opentelemetry.io/) y [Zipkin](https://zipkin.io/).</span><span class="sxs-lookup"><span data-stu-id="4524d-151">By default, Dapr supports [OpenTelemetry](https://opentelemetry.io/) and [Zipkin](https://zipkin.io/).</span></span>

<span data-ttu-id="4524d-152">DAPR proporciona [recopiladores](https://docs.dapr.io/operations/monitoring/open-telemetry-collector/) que pueden publicar la telemetría en diferentes herramientas de supervisión de back-end.</span><span class="sxs-lookup"><span data-stu-id="4524d-152">Dapr provides [collectors](https://docs.dapr.io/operations/monitoring/open-telemetry-collector/) that can publish telemetry to different back-end monitoring tools.</span></span> <span data-ttu-id="4524d-153">Estas herramientas presentan telemetría DAPR para el análisis y las consultas.</span><span class="sxs-lookup"><span data-stu-id="4524d-153">These tools present Dapr telemetry for analysis and querying.</span></span> <span data-ttu-id="4524d-154">En la figura 9-1 se muestra la arquitectura de observación de DAPR:</span><span class="sxs-lookup"><span data-stu-id="4524d-154">Figure 9-1 shows the Dapr observability architecture:</span></span>

![Arquitectura de observación de DAPR](media/observability/observability-architecture.png)

<span data-ttu-id="4524d-156">**Figura 9-1**.</span><span class="sxs-lookup"><span data-stu-id="4524d-156">**Figure 9-1**.</span></span> <span data-ttu-id="4524d-157">Arquitectura de observación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-157">Dapr observability architecture.</span></span>

1. <span data-ttu-id="4524d-158">El servicio A llama a una operación en el servicio B. La llamada se enruta desde un sidecar DAPR para el servicio a a un sidecar para el servicio B.</span><span class="sxs-lookup"><span data-stu-id="4524d-158">Service A calls an operation on Service B. The call is routed from a Dapr sidecar for Service A to a sidecar for Service B.</span></span>
1. <span data-ttu-id="4524d-159">Cuando el servicio B completa la operación, se devuelve una respuesta al servicio a a través de los sidecars DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-159">When Service B completes the operation, a response is sent back to Service A through the Dapr sidecars.</span></span> <span data-ttu-id="4524d-160">Recopilan y publican toda la telemetría disponible para cada solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="4524d-160">They gather and publish all available telemetry for every request and response.</span></span>
1. <span data-ttu-id="4524d-161">El recopilador configurado ingeri la telemetría y la envía al back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-161">The configured collector ingests the telemetry and sends it to the monitoring back end.</span></span>  

<span data-ttu-id="4524d-162">Como desarrollador, tenga en cuenta que la adición de observación es diferente de la configuración de otros bloques de creación de DAPR, como pub/sub o administración de Estados.</span><span class="sxs-lookup"><span data-stu-id="4524d-162">As a developer, keep in mind that adding observability is different from configuring other Dapr building blocks, like pub/sub or state management.</span></span> <span data-ttu-id="4524d-163">En lugar de hacer referencia a un bloque de creación, agregue un recopilador y un back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-163">Instead of referencing a building block, you add a collector and a monitoring back end.</span></span> <span data-ttu-id="4524d-164">En la figura 9-1 se muestra cómo configurar varios recopiladores que se integran con diferentes servidores back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-164">Figure 9-1 shows it's possible to configure multiple collectors that integrate with different monitoring back ends.</span></span>

<span data-ttu-id="4524d-165">Al principio de este capítulo, se identificaron cuatro categorías de telemetría.</span><span class="sxs-lookup"><span data-stu-id="4524d-165">At the beginning of this chapter, four categories of telemetry were identified.</span></span> <span data-ttu-id="4524d-166">En las secciones siguientes se proporcionan detalles para cada categoría.</span><span class="sxs-lookup"><span data-stu-id="4524d-166">The following sections will provide detail for each category.</span></span> <span data-ttu-id="4524d-167">Incluyen instrucciones sobre cómo configurar los recopiladores que se integran con los back-ends de supervisión más populares.</span><span class="sxs-lookup"><span data-stu-id="4524d-167">They'll include instruction on how to configure collectors that integrate with popular monitoring back ends.</span></span>

### <a name="distributed-tracing"></a><span data-ttu-id="4524d-168">Seguimiento distribuido</span><span class="sxs-lookup"><span data-stu-id="4524d-168">Distributed tracing</span></span>

<span data-ttu-id="4524d-169">La traza distribuida proporciona información sobre el tráfico que fluye entre los servicios de una aplicación distribuida.</span><span class="sxs-lookup"><span data-stu-id="4524d-169">Distributed tracing provides insight into the traffic that flows across services in a distributed application.</span></span> <span data-ttu-id="4524d-170">El registro de mensajes de solicitud y respuesta intercambiados es un origen de información muy valioso para solucionar problemas.</span><span class="sxs-lookup"><span data-stu-id="4524d-170">The log of exchanged request and response messages is an invaluable source of information for troubleshooting issues.</span></span> <span data-ttu-id="4524d-171">La parte difícil es poner en *correlación los mensajes* que se originan a partir de la misma operación.</span><span class="sxs-lookup"><span data-stu-id="4524d-171">The hard part is *correlating messages* that originate from the same operation.</span></span>

<span data-ttu-id="4524d-172">DAPR usa el [contexto de seguimiento de W3C](https://www.w3.org/TR/trace-context) para poner en correlación los mensajes relacionados.</span><span class="sxs-lookup"><span data-stu-id="4524d-172">Dapr uses the [W3C Trace Context](https://www.w3.org/TR/trace-context) to correlate related messages.</span></span> <span data-ttu-id="4524d-173">Inserta la misma información de contexto en las solicitudes y respuestas que forman una operación única.</span><span class="sxs-lookup"><span data-stu-id="4524d-173">It injects the same context information into requests and responses that form a unique operation.</span></span> <span data-ttu-id="4524d-174">En la figura 9-2 se muestra cómo funciona la correlación:</span><span class="sxs-lookup"><span data-stu-id="4524d-174">Figure 9-2 shows how correlation works:</span></span>

![Ejemplo de contexto de seguimiento de W3C](media/observability/w3c-trace-context.png)

<span data-ttu-id="4524d-176">**Figura 9-2**.</span><span class="sxs-lookup"><span data-stu-id="4524d-176">**Figure 9-2**.</span></span> <span data-ttu-id="4524d-177">Ejemplo de contexto de seguimiento de W3C.</span><span class="sxs-lookup"><span data-stu-id="4524d-177">W3C Trace Context example.</span></span>

1. <span data-ttu-id="4524d-178">El servicio A invoca una operación en el servicio B. Cuando el servicio A inicia la llamada, DAPR crea un contexto de seguimiento único y lo inserta en la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4524d-178">Service A invokes an operation on Service B. As Service A starts the call, Dapr creates a unique trace context and injects it into the request.</span></span>
1. <span data-ttu-id="4524d-179">El servicio B recibe la solicitud e invoca una operación en el servicio C. DAPR detecta que la solicitud entrante contiene un contexto de seguimiento y la propaga inyectando en la solicitud saliente al servicio C.</span><span class="sxs-lookup"><span data-stu-id="4524d-179">Service B receives the request and invokes an operation on Service C. Dapr detects that the incoming request contains a trace context and propagates it by injecting it into the outgoing request to Service C.</span></span>  
1. <span data-ttu-id="4524d-180">El servicio C recibe la solicitud y la controla.</span><span class="sxs-lookup"><span data-stu-id="4524d-180">Service C receives the request and handles it.</span></span> <span data-ttu-id="4524d-181">DAPR detecta que la solicitud entrante contiene un contexto de seguimiento y la propaga inyectando en la respuesta saliente de vuelta al servicio B.</span><span class="sxs-lookup"><span data-stu-id="4524d-181">Dapr detects that the incoming request contains a trace context and propagates it by injecting it into the outgoing response back to Service B.</span></span>
1. <span data-ttu-id="4524d-182">El servicio B recibe la respuesta y la controla.</span><span class="sxs-lookup"><span data-stu-id="4524d-182">Service B receives the response and handles it.</span></span> <span data-ttu-id="4524d-183">A continuación, crea una nueva respuesta y propaga el contexto de seguimiento inyectando en la respuesta saliente hacia el servicio a.</span><span class="sxs-lookup"><span data-stu-id="4524d-183">It then creates a new response and propagates the trace context by injecting it into the outgoing response back to Service A.</span></span>

<span data-ttu-id="4524d-184">Un conjunto de solicitudes y respuestas que pertenecen a la vez se denomina *seguimiento*.</span><span class="sxs-lookup"><span data-stu-id="4524d-184">A set of requests and responses that belong together is called a *trace*.</span></span> <span data-ttu-id="4524d-185">En la figura 9-3 se muestra un seguimiento:</span><span class="sxs-lookup"><span data-stu-id="4524d-185">Figure 9-3 shows a trace:</span></span>

![Seguimientos e intervalos](media/observability/traces-spans.png)

<span data-ttu-id="4524d-187">**Figura 9-3**.</span><span class="sxs-lookup"><span data-stu-id="4524d-187">**Figure 9-3**.</span></span> <span data-ttu-id="4524d-188">Seguimientos e intervalos.</span><span class="sxs-lookup"><span data-stu-id="4524d-188">Traces and spans.</span></span>

<span data-ttu-id="4524d-189">En la ilustración, observe cómo el seguimiento representa una transacción de aplicación única que tiene lugar en varios servicios.</span><span class="sxs-lookup"><span data-stu-id="4524d-189">In the figure, note how the trace represents a unique application transaction that takes place across many services.</span></span> <span data-ttu-id="4524d-190">Un seguimiento es una colección de *intervalos*.</span><span class="sxs-lookup"><span data-stu-id="4524d-190">A trace is a collection of *spans*.</span></span> <span data-ttu-id="4524d-191">Cada intervalo representa una única operación o unidad de trabajo realizada en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4524d-191">Each span represents a single operation or unit of work done within the trace.</span></span> <span data-ttu-id="4524d-192">Los intervalos son las solicitudes y las respuestas que se envían entre los servicios que implementan la transacción única.</span><span class="sxs-lookup"><span data-stu-id="4524d-192">Spans are the requests and responses that are sent between services that implement the unique transaction.</span></span>

<span data-ttu-id="4524d-193">En las secciones siguientes se explica cómo inspeccionar la telemetría de seguimiento publicándola en un back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-193">The next sections discuss how to inspect tracing telemetry by publishing it to a monitoring back end.</span></span>

#### <a name="use-a-zipkin-monitoring-back-end"></a><span data-ttu-id="4524d-194">Usar un back-end de supervisión de Zipkin</span><span class="sxs-lookup"><span data-stu-id="4524d-194">Use a Zipkin monitoring back end</span></span>

<span data-ttu-id="4524d-195">[Zipkin](https://zipkin.io/) es un sistema de seguimiento distribuido de código abierto.</span><span class="sxs-lookup"><span data-stu-id="4524d-195">[Zipkin](https://zipkin.io/) is an open-source distributed tracing system.</span></span> <span data-ttu-id="4524d-196">Puede ingerir y visualizar datos de telemetría.</span><span class="sxs-lookup"><span data-stu-id="4524d-196">It can ingest and visualize telemetry data.</span></span> <span data-ttu-id="4524d-197">DAPR ofrece compatibilidad predeterminada para Zipkin.</span><span class="sxs-lookup"><span data-stu-id="4524d-197">Dapr offers default support for Zipkin.</span></span> <span data-ttu-id="4524d-198">En el ejemplo siguiente se muestra cómo configurar Zipkin para visualizar la telemetría DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-198">The following example demonstrates how to configure Zipkin to visualize Dapr telemetry.</span></span>

##### <a name="enable-and-configure-tracing"></a><span data-ttu-id="4524d-199">Habilitar y configurar el seguimiento</span><span class="sxs-lookup"><span data-stu-id="4524d-199">Enable and configure tracing</span></span>

<span data-ttu-id="4524d-200">Para empezar, el seguimiento debe estar habilitado para el tiempo de ejecución de DAPR mediante un archivo de configuración de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-200">To start, tracing must be enabled for the Dapr runtime using a Dapr configuration file.</span></span> <span data-ttu-id="4524d-201">A continuación se muestra un ejemplo de un archivo de configuración denominado `tracing-config.yaml` :</span><span class="sxs-lookup"><span data-stu-id="4524d-201">Here's an example of a configuration file named `tracing-config.yaml`:</span></span>  

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: tracing-config
  namespace: default
spec:
  tracing:
    samplingRate: "1"
    zipkin:
      endpointAddress: "http://zipkin.default.svc.cluster.local:9411/api/v2/spans"
```

<span data-ttu-id="4524d-202">El `samplingRate` atributo especifica el intervalo utilizado para la publicación de seguimientos.</span><span class="sxs-lookup"><span data-stu-id="4524d-202">The `samplingRate` attribute specifies the interval used for publishing traces.</span></span> <span data-ttu-id="4524d-203">El valor debe estar comprendido entre `0` (seguimiento deshabilitado) y `1` (se publican todos los seguimientos).</span><span class="sxs-lookup"><span data-stu-id="4524d-203">The value must be between `0` (tracing disabled) and `1` (every trace is published).</span></span> <span data-ttu-id="4524d-204">Con un valor de `0.5` , por ejemplo, se publican todos los demás seguimientos, lo que reduce significativamente el tráfico publicado.</span><span class="sxs-lookup"><span data-stu-id="4524d-204">With a value of `0.5`, for example, every other trace is published, significantly reducing published traffic.</span></span> <span data-ttu-id="4524d-205">`endpointAddress`Apunta a un punto de conexión en un servidor de Zipkin que se ejecuta en un clúster de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="4524d-205">The `endpointAddress` points to an endpoint on a Zipkin server running in a Kubernetes cluster.</span></span> <span data-ttu-id="4524d-206">El puerto predeterminado para Zipkin es `9411` .</span><span class="sxs-lookup"><span data-stu-id="4524d-206">The default port for Zipkin is `9411`.</span></span> <span data-ttu-id="4524d-207">La configuración debe aplicarse al clúster de Kubernetes mediante la CLI de Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="4524d-207">The configuration must be applied to the Kubernetes cluster using the Kubernetes CLI:</span></span>

```console
kubectl apply -f tracing-config.yaml
```

##### <a name="install-the-zipkin-server"></a><span data-ttu-id="4524d-208">Instalación del servidor de Zipkin</span><span class="sxs-lookup"><span data-stu-id="4524d-208">Install the Zipkin server</span></span>

<span data-ttu-id="4524d-209">Al instalar DAPR en modo autohospedado, se instala automáticamente un servidor de Zipkin y el seguimiento se habilita en el archivo de configuración predeterminado que se encuentra en `$HOME/.dapr/config.yaml` o `%USERPROFILE%\.dapr\config.yaml` en Windows.</span><span class="sxs-lookup"><span data-stu-id="4524d-209">When installing Dapr in self-hosted mode, a Zipkin server is automatically installed and tracing is enabled in the default configuration file located in `$HOME/.dapr/config.yaml` or `%USERPROFILE%\.dapr\config.yaml` on Windows.</span></span>

<span data-ttu-id="4524d-210">Sin embargo, al instalar DAPR en un clúster de Kubernetes, no se agrega Zipkin de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4524d-210">When installing Dapr on a Kubernetes cluster though, Zipkin isn't added by default.</span></span> <span data-ttu-id="4524d-211">El siguiente archivo de manifiesto de Kubernetes denominado `zipkin.yaml` , implementa un servidor Zipkin estándar en el clúster:</span><span class="sxs-lookup"><span data-stu-id="4524d-211">The following Kubernetes manifest file named `zipkin.yaml`, deploys a standard Zipkin server to the cluster:</span></span>

```yaml
kind: Deployment
apiVersion: apps/v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  replicas: 1
  selector:
    matchLabels:
      service: zipkin
  template:
    metadata:
      labels:
        service: zipkin
    spec:
      containers:
        - name: zipkin
          image: openzipkin/zipkin-slim
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 9411
              protocol: TCP

---

kind: Service
apiVersion: v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  type: NodePort
  ports:
    - port: 9411
      targetPort: 9411
      nodePort: 32411
      protocol: TCP
      name: zipkin
  selector:
    service: zipkin

```

<span data-ttu-id="4524d-212">La implementación usa la `openzipkin/zipkin-slim` imagen de contenedor estándar.</span><span class="sxs-lookup"><span data-stu-id="4524d-212">The deployment uses the standard `openzipkin/zipkin-slim` container image.</span></span> <span data-ttu-id="4524d-213">El servicio Zipkin expone el front-end web Zipkin, que puede usar para ver la telemetría en el puerto `32411` .</span><span class="sxs-lookup"><span data-stu-id="4524d-213">The Zipkin service exposes the Zipkin web front end, which you can use to view the telemetry on port `32411`.</span></span> <span data-ttu-id="4524d-214">Use la CLI de Kubernetes para aplicar el archivo de manifiesto de Zipkin en el clúster de Kubernetes e implementar el servidor de Zipkin:</span><span class="sxs-lookup"><span data-stu-id="4524d-214">Use the Kubernetes CLI to apply the Zipkin manifest file to the Kubernetes cluster and deploy the Zipkin server:</span></span>

```console
kubectl apply -f zipkin.yaml
```

##### <a name="configure-the-services-to-use-the-tracing-configuration"></a><span data-ttu-id="4524d-215">Configurar los servicios para usar la configuración de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4524d-215">Configure the services to use the tracing configuration</span></span>

<span data-ttu-id="4524d-216">Ahora todo está configurado correctamente para empezar a publicar la telemetría.</span><span class="sxs-lookup"><span data-stu-id="4524d-216">Now everything is set up correctly to start publishing telemetry.</span></span> <span data-ttu-id="4524d-217">Cada sidecar de DAPR que se implementa como parte de la aplicación debe indicar a que emita la telemetría al iniciarse.</span><span class="sxs-lookup"><span data-stu-id="4524d-217">Every Dapr sidecar that is deployed as part of the application must be instructed to emit telemetry when started.</span></span> <span data-ttu-id="4524d-218">Para ello, agregue una `dapr.io/config` anotación que haga referencia a la `tracing-config` configuración para la implementación de cada servicio.</span><span class="sxs-lookup"><span data-stu-id="4524d-218">To do that, add a `dapr.io/config` annotation that references the `tracing-config` configuration to the deployment of each service.</span></span> <span data-ttu-id="4524d-219">Este es un ejemplo del archivo de manifiesto del servicio de la API de pedidos de eShop que contiene la anotación:</span><span class="sxs-lookup"><span data-stu-id="4524d-219">Here's an example of the eShop ordering API service's manifest file containing the annotation:</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ordering-api
  namespace: eshop
  labels:
    app: eshop
spec:
  replicas: 1
  selector:
    matchLabels:
      app: eshop
  template:
    metadata:
      labels:
        app: simulation
      annotations:
        dapr.io/enabled: "true"
        dapr.io/app-id: "ordering-api"
        dapr.io/config: "tracing-config"
    spec:
      containers:
      - name: simulation
        image: eshop/ordering.api:linux-latest
```

##### <a name="inspect-the-telemetry-in-zipkin"></a><span data-ttu-id="4524d-220">Inspección de la telemetría en Zipkin</span><span class="sxs-lookup"><span data-stu-id="4524d-220">Inspect the telemetry in Zipkin</span></span>

<span data-ttu-id="4524d-221">Una vez que se inicia la aplicación, los sidecares de DAPR emitirán telemetría al servidor de Zipkin.</span><span class="sxs-lookup"><span data-stu-id="4524d-221">Once the application is started, the Dapr sidecars will emit telemetry to the Zipkin server.</span></span> <span data-ttu-id="4524d-222">Para inspeccionar esta telemetría, apunte un explorador Web a <http://localhost:32411> .</span><span class="sxs-lookup"><span data-stu-id="4524d-222">To inspect this telemetry, point a web-browser to <http://localhost:32411>.</span></span> <span data-ttu-id="4524d-223">Verá el front-end web Zipkin:</span><span class="sxs-lookup"><span data-stu-id="4524d-223">You'll see the Zipkin web front end:</span></span>

![Página de inicio de Zipkin](media/observability/zipkin.png)

<span data-ttu-id="4524d-225">En la pestaña *Buscar un seguimiento* , puede consultar los seguimientos.</span><span class="sxs-lookup"><span data-stu-id="4524d-225">On the *Find a trace* tab, you can query traces.</span></span> <span data-ttu-id="4524d-226">Si presiona el botón *Ejecutar consulta* sin especificar ninguna restricción, se mostrarán todos los *seguimientos* ingeridos:</span><span class="sxs-lookup"><span data-stu-id="4524d-226">Pressing the *RUN QUERY* button without specifying any restrictions will show all the ingested *traces*:</span></span>

![Una lista de seguimientos](media/observability/zipkin-traces-overview.png)

<span data-ttu-id="4524d-228">Al hacer clic en el botón *Mostrar* situado junto a un seguimiento específico, se mostrarán los detalles de dicho seguimiento:</span><span class="sxs-lookup"><span data-stu-id="4524d-228">Clicking the *SHOW* button next to a specific trace, will show the details of that trace:</span></span>

![Detalles de un seguimiento](media/observability/zipkin-trace-details.png)

<span data-ttu-id="4524d-230">Cada elemento de la página de detalles, es un intervalo que representa una solicitud que forma parte del seguimiento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="4524d-230">Each item on the details page, is a span that represents a request that is part of the selected trace.</span></span>

##### <a name="inspect-the-dependencies-between-services"></a><span data-ttu-id="4524d-231">Inspeccionar las dependencias entre servicios</span><span class="sxs-lookup"><span data-stu-id="4524d-231">Inspect the dependencies between services</span></span>

<span data-ttu-id="4524d-232">Dado que DAPR sidecars controla el tráfico entre los servicios, Zipkin puede usar la información de seguimiento para determinar las dependencias entre los servicios.</span><span class="sxs-lookup"><span data-stu-id="4524d-232">Because Dapr sidecars handle traffic between services, Zipkin can use the trace information to determine the dependencies between the services.</span></span> <span data-ttu-id="4524d-233">Para verlo en acción, vaya a la pestaña *dependencias* de la Página Web de Zipkin y seleccione el botón con la lupa.</span><span class="sxs-lookup"><span data-stu-id="4524d-233">To see it in action, go to the *Dependencies* tab on the Zipkin web page and select the button with the magnifying glass.</span></span> <span data-ttu-id="4524d-234">Zipkin mostrará información general de los servicios y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="4524d-234">Zipkin will show an overview of the services and their dependencies:</span></span>

![Gráfico de dependencias en Zipkin](media/observability/zipkin-dependencies.png)

<span data-ttu-id="4524d-236">Los puntos animados de las líneas entre los servicios representan solicitudes y se mueven desde el origen al destino.</span><span class="sxs-lookup"><span data-stu-id="4524d-236">The animated dots on the lines between the services represent requests and move from source to destination.</span></span> <span data-ttu-id="4524d-237">Los puntos rojos indican una solicitud con error.</span><span class="sxs-lookup"><span data-stu-id="4524d-237">Red dots indicate a failed request.</span></span>

#### <a name="use-a-jaeger-or-new-relic-monitoring-back-end"></a><span data-ttu-id="4524d-238">Usar un back-end de supervisión de Jaeger o nuevo Relic</span><span class="sxs-lookup"><span data-stu-id="4524d-238">Use a Jaeger or New Relic monitoring back end</span></span>

<span data-ttu-id="4524d-239">Además de Zipkin, otro software de back-end de supervisión también admite la ingesta de telemetría con el formato Zipkin.</span><span class="sxs-lookup"><span data-stu-id="4524d-239">Beyond Zipkin itself, other monitoring back-end software also supports ingesting telemetry using the Zipkin format.</span></span> <span data-ttu-id="4524d-240">[Jaeger](https://www.jaegertracing.io/) es un sistema de seguimiento de código abierto creado por las tecnologías de uber.</span><span class="sxs-lookup"><span data-stu-id="4524d-240">[Jaeger](https://www.jaegertracing.io/) is an open source tracing system created by Uber Technologies.</span></span> <span data-ttu-id="4524d-241">Se usa para realizar un seguimiento de las transacciones entre servicios distribuidos y solucionar problemas complejos de los entornos de microservicios.</span><span class="sxs-lookup"><span data-stu-id="4524d-241">It's used to trace transactions between distributed services and troubleshoot complex microservices environments.</span></span> <span data-ttu-id="4524d-242">[New Relic](https://newrelic.com/) es una plataforma *de observación de pila completa* .</span><span class="sxs-lookup"><span data-stu-id="4524d-242">[New Relic](https://newrelic.com/) is a *full-stack* observability platform.</span></span> <span data-ttu-id="4524d-243">Vincula los datos pertinentes de una aplicación distribuida para proporcionar una imagen completa del sistema.</span><span class="sxs-lookup"><span data-stu-id="4524d-243">It links relevant data from a distributed application to provide a complete picture of your system.</span></span> <span data-ttu-id="4524d-244">Para probarlas, especifique un `endpointAddress` que apunte a un servidor de Jaeger o nuevo Relic en el archivo de configuración DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-244">To try them out, specify an `endpointAddress` pointing to either a Jaeger or New Relic server in the Dapr configuration file.</span></span> <span data-ttu-id="4524d-245">A continuación se muestra un ejemplo de un archivo de configuración que configura DAPR para enviar telemetría a un servidor de Jaeger.</span><span class="sxs-lookup"><span data-stu-id="4524d-245">Here's an example of a configuration file that configures Dapr to send telemetry to a Jaeger server.</span></span> <span data-ttu-id="4524d-246">La dirección URL de Jaeger es idéntica a la dirección URL de Zipkin.</span><span class="sxs-lookup"><span data-stu-id="4524d-246">The URL for Jaeger is identical to the URL for the Zipkin.</span></span> <span data-ttu-id="4524d-247">La única diferencia es el puerto en el que se ejecuta el servidor:</span><span class="sxs-lookup"><span data-stu-id="4524d-247">The only difference is the port on which the server runs:</span></span>

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "http://localhost:9415/api/v2/spans"
 ```

<span data-ttu-id="4524d-248">Para probar New Relic, especifique el punto de conexión de la nueva API de Relic.</span><span class="sxs-lookup"><span data-stu-id="4524d-248">To try out New Relic, specify the endpoint of the New Relic API.</span></span> <span data-ttu-id="4524d-249">A continuación se muestra un ejemplo de un archivo de configuración para New Relic:</span><span class="sxs-lookup"><span data-stu-id="4524d-249">Here's an example of a configuration file for New Relic:</span></span>

 ```yaml
apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "https://trace-api.newrelic.com/trace/v1?Api-Key=<NR-API-KEY>&Data-Format=zipkin&Data-Format-Version=2"
 ```

<span data-ttu-id="4524d-250">Consulte los sitios web Jaeger y New Relic para obtener más información sobre cómo usarlos.</span><span class="sxs-lookup"><span data-stu-id="4524d-250">Check out the Jaeger and New Relic websites for more information on how to use them.</span></span>

### <a name="metrics"></a><span data-ttu-id="4524d-251">Métricas</span><span class="sxs-lookup"><span data-stu-id="4524d-251">Metrics</span></span>

<span data-ttu-id="4524d-252">Las métricas proporcionan información sobre el rendimiento y el consumo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4524d-252">Metrics provide insight into performance and resource consumption.</span></span> <span data-ttu-id="4524d-253">En el capó, DAPR emite una amplia colección de métricas del sistema y en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4524d-253">Under the hood, Dapr emits a wide collection of system and runtime metrics.</span></span> <span data-ttu-id="4524d-254">DAPR usa [Prometheus](https://prometheus.io/) como estándar de métricas.</span><span class="sxs-lookup"><span data-stu-id="4524d-254">Dapr uses [Prometheus](https://prometheus.io/) as a metric standard.</span></span> <span data-ttu-id="4524d-255">DAPR sidecars and System Services, exponga un punto de conexión de métricas en el puerto `9090` .</span><span class="sxs-lookup"><span data-stu-id="4524d-255">Dapr sidecars and system services, expose a metrics endpoint on port `9090`.</span></span> <span data-ttu-id="4524d-256">Un *recorter de Prometheus* llama a este punto de conexión en un intervalo predefinido para recopilar métricas.</span><span class="sxs-lookup"><span data-stu-id="4524d-256">A *Prometheus scraper* calls this endpoint at a predefined interval to collect metrics.</span></span> <span data-ttu-id="4524d-257">El residuo envía valores de métricas a un back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-257">The scraper sends metric values to a monitoring back end.</span></span> <span data-ttu-id="4524d-258">En la figura 9-4 se muestra el proceso de recorte:</span><span class="sxs-lookup"><span data-stu-id="4524d-258">Figure 9-4 shows the scraping process:</span></span>

![Métricas de Prometheus de barrido](media/observability/prometheus-scraper.png)

<span data-ttu-id="4524d-260">**Figura 9-4**.</span><span class="sxs-lookup"><span data-stu-id="4524d-260">**Figure 9-4**.</span></span> <span data-ttu-id="4524d-261">Prometheus métricas de recorte.</span><span class="sxs-lookup"><span data-stu-id="4524d-261">Scraping Prometheus metrics.</span></span>

<span data-ttu-id="4524d-262">En la ilustración anterior, cada sidecar y el servicio del sistema exponen un punto de conexión de métrica que realiza escuchas en el puerto 9090.</span><span class="sxs-lookup"><span data-stu-id="4524d-262">In the above figure, each sidecar and system service exposes a metric endpoint that listens on port 9090.</span></span> <span data-ttu-id="4524d-263">El rechazo de las métricas de Prometheus captura las métricas de cada punto de conexión y publica la información en el back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-263">The Prometheus Metrics Scrapper captures metrics from each endpoint and published the information to the monitoring back end.</span></span>  

#### <a name="service-discovery"></a><span data-ttu-id="4524d-264">Detección de servicios</span><span class="sxs-lookup"><span data-stu-id="4524d-264">Service discovery</span></span>

<span data-ttu-id="4524d-265">Es posible que se pregunte cómo el receptor de métricas sabe dónde recopilar métricas.</span><span class="sxs-lookup"><span data-stu-id="4524d-265">You might wonder how the metrics scraper knows where to collect metrics.</span></span> <span data-ttu-id="4524d-266">Prometheus puede integrarse con mecanismos de detección integrados en entornos de implementación de destino.</span><span class="sxs-lookup"><span data-stu-id="4524d-266">Prometheus can integrate with discovery mechanisms built into target deployment environments.</span></span> <span data-ttu-id="4524d-267">Por ejemplo, cuando se ejecuta en Kubernetes, Prometheus puede integrarse con la API de Kubernetes para buscar todos los recursos de Kubernetes disponibles que se ejecutan en el entorno.</span><span class="sxs-lookup"><span data-stu-id="4524d-267">For example, when running in Kubernetes, Prometheus can integrate with the Kubernetes API to find all available Kubernetes resources running in the environment.</span></span>

#### <a name="metrics-list"></a><span data-ttu-id="4524d-268">Lista de métricas</span><span class="sxs-lookup"><span data-stu-id="4524d-268">Metrics list</span></span>

<span data-ttu-id="4524d-269">DAPR genera un gran conjunto de métricas para los servicios del sistema de DAPR y su tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4524d-269">Dapr generates a large set of metrics for Dapr system services and its runtime.</span></span> <span data-ttu-id="4524d-270">Estos son algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="4524d-270">Some examples include:</span></span>

| <span data-ttu-id="4524d-271">Métrica</span><span class="sxs-lookup"><span data-stu-id="4524d-271">Metric</span></span>                                         | <span data-ttu-id="4524d-272">Source</span><span class="sxs-lookup"><span data-stu-id="4524d-272">Source</span></span> | <span data-ttu-id="4524d-273">Descripción</span><span class="sxs-lookup"><span data-stu-id="4524d-273">Description</span></span>                                                  |
| ---------------------------------------------- | :----: | ------------------------------------------------------------ |
| <span data-ttu-id="4524d-274">dapr_operator_service_created_total</span><span class="sxs-lookup"><span data-stu-id="4524d-274">dapr_operator_service_created_total</span></span>            | <span data-ttu-id="4524d-275">Sistema</span><span class="sxs-lookup"><span data-stu-id="4524d-275">System</span></span> | <span data-ttu-id="4524d-276">El número total de servicios de DAPR creados por el servicio del operador DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-276">The total number of Dapr services created by the Dapr Operator service.</span></span> |
| <span data-ttu-id="4524d-277">dapr_injector_sidecar_injection/requests_total</span><span class="sxs-lookup"><span data-stu-id="4524d-277">dapr_injector_sidecar_injection/requests_total</span></span> | <span data-ttu-id="4524d-278">Sistema</span><span class="sxs-lookup"><span data-stu-id="4524d-278">System</span></span> | <span data-ttu-id="4524d-279">Número total de solicitudes de inyección de sidecar recibidas por el servicio Sidecar-Injector de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-279">The total number of sidecar injection requests received by the Dapr Sidecar-Injector service.</span></span> |
| <span data-ttu-id="4524d-280">dapr_placement_runtimes_total</span><span class="sxs-lookup"><span data-stu-id="4524d-280">dapr_placement_runtimes_total</span></span>                  | <span data-ttu-id="4524d-281">Sistema</span><span class="sxs-lookup"><span data-stu-id="4524d-281">System</span></span> | <span data-ttu-id="4524d-282">El número total de hosts que se han comunicado al servicio de selección de ubicación DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-282">The total number of hosts reported to the Dapr Placement service.</span></span> |
| <span data-ttu-id="4524d-283">dapr_sentry_cert_sign_request_received_total</span><span class="sxs-lookup"><span data-stu-id="4524d-283">dapr_sentry_cert_sign_request_received_total</span></span>   | <span data-ttu-id="4524d-284">Sistema</span><span class="sxs-lookup"><span data-stu-id="4524d-284">System</span></span> | <span data-ttu-id="4524d-285">El número de solicitudes de firma de certificado (Sir) recibidas por el servicio de DAPR Sentry.</span><span class="sxs-lookup"><span data-stu-id="4524d-285">The number of certificate signing requests (CRSs) received by the Dapr Sentry service.</span></span> |
| <span data-ttu-id="4524d-286">dapr_runtime_component_loaded</span><span class="sxs-lookup"><span data-stu-id="4524d-286">dapr_runtime_component_loaded</span></span>      | <span data-ttu-id="4524d-287">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4524d-287">Runtime</span></span> | <span data-ttu-id="4524d-288">Número de componentes DAPR cargados correctamente.</span><span class="sxs-lookup"><span data-stu-id="4524d-288">The number of successfully loaded Dapr components.</span></span>           |
| <span data-ttu-id="4524d-289">dapr_grpc_io_server_completed_rpcs</span><span class="sxs-lookup"><span data-stu-id="4524d-289">dapr_grpc_io_server_completed_rpcs</span></span> | <span data-ttu-id="4524d-290">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4524d-290">Runtime</span></span> | <span data-ttu-id="4524d-291">Recuento de llamadas de gRPC por método y estado.</span><span class="sxs-lookup"><span data-stu-id="4524d-291">Count of gRPC calls by method and status.</span></span>                    |
| <span data-ttu-id="4524d-292">dapr_http_server_request_count</span><span class="sxs-lookup"><span data-stu-id="4524d-292">dapr_http_server_request_count</span></span>     | <span data-ttu-id="4524d-293">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4524d-293">Runtime</span></span> | <span data-ttu-id="4524d-294">Número de solicitudes HTTP iniciadas en un servidor HTTP.</span><span class="sxs-lookup"><span data-stu-id="4524d-294">Number of HTTP requests started in an HTTP server.</span></span>           |
| <span data-ttu-id="4524d-295">dapr_http/Client/sent_bytes</span><span class="sxs-lookup"><span data-stu-id="4524d-295">dapr_http/client/sent_bytes</span></span>        | <span data-ttu-id="4524d-296">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="4524d-296">Runtime</span></span> | <span data-ttu-id="4524d-297">Número total de bytes enviados en el cuerpo de la solicitud (sin incluir los encabezados) por un cliente HTTP.</span><span class="sxs-lookup"><span data-stu-id="4524d-297">Total bytes sent in request body (not including headers) by an HTTP client.</span></span> |

<span data-ttu-id="4524d-298">Para más información sobre las métricas disponibles, consulte la [documentación de métricas de DAPR](https://docs.dapr.io/developing-applications/building-blocks/observability/metrics).</span><span class="sxs-lookup"><span data-stu-id="4524d-298">For more information on available metrics, see the [Dapr metrics documentation](https://docs.dapr.io/developing-applications/building-blocks/observability/metrics).</span></span>

#### <a name="configure-dapr-metrics"></a><span data-ttu-id="4524d-299">Configuración de métricas de DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-299">Configure Dapr metrics</span></span>

<span data-ttu-id="4524d-300">En tiempo de ejecución, puede deshabilitar el punto de conexión de la colección de métricas incluyendo el `--enable-metrics=false` argumento en el comando DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-300">At runtime, you can disable the metrics collection endpoint by including the `--enable-metrics=false` argument in the Dapr command.</span></span> <span data-ttu-id="4524d-301">O bien, también puede cambiar el puerto predeterminado para el extremo con el `--metrics-port 9090` argumento.</span><span class="sxs-lookup"><span data-stu-id="4524d-301">Or, you can also change the default port for the endpoint with the `--metrics-port 9090` argument.</span></span>

<span data-ttu-id="4524d-302">También puede usar un archivo de configuración DAPR para habilitar o deshabilitar la recopilación de métricas en tiempo de ejecución de forma estática:</span><span class="sxs-lookup"><span data-stu-id="4524d-302">You can also use a Dapr configuration file to statically enable or disable runtime metrics collection:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  metric:
    enabled: false
```

#### <a name="visualize-dapr-metrics"></a><span data-ttu-id="4524d-303">Visualización de métricas de DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-303">Visualize Dapr metrics</span></span>

<span data-ttu-id="4524d-304">Con las métricas de recopilación y publicación de la Prometheus de recortes en el back-end de supervisión, ¿cómo tiene sentido los datos sin procesar?</span><span class="sxs-lookup"><span data-stu-id="4524d-304">With the Prometheus scraper collecting and publishing metrics into the monitoring back end, how do you make sense of the raw data?</span></span> <span data-ttu-id="4524d-305">Una popular herramienta de visualización para analizar métricas es [Grafana](https://grafana.com/grafana/).</span><span class="sxs-lookup"><span data-stu-id="4524d-305">A popular visualization tool for analyzing metrics is [Grafana](https://grafana.com/grafana/).</span></span> <span data-ttu-id="4524d-306">Con Grafana, puede crear paneles a partir de las métricas disponibles.</span><span class="sxs-lookup"><span data-stu-id="4524d-306">With Grafana, you can create dashboards from the available metrics.</span></span> <span data-ttu-id="4524d-307">Este es un ejemplo de un panel que muestra las métricas de servicios del sistema de DAPR:</span><span class="sxs-lookup"><span data-stu-id="4524d-307">Here's an example of a dashboard displaying Dapr system services metrics:</span></span>

![Panel de Grafana que muestra las métricas de servicios del sistema de DAPR](media/observability/grafana-sample.png)

<span data-ttu-id="4524d-309">La documentación de DAPR incluye un [tutorial para la instalación de Prometheus y Grafana](https://docs.dapr.io/operations/monitoring/grafana/).</span><span class="sxs-lookup"><span data-stu-id="4524d-309">The Dapr documentation includes a [tutorial for installing Prometheus and Grafana](https://docs.dapr.io/operations/monitoring/grafana/).</span></span>

### <a name="logging"></a><span data-ttu-id="4524d-310">Registro</span><span class="sxs-lookup"><span data-stu-id="4524d-310">Logging</span></span>

<span data-ttu-id="4524d-311">El registro proporciona información sobre lo que ocurre con un servicio en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4524d-311">Logging provides insight into what is happening with a service at runtime.</span></span> <span data-ttu-id="4524d-312">Al ejecutar una aplicación, DAPR emite automáticamente las entradas de registro de los servicios de sistema de DAPR de los sidecar y DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-312">When running an application, Dapr automatically emits log entries from Dapr sidecars and Dapr system services.</span></span> <span data-ttu-id="4524d-313">Sin embargo, las entradas de registro instrumentadas en el código de la aplicación **no** se incluyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4524d-313">However, logging entries instrumented in your application code **aren't** automatically included.</span></span> <span data-ttu-id="4524d-314">Para emitir el registro del código de la aplicación, puede importar un SDK específico como [OPENTELEMETRY SDK para .net](https://opentelemetry.io/docs/net/).</span><span class="sxs-lookup"><span data-stu-id="4524d-314">To emit logging from application code, you can import a specific SDK like [OpenTelemetry SDK for .NET](https://opentelemetry.io/docs/net/).</span></span> <span data-ttu-id="4524d-315">El código de la aplicación de registro se trata más adelante en este capítulo en la sección *uso del SDK de .net de DAPR*.</span><span class="sxs-lookup"><span data-stu-id="4524d-315">Logging application code is covered later in this chapter in the section *Using the Dapr .NET SDK*.</span></span>  

#### <a name="log-entry-structure"></a><span data-ttu-id="4524d-316">Estructura de entrada de registro</span><span class="sxs-lookup"><span data-stu-id="4524d-316">Log entry structure</span></span>

<span data-ttu-id="4524d-317">DAPR emite un registro estructurado.</span><span class="sxs-lookup"><span data-stu-id="4524d-317">Dapr emits structured logging.</span></span> <span data-ttu-id="4524d-318">Cada entrada de registro tiene el formato siguiente:</span><span class="sxs-lookup"><span data-stu-id="4524d-318">Each log entry has the following format:</span></span>

| <span data-ttu-id="4524d-319">Campo</span><span class="sxs-lookup"><span data-stu-id="4524d-319">Field</span></span>    | <span data-ttu-id="4524d-320">Descripción</span><span class="sxs-lookup"><span data-stu-id="4524d-320">Description</span></span>                                          | <span data-ttu-id="4524d-321">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4524d-321">Example</span></span>                             |
| -------- | ---------------------------------------------------- | ----------------------------------- |
| <span data-ttu-id="4524d-322">time</span><span class="sxs-lookup"><span data-stu-id="4524d-322">time</span></span>     | <span data-ttu-id="4524d-323">Marca de tiempo con formato ISO8601</span><span class="sxs-lookup"><span data-stu-id="4524d-323">ISO8601 formatted timestamp</span></span>                          | `2021-01-10T14:19:31.000Z`          |
| <span data-ttu-id="4524d-324">level</span><span class="sxs-lookup"><span data-stu-id="4524d-324">level</span></span>    | <span data-ttu-id="4524d-325">Nivel de la entrada ( `debug` \| `info` \| `warn` \| `error` )  </span><span class="sxs-lookup"><span data-stu-id="4524d-325">Level of the entry (`debug` \| `info` \| `warn`  \| `error`)</span></span> | `info`                              |
| <span data-ttu-id="4524d-326">type</span><span class="sxs-lookup"><span data-stu-id="4524d-326">type</span></span>     | <span data-ttu-id="4524d-327">Tipo de registro</span><span class="sxs-lookup"><span data-stu-id="4524d-327">Log Type</span></span>                                             | `log`                               |
| <span data-ttu-id="4524d-328">msg</span><span class="sxs-lookup"><span data-stu-id="4524d-328">msg</span></span>      | <span data-ttu-id="4524d-329">Mensaje de registro</span><span class="sxs-lookup"><span data-stu-id="4524d-329">Log Message</span></span>                                          | `metrics server started on :62408/` |
| <span data-ttu-id="4524d-330">scope</span><span class="sxs-lookup"><span data-stu-id="4524d-330">scope</span></span>    | <span data-ttu-id="4524d-331">Ámbito de registro</span><span class="sxs-lookup"><span data-stu-id="4524d-331">Logging Scope</span></span>                                        | `dapr.runtime`                      |
| <span data-ttu-id="4524d-332">instance</span><span class="sxs-lookup"><span data-stu-id="4524d-332">instance</span></span> | <span data-ttu-id="4524d-333">Nombre de host donde se ejecuta DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-333">Hostname where Dapr runs</span></span>                             | <span data-ttu-id="4524d-334">TSTSRV01</span><span class="sxs-lookup"><span data-stu-id="4524d-334">TSTSRV01</span></span>                            |
| <span data-ttu-id="4524d-335">app_id</span><span class="sxs-lookup"><span data-stu-id="4524d-335">app_id</span></span>   | <span data-ttu-id="4524d-336">IDENTIFICADOR de la aplicación DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-336">Dapr App ID</span></span>                                          | <span data-ttu-id="4524d-337">ordering-api</span><span class="sxs-lookup"><span data-stu-id="4524d-337">ordering-api</span></span>                        |
| <span data-ttu-id="4524d-338">ver</span><span class="sxs-lookup"><span data-stu-id="4524d-338">ver</span></span>      | <span data-ttu-id="4524d-339">Versión de tiempo de ejecución de DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-339">Dapr Runtime Version</span></span>                                 | <span data-ttu-id="4524d-340">`1.0.0`-RC. 2</span><span class="sxs-lookup"><span data-stu-id="4524d-340">`1.0.0`-rc.2</span></span>                        |

<span data-ttu-id="4524d-341">Al buscar en las entradas de registro en un escenario de solución de problemas, los `time` `level` campos y son especialmente útiles.</span><span class="sxs-lookup"><span data-stu-id="4524d-341">When searching through logging entries in a troubleshooting scenario, the `time` and `level` fields are especially helpful.</span></span> <span data-ttu-id="4524d-342">El campo de hora ordena las entradas de registro para que pueda identificar períodos de tiempo específicos.</span><span class="sxs-lookup"><span data-stu-id="4524d-342">The time field orders log entries so that you can pinpoint specific time periods.</span></span> <span data-ttu-id="4524d-343">Al solucionar problemas, las entradas de registro en el *nivel de depuración* proporcionan más información sobre el comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="4524d-343">When troubleshooting, log entries at the *debug level* provide more information on the behavior of the code.</span></span>

#### <a name="plain-text-versus-json-format"></a><span data-ttu-id="4524d-344">Texto sin formato frente al formato JSON</span><span class="sxs-lookup"><span data-stu-id="4524d-344">Plain text versus JSON format</span></span>

<span data-ttu-id="4524d-345">De forma predeterminada, DAPR emite un registro estructurado en formato de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="4524d-345">By default, Dapr emits structured logging in plain-text format.</span></span> <span data-ttu-id="4524d-346">Cada entrada de registro se formatea como una cadena que contiene pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="4524d-346">Every log entry is formatted as a string containing key/value pairs.</span></span> <span data-ttu-id="4524d-347">Este es un ejemplo de registro en texto sin formato:</span><span class="sxs-lookup"><span data-stu-id="4524d-347">Here's an example of logging in plain text:</span></span>

```text
== DAPR == time="2021-01-12T16:11:39.4669323+01:00" level=info msg="starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="log level set to: info" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="metrics server started on :62408/" app_id=ordering-api instance=TSTSRV03 scope=dapr.metrics type=log ver=1.0.0-rc.2
```

<span data-ttu-id="4524d-348">Aunque es sencillo, este formato es difícil de analizar.</span><span class="sxs-lookup"><span data-stu-id="4524d-348">While simple, this format is difficult to parse.</span></span> <span data-ttu-id="4524d-349">Si desea ver las entradas del registro con una herramienta de supervisión, querrá habilitar el registro con formato JSON.</span><span class="sxs-lookup"><span data-stu-id="4524d-349">If viewing log entries with a monitoring tool, you'll want to enable JSON formatted logging.</span></span> <span data-ttu-id="4524d-350">Con las entradas JSON, una herramienta de supervisión puede indexar y consultar campos individuales.</span><span class="sxs-lookup"><span data-stu-id="4524d-350">With JSON entries, a monitoring tool can index and query individual fields.</span></span> <span data-ttu-id="4524d-351">Estas son las mismas entradas de registro en formato JSON:</span><span class="sxs-lookup"><span data-stu-id="4524d-351">Here's the same log entries in JSON format:</span></span>

```json
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d", "scope": "dapr.runtime", "time": "2021-01-12T16:11:39.4669323+01:00", "type": "log", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "log level set to: info", "scope": "dapr.runtime", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "metrics server started on :62408/", "scope": "dapr.metrics", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
```

<span data-ttu-id="4524d-352">Para habilitar el formato JSON, debe configurar cada sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-352">To enable JSON formatting, you need to configure each Dapr sidecar.</span></span> <span data-ttu-id="4524d-353">En el modo autohospedado, puede especificar la marca `--log-as-json` en la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="4524d-353">In self-hosted mode, you can specify the flag `--log-as-json` on the command line:</span></span>

```console
dapr run --app-id ordering-api --log-level info --log-as-json dotnet run
```

<span data-ttu-id="4524d-354">En Kubernetes, puede Agregar una `dapr.io/log-as-json` anotación a cada implementación de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4524d-354">In Kubernetes, you can add a `dapr.io/log-as-json` annotation to each deployment for the application:</span></span>

```yaml
annotations:
   dapr.io/enabled: "true"
   dapr.io/app-id: "ordering-api"
   dapr.io/app-port: "80"
   dapr.io/config: "dapr-config"
   dapr.io/log-as-json: "true"
```

<span data-ttu-id="4524d-355">Al instalar DAPR en un clúster de Kubernetes con Helm, puede habilitar el registro con formato JSON para todos los servicios del sistema DAPR:</span><span class="sxs-lookup"><span data-stu-id="4524d-355">When you install Dapr in a Kubernetes cluster using Helm, you can enable JSON formatted logging for all the Dapr system services:</span></span>

```console
helm repo add dapr https://dapr.github.io/helm-charts/
helm repo update
kubectl create namespace dapr-system
helm install dapr dapr/dapr --namespace dapr-system --set global.logAsJson=true
```

#### <a name="collect-logs"></a><span data-ttu-id="4524d-356">Recopilación de registros</span><span class="sxs-lookup"><span data-stu-id="4524d-356">Collect logs</span></span>

<span data-ttu-id="4524d-357">Los registros emitidos por DAPR se pueden alimentar en un back-end de supervisión para su análisis.</span><span class="sxs-lookup"><span data-stu-id="4524d-357">The logs emitted by Dapr can be fed into a monitoring back end for analysis.</span></span> <span data-ttu-id="4524d-358">Un recopilador de registros es un componente que recopila registros de un sistema y los envía a un back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-358">A log collector is a component that collects logs from a system and sends them to a monitoring back end.</span></span> <span data-ttu-id="4524d-359">Un recopilador de registros conocido está [habituado](https://www.fluentd.org/).</span><span class="sxs-lookup"><span data-stu-id="4524d-359">A popular log collector is [Fluentd](https://www.fluentd.org/).</span></span> <span data-ttu-id="4524d-360">Consulte el [artículo sobre cómo configurar la búsqueda elástica y las Kibana en Kubernetes](https://docs.dapr.io/operations/monitoring/fluentd/) en la documentación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-360">Check out the [How-To: Set up Fluentd, Elastic search and Kibana in Kubernetes](https://docs.dapr.io/operations/monitoring/fluentd/) in the Dapr documentation.</span></span> <span data-ttu-id="4524d-361">En este artículo se incluyen instrucciones para configurar el recopilador de registros y la [pila de Elk](https://www.elastic.co/elastic-stack) (búsqueda elástica y Kibana) como un back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-361">This article contains instructions for setting up Fluentd as log collector and the [ELK Stack](https://www.elastic.co/elastic-stack) (Elastic Search and Kibana) as a monitoring back end.</span></span>

### <a name="health-status"></a><span data-ttu-id="4524d-362">Estado de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="4524d-362">Health status</span></span>

<span data-ttu-id="4524d-363">El estado de mantenimiento de un servicio proporciona una visión general de su disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="4524d-363">The health status of a service provides insight into its availability.</span></span> <span data-ttu-id="4524d-364">Cada sidecar de DAPR expone una API de estado que el entorno de hospedaje puede usar para determinar el estado del sidecar.</span><span class="sxs-lookup"><span data-stu-id="4524d-364">Each Dapr sidecar exposes a health API that can be used by the hosting environment to determine the health of the sidecar.</span></span> <span data-ttu-id="4524d-365">La API tiene una operación:</span><span class="sxs-lookup"><span data-stu-id="4524d-365">The API has one operation:</span></span>

```console
GET http://localhost:3500/v1.0/healthz
```

<span data-ttu-id="4524d-366">La operación devuelve dos códigos de Estado HTTP:</span><span class="sxs-lookup"><span data-stu-id="4524d-366">The operation returns two HTTP status codes:</span></span>

- <span data-ttu-id="4524d-367">204: cuando el sidecar es correcto</span><span class="sxs-lookup"><span data-stu-id="4524d-367">204: When the sidecar is healthy</span></span>
- <span data-ttu-id="4524d-368">500: cuando el sidecar no es correcto</span><span class="sxs-lookup"><span data-stu-id="4524d-368">500: when the sidecar isn't healthy</span></span>

<span data-ttu-id="4524d-369">Cuando se ejecuta en modo autohospedado, la API de mantenimiento no se invoca automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4524d-369">When running in self-hosted mode, the health API isn't automatically invoked.</span></span> <span data-ttu-id="4524d-370">Puede invocar la API a través del código de la aplicación o de una herramienta de supervisión de estado.</span><span class="sxs-lookup"><span data-stu-id="4524d-370">You can invoke the API though from application code or a health monitoring tool.</span></span>

<span data-ttu-id="4524d-371">Cuando se ejecuta en Kubernetes, el DAPR sidecar-inyector configura automáticamente Kubernetes para usar la API de mantenimiento para ejecutar *sondeos de liveness* y *sondeos de preparación*.</span><span class="sxs-lookup"><span data-stu-id="4524d-371">When running in Kubernetes, the Dapr sidecar-injector automatically configures Kubernetes to use the health API for executing *liveness probes* and *readiness probes*.</span></span>

<span data-ttu-id="4524d-372">Kubernetes usa sondeos de liveness para determinar si un contenedor está en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="4524d-372">Kubernetes uses liveness probes to determine whether a container is up and running.</span></span> <span data-ttu-id="4524d-373">Si un sondeo de liveness devuelve un código de error, Kubernetes asumirá que el contenedor está inactivo y lo reinicia automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4524d-373">If a liveness probe returns a failure code, Kubernetes will assume the container is dead and automatically restart it.</span></span> <span data-ttu-id="4524d-374">Esta característica aumenta la disponibilidad general de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-374">This feature increases the overall availability of your application.</span></span>

<span data-ttu-id="4524d-375">Kubernetes usa sondeos de preparación para determinar si un contenedor está listo para empezar a aceptar tráfico.</span><span class="sxs-lookup"><span data-stu-id="4524d-375">Kubernetes uses readiness probes to determine whether a container is ready to start accepting traffic.</span></span> <span data-ttu-id="4524d-376">Un pod se considera listo cuando todos sus contenedores están listos.</span><span class="sxs-lookup"><span data-stu-id="4524d-376">A pod is considered ready when all of its containers are ready.</span></span> <span data-ttu-id="4524d-377">Preparación determina si un servicio Kubernetes puede dirigir el tráfico a un Pod en un escenario de equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="4524d-377">Readiness determines whether a Kubernetes service can direct traffic to a pod in a load-balancing scenario.</span></span> <span data-ttu-id="4524d-378">Los pods que no están listos se quitan automáticamente del equilibrador de carga.</span><span class="sxs-lookup"><span data-stu-id="4524d-378">Pods that aren't ready are automatically removed from the load-balancer.</span></span>

<span data-ttu-id="4524d-379">Los sondeos de vida y preparación tienen varios parámetros configurables.</span><span class="sxs-lookup"><span data-stu-id="4524d-379">Liveness and readiness probes have several configurable parameters.</span></span> <span data-ttu-id="4524d-380">Ambos se configuran en la sección especificación de contenedor del archivo de manifiesto de Pod.</span><span class="sxs-lookup"><span data-stu-id="4524d-380">Both are configured in the container spec section of a pod's manifest file.</span></span> <span data-ttu-id="4524d-381">De forma predeterminada, DAPR usa la siguiente configuración para cada contenedor sidecar:</span><span class="sxs-lookup"><span data-stu-id="4524d-381">By default, Dapr uses the following configuration for each sidecar container:</span></span>

```yaml
livenessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold : 3
readinessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold: 3
```

 <span data-ttu-id="4524d-382">Los parámetros siguientes están disponibles para los sondeos:</span><span class="sxs-lookup"><span data-stu-id="4524d-382">The following parameters are available for the probes:</span></span>

- <span data-ttu-id="4524d-383">`path`Especifica el punto de conexión de la API de estado DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-383">The `path` specifies the Dapr health API endpoint.</span></span>
- <span data-ttu-id="4524d-384">`port`Especifica el puerto de la API de estado de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-384">The `port` specifies the Dapr health API port.</span></span>
- <span data-ttu-id="4524d-385">`initialDelaySeconds`Especifica el número de segundos que Kubernetes esperará antes de que empiece a sondear un contenedor por primera vez.</span><span class="sxs-lookup"><span data-stu-id="4524d-385">The `initialDelaySeconds`specifies the number of seconds Kubernetes will wait before it starts probing a container for the first time.</span></span>
- <span data-ttu-id="4524d-386">`periodSeconds`Especifica el número de segundos que Kubernetes esperará entre cada sondeo.</span><span class="sxs-lookup"><span data-stu-id="4524d-386">The `periodSeconds` specifies the number of seconds Kubernetes will wait between each probe.</span></span>
- <span data-ttu-id="4524d-387">`timeoutSeconds`Especifica el número de segundos que Kubernetes esperará una respuesta de la API antes de que se agote el tiempo de espera. Un tiempo de espera se interpreta como un error.</span><span class="sxs-lookup"><span data-stu-id="4524d-387">The `timeoutSeconds` specifies the number of seconds Kubernetes will wait on a response from the API before timing out. A timeout is interpreted as a failure.</span></span>
- <span data-ttu-id="4524d-388">`failureThreshold`Especifica el número de errores de código de estado que Kubernetes aceptará antes de considerar que el contenedor no está activo o no está listo.</span><span class="sxs-lookup"><span data-stu-id="4524d-388">The `failureThreshold`specifies the number of failed status code Kubernetes will accept before considering the container not alive or not ready.</span></span>

### <a name="dapr-dashboard"></a><span data-ttu-id="4524d-389">Panel de DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-389">Dapr dashboard</span></span>

<span data-ttu-id="4524d-390">DAPR ofrece un panel que presenta información de estado sobre las aplicaciones, los componentes y las configuraciones de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-390">Dapr offers a dashboard that presents status information on Dapr applications, components, and configurations.</span></span> <span data-ttu-id="4524d-391">Use la CLI de DAPR para iniciar el panel como una aplicación web en el equipo local en el puerto 8080:</span><span class="sxs-lookup"><span data-stu-id="4524d-391">Use the Dapr CLI to start the dashboard as a web-application on the local machine on port 8080:</span></span>

```console
dapr dashboard
```

<span data-ttu-id="4524d-392">Para la aplicación DAPR que se ejecuta en Kubernetes, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="4524d-392">For Dapr application running in Kubernetes, use the following command:</span></span>

```console
dapr dashboard -k
```

<span data-ttu-id="4524d-393">El panel se abre con una visión general de todos los servicios de la aplicación que tienen un sidecar DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-393">The dashboard opens with an overview of all services in your application that have a Dapr sidecar.</span></span> <span data-ttu-id="4524d-394">En la captura de pantalla siguiente se muestra el panel de DAPR para la aplicación eShopOnDapr que se ejecuta en Kubernetes:</span><span class="sxs-lookup"><span data-stu-id="4524d-394">The following screenshot shows the Dapr dashboard for the eShopOnDapr application running in Kubernetes:</span></span>

![Página de información general del panel de DAPR](media/observability/dapr-dashboard-overview.png)

<span data-ttu-id="4524d-396">El panel de DAPR es muy valioso al solucionar problemas de una aplicación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-396">The Dapr dashboard is invaluable when troubleshooting a Dapr application.</span></span> <span data-ttu-id="4524d-397">Proporciona información sobre los DAPR sidecar y los servicios del sistema.</span><span class="sxs-lookup"><span data-stu-id="4524d-397">It provides information about Dapr sidecars and system services.</span></span> <span data-ttu-id="4524d-398">Puede explorar en profundidad la configuración de cada servicio, incluidas las entradas de registro.</span><span class="sxs-lookup"><span data-stu-id="4524d-398">You can drill down into the configuration of each service, including the logging entries.</span></span>

<span data-ttu-id="4524d-399">El panel también muestra los componentes configurados (y su configuración) para la aplicación:</span><span class="sxs-lookup"><span data-stu-id="4524d-399">The dashboard also shows the configured components (and their configuration) for your application:</span></span>

![Página componentes del panel de DAPR](media/observability/dapr-dashboard-components.png)

<span data-ttu-id="4524d-401">Hay una gran cantidad de información disponible a través del panel.</span><span class="sxs-lookup"><span data-stu-id="4524d-401">There's a large amount of information available through the dashboard.</span></span> <span data-ttu-id="4524d-402">Puede detectarlo mediante la ejecución de una aplicación de DAPR y el examen del panel.</span><span class="sxs-lookup"><span data-stu-id="4524d-402">You can discover it by running a Dapr application and browsing the dashboard.</span></span> <span data-ttu-id="4524d-403">Puede usar la aplicación eShopOnDapr correspondiente para iniciar.</span><span class="sxs-lookup"><span data-stu-id="4524d-403">You can use the accompanying eShopOnDapr application to start.</span></span>

<span data-ttu-id="4524d-404">Consulte la referencia de comandos de la [CLI de DAPR Dashboard](https://docs.dapr.io/reference/cli/dapr-dashboard/) en los documentos de DAPR para obtener más información sobre los comandos del panel de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-404">Check out the [Dapr dashboard CLI command reference](https://docs.dapr.io/reference/cli/dapr-dashboard/) in the Dapr docs for more information on the Dapr dashboard commands.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="4524d-405">Uso del SDK de .NET para DAPR</span><span class="sxs-lookup"><span data-stu-id="4524d-405">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="4524d-406">El SDK de .NET de DAPR no contiene ninguna característica de observación específica.</span><span class="sxs-lookup"><span data-stu-id="4524d-406">The Dapr .NET SDK doesn't contain any specific observability features.</span></span> <span data-ttu-id="4524d-407">Todas las características de observación se ofrecen en el nivel DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-407">All observability features are offered at the Dapr level.</span></span>

<span data-ttu-id="4524d-408">Si desea emitir la telemetría del código de la aplicación .NET, debe tener en cuenta el [SDK de OpenTelemetry para .net](https://opentelemetry.io/docs/net/).</span><span class="sxs-lookup"><span data-stu-id="4524d-408">If you want to emit telemetry from your .NET application code, you should consider the [OpenTelemetry SDK for .NET](https://opentelemetry.io/docs/net/).</span></span> <span data-ttu-id="4524d-409">El proyecto Open Telemetry es multiplataforma, de código abierto y independiente del proveedor.</span><span class="sxs-lookup"><span data-stu-id="4524d-409">The Open Telemetry project is cross-platform, open source, and vendor agnostic.</span></span> <span data-ttu-id="4524d-410">Proporciona una implementación de un extremo a otro para generar, emitir, recopilar, procesar y exportar datos de telemetría.</span><span class="sxs-lookup"><span data-stu-id="4524d-410">It provides an end-to-end implementation to generate, emit, collect, process, and export telemetry data.</span></span> <span data-ttu-id="4524d-411">Hay una única biblioteca de instrumentación por lenguaje que admite la instrumentación automática y manual.</span><span class="sxs-lookup"><span data-stu-id="4524d-411">There's a single instrumentation library per language that supports automatic and manual instrumentation.</span></span> <span data-ttu-id="4524d-412">La telemetría se publica con el estándar Open Telemetry.</span><span class="sxs-lookup"><span data-stu-id="4524d-412">Telemetry is published using the Open Telemetry standard.</span></span> <span data-ttu-id="4524d-413">El proyecto tiene una amplia compatibilidad con el sector y la adopción de proveedores de servicios en la nube, proveedores y usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="4524d-413">The project has broad industry support and adoption from cloud providers, vendors, and end users.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="4524d-414">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="4524d-414">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="4524d-415">La observación de la aplicación de referencia eShopOnDapr que la acompaña se compone de varias partes.</span><span class="sxs-lookup"><span data-stu-id="4524d-415">Observability in accompanying eShopOnDapr reference application consists of several parts.</span></span> <span data-ttu-id="4524d-416">Se captura la telemetría de todos los sidecar.</span><span class="sxs-lookup"><span data-stu-id="4524d-416">Telemetry from all of the sidecars is captured.</span></span> <span data-ttu-id="4524d-417">Además, hay otras características de observación heredadas del ejemplo de eShopOnContainers anterior.</span><span class="sxs-lookup"><span data-stu-id="4524d-417">Additionally, there are other observability features inherited from the earlier eShopOnContainers sample.</span></span>

### <a name="custom-health-dashboard"></a><span data-ttu-id="4524d-418">Panel de estado personalizado</span><span class="sxs-lookup"><span data-stu-id="4524d-418">Custom health dashboard</span></span>

<span data-ttu-id="4524d-419">El proyecto **Webstatus** de eShopOnDapr es un panel de estado personalizado que proporciona información sobre el estado de los servicios de eShop.</span><span class="sxs-lookup"><span data-stu-id="4524d-419">The **WebStatus** project in eShopOnDapr is a custom health dashboard that gives insight into the health of the eShop services.</span></span> <span data-ttu-id="4524d-420">Este panel no usa la API de mantenimiento de DAPR, pero usa el [mecanismo de comprobación de estado](/aspnet/core/host-and-deploy/health-checks) integrado de ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="4524d-420">This dashboard doesn't use the Dapr health API but uses the built-in [health checks mechanism](/aspnet/core/host-and-deploy/health-checks) of ASP.NET Core.</span></span> <span data-ttu-id="4524d-421">El panel no solo proporciona el estado de mantenimiento de los servicios, sino también el estado de las dependencias de los servicios.</span><span class="sxs-lookup"><span data-stu-id="4524d-421">The dashboard not only provides the health status of the services, but also the health of the dependencies of the services.</span></span> <span data-ttu-id="4524d-422">Por ejemplo, un servicio que utiliza una base de datos también proporciona el estado de mantenimiento de esta base de datos, tal como se muestra en la siguiente captura de pantalla:</span><span class="sxs-lookup"><span data-stu-id="4524d-422">For example, a service that uses a database also provides the health status of this database as shown in the following screenshot:</span></span>

![panel de estado personalizado de eShopOnDapr](media/observability/eshop-health-dashboard.png)

### <a name="seq-log-aggregator"></a><span data-ttu-id="4524d-424">Agregador de registro de SEQ</span><span class="sxs-lookup"><span data-stu-id="4524d-424">Seq log aggregator</span></span>

<span data-ttu-id="4524d-425">[Seq](https://datalust.co/seq) es un popular servidor de agregador de registros que se usa en eShopOnDapr para agregar registros.</span><span class="sxs-lookup"><span data-stu-id="4524d-425">[Seq](https://datalust.co/seq) is a popular log aggregator server that is used in eShopOnDapr to aggregate logs.</span></span> <span data-ttu-id="4524d-426">SEQ introduce el registro de servicios de aplicaciones, pero no de servicios del sistema de DAPR o sidecar.</span><span class="sxs-lookup"><span data-stu-id="4524d-426">Seq ingests logging from application services, but not from Dapr system services or sidecars.</span></span> <span data-ttu-id="4524d-427">SEQ indexa el registro de aplicaciones y ofrece un front-end web para analizar y consultar los registros.</span><span class="sxs-lookup"><span data-stu-id="4524d-427">Seq indexes application logging and offers a web front end for analyzing and querying the logs.</span></span> <span data-ttu-id="4524d-428">También ofrece funcionalidad para crear paneles de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-428">It also offers functionality for building monitoring dashboards.</span></span>

<span data-ttu-id="4524d-429">Los servicios de aplicaciones de eShopOnDapr emiten un registro estructurado mediante la biblioteca de registro de [SeriLog](https://serilog.net/) .</span><span class="sxs-lookup"><span data-stu-id="4524d-429">The eShopOnDapr application services emit structured logging using the [SeriLog](https://serilog.net/) logging library.</span></span> <span data-ttu-id="4524d-430">Serilog publica eventos de registro en una construcción denominada **receptor**.</span><span class="sxs-lookup"><span data-stu-id="4524d-430">Serilog publishes log events to a construct called a **sink**.</span></span> <span data-ttu-id="4524d-431">Un receptor es simplemente una plataforma de destino en la que Serilog escribe los eventos de registro.</span><span class="sxs-lookup"><span data-stu-id="4524d-431">A sink is simply a target platform to which Serilog writes its logging events.</span></span> <span data-ttu-id="4524d-432">[Hay muchos receptores de Serilog disponibles](https://github.com/serilog/serilog/wiki/Provided-Sinks), incluido uno para seq.</span><span class="sxs-lookup"><span data-stu-id="4524d-432">[Many Serilog sinks are available](https://github.com/serilog/serilog/wiki/Provided-Sinks), including one for Seq.</span></span> <span data-ttu-id="4524d-433">SEQ es el receptor de Serilog usado en eShopOnDapr.</span><span class="sxs-lookup"><span data-stu-id="4524d-433">Seq is the Serilog sink used in eShopOnDapr.</span></span>

### <a name="application-insights"></a><span data-ttu-id="4524d-434">Application Insights</span><span class="sxs-lookup"><span data-stu-id="4524d-434">Application Insights</span></span>

<span data-ttu-id="4524d-435">los servicios de eShopOnDapr también envían telemetría directamente a Aplicación de Azure Insights mediante el SDK de Microsoft Application Insights para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4524d-435">eShopOnDapr services also send telemetry directly to Azure Application Insights using the Microsoft Application Insights SDK for .NET Core.</span></span> <span data-ttu-id="4524d-436">Para obtener más información, vea [aplicación de Azure Insights para aplicaciones de ASP.net Core](/azure/azure-monitor/app/asp-net-core) en Microsoft docs.</span><span class="sxs-lookup"><span data-stu-id="4524d-436">For more information, see [Azure Application Insights for ASP.NET Core applications](/azure/azure-monitor/app/asp-net-core) in the Microsoft docs.</span></span>

## <a name="summary"></a><span data-ttu-id="4524d-437">Resumen</span><span class="sxs-lookup"><span data-stu-id="4524d-437">Summary</span></span>

<span data-ttu-id="4524d-438">La buena observación es fundamental cuando se ejecuta un sistema distribuido en producción.</span><span class="sxs-lookup"><span data-stu-id="4524d-438">Good observability is crucial when running a distributed system in production.</span></span>

<span data-ttu-id="4524d-439">DAPR proporciona distintos tipos de telemetría, como el seguimiento distribuido, el registro, las métricas y el estado de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="4524d-439">Dapr provides different types of telemetry, including distributed tracing, logging, metrics, and health status.</span></span>

<span data-ttu-id="4524d-440">DAPR solo genera telemetría para los servicios del sistema DAPR y los sidecar.</span><span class="sxs-lookup"><span data-stu-id="4524d-440">Dapr only produces telemetry for the Dapr system services and sidecars.</span></span> <span data-ttu-id="4524d-441">La telemetría del código de la aplicación no se incluye automáticamente.</span><span class="sxs-lookup"><span data-stu-id="4524d-441">Telemetry from your application code isn't automatically included.</span></span> <span data-ttu-id="4524d-442">Sin embargo, puede usar un SDK específico como el SDK de OpenTelemetry para .NET con el fin de emitir la telemetría del código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4524d-442">You can however use a specific SDK like the OpenTelemetry SDK for .NET to emit telemetry from your application code.</span></span>

<span data-ttu-id="4524d-443">La telemetría DAPR se produce en un formato basado en estándares abiertos para que se pueda ingerir mediante un amplio conjunto de herramientas de supervisión disponibles.</span><span class="sxs-lookup"><span data-stu-id="4524d-443">Dapr telemetry is produced in an open-standards based format so it can be ingested by a large set of available monitoring tools.</span></span> <span data-ttu-id="4524d-444">Algunos ejemplos son: Zipkin, Aplicación de Azure Insights, la pila de ELK, New Relic y Grafana.</span><span class="sxs-lookup"><span data-stu-id="4524d-444">Some examples are: Zipkin, Azure Application Insights, the ELK Stack, New Relic, and Grafana.</span></span> <span data-ttu-id="4524d-445">Consulte [supervisión de la aplicación con DAPR](https://docs.dapr.io/operations/monitoring/) en la documentación de DAPR para ver Tutoriales sobre cómo supervisar las aplicaciones de DAPR con back-ends de supervisión específicos.</span><span class="sxs-lookup"><span data-stu-id="4524d-445">See [Monitor your application with Dapr](https://docs.dapr.io/operations/monitoring/) in the Dapr documentation for tutorials on how to monitor your Dapr applications with specific monitoring back ends.</span></span>

<span data-ttu-id="4524d-446">Necesitará un recortedor de telemetría que ingesta la telemetría y la publique en el back-end de supervisión.</span><span class="sxs-lookup"><span data-stu-id="4524d-446">You'll need a telemetry scraper that ingests telemetry and publishes it to the monitoring back end.</span></span>

<span data-ttu-id="4524d-447">DAPR puede configurarse para emitir un registro estructurado.</span><span class="sxs-lookup"><span data-stu-id="4524d-447">Dapr can be configured to emit structured logging.</span></span> <span data-ttu-id="4524d-448">Se favorece el registro estructurado, ya que se puede indexar mediante herramientas de supervisión de back-end.</span><span class="sxs-lookup"><span data-stu-id="4524d-448">Structured logging is favored as it can be indexed by back-end monitoring tools.</span></span> <span data-ttu-id="4524d-449">El registro indizado permite a los usuarios ejecutar consultas enriquecidas al buscar en el registro.</span><span class="sxs-lookup"><span data-stu-id="4524d-449">Indexed logging enables users to execute rich queries when searching through the logging.</span></span>

<span data-ttu-id="4524d-450">DAPR ofrece un panel que presenta información acerca de los servicios y la configuración de DAPR.</span><span class="sxs-lookup"><span data-stu-id="4524d-450">Dapr offers a dashboard that presents information about the Dapr services and configuration.</span></span>

## <a name="references"></a><span data-ttu-id="4524d-451">Referencias</span><span class="sxs-lookup"><span data-stu-id="4524d-451">References</span></span>

- [<span data-ttu-id="4524d-452">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="4524d-452">Azure Application Insights</span></span>](/azure/azure-monitor/app/app-insights-overview/)
- [<span data-ttu-id="4524d-453">Abrir la telemetría</span><span class="sxs-lookup"><span data-stu-id="4524d-453">Open Telemetry</span></span>](https://opentelemetry.io/)
- [<span data-ttu-id="4524d-454">Zipkin</span><span class="sxs-lookup"><span data-stu-id="4524d-454">Zipkin</span></span>](https://zipkin.io/)
- [<span data-ttu-id="4524d-455">Contexto de seguimiento W3C</span><span class="sxs-lookup"><span data-stu-id="4524d-455">W3C Trace Context</span></span>](https://www.w3.org/TR/trace-context/)
- [<span data-ttu-id="4524d-456">Jaeger</span><span class="sxs-lookup"><span data-stu-id="4524d-456">Jaeger</span></span>](https://www.jaegertracing.io/)
- [<span data-ttu-id="4524d-457">New Relic</span><span class="sxs-lookup"><span data-stu-id="4524d-457">New Relic</span></span>](https://newrelic.com/)
- [<span data-ttu-id="4524d-458">Prometheus</span><span class="sxs-lookup"><span data-stu-id="4524d-458">Prometheus</span></span>](https://prometheus.io/)
- [<span data-ttu-id="4524d-459">Grafana</span><span class="sxs-lookup"><span data-stu-id="4524d-459">Grafana</span></span>](https://grafana.com/grafana/)
- [<span data-ttu-id="4524d-460">Abrir el SDK de telemetría para .NET</span><span class="sxs-lookup"><span data-stu-id="4524d-460">Open Telemetry SDK for .NET</span></span>](https://opentelemetry.io/docs/net/)
- [<span data-ttu-id="4524d-461">Fluentd</span><span class="sxs-lookup"><span data-stu-id="4524d-461">Fluentd</span></span>](https://www.fluentd.org/)
- [<span data-ttu-id="4524d-462">Pila de ELK</span><span class="sxs-lookup"><span data-stu-id="4524d-462">ELK stack</span></span>](https://www.elastic.co/elastic-stack)
- [<span data-ttu-id="4524d-463">Próx</span><span class="sxs-lookup"><span data-stu-id="4524d-463">Seq</span></span>](https://datalust.co/seq)
- [<span data-ttu-id="4524d-464">Serilog</span><span class="sxs-lookup"><span data-stu-id="4524d-464">Serilog</span></span>](https://serilog.net/)

> [!div class="step-by-step"]
> <span data-ttu-id="4524d-465">[Anterior](bindings.md)
> [Siguiente](secrets.md)</span><span class="sxs-lookup"><span data-stu-id="4524d-465">[Previous](bindings.md)
[Next](secrets.md)</span></span>
