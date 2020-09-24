---
title: Comunicación resistente
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Comunicación resistente
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 18b26223634efc5c05f680d0cbb7c8cbc2490a59
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166045"
---
# <a name="resilient-communications"></a><span data-ttu-id="4d1ba-103">Comunicaciones resistentes</span><span class="sxs-lookup"><span data-stu-id="4d1ba-103">Resilient communications</span></span>

<span data-ttu-id="4d1ba-104">En este libro, hemos adoptado un enfoque arquitectónico basado en microservicios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-104">Throughout this book, we've embraced a microservice-based architectural approach.</span></span> <span data-ttu-id="4d1ba-105">Aunque este tipo de arquitectura proporciona ventajas importantes, presenta muchos desafíos:</span><span class="sxs-lookup"><span data-stu-id="4d1ba-105">While such an architecture provides important benefits, it presents many challenges:</span></span>

- <span data-ttu-id="4d1ba-106">*Comunicación de red fuera de proceso.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-106">*Out-of-process network communication.*</span></span> <span data-ttu-id="4d1ba-107">Cada microservicio se comunica a través de un protocolo de red que presenta la congestión de la red, la latencia y los errores transitorios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-107">Each microservice communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>

- <span data-ttu-id="4d1ba-108">*Detección de servicios.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-108">*Service discovery.*</span></span> <span data-ttu-id="4d1ba-109">¿Cómo se detectan y se comunican entre sí los microservicios cuando se ejecutan en un clúster de máquinas con sus propias direcciones IP y puertos?</span><span class="sxs-lookup"><span data-stu-id="4d1ba-109">How do microservices discover and communicate with each other when running across a cluster of machines with their own IP addresses and ports?</span></span>

- <span data-ttu-id="4d1ba-110">*Resistencia.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-110">*Resiliency.*</span></span> <span data-ttu-id="4d1ba-111">¿Cómo se administran los errores de corta duración y se mantiene estable el sistema?</span><span class="sxs-lookup"><span data-stu-id="4d1ba-111">How do you manage short-lived failures and keep the system stable?</span></span>

- <span data-ttu-id="4d1ba-112">*Equilibrio de carga.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-112">*Load balancing.*</span></span> <span data-ttu-id="4d1ba-113">¿Cómo se distribuye el tráfico entrante a través de varias instancias de un microservicio?</span><span class="sxs-lookup"><span data-stu-id="4d1ba-113">How does inbound traffic get distributed across multiple instances of a microservice?</span></span>

- <span data-ttu-id="4d1ba-114">*Seguridad.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-114">*Security.*</span></span> <span data-ttu-id="4d1ba-115">¿Cómo se aplican los problemas de seguridad, como el cifrado de nivel de transporte y la administración de certificados?</span><span class="sxs-lookup"><span data-stu-id="4d1ba-115">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>

- <span data-ttu-id="4d1ba-116">*Supervisión distribuida.*</span><span class="sxs-lookup"><span data-stu-id="4d1ba-116">*Distributed Monitoring.*</span></span> <span data-ttu-id="4d1ba-117">-¿Cómo se correlaciona y captura la rastreabilidad y la supervisión de una única solicitud entre varios microservicios de consumo?</span><span class="sxs-lookup"><span data-stu-id="4d1ba-117">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming microservices?</span></span>

<span data-ttu-id="4d1ba-118">Puede resolver estos problemas con diferentes bibliotecas y marcos de trabajo, pero la implementación puede ser costosa, compleja y llevar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-118">You can address these concerns with different libraries and frameworks, but the implementation can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="4d1ba-119">También termina con los problemas de infraestructura asociados a la lógica de negocios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-119">You also end up with infrastructure concerns coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="4d1ba-120">Malla de servicio</span><span class="sxs-lookup"><span data-stu-id="4d1ba-120">Service mesh</span></span>

<span data-ttu-id="4d1ba-121">Un enfoque mejor es una tecnología en evolución titulada *malla de servicio*.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-121">A better approach is an evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="4d1ba-122">Una [malla de servicio](https://www.nginx.com/blog/what-is-a-service-mesh/) es un nivel de infraestructura configurable con capacidades integradas para controlar la comunicación del servicio y los otros desafíos mencionados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-122">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and the other challenges mentioned above.</span></span> <span data-ttu-id="4d1ba-123">Desacopla estos problemas moviéndolos a un proxy de servicio.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-123">It decouples these concerns by moving them into a service proxy.</span></span> <span data-ttu-id="4d1ba-124">El proxy se implementa en un proceso independiente (denominado [sidecar](/azure/architecture/patterns/sidecar)) para proporcionar aislamiento del código empresarial.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-124">The proxy is deployed into a separate process (called a [sidecar](/azure/architecture/patterns/sidecar)) to provide isolation from business code.</span></span> <span data-ttu-id="4d1ba-125">Sin embargo, el sidecar está vinculado al servicio: se crea con él y comparte su ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-125">However, the sidecar is linked to the service - it's created with it and shares its lifecycle.</span></span> <span data-ttu-id="4d1ba-126">En la figura 6-7 se muestra este escenario.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-126">Figure 6-7 shows this scenario.</span></span>

