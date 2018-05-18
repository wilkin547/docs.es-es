---
title: Uso de Azure Service Fabric
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Uso de Azure Service Fabric
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.openlocfilehash: d65968e3d37f53cceee55120110ad4bb3c13d304
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="using-azure-service-fabric"></a>Uso de Azure Service Fabric

Azure Service Fabric surgió de la transición que Microsoft realizó al dejar de ofrecer productos empaquetados, que normalmente tenían un estilo monolítico, para ofrecer servicios. La experiencia de crear y usar servicios de gran tamaño a escala, como Azure SQL Database, Azure Cosmos DB, Azure Service Bus o Backend de Cortana, definió el formato de Service Fabric. La plataforma evolucionó con el tiempo, a medida que la adoptaron cada vez más servicios. Cabe destacar que Service Fabric tuvo que ejecutarse no solo en Azure sino también en implementaciones independientes de Windows Server.

El objetivo de Service Fabric es solucionar los arduos problemas de compilar y ejecutar un servicio y usar recursos de infraestructura de forma eficaz, de manera que los equipos puedan resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarlo a crear aplicaciones que usan un enfoque de microservicios:

-   Una plataforma que proporciona servicios de sistema para implementar, escalar, actualizar, detectar y reiniciar servicios erróneos, detectar la ubicación del servicio, administrar el estado y supervisar el mantenimiento. Estos servicios de sistema efectivamente habilitan muchas de las características de microservicios descritas anteriormente.

