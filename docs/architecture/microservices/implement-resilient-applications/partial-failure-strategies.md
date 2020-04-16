---
title: Estrategias para tratar errores parciales
description: Conozca varias estrategias para controlar errores parciales con elegancia.
ms.date: 10/16/2018
ms.openlocfilehash: abf87df5afed02b4d794a1307a0ed943cafb4db3
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80988809"
---
# <a name="strategies-to-handle-partial-failure"></a>Estrategias para controlar errores parciales

Las estrategias para tratar los errores parciales son las siguientes.

**Usar la comunicación asincrónica (por ejemplo, la comunicación basada en mensajes) a través de microservicios internos**. Es muy aconsejable no crear cadenas largas de llamadas HTTP sincrónicas a través de los microservicios internos, porque ese diseño incorrecto podría convertirse en la principal causa de interrupciones incorrectas. Por el contrario, excepto en el caso de comunicaciones front-end entre las aplicaciones cliente y el primer nivel de microservicios o puertas de enlace de API específicas, se recomienda usar solamente una comunicación asíncrona (basada en mensajes) cuando haya pasado el ciclo inicial de solicitud/respuesta en los microservicios internos. La coherencia definitiva y las arquitecturas orientadas a eventos le ayudarán a minimizar el efecto dominó. Estos enfoques exigen un nivel más alto de autonomía de microservicio y, por lo tanto, evitan el problema que se describe a continuación.

**Usar reintentos con retroceso exponencial**. Esta técnica ayuda a evitar fallos cortos e intermitentes mediante la realización de un número determinado de intentos de llamada en caso de que el servicio no esté disponible solo durante un breve período de tiempo. Esto puede ocurrir debido a problemas de red intermitentes o cuando un contenedor o microservicio se mueve a otro nodo del clúster. Pero si estos intentos no se diseñan correctamente con interruptores, pueden agravar el efecto dominó e incluso pueden llegar a producir un [ataque por denegación de servicio (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack).

**Solucionar los tiempos de expiración de red**. En general, los clientes deben diseñarse para que no se bloqueen indefinidamente y para que usen siempre los tiempos de expiración cuando esperen una respuesta. Utilizar tiempos de expiración garantiza que los recursos nunca se bloqueen indefinidamente.

**Usar el patrón de interruptor**. En este enfoque, el proceso de cliente supervisa el número de solicitudes con error. Si la tasa de errores supera el límite establecido, se activa un "interruptor" para que los intentos adicionales fallen de inmediato. (Si se producen errores en un gran número de solicitudes, esto sugiere que el servicio no está disponible y que enviar solicitudes no sirve de nada.) Tras un período de tiempo de expiración, el cliente debe volver a intentarlo y, si las nuevas solicitudes se realizan correctamente, desactivar el interruptor.

**Proporcionar reservas**. En este enfoque, el proceso del cliente realiza una lógica de reserva cuando falla una solicitud, como devolver los datos almacenados en caché o un valor predeterminado. Este enfoque es adecuado para las consultas, pero es más complejo para las actualizaciones o los comandos.

**Limitar el número de solicitudes en cola**. Los clientes también deben imponer un límite máximo en la cantidad de solicitudes pendientes que un microservicio de cliente puede enviar a un servicio determinado. Si se alcanza el límite, probablemente no tenga sentido realizar más solicitudes y dichos intentos deben generar error inmediatamente. En cuanto a la implementación, la directiva [Aislamiento compartimentado](https://github.com/App-vNext/Polly/wiki/Bulkhead) de Polly se puede usar para cumplir este requisito. Este enfoque es básicamente una limitación en paralelo con <xref:System.Threading.SemaphoreSlim> como implementación. También admite una "cola" fuera de la mampara. Puede perder proactivamente una carga excesiva incluso antes de la ejecución (por ejemplo, porque se considera que ha llegado al límite de su capacidad). Esto hace que su respuesta a determinados escenarios de error sea mucho más rápida que la que tendría un interruptor, puesto que el interruptor espera a que se produzcan los errores. El objeto BulkheadPolicy de [Polly](http://www.thepollyproject.org/) expone hasta qué punto están llenos el espacio limitado por la mampara y la cola, y ofrece eventos sobre desbordamiento para que también se puedan utilizar para administrar un escalado horizontal automatizado.

## <a name="additional-resources"></a>Recursos adicionales

- **Resiliency patterns (Patrones de resistencia)** \
  [https://docs.microsoft.com/azure/architecture/patterns/category/resiliency](/azure/architecture/patterns/category/resiliency)

- **Adding Resilience and Optimizing Performance (Agregar resistencia y optimizar el rendimiento)** \
  <https://docs.microsoft.com/previous-versions/msp-n-p/jj591574(v=pandp.10)>

- **Bulkhead** (Mampara). Repositorio de GitHub. Implementación con la directiva de Polly. \
  <https://github.com/App-vNext/Polly/wiki/Bulkhead>

- **Designing resilient applications for Azure (Diseñar aplicaciones resistentes de Azure)** \
  [https://docs.microsoft.com/azure/architecture/resiliency/](/azure/architecture/resiliency/)

- **Control de errores transitorios**\
  [https://docs.microsoft.com/azure/architecture/best-practices/transient-faults](/azure/architecture/best-practices/transient-faults)

>[!div class="step-by-step"]
>[Anterior](handle-partial-failure.md)
>[Siguiente](implement-retries-exponential-backoff.md)
