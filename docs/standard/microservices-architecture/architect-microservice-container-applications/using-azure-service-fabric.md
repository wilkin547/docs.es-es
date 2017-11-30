---
title: Uso de Azure Service Fabric.
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Uso de Azure Service Fabric.
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: aa15f9cf9bc60e9e70607da921f2ce2c75e39ec2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="using-azure-service-fabric"></a>Uso de Azure Service Fabric.

Azure Service Fabric procedan de transición de Microsoft de entrega de productos de cuadro, que son normalmente monolíticos en estilo, en la entrega de servicios. La experiencia de creación y utilización de servicios de gran tamaño a escala, como la base de datos de SQL Azure, base de datos de Azure Cosmos, Service Bus de Azure o back-end de Cortana, en forma de Service Fabric. La plataforma evolucionado con el tiempo, tal y como se hayan adoptado servicios cada vez más. Lo que es importante, Service Fabric deberían ejecutado no solo en Azure, sino también en las implementaciones de Windows Server independiente.

El objetivo de Service Fabric es solucionar los problemas de disco duros de compilar y ejecutar un servicio y la utilización de recursos de infraestructura de forma eficaz, para que los equipos pueden resolver problemas empresariales con un enfoque de microservicios.

Service Fabric proporciona dos áreas generales para ayudarle a crear aplicaciones que utilizan un enfoque de microservicios:

-   Una plataforma que proporciona servicios del sistema para implementar, escalar, actualizar, detectar y reiniciar servicios fallidos, detectar la ubicación del servicio, administrar el estado y supervisar el estado. Estos servicios del sistema en vigor permiten muchas de las características de microservicios que se ha descrito anteriormente.