![Malla de servicio con un coche lateral](./media/service-mesh-with-side-car.png)

<span data-ttu-id="4d1ba-128">**Figura 6-7**.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-128">**Figure 6-7**.</span></span> <span data-ttu-id="4d1ba-129">Malla de servicio con un coche lateral</span><span class="sxs-lookup"><span data-stu-id="4d1ba-129">Service mesh with a side car</span></span>

<span data-ttu-id="4d1ba-130">En la ilustración anterior, observe cómo el proxy intercepta y administra la comunicación entre los microservicios y el clúster.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-130">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="4d1ba-131">Una malla de servicio se divide lógicamente en dos componentes dispares: un plano de [datos](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) y un [plano de control](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span><span class="sxs-lookup"><span data-stu-id="4d1ba-131">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="4d1ba-132">En la figura 6-8 se muestran estos componentes y sus responsabilidades.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-132">Figure 6-8 shows these components and their responsibilities.</span></span>

![Control de malla de servicio y plano de datos](./media/istio-control-and-data-plane.png)

<span data-ttu-id="4d1ba-134">**Figura 6-8.**</span><span class="sxs-lookup"><span data-stu-id="4d1ba-134">**Figure 6-8.**</span></span> <span data-ttu-id="4d1ba-135">Control de malla de servicio y plano de datos</span><span class="sxs-lookup"><span data-stu-id="4d1ba-135">Service mesh control and data plane</span></span>

<span data-ttu-id="4d1ba-136">Una vez configurada, una malla de servicio es muy funcional.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-136">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="4d1ba-137">Puede recuperar un grupo correspondiente de instancias de un punto de conexión de detección de servicios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-137">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="4d1ba-138">A continuación, la malla puede enviar una solicitud a una instancia específica, registrando la latencia y el tipo de respuesta del resultado.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-138">The mesh can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="4d1ba-139">Una malla puede elegir la instancia más probable de que devuelva una respuesta rápida en función de muchos factores, incluida la latencia observada para solicitudes recientes.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-139">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="4d1ba-140">Si una instancia no responde o se produce un error, la malla reintentará la solicitud en otra instancia.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-140">If an instance is unresponsive or fails, the mesh will retry the request on another instance.</span></span> <span data-ttu-id="4d1ba-141">Si devuelve errores, una malla expulsará la instancia del grupo de equilibrio de carga y la volverá a cambiar después de que se haya recuperado.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-141">If it returns errors, a mesh will evict the instance from the load-balancing pool and restate it after it heals.</span></span> <span data-ttu-id="4d1ba-142">Si se agota el tiempo de espera de una solicitud, se puede producir un error en una malla y volver a intentar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-142">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="4d1ba-143">Una malla captura y emite métricas y seguimiento distribuido a un sistema de métricas centralizado.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-143">A mesh captures and emits metrics and distributed tracing to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="4d1ba-144">Istio y envío</span><span class="sxs-lookup"><span data-stu-id="4d1ba-144">Istio and Envoy</span></span>

