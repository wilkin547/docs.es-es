---
title: Direccionabilidad de microservicios y el Registro del servicio
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Direccionabilidad de microservicios y el Registro del servicio
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cc26b22d18d460fe6870da7360d73368e20f71d2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>Direccionabilidad de microservicios y el Registro del servicio

Cada microservicio tiene un nombre único (URL) que se usa para resolver su ubicación. El microservicio debe ser direccionable en cualquier lugar donde se ejecute. Si tiene que pensar en qué equipo se ejecuta un microservicio determinado, todo puede ir mal rápidamente. De la misma manera que DNS resuelve una URL para un equipo en particular, su microservicio debe tener un nombre único para que su ubicación actual sea reconocible. Los microservicios deben tener nombres direccionables que les permitan ser independientes de la infraestructura en que se ejecutan. Esto implica que hay una interacción entre cómo se implementa el servicio y cómo se detecta, porque debe haber un [Registro del servicio](http://microservices.io/patterns/service-registry.html). Del mismo modo, cuando se produce un error en un equipo, el servicio del Registro debe ser capaz de indicar que el servicio se está ejecutando.

El [patrón del Registro del servicio](http://microservices.io/patterns/service-registry.html) es una parte fundamental de la detección de servicios. El Registro es una base de datos que contiene las ubicaciones de red de las instancias del servicio. Un Registro del servicio debe estar muy disponible y actualizado. Los clientes podrían almacenar en caché las ubicaciones de red obtenidas del Registro del servicio. Sin embargo, esa información finalmente se queda obsoleta y los clientes ya no pueden detectar las instancias del servicio. Por tanto, un Registro del servicio consta de un clúster de servidores que usan un protocolo de replicación para mantener su coherencia.

En algunos entornos de implementación de microservicios (denominados clústeres, de los cuales se hablará en una sección posterior), la detección de servicios está integrada. Por ejemplo, dentro de un entorno de Azure Container Service, Kubernetes y DC/OS con Marathon pueden controlar el Registro y la anulación del Registro de la instancia del servicio. También ejecutan un proxy en cada host del clúster que desempeña el rol de enrutador de detección del lado servidor. Otro ejemplo es Azure Service Fabric, que también proporciona un Registro del servicio a través de su servicio de nombres estándar.

Tenga en cuenta que se produce cierta superposición entre el Registro del servicio y el patrón de puerta de enlace de API, lo que también ayuda a resolver este problema. Por ejemplo, el [proxy inverso de Service Fabric](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) es un tipo de implementación de una puerta de enlace de API basada en el servicio de nombres de Service Fabric que ayuda a resolver la resolución de direcciones para los servicios internos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Chris Richardson. Patrón: Registro del servicio**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0. El Registro del servicio**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker. Detección de servicios**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[Previous] (maintain-microservice-apis.md) [Next] (microservice-based-composite-ui-shape-layout.md)
