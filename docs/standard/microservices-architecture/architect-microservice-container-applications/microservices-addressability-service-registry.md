---
title: Direccionamiento de Microservicios y el registro del servicio
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Direccionamiento de Microservicios y el registro del servicio
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 19a0200dadfb90a455de690d880f4eeae4772ed7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="microservices-addressability-and-the-service-registry"></a>Direccionamiento de Microservicios y el registro del servicio

Cada microservicio tiene un nombre único (URL) que se utiliza para resolver su ubicación. El microservicio debe ser direccionable siempre que se está ejecutando. Si tiene que pensar sobre el equipo en el que se ejecuta un microservicio determinado, posibles incorrecta rápidamente. En la misma manera que DNS resuelve una dirección URL a un equipo en particular, su microservicio debe tener un nombre único para que su ubicación actual sea reconocible. Microservicios necesitan nombres direccionables que hacer que sean independientes de la infraestructura que se ejecutan en. Esto implica que hay una interacción entre cómo se implementa el servicio y cómo se detecta, porque debe haber un [registro del servicio](http://microservices.io/patterns/service-registry.html). Del mismo modo, cuando se produce un error en un equipo, el servicio de registro debe ser capaz de indicar que el servicio se está ejecutando.

El [modelo de servicio del registro](http://microservices.io/patterns/service-registry.html) es una parte fundamental de detección de servicios. El registro es una base de datos que contiene las ubicaciones de red de las instancias de servicio. Un registro de servicio debe estar actualizado y de alta disponibilidad. Los clientes pudieron almacenar en caché las ubicaciones de red obtenidas del registro del servicio. Sin embargo, esa información finalmente se queda obsoleta y los clientes ya no pueden detectar las instancias de servicio. Por lo tanto, un registro de servicio consta de un clúster de servidores que utilizan un protocolo de replicación y para mantener su coherencia.

En algunos entornos de implementación de microservicio (denominados clústeres, que debe incluirse en una sección posterior), la detección de servicios está integrada. Por ejemplo, dentro de un entorno de servicio de contenedor de Azure, Kubernetes DC/OS con maratón pueden controlar el registro de la instancia de servicio y de anulación de registro. Un servidor proxy también se ejecuta en cada host del clúster que desempeña el rol del enrutador de detección del lado servidor. Otro ejemplo es Azure Service Fabric, que también proporciona un registro de servicio a través de su servicio de nomenclatura de cuadro.

Tenga en cuenta que hay determinada superposición entre el registro del servicio y el patrón de puerta de enlace de API, lo que ayuda a resolver este problema también. Por ejemplo, el [servicio un Proxy inverso tejido](https://docs.microsoft.com/azure/service-fabric/service-fabric-reverseproxy) es un tipo de implementación de una puerta de enlace de API que se basa en el servicio de nombres de servicio Fabrice y que ayuda a resolver la resolución de direcciones para los servicios internos.

## <a name="additional-resources"></a>Recursos adicionales

-   **Chris Richardson. Patrón: Registro del servicio**
    *http://microservices.io/patterns/service-registry.html*

-   **Auth0. El registro del servicio**
    [*https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/*](https://auth0.com/blog/an-introduction-to-microservices-part-3-the-service-registry/)

-   **Gabriel Schenker. Detección de servicios**
    [*https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/*](https://lostechies.com/gabrielschenker/2016/01/27/service-discovery/)


>[!div class="step-by-step"]
[Anterior] (mantener-microservicio-apis.md) [siguiente] (microservice-based-composite-ui-shape-layout.md)
