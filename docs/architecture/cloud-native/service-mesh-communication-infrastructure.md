---
title: Infraestructura de comunicación de la malla de servicio
description: Obtenga información sobre cómo las tecnologías de malla de servicio optimizan la comunicación de microservicios nativos de la nube
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 6b177ef33b804ec35f3acb919539a97683e5a487
ms.sourcegitcommit: 79b0dd8bfc63f33a02137121dd23475887ecefda
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "80523517"
---
# <a name="service-mesh-communication-infrastructure"></a>Infraestructura de comunicación de la malla de servicio

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

A lo largo de este capítulo, hemos explorado los desafíos de la comunicación de microservicios. Dijimos que los equipos de desarrollo deben ser sensibles a cómo los servicios back-end se comunican entre sí. Idealmente, cuanto menos comunicación entre servicios, mejor. Sin embargo, la evitación no siempre es posible, ya que los servicios back-end a menudo dependen unos de otros para completar las operaciones.

Exploramos diferentes enfoques para implementar la comunicación HTTP sincrónica y la mensajería asincrónica. En cada uno de los casos, el desarrollador se ve obligado a implementar código de comunicación. El código de comunicación es complejo y requiere mucho tiempo. Las decisiones incorrectas pueden dar lugar a problemas de rendimiento significativos.

Un enfoque más moderno de la comunicación de microservicios se centra en una tecnología nueva y en rápida evolución titulada *Service Mesh*. Una malla de [servicio](https://www.nginx.com/blog/what-is-a-service-mesh/) es una capa de infraestructura configurable con capacidades integradas para manejar la comunicación de servicio a servicio, la resistencia y muchas preocupaciones transversales. Mueve la responsabilidad de estas preocupaciones fuera de los microservicios y en la capa de malla de servicio. La comunicación se abstrae de los microservicios.

Un componente clave de una malla de servicio es un proxy. En una aplicación nativa de la nube, una instancia de un proxy normalmente se coloca con cada microservicio. Mientras se ejecutan en procesos independientes, los dos están estrechamente vinculados y comparten el mismo ciclo de vida. Este patrón, conocido como [el patrón Sidecar,](https://docs.microsoft.com/azure/architecture/patterns/sidecar)y se muestra en la Figura 4-24.

![Malla de servicio con un coche lateral](./media/service-mesh-with-side-car.png)

**Figura 4-24**. Malla de servicio con un coche lateral

Tenga en cuenta en la figura anterior cómo los mensajes son interceptados por un proxy que se ejecuta junto a cada microservicio. Cada proxy se puede configurar con reglas de tráfico específicas para el microservicio. Entiende los mensajes y puede enrutarlos a través de sus servicios y el mundo exterior.

Además de administrar la comunicación de servicio a servicio, Service Mesh proporciona compatibilidad para la detección de servicios y el equilibrio de carga.

Una vez configurada, una malla de servicio es altamente funcional. La malla recupera un grupo correspondiente de instancias de un punto de conexión de detección de servicios. Envía una solicitud a una instancia de servicio específica, registrando la latencia y el tipo de respuesta del resultado. Elige la instancia con más probabilidades de devolver una respuesta rápida en función de diferentes factores, incluida la latencia observada para las solicitudes recientes.

Una malla de servicio administra los problemas de tráfico, comunicación y redes en el nivel de aplicación. Entiende mensajes y solicitudes. Normalmente, una malla de servicio se integra con un orquestador de contenedores. Kubernetes admite una arquitectura extensible en la que se puede agregar una malla de servicio.

En el capítulo 6, profundizamos en las tecnologías de Service Mesh, incluida una discusión sobre su arquitectura y las implementaciones de código abierto disponibles.

## <a name="summary"></a>Resumen

En este capítulo, discutimos patrones de comunicación nativos de la nube. Comenzamos examinando cómo se comunican los clientes front-end con los microservicios back-end. En el camino, hablamos de plataformas de API Gateway y comunicación en tiempo real. A continuación, examinamos cómo los microservicios se comunican con otros servicios back-end. Examinamos tanto la comunicación HTTP sincrónica como la mensajería asincrónica entre servicios. Cubrimos gRPC, una tecnología próxima en el mundo nativo de la nube. Por último, introdujimos una nueva tecnología de rápida evolución titulada Service Mesh que puede agilizar la comunicación de microservicios.

Se hizo especial hincapié en los servicios de Azure administrados que pueden ayudar a implementar la comunicación en sistemas nativos de la nube:

- [Introducción a Puerta de enlace de aplicaciones](https://docs.microsoft.com/azure/application-gateway/overview)
- [Azure API Management](https://azure.microsoft.com/services/api-management/)
- [Servicio Azure SignalR](https://azure.microsoft.com/services/signalr-service/)
- [Colas de Azure Storage](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [Azure Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Centro de eventos de Azure](https://azure.microsoft.com/services/event-hubs/)

A continuación, pasamos a los datos distribuidos en sistemas nativos de la nube y los beneficios y desafíos que presenta.

### <a name="references"></a>Referencias

- [Microservicios de .NET: arquitectura para aplicaciones .NET en contenedores](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [Diseño de la comunicación entre servicios para microservicios](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [Azure SignalR Service, un servicio totalmente administrado para agregar funcionalidad en tiempo real](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [Controlador de entrada de Azure API Gateway](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [Acerca de Ingress en Azure Kubernetes Service (AKS)](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [Documentación gRPC](https://grpc.io/docs/guides/)

- [gRPC para desarrolladores de WCF](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [Comparación de los servicios gRPC con las API HTTP](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [Creación de servicios gRPC con vídeo .NET](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
>[Anterior](grpc.md)
>[Siguiente](Database-per-microservice.md)
