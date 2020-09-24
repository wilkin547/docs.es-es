---
title: Infraestructura de comunicación de la malla de servicio
description: Más información sobre cómo las tecnologías de la malla de servicio simplifican la comunicación de microservicios nativa en la nube
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 39dc1ded06eb0b92a2a1b40cfe981d9bd49bf381
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91165954"
---
# <a name="service-mesh-communication-infrastructure"></a>Infraestructura de comunicación de la malla de servicio

En este capítulo, hemos explorado los desafíos de la comunicación de microservicios. Dijimos que los equipos de desarrollo deben ser sensibles a la manera en que los servicios back-end se comunican entre sí. Idealmente, la menor comunicación entre servicios, mejor. Sin embargo, la prevención no siempre es posible, ya que los servicios back-end se basan a menudo en otro para completar las operaciones.

Hemos explorado distintos enfoques para implementar la comunicación HTTP sincrónica y la mensajería asincrónica. En cada uno de los casos, el desarrollador se sobrecarga con la implementación del código de comunicación. El código de comunicación es complejo y requiere mucho tiempo. Las decisiones incorrectas pueden dar lugar a problemas de rendimiento importantes.

Un enfoque más moderno para centros de comunicación de microservicios en torno a una tecnología nueva y que evoluciona rápidamente titulada *malla de servicio*. Una [malla de servicio](https://www.nginx.com/blog/what-is-a-service-mesh/) es una capa de infraestructura configurable con capacidades integradas para administrar la comunicación entre servicios, la resistencia y muchas cuestiones transversales. Traslada la responsabilidad de estas cuestiones fuera de los microservicios y a la capa de malla de servicio. La comunicación se abstrae de los microservicios.

Un componente clave de una malla de servicio es un proxy. En una aplicación nativa en la nube, una instancia de un proxy suele colocalizarse con cada microservicio. Mientras se ejecutan en procesos independientes, los dos están estrechamente vinculados y comparten el mismo ciclo de vida. Este patrón, conocido como el [patrón sidecar](/azure/architecture/patterns/sidecar), se muestra en la figura 4-24.

![Malla de servicio con un coche lateral](./media/service-mesh-with-side-car.png)

**Figura 4-24**. Malla de servicio con un coche lateral

Observe en la figura anterior cómo interceptan los mensajes un proxy que se ejecuta junto con cada microservicio. Cada proxy se puede configurar con reglas de tráfico específicas del microservicio. Comprende los mensajes y los puede enrutar a través de los servicios y del mundo exterior.

Junto con la administración de la comunicación de servicio a servicio, la malla de servicio proporciona compatibilidad para la detección de servicios y el equilibrio de carga.

Una vez configurada, una malla de servicio es muy funcional. La malla recupera un grupo de instancias correspondiente de un punto de conexión de detección de servicios. Envía una solicitud a una instancia de servicio específica, registrando la latencia y el tipo de respuesta del resultado. Elige la instancia más probable de que devuelva una respuesta rápida basada en diferentes factores, incluida la latencia observada para las solicitudes recientes.

Una malla de servicio administra el tráfico, la comunicación y los problemas de red en el nivel de aplicación. Comprende mensajes y solicitudes. Una malla de servicio normalmente se integra con un orquestador de contenedores. Kubernetes admite una arquitectura extensible en la que se puede Agregar una malla de servicio.

En el capítulo 6, profundizaremos en las tecnologías de la malla de servicio, incluida una explicación sobre su arquitectura y las implementaciones de código abierto disponibles.

## <a name="summary"></a>Resumen

En este capítulo, analizamos patrones de comunicación nativos de la nube. Comenzamos examinando cómo se comunican los clientes front-end con los microservicios de back-end. A lo largo del proceso, hablamos sobre las plataformas de puerta de enlace de API y la comunicación en tiempo real. A continuación, veremos cómo se comunican los microservicios con otros servicios de back-end. Analizamos la comunicación HTTP sincrónica y la mensajería asincrónica a través de los servicios. Hemos tratado gRPC, una próxima tecnología en el mundo de la nube nativa. Por último, se presentó una nueva tecnología de la malla de servicio con un nuevo y rápido desarrollo que puede agilizar la comunicación con microservicios.

Especial énfasis en los servicios de Azure administrados que pueden ayudar a implementar la comunicación en los sistemas nativos de la nube:

- [Introducción a Puerta de enlace de aplicaciones](/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Servicio Azure SignalR](https://azure.microsoft.com/services/signalr-service/)
- [Colas de Azure Storage](/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](/azure/event-grid/overview)
- [Centro de eventos de Azure](https://azure.microsoft.com/services/event-hubs/)

A continuación, nos trasladamos a los datos distribuidos en los sistemas nativos de la nube y a las ventajas y los desafíos que presenta.

### <a name="references"></a>Referencias

- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedor](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Diseño de la comunicación entre servicios para microservicios](/azure/architecture/microservices/design/interservice-communication)

- [Azure Signalr Service, un servicio totalmente administrado para agregar funcionalidad en tiempo real](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Controlador de entrada de puerta de enlace de API de Azure](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Acerca de la entrada en Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [Documentación de gRPC](https://grpc.io/docs/guides/)

- [gRPC para desarrolladores de WCF](../grpc-for-wcf-developers/index.md)

- [Comparación de los servicios de gRPC con las API de HTTP](/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [Creación de servicios de gRPC con vídeo de .NET](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[Anterior](grpc.md)
>[Siguiente](distributed-data.md)