-   Programar API, o marcos, para ayudarlo a crear aplicaciones como microservicios: [actores fiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Por supuesto, puede elegir cualquier código para generar el microservicio, pero estas API facilitan el trabajo y se integran con la plataforma a un nivel más profundo. De este modo, puede obtener información de mantenimiento y diagnóstico o puede sacar partido de la administración de estado confiable.

Para crear su servicio puede usar cualquier tecnología ya que Service Fabric no interviene en el proceso. Sin embargo, proporciona API de programación integradas que facilitan la creación de microservicios.

Como se muestra en la figura 4-26, puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basados en contenedores con microservicios basados en procesos en el mismo clúster de Service Fabric.

![](./media/image30.png)

**Figura 4-26**. Implementar microservicios como procesos o como contenedores en Azure Service Fabric

Los clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows, respectivamente.

Para más información actualizada sobre la compatibilidad con contenedores en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma en que puede definir una arquitectura lógica diferente (microservicios empresariales o contextos limitados) de la implementación física que se describió en la sección [Arquitectura lógica frente a arquitectura física](#logical-architecture-versus-physical-architecture). Por ejemplo, si implementa en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview) los [Servicios de confianza con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) que se describen más adelante en la sección [Microservicios sin estado frente a microservicios con estado](#stateless-versus-stateful-microservices), puede tener un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-27, y bajo una perspectiva de microservicio lógico/empresarial, al implementar un servicio de confianza con estado de Service Fabric, normalmente deberá implementar dos niveles de servicios. El primero es el servicio de confianza con estado back-end, que administra varias particiones (cada partición es un servicio con estado). El segundo es el servicio front-end, o servicio de puerta de enlace, que se encarga del enrutamiento y de la agregación de datos en varias particiones o instancias de servicio con estado. Este servicio de puerta de enlace también controla la comunicación del lado cliente con los bucles de reintento que acceden al servicio back-end.
Se denomina servicio de puerta de enlace si implementa el servicio personalizado, pero alternativamente también puede usar el [servicio de proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) estándar de Service Fabric.

![](./media/image31.png)

**Figura 4-27**. Microservicio de negocio con varias instancias de servicio con estado y un front-end con puerta de enlace personalizado

En cualquier caso, al usar servicios de confianza con estado de Service Fabric, también dispone de un microservicio lógico o empresarial (contexto limitado) que normalmente se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de partición, podría implementarse como servicios de ASP.NET Web API, como se muestra en la figura 4-26.

En Service Fabric, puede agrupar e implementar grupos de servicios como una [aplicación de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el orquestador o clúster. Por tanto, la aplicación de Service Fabric también podría asignarse a este límite de microservicio o contexto limitado lógico y empresarial autónomo, por lo que podría implementar estos servicios de forma autónoma.

## <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores de Service Fabric, también puede implementar servicios en las imágenes de contenedor dentro de un clúster de Service Fabric. Como se muestra en la figura 4-28, la mayoría de las veces solo habrá un contenedor por cada servicio.

![](./media/image32.png)

**Figura 4-28**. Microservicio empresarial con varios servicios (contenedores) en Service Fabric

Sin embargo, los contenedores llamados "asociados" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógico) también son posibles en Service Fabric. Lo importante es que un microservicio empresarial sea el límite lógico alrededor de varios elementos cohesivos. En muchos casos, puede que sea un único servicio con un solo modelo de datos, pero en otros casos también es posible que tenga varios servicios físicos.

A partir de mediados de 2017, en Service Fabric no se pueden implementar servicios con estado de confianza de SF en contenedores, solo se pueden implementar servicios sin estado y servicios de actor en contenedores. Pero tenga en cuenta que se pueden combinar servicios en procesos y servicios en contenedores en la misma aplicación de Service Fabric, tal como se muestra en la figura 4-29.

![](./media/image33.png)

**Figura 4-29**. Microservicio empresarial asignado a una aplicación de Service Fabric con contenedores y servicios con estado

Para más información sobre la compatibilidad de contenedor en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Microservicios sin estado frente a microservicios con estado

Como se ha mencionado anteriormente, cada microservicio (contexto limitado lógico) debe tener su modelo de dominio (datos y lógica). En el caso de los microservicios sin estado, las bases de datos serán externas y se usarán opciones relacionales, como SQL Server, u opciones de NoSQL, como MongoDB o Azure Cosmos DB.

Pero los propios servicios también pueden ser con estado en Service Fabric, lo que significa que los datos se encuentran en el microservicio. Estos datos pueden existir no solo en el mismo servidor, sino dentro del proceso del microservicio, en memoria, conservados en discos duros y replicados en otros nodos. En la figura 4-30 se muestran los distintos enfoques.

![](./media/image34.png)

**Figura 4-30**. Microservicios sin estado frente a microservicios con estado

Un enfoque sin estado es perfectamente válido y es más fácil de implementar que los microservicios con estado, ya que el enfoque es similar a los patrones tradicionales y conocidos. Pero los microservicios sin estado imponen latencia entre el proceso y los orígenes de datos. También implican más piezas móviles cuando se intenta mejorar el rendimiento con memoria caché y colas adicionales. El resultado es que puede acabar con arquitecturas complejas que tienen demasiados niveles.

Por el contrario, los [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) pueden destacar en escenarios avanzados, ya que no hay latencia entre los datos y la lógica del dominio. El procesamiento intenso de datos, los back-ends de juegos, las bases de datos como servicio y otros escenarios con baja latencia se benefician de los servicios con estado, que habilitan el estado local para un acceso más rápido.

Los servicios sin estado y los servicios con estado se complementan. Por ejemplo, puede ver en la figura 4-30, en el diagrama de la derecha, que un servicio con estado se puede dividir en varias particiones. Para acceder a esas particiones, es posible que deba contar con un servicio sin estado que actúe como un servicio de puerta de enlace que sepa cómo dirigirse a cada partición en función de las claves de partición.

Los servicios con estado tienen diversos inconvenientes. Imponen un nivel de complejidad que permite escalar horizontalmente. Las funciones que normalmente se implementarían mediante sistemas de bases de datos externas se debe abordar en tareas como la replicación de datos a través de microservicios con estado y la creación de particiones de datos. Sin embargo, esta es una de las áreas en que un orquestador como [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con sus [servicios de confianza con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar al máximo, ya que simplifica el desarrollo y el ciclo de vida de los microservicios con estado mediante la [API de Reliable Services](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten los servicios con estado, que admiten el patrón de actor y que mejoran la tolerancia a errores y la latencia entre la lógica y los datos empresariales son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research, y [ Akka.NET](https://getakka.net/). Actualmente, ambos marcos están mejorando su compatibilidad con Docker.

Tenga en cuenta que los contenedores de Docker son sin estado. Si quiere implementar un servicio con estado, debe contar con uno de los marcos prescriptivos y de nivel superior adicionales que se han indicado anteriormente. 

>[!div class="step-by-step"]
[Previous] (scalable-available-multi-container-microservice-applications.md) [Next] (../docker-application-development-process/index.md)