<span data-ttu-id="4d1ba-145">Aunque actualmente existen algunas opciones de malla de servicio, [istio](https://istio.io/docs/concepts/what-is-istio/) es el más popular en el momento de redactar este documento.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-145">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular at the time of this writing.</span></span> <span data-ttu-id="4d1ba-146">Istio es una empresa conjunta de IBM, Google y Lyft.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-146">Istio is a joint venture from IBM, Google, and Lyft.</span></span> <span data-ttu-id="4d1ba-147">Es una oferta de código abierto que se puede integrar en una aplicación distribuida nueva o existente.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-147">It's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="4d1ba-148">La tecnología proporciona una solución coherente y completa para proteger, conectar y supervisar microservicios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-148">The technology provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="4d1ba-149">Sus características incluyen:</span><span class="sxs-lookup"><span data-stu-id="4d1ba-149">Its features include:</span></span>

- <span data-ttu-id="4d1ba-150">Protección de la comunicación de servicio a servicio en un clúster con autenticación y autorización seguras basadas en identidades.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="4d1ba-151">Equilibrio de carga automático para el tráfico HTTP, [gRPC](https://grpc.io/), WebSocket y TCP.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="4d1ba-152">Control específico del comportamiento del tráfico con reglas de enrutamiento enriquecidas, reintentos, conmutaciones por error e inserción de errores.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="4d1ba-153">Un nivel de directiva acoplable y una API de configuración que admiten los controles de acceso, los límites de velocidad y las cuotas.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="4d1ba-154">Métricas, registros y seguimientos automáticos para todo el tráfico dentro de un clúster, incluida la entrada y salida del clúster.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="4d1ba-155">Un componente clave de una implementación de istio es un servicio de proxy titulado el [proxy de envío](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span><span class="sxs-lookup"><span data-stu-id="4d1ba-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="4d1ba-156">Se ejecuta junto con cada servicio y proporciona una base independiente de la plataforma para las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="4d1ba-156">It runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="4d1ba-157">Detección dinámica de servicios.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="4d1ba-158">Equilibrio de carga.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-158">Load balancing.</span></span>
- <span data-ttu-id="4d1ba-159">Terminación de TLS.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-159">TLS termination.</span></span>
- <span data-ttu-id="4d1ba-160">Proxies HTTP y gRPC.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="4d1ba-161">Resistencia del disyuntor.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="4d1ba-162">Comprobaciones de estado.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-162">Health checks.</span></span>
- <span data-ttu-id="4d1ba-163">Actualizaciones graduales con implementaciones [Canarias](https://martinfowler.com/bliki/CanaryRelease.html) .</span><span class="sxs-lookup"><span data-stu-id="4d1ba-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="4d1ba-164">Como se explicó anteriormente, el envío se implementa como sidecar en cada microservicio del clúster.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="4d1ba-165">Integración con Azure Kubernetes Services</span><span class="sxs-lookup"><span data-stu-id="4d1ba-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="4d1ba-166">La nube de Azure adopta istio y proporciona soporte técnico directo para ella en Azure Kubernetes Services.</span><span class="sxs-lookup"><span data-stu-id="4d1ba-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="4d1ba-167">Los vínculos siguientes pueden ayudarle a empezar a trabajar:</span><span class="sxs-lookup"><span data-stu-id="4d1ba-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="4d1ba-168">Instalación de istio en AKS</span><span class="sxs-lookup"><span data-stu-id="4d1ba-168">Installing Istio in AKS</span></span>](/azure/aks/istio-install)
- [<span data-ttu-id="4d1ba-169">Usar AKS y istio</span><span class="sxs-lookup"><span data-stu-id="4d1ba-169">Using AKS and Istio</span></span>](/azure/aks/istio-scenario-routing)

### <a name="references"></a><span data-ttu-id="4d1ba-170">Referencias</span><span class="sxs-lookup"><span data-stu-id="4d1ba-170">References</span></span>

- [<span data-ttu-id="4d1ba-171">Polly</span><span class="sxs-lookup"><span data-stu-id="4d1ba-171">Polly</span></span>](http://www.thepollyproject.org/)

- [<span data-ttu-id="4d1ba-172">Patrón de reintento</span><span class="sxs-lookup"><span data-stu-id="4d1ba-172">Retry pattern</span></span>](/azure/architecture/patterns/retry)

- <span data-ttu-id="4d1ba-173">[Circuit Breaker pattern](/azure/architecture/patterns/circuit-breaker) (Patrón Circuit Breaker)</span><span class="sxs-lookup"><span data-stu-id="4d1ba-173">[Circuit Breaker pattern](/azure/architecture/patterns/circuit-breaker)</span></span>

- [<span data-ttu-id="4d1ba-174">Notas del producto resistencia en Azure</span><span class="sxs-lookup"><span data-stu-id="4d1ba-174">Resilience in Azure whitepaper</span></span>](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [<span data-ttu-id="4d1ba-175">latencia de red</span><span class="sxs-lookup"><span data-stu-id="4d1ba-175">network latency</span></span>](https://www.techopedia.com/definition/8553/network-latency)

- [<span data-ttu-id="4d1ba-176">Redundancia</span><span class="sxs-lookup"><span data-stu-id="4d1ba-176">Redundancy</span></span>](/azure/architecture/guide/design-principles/redundancy)

- [<span data-ttu-id="4d1ba-177">replicación geográfica</span><span class="sxs-lookup"><span data-stu-id="4d1ba-177">geo-replication</span></span>](/azure/sql-database/sql-database-active-geo-replication)

- [<span data-ttu-id="4d1ba-178">Azure Traffic Manager</span><span class="sxs-lookup"><span data-stu-id="4d1ba-178">Azure Traffic Manager</span></span>](/azure/traffic-manager/traffic-manager-overview)

- [<span data-ttu-id="4d1ba-179">Guía de escalado automático</span><span class="sxs-lookup"><span data-stu-id="4d1ba-179">Autoscaling guidance</span></span>](/azure/architecture/best-practices/auto-scaling)

- [<span data-ttu-id="4d1ba-180">Istio</span><span class="sxs-lookup"><span data-stu-id="4d1ba-180">Istio</span></span>](https://istio.io/docs/concepts/what-is-istio/)

- [<span data-ttu-id="4d1ba-181">Proxy de envío</span><span class="sxs-lookup"><span data-stu-id="4d1ba-181">Envoy proxy</span></span>](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
><span data-ttu-id="4d1ba-182">[Anterior](infrastructure-resiliency-azure.md)
>[Siguiente](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="4d1ba-182">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>