-   API de programación, o marcos de trabajo, para ayudarle a crear aplicaciones como microservicios: [actores confiables y servicios de confianza](https://docs.microsoft.com/azure/service-fabric/service-fabric-choose-framework). Por supuesto, puede elegir cualquier código para generar el microservicio, pero estas API hacen más sencillo que el trabajo y que se integran con la plataforma en un nivel más profundo. Este modo puede obtener el estado y la información de diagnóstico o puede sacar partido de administración de estado confiable.

Service Fabric es independiente con respecto a cómo compilar su servicio, y puede usar cualquier tecnología. Sin embargo, proporciona API de programación integradas que facilitan la compilación microservicios.

Como se muestra en la figura 4-26, puede crear y ejecutar microservicios en Service Fabric como procesos simples o como contenedores de Docker. También es posible mezclar microservicios basado en el contenedor con microservicios basada en procesos en el mismo clúster de Service Fabric.

![](./media/image30.png)

**Figura 4-26**. Implementar microservicios como procesos o como contenedores en Azure Service Fabric

Clústeres de Service Fabric basados en hosts de Linux y Windows pueden ejecutar contenedores de Docker Linux y Windows, respectivamente.

Para obtener información actualizada sobre la compatibilidad con contenedores en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

Service Fabric es un buen ejemplo de una plataforma, donde puede definir una arquitectura lógica diferente (microservicios de negocios o contextos limitado) de la implementación física que se introdujeron en la [arquitectura lógica y física arquitectura](#logical-architecture-versus-physical-architecture) sección. Por ejemplo, si implementa [Reliable Services con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction) en [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview), que se introducen en la sección [Stateless frente a microservicios con estado](#stateless-versus-stateful-microservices) más adelante, puede tener un concepto de microservicio empresarial con varios servicios físicos.

Como se muestra en la figura 4-27 y pensar desde una perspectiva de lógica de negocios/microservicio, al implementar un servicio confiable de servicio de Fabric con estado, normalmente debe implementar dos niveles de servicios. El primero es el servicio back-end con estado confiable, que administra varias particiones (cada partición es un servicio con estado). El segundo es el servicio front-end, o el servicio de puerta de enlace, a cargo de la agregación de enrutamiento y los datos en varias particiones o instancias de servicio con estado. Ese servicio de puerta de enlace también controla la comunicación de cliente con bucles vuelva a intentar obtener acceso al servicio back-end.
Se invoca un servicio de puerta de enlace si se implementa el servicio personalizado o alternatevely también puede usar el cuadro Service Fabric [servicio de Proxy inverso](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy).

![](./media/image31.png)

**Figura 4-27**. Microservicio de negocio con varias instancias de servicio con estado y una puerta de enlace personalizado front-end

En cualquier caso, cuando se usa servicios de Service Fabric Stateful confiable, también tiene un microservicio lógica o de empresa (contexto limitado) que normalmente se compone de varios servicios físicos. Cada uno de ellos, el servicio de puerta de enlace y el servicio de la partición podría implementarse como servicios de ASP.NET Web API, como se muestra en la figura 4-26.

En el tejido de servicio, puede agrupar e implementar grupos de servicios como un [aplicación de servicio de Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-application-model), que es la unidad de empaquetado e implementación para el clúster o de orchestrator. Por lo tanto, la aplicación de servicio de Fabric podría asignarse a este independientes y límite de microservicio lógico o contexto limitado, así, por lo que puede implementar estos servicios de forma autónoma.

## <a name="service-fabric-and-containers"></a>Service Fabric y contenedores

Con respecto a los contenedores de Service Fabric, también puede implementar servicios en las imágenes de contenedor dentro de un clúster de Service Fabric. Como se muestra en la figura 4-28, la mayoría de las veces sólo habrá un contenedor por cada servicio.

![](./media/image32.png)

**Figura 4-28**. Microservicio de negocios con varios servicios (contenedores) en Service Fabric

Sin embargo, los contenedores llamados "asociado" (dos contenedores que deben implementarse conjuntamente como parte de un servicio lógicos) también son posibles en Service Fabric. Lo importante es que un microservicio de negocios es el límite lógico alrededor de varios elementos coherente. En muchos casos, puede que sea un único servicio con un único modelo de datos, pero en otros casos es posible que tenga varios físicos también servicios.

A partir de mediados de 2017, en Service Fabric no se puede implementar servicios con estado confiables de SF en contenedores, solo se pueden implementar servicios sin estado y los servicios de actor en contenedores. Pero tenga en cuenta que se pueden mezclar servicios de procesos y servicios en contenedores en la misma aplicación de Service Fabric, tal como se muestra en la figura 4-29.

![](./media/image33.png)

**Figura 4-29**. Microservicio empresarial asignado a una aplicación de Service Fabric con contenedores y servicios con estado

Para obtener más información sobre la compatibilidad de contenedor en Azure Service Fabric, vea [Service Fabric y contenedores](https://docs.microsoft.com/azure/service-fabric/service-fabric-containers-overview).

## <a name="stateless-versus-stateful-microservices"></a>Sin estado frente a microservicios con estado

Como se mencionó anteriormente, cada microservicio (contexto de limitado lógica) debe poseer su modelo de dominio (datos y lógica). En el caso de microservicios sin estado, las bases de datos será externos, que emplean opciones relacional como SQL Server u opciones de NoSQL como MongoDB o base de datos de Azure Cosmos.

Pero los propios servicios también pueden ser con estado en Service Fabric, lo que significa que los datos se encuentran en la microservicio. Estos datos podrían existir no solo en el mismo servidor, pero dentro del proceso de microservicio, en la memoria y se conservan en unidades de disco duro y replican en otros nodos. Figura 4-30 muestra los distintos enfoques.

![](./media/image34.png)

**Figura 4-30**. Sin estado frente a microservicios con estado

Un enfoque sin estado es perfectamente válido y es más fácil de implementar que microservicios con estado, ya que el enfoque es similar a patrones tradicionales y conocidos. Pero sin estado microservicios imponen latencia entre el proceso y orígenes de datos. También implican más mover partes cuando se desea mejorar el rendimiento con más de memoria caché y las colas. El resultado es que puede acabar con arquitecturas complejas que dispone de demasiados niveles.

En cambio, [microservicios con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede excel en escenarios avanzados, porque no hay ninguna latencia entre la lógica del dominio y los datos. Procesamiento intensivo de datos, juegos volver finaliza, bases de datos como un servicio, y todos los otros escenarios de baja latencia beneficiarán de servicios con estado, lo que permite que el estado local para un acceso más rápido.

Servicios y sin estado son complementarios. Por ejemplo, puede ver en la figura 4-30, en el diagrama de la derecha, que un servicio con estado se puede dividir en varias particiones. Para obtener acceso a esas particiones, tendrá que un servicio sin estado que actúa como un servicio de puerta de enlace que sabe cómo tratar cada partición en función de las claves de partición.

Servicios con estado presentan unas desventajas. Que imponen un nivel de complejidad que permite escalar horizontalmente. Funcionalidad que normalmente se implementa mediante sistemas de base de datos externa debe solucionarse para tareas como la replicación de datos a través de microservicios con estado y la partición de datos. Sin embargo, esta es una de las áreas donde como organizador [Azure Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-platform-architecture) con su [servicios confiables con estado](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-services-introduction#when-to-use-reliable-services-apis) puede ayudar a la mayoría, ya que simplifica el desarrollo y el ciclo de vida de stateful uso de microservicios la [confiable de servicios de API](https://docs.microsoft.com/azure/service-fabric/service-fabric-work-with-reliable-collections) y [Reliable Actors](https://docs.microsoft.com/azure/service-fabric/service-fabric-reliable-actors-introduction).

Otros marcos de microservicio que permiten que los servicios con estado, que admite el patrón de Actor y mejorar la tolerancia a errores y la latencia entre la lógica de negocios y datos son Microsoft [Orleans](https://github.com/dotnet/orleans), de Microsoft Research y [ Akka.NET](http://getakka.net/). Ambos marcos de trabajo actualmente están mejorando su compatibilidad con Docker.

Tenga en cuenta que los contenedores de Docker son sin estado. Si desea implementar un servicio con estado, se deberán cumplir alguno de los marcos adicionales de descriptiva y de nivel superiores que se ha indicado anteriormente. 

>[!div class="step-by-step"]
[Anterior] (scalable-available-multi-container-microservice-applications.md) [siguiente] (.. /docker-Application-Development-Process/index.MD)
