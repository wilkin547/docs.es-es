---
title: Creación, desarrollo y control de versiones de los contratos y las API de microservicio
description: Cree las API de microservicio y contratos teniendo en cuenta la evolución y el control de versiones, porque las necesidades pueden cambiar.
ms.date: 09/20/2018
ms.openlocfilehash: 9164bfd12df18a88ac187c8962f0afc80b702881
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557677"
---
# <a name="creating-evolving-and-versioning-microservice-apis-and-contracts"></a>Creación, desarrollo y control de versiones de los contratos y las API de microservicio

Una API de microservicio es un contrato entre el servicio y sus clientes. Solo podrá desarrollar un microservicio de forma independiente si no incumple el contrato de su API. Por este motivo el contrato es tan importante. Cualquier cambio en el contrato afectará a sus aplicaciones cliente o a la puerta de enlace de API.

La naturaleza de la definición de API depende del protocolo que esté utilizando. Por ejemplo, si usa mensajería (como [AMQP](http://www.amqp.org/)), la API consiste en los tipos de mensaje. Si usa servicios HTTP y RESTful, la API consiste en las direcciones URL y los formatos JSON de solicitud y respuesta.

Pero, aunque piense en su contrato inicial, una API de servicio debe cambiar con el tiempo. Normalmente, cuando esto ocurre, y especialmente si la API es una API pública utilizada por varias aplicaciones cliente, no puede forzar a todos los clientes a actualizar la versión a su nuevo contrato de API. Lo más habitual es implementar progresivamente nuevas versiones de un servicio, de forma que se ejecuten simultáneamente las versiones anteriores y las nuevas de un contrato de servicio. Por tanto, es importante contar con una estrategia para el control de versiones del servicio.

Cuando los cambios en la API son pequeños, por ejemplo, si agrega atributos o parámetros a la API, los clientes que usen una API anterior deberán cambiar y trabajar con la nueva versión del servicio. Usted puede proporcionar los valores predeterminados para los atributos que falten y que sean necesarios, y los clientes pueden pasar por alto cualquier atributo de respuesta adicional.

Pero en ciertas ocasiones necesitará realizar cambios importantes e incompatibles en una API de servicio. Puesto que es posible que no pueda forzar a los servicios o aplicaciones cliente a que se actualicen inmediatamente a la nueva versión, un servicio debe admitir versiones anteriores de la API durante cierto período de tiempo. Si está utilizando un mecanismo basado en HTTP, como REST, una opción es insertar el número de versión de la API en la dirección URL o en un encabezado HTTP. A continuación, puede decidir si quiere implementar ambas versiones del servicio al mismo tiempo en la misma instancia de servicio o si prefiere implementar distintas instancias y que cada una controle una versión de la API. Una buena opción es utilizar el [patrón mediador](https://en.wikipedia.org/wiki/Mediator_pattern) (por ejemplo, la [biblioteca MediatR](https://github.com/jbogard/MediatR)) para desacoplar las diferentes versiones de implementación en los controladores independientes.

Por último, si utiliza una arquitectura REST, [Hypermedia](https://www.infoq.com/articles/mark-baker-hypermedia) es la mejor solución para controlar las versiones de los servicios y permitir las API avanzadas.

## <a name="additional-resources"></a>Recursos adicionales

- **Scott Hanselman. ASP.NET Core RESTful Web API versioning made easy** (Control de versiones simplificado de API web RESTful de ASP.NET Core) \
  <https://www.hanselman.com/blog/ASPNETCoreRESTfulWebAPIVersioningMadeEasy.aspx>

- **Control de versiones de una API web RESTful** \
  <https://docs.microsoft.com/azure/architecture/best-practices/api-design#versioning-a-restful-web-api>

- **Roy Fielding. Control de versiones, hipermedios y REST** \
  <https://www.infoq.com/articles/roy-fielding-on-versioning>

>[!div class="step-by-step"]
>[Anterior](asynchronous-message-based-communication.md)
>[Siguiente](microservices-addressability-service-registry.md)
