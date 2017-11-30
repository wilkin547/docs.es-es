---
title: Estrategias para controlar los errores parciales
description: Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Estrategias para controlar los errores parciales
keywords: Docker, microservicios, ASP.NET, contenedor
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ff3bed530b13a9b1822c7cccf5a4d47df6fc6239
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="strategies-for-handling-partial-failure"></a>Estrategias para controlar los errores parciales

Estrategias para tratar los errores parciales son los siguientes.

**Usar la comunicación asincrónica (por ejemplo, la comunicación basada en mensajes) a través de microservicios interno**. Es muy aconsejable no crear cadenas largas de las llamadas sincrónicas de HTTP a través de la microservicios interna porque ese diseño incorrecto finalmente se convertirá en la causa principal de interrupciones incorrectas. Por el contrario, excepto para las comunicaciones de front-end entre las aplicaciones cliente y el primer nivel de microservicios o puertas de enlace de API específica, se recomienda usar solo (basada en mensajes) comunicación asincrónica una vez más allá de la solicitud inicial / ciclo de respuesta, en la microservicios interno. Coherencia definitiva y arquitecturas orientadas a eventos le ayudará a minimizar el efecto dominó. Estos enfoques exigir un nivel más alto de autonomía de microservicio y, por tanto, evitar el problema que se describen a continuación.

**Usar reintentos con retroceso exponencial**. Esta técnica ayuda a evitar corto errores intermitentes mediante la realización de llamadas y vuelve a un número determinado de veces, en caso de que el servicio no estaba disponible sólo durante un breve período. Esto puede ocurrir debido a problemas de red intermitentes, o cuando un contenedor de microservicio se mueva a otro nodo en un clúster. Sin embargo, si estos intentos no se ha diseñado correctamente con los disyuntores, puede agravar el efecto dominó, en última instancia, incluso que producen un [denegación de servicio (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Solucionar los tiempos de espera de la red**. En general, los clientes deben diseñarse para que no se bloquea indefinidamente y usen siempre los tiempos de espera al esperar una respuesta. Utilizar tiempos de espera garantiza que los recursos nunca se acumular la indefinidamente.

**Usar el patrón de disyuntor**. En este enfoque, el proceso de cliente supervisa el número de solicitudes con error. Si la tasa de errores supera el límite configurado, un viajes "disyuntor" para que los repetidos intentos produce un error inmediato. (Si se producen errores en un gran número de solicitudes, que sugiere el servicio no está disponible y que las solicitudes de envío es inútil.) Tras un período de tiempo de espera, el cliente debe vuelva a intentarlo y, si las nuevas solicitudes se realizan correctamente, cierre el disyuntor.

**Proporcionar las reservas**. En este enfoque, el proceso del cliente realiza la lógica de retroceso cuando falla una solicitud, como devolver datos almacenados en caché o un valor predeterminado. Esto es un enfoque adecuado para las consultas y es más compleja para las actualizaciones o los comandos.

**Limitar el número de solicitudes en cola**. Los clientes también deben imponer un límite superior en el número de solicitudes pendientes que un microservicio de cliente puede enviar a un servicio determinado. Si se ha alcanzado el límite, tiene sentido probablemente realizar solicitudes adicionales y dichos intentos deben generar error inmediatamente. En cuanto a implementación, el Polly [cierre aislamiento](https://github.com/App-vNext/Polly/wiki/Bulkhead) directiva puede usarse para cumplir este requisito. Este enfoque es básicamente una limitación de la ejecución en paralelo con [SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1) como la implementación. También permite a una "cola" fuera de la pared. Proactivamente puede perder una carga excesiva incluso antes de la ejecución (por ejemplo, porque se considera completa de capacidad). Esto hace que su respuesta a determinados escenarios de error mucho más rápido que sería un disyuntor, puesto que el disyuntor esperará a que los errores. El objeto BulkheadPolicy en Polly expone la cantidad de espacio libre pared cola son y ofertas de eventos si se produce desbordamiento por lo que también sirve para controlar el escalado horizontal automatizadas.

## <a name="additional-resources"></a>Recursos adicionales

-   **Patrones de resistencia**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **Agregar resistencia y optimizar el rendimiento de**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)

-   **Cierre.** Repositorio de GitHub. Implementación con la directiva Polly. \
    [*https://github.com/app-vNext/Polly/Wiki/bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **Diseñar las aplicaciones resistentes de Azure**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **Control de errores transitorios**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[Anterior] (identificador-parcial-failure.md) [siguiente] (implemente-reintentos-exponencial-backoff.md)
