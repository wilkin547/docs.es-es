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
# <a name="resilient-communications"></a>Comunicaciones resistentes

En este libro, hemos adoptado un enfoque arquitectónico basado en microservicios. Aunque este tipo de arquitectura proporciona ventajas importantes, presenta muchos desafíos:

- *Comunicación de red fuera de proceso.* Cada microservicio se comunica a través de un protocolo de red que presenta la congestión de la red, la latencia y los errores transitorios.

- *Detección de servicios.* ¿Cómo se detectan y se comunican entre sí los microservicios cuando se ejecutan en un clúster de máquinas con sus propias direcciones IP y puertos?

- *Resistencia.* ¿Cómo se administran los errores de corta duración y se mantiene estable el sistema?

- *Equilibrio de carga.* ¿Cómo se distribuye el tráfico entrante a través de varias instancias de un microservicio?

- *Seguridad.* ¿Cómo se aplican los problemas de seguridad, como el cifrado de nivel de transporte y la administración de certificados?

- *Supervisión distribuida.* -¿Cómo se correlaciona y captura la rastreabilidad y la supervisión de una única solicitud entre varios microservicios de consumo?

Puede resolver estos problemas con diferentes bibliotecas y marcos de trabajo, pero la implementación puede ser costosa, compleja y llevar mucho tiempo. También termina con los problemas de infraestructura asociados a la lógica de negocios.

## <a name="service-mesh"></a>Malla de servicio

Un enfoque mejor es una tecnología en evolución titulada *malla de servicio*. Una [malla de servicio](https://www.nginx.com/blog/what-is-a-service-mesh/) es un nivel de infraestructura configurable con capacidades integradas para controlar la comunicación del servicio y los otros desafíos mencionados anteriormente. Desacopla estos problemas moviéndolos a un proxy de servicio. El proxy se implementa en un proceso independiente (denominado [sidecar](/azure/architecture/patterns/sidecar)) para proporcionar aislamiento del código empresarial. Sin embargo, el sidecar está vinculado al servicio: se crea con él y comparte su ciclo de vida. En la figura 6-7 se muestra este escenario.

![Malla de servicio con un coche lateral](./media/service-mesh-with-side-car.png)

**Figura 6-7**. Malla de servicio con un coche lateral

En la ilustración anterior, observe cómo el proxy intercepta y administra la comunicación entre los microservicios y el clúster.

Una malla de servicio se divide lógicamente en dos componentes dispares: un plano de [datos](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) y un [plano de control](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). En la figura 6-8 se muestran estos componentes y sus responsabilidades.

![Control de malla de servicio y plano de datos](./media/istio-control-and-data-plane.png)

**Figura 6-8.** Control de malla de servicio y plano de datos

Una vez configurada, una malla de servicio es muy funcional. Puede recuperar un grupo correspondiente de instancias de un punto de conexión de detección de servicios. A continuación, la malla puede enviar una solicitud a una instancia específica, registrando la latencia y el tipo de respuesta del resultado. Una malla puede elegir la instancia más probable de que devuelva una respuesta rápida en función de muchos factores, incluida la latencia observada para solicitudes recientes.

Si una instancia no responde o se produce un error, la malla reintentará la solicitud en otra instancia. Si devuelve errores, una malla expulsará la instancia del grupo de equilibrio de carga y la volverá a cambiar después de que se haya recuperado. Si se agota el tiempo de espera de una solicitud, se puede producir un error en una malla y volver a intentar la solicitud. Una malla captura y emite métricas y seguimiento distribuido a un sistema de métricas centralizado.

## <a name="istio-and-envoy"></a>Istio y envío

Aunque actualmente existen algunas opciones de malla de servicio, [istio](https://istio.io/docs/concepts/what-is-istio/) es el más popular en el momento de redactar este documento. Istio es una empresa conjunta de IBM, Google y Lyft. Es una oferta de código abierto que se puede integrar en una aplicación distribuida nueva o existente. La tecnología proporciona una solución coherente y completa para proteger, conectar y supervisar microservicios. Sus características incluyen:

- Protección de la comunicación de servicio a servicio en un clúster con autenticación y autorización seguras basadas en identidades.
- Equilibrio de carga automático para el tráfico HTTP, [gRPC](https://grpc.io/), WebSocket y TCP.
- Control específico del comportamiento del tráfico con reglas de enrutamiento enriquecidas, reintentos, conmutaciones por error e inserción de errores.
- Un nivel de directiva acoplable y una API de configuración que admiten los controles de acceso, los límites de velocidad y las cuotas.
- Métricas, registros y seguimientos automáticos para todo el tráfico dentro de un clúster, incluida la entrada y salida del clúster.

Un componente clave de una implementación de istio es un servicio de proxy titulado el [proxy de envío](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy). Se ejecuta junto con cada servicio y proporciona una base independiente de la plataforma para las siguientes características:

- Detección dinámica de servicios.
- Equilibrio de carga.
- Terminación de TLS.
- Proxies HTTP y gRPC.
- Resistencia del disyuntor.
- Comprobaciones de estado.
- Actualizaciones graduales con implementaciones [Canarias](https://martinfowler.com/bliki/CanaryRelease.html) .

Como se explicó anteriormente, el envío se implementa como sidecar en cada microservicio del clúster.

## <a name="integration-with-azure-kubernetes-services"></a>Integración con Azure Kubernetes Services

La nube de Azure adopta istio y proporciona soporte técnico directo para ella en Azure Kubernetes Services. Los vínculos siguientes pueden ayudarle a empezar a trabajar:

- [Instalación de istio en AKS](/azure/aks/istio-install)
- [Usar AKS y istio](/azure/aks/istio-scenario-routing)

### <a name="references"></a>Referencias

- [Polly](http://www.thepollyproject.org/)

- [Patrón de reintento](/azure/architecture/patterns/retry)

- [Circuit Breaker pattern](/azure/architecture/patterns/circuit-breaker) (Patrón Circuit Breaker)

- [Notas del producto resistencia en Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [latencia de red](https://www.techopedia.com/definition/8553/network-latency)

- [Redundancia](/azure/architecture/guide/design-principles/redundancy)

- [replicación geográfica](/azure/sql-database/sql-database-active-geo-replication)

- [Azure Traffic Manager](/azure/traffic-manager/traffic-manager-overview)

- [Guía de escalado automático](/azure/architecture/best-practices/auto-scaling)

- [Istio](https://istio.io/docs/concepts/what-is-istio/)

- [Proxy de envío](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
>[Anterior](infrastructure-resiliency-azure.md)
>[Siguiente](monitoring-health.md)
