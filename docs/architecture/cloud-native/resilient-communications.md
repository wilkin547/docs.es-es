---
title: Comunicación resistente
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Comunicación resistente
ms.date: 06/30/2019
ms.openlocfilehash: 324f5426af1c892db73aa6fc2336a19b7a8e499e
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "73841226"
---
# <a name="resilient-communications"></a>Comunicaciones resistentes

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

A lo largo de este libro, hemos distribuido las ventajas de moverse más allá del diseño de aplicaciones monolíticas tradicional y de adoptar una arquitectura basada en microservicios donde un conjunto de servicios independientes distribuidos se ejecuten de forma independiente y se comuniquen con cada uno otros mediante protocolos de comunicación estándar como HTTP y HTTPS. Aunque este tipo de arquitectura le adquiere muchas ventajas importantes, también presenta muchos desafíos. Considere, por ejemplo, los siguientes aspectos:

- *Comunicación de red fuera de proceso.* Cada servicio se comunica a través de un protocolo de red que presenta la congestión de la red, la latencia y los errores transitorios.
- *Detección de servicios.* Con cada servicio que se ejecuta en un clúster de máquinas con su propia dirección IP y puerto, ¿cómo se detectan y se comunican entre sí los servicios?
- *Resistencia.* ¿Cómo se administran los errores de corta duración y se mantiene estable el sistema?
- *Equilibrio de carga.* ¿Cómo se distribuye el tráfico entrante entre varias instancias de un servicio?
- *Seguridad.* ¿Cómo se aplican los problemas de seguridad, como el cifrado de nivel de transporte y la administración de certificados?
- *Supervisión distribuida.* -¿Cómo se correlaciona y captura la rastreabilidad y la supervisión de una única solicitud entre varios servicios de consumo?

Aunque estos problemas se pueden solucionar con varias bibliotecas y marcos de trabajo, implementarlos dentro de su código base puede ser costoso, complejo y llevar mucho tiempo. Además, acaba con una solución en la que los problemas de infraestructura se acoplan a la lógica de negocios.

## <a name="service-mesh"></a>Malla de servicio

Un enfoque mejor es tener en cuenta una tecnología nueva y que evoluciona rápidamente titulada *malla de servicio*. Una [malla de servicio](https://www.nginx.com/blog/what-is-a-service-mesh/) es un nivel de infraestructura configurable con capacidades integradas para controlar la comunicación del servicio y muchos de los desafíos mencionados anteriormente. Desacopla estas preocupaciones del código empresarial y las mueve a un proxy de servicio, una instancia de que acompaña a cada uno de los servicios. A menudo conocido como el [patrón sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar), el proxy de la malla de servicio se implementa en un proceso independiente para proporcionar aislamiento y encapsulación del código de negocio. Sin embargo, el proxy está estrechamente vinculado al servicio que se crea junto con él y comparte su ciclo de vida. En la figura 6-9 se muestra este escenario.

![Malla de servicio con un coche lateral](./media/service-mesh-with-side-car.png)

**Figura 6-9**. Malla de servicio con un coche lateral

En la ilustración anterior, observe cómo el proxy intercepta y administra la comunicación entre los microservicios y el clúster.

Una malla de servicio se divide lógicamente en dos componentes dispares: un plano de [datos](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) y un [plano de control](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc). En la figura 6-10 se muestran estos componentes y sus responsabilidades.

![Control de malla de servicio y plano de datos](./media/istio-control-and-data-plane.png)

**Figura 6-10.** Control de malla de servicio y plano de datos

Una vez configurada, una malla de servicio es muy funcional. Puede recuperar un grupo correspondiente de instancias de un punto de conexión de detección de servicios. Después, puede enviar una solicitud a una instancia específica, registrando la latencia y el tipo de respuesta del resultado. Una malla puede elegir la instancia más probable de que devuelva una respuesta rápida en función de muchos factores, incluida la latencia observada para solicitudes recientes.

Si una instancia no responde o se produce un error, la malla puede reintentar la solicitud en otra instancia. Si un grupo devuelve los errores de forma coherente, una malla puede expulsarlo del grupo de equilibrio de carga para que se vuelva a intentar periódicamente después de la reparación. Si se agota el tiempo de espera de una solicitud, se puede producir un error en una malla y volver a intentar la solicitud. Una malla captura el comportamiento en forma de métricas y seguimiento distribuido, que luego se puede emitir en un sistema de métricas centralizado.

## <a name="istio-and-envoy"></a>Istio y envío

Aunque actualmente existen algunas opciones de malla de servicio, [istio](https://istio.io/docs/concepts/what-is-istio/) es el más popular en el momento de redactar este documento. Una empresa conjunta de IBM, Google y Lyft, es una oferta de código abierto que se puede integrar en una aplicación distribuida nueva o existente. Proporciona una solución coherente y completa para proteger, conectar y supervisar microservicios. Sus características incluyen:

- Protección de la comunicación de servicio a servicio en un clúster con autenticación y autorización seguras basadas en identidades.
- Equilibrio de carga automático para el tráfico HTTP, [gRPC](https://grpc.io/), WebSocket y TCP.
- Control específico del comportamiento del tráfico con reglas de enrutamiento enriquecidas, reintentos, conmutaciones por error e inserción de errores.
- Un nivel de directiva acoplable y una API de configuración que admiten los controles de acceso, los límites de velocidad y las cuotas.
- Métricas, registros y seguimientos automáticos para todo el tráfico dentro de un clúster, incluida la entrada y salida del clúster.

Un componente clave de una implementación de istio es un servicio de proxy titulado el [proxy de envío](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy). Como origen de Lyft y, posteriormente, se ha contribuido a la [base informática nativa](https://www.cncf.io/) de la nube (descrita en el capítulo 1), el proxy de envío se ejecuta junto a cada servicio y proporciona una base independiente de la plataforma para las siguientes características:

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

- [Instalación de istio en AKS](https://docs.microsoft.com/azure/aks/istio-install)
- [Usar AKS y istio](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

>[!div class="step-by-step"]
>[Anterior](infrastructure-resiliency-azure.md)
>[Siguiente](monitoring-health.md)
