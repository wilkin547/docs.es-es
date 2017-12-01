---
title: Crear, evolucionando y control de versiones microservicio API y contratos
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Crear, evolucionando y control de versiones microservicio API y contratos
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 433711c3479eafd52bf9f5d53faf8e5707c6c624
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Crear, evolucionando y control de versiones microservicio API y contratos

Una API de microservicio es un contrato entre el servicio y sus clientes. Podrá evolucionar independientemente un microservicio sólo si no se interrumpe el contrato de API, motivo por el cual el contrato es tan importante. Si cambia el contrato, afectará a las aplicaciones cliente o la puerta de enlace de API.

La naturaleza de la definición de API depende en el protocolo que se esté utilizando. Por ejemplo, si se usa mensajería (como [AMQP](https://www.amqp.org/)), la API consta de los tipos de mensaje. Si usas HTTP y servicios RESTful, la API consta de las direcciones URL y los formatos de solicitud y respuesta JSON.

Sin embargo, incluso si es reflexivo sobre su contrato inicial, será necesario cambiar con el tiempo una API de servicio. Cuando esto ocurre, y especialmente si la API es una API pública consumida por varias aplicaciones cliente, normalmente no puede forzar que todos los clientes para actualizar en el nuevo contrato de API. Normalmente, debe implementar de forma incremental las nuevas versiones de un servicio de forma que las versiones anteriores y nuevas de un contrato de servicio se ejecutan simultáneamente. Por lo tanto, es importante contar con una estrategia para el control de versiones de servicio.

Cuando los cambios en la API son pequeños, como si agrega atributos o parámetros a la API, los clientes que usan una API anterior deben cambiar y trabajar con la nueva versión del servicio. Es posible que pueda proporcionar los valores predeterminados para los atributos que faltan que son necesarios y los clientes podrían llevar pasar por alto los atributos de respuesta adicionales.

Sin embargo, en ciertas ocasiones necesitará realizar cambios principales e incompatibles en una API de servicio. Dado que es posible que no pueda forzar servicios o aplicaciones cliente para actualizar inmediatamente a la nueva versión, un servicio debe admitir versiones anteriores de la API durante algún tiempo. Si está utilizando un mecanismo basado en HTTP, como REST, es un enfoque insertar el número de versión de API en la dirección URL o en un encabezado HTTP. A continuación, puede decidir entre implementar ambas versiones del servicio al mismo tiempo en la misma instancia de servicio o la implementación de distintas instancias que controlar cada uno de ellos una versión de la API. Un buen método para esto es el [patrón mediador](https://en.wikipedia.org/wiki/Mediator_pattern) (por ejemplo, [MediatR biblioteca](https://github.com/jbogard/MediatR)) desacoplar las versiones de implementación diferente en los controladores independientes.

Por último, si utiliza una arquitectura REST, [hipermedia](https://www.infoq.com/articles/mark-baker-hypermedia) es la mejor solución para las versiones de los servicios y permitir que las API avanzadas.

## <a name="additional-resources"></a>Recursos adicionales

-   **Scott Hanselman. Control de versiones ASP.NET Core RESTful Web API facilitan**
    <http://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

-   **Control de versiones de una API web RESTful**
    [*https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api*](https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api)

-   **Roy Fielding. Control de versiones, hipermedia y REST**
    <https://www.infoq.com/articles/roy-fielding-on-versioning>


>[!div class="step-by-step"]
[Anterior] (asincrónica-message-según-communication.md) [siguiente] (microservicios-direccionabilidad-servicio-registry.md)
