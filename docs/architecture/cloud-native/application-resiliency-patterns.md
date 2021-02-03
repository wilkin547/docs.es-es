---
title: Patrones de resistencia de las aplicaciones
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Patrones de resistencia de aplicaciones
author: robvet
ms.date: 01/19/2021
ms.openlocfilehash: 9a59a7d93b61b0dea11680f6caf0bd3b68a0f853
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505926"
---
# <a name="application-resiliency-patterns"></a>Patrones de resistencia de las aplicaciones

La primera línea de defensa es la resistencia de las aplicaciones.

Aunque podría invertir un tiempo considerable en escribir su propio marco de resistencia, tales productos ya existen. [Polly](http://www.thepollyproject.org/) es una biblioteca completa de control de errores y resistencia de .net que permite a los desarrolladores expresar directivas de resistencia de forma fluida y segura para subprocesos. Polly tiene como destino aplicaciones compiladas con el .NET Framework o .NET 5. En la tabla siguiente se describen las características de resistencia, llamadas `policies` , disponibles en la biblioteca Polly. Se pueden aplicar individualmente o agruparse.

| Directiva | Experiencia |
| :-------- | :-------- |
| Reintento | Configura las operaciones de reintento en las operaciones designadas. |
| Disyuntor | Bloquea las operaciones solicitadas para un período predefinido cuando los errores superan un umbral configurado |
| Tiempo de espera | Establece el límite de tiempo durante el cual un llamador puede esperar una respuesta. |
| Compartimentado | Restringe las acciones a un grupo de recursos de tamaño fijo para evitar que las llamadas que producen errores impidan un recurso. |
| Cache | Almacena las respuestas automáticamente. |
| Reserva | Define el comportamiento estructurado cuando se produce un error. |

Observe cómo en la figura anterior las directivas de resistencia se aplican a los mensajes de solicitud, ya procedan de un cliente externo o de un servicio back-end. El objetivo es compensar la solicitud de un servicio que puede estar temporalmente no disponible. Estas interrupciones de corta duración suelen manifestarse con los códigos de Estado HTTP que se muestran en la tabla siguiente.

| Código de estado HTTP| Causa |
| :-------- | :-------- |
| 404 | No encontrado |
| 408 | Tiempo de espera de solicitud |
| 429 | Demasiadas solicitudes (lo más probable es que se haya limitado) |
| 502 | Puerta de enlace incorrecta |
| 503 | Servicio no disponible |
| 504 | Tiempo de espera del Gateway |

Pregunta: ¿reintentaría un código de Estado HTTP de 403-prohibido? No. En este caso, el sistema funciona correctamente, pero informa al llamador de que no está autorizado para realizar la operación solicitada. Se debe tener cuidado para reintentar solo las operaciones causadas por errores.

Como se recomienda en el capítulo 1, los desarrolladores de Microsoft que crean aplicaciones nativas de la nube deben tener como destino la plataforma .NET. La versión 2,1 presentó la biblioteca [HTTPClientFactory](https://www.stevejgordon.co.uk/introduction-to-httpclientfactory-aspnetcore) para crear instancias de cliente http para interactuar con recursos basados en URL. Al sustituir la clase HTTPClient original, la clase Factory admite muchas características mejoradas, una de las cuales es una [integración estrecha](../microservices/implement-resilient-applications/implement-http-call-retries-exponential-backoff-polly.md) con la biblioteca de resistencia Polly. Con él, puede definir fácilmente directivas de resistencia en la clase de inicio de la aplicación para controlar los errores parciales y los problemas de conectividad.

A continuación, vamos a expandir los patrones de reintento y de disyuntor.

### <a name="retry-pattern"></a>Patrón Retry

En un entorno de nube nativo distribuido, las llamadas a los servicios y a los recursos en la nube pueden producir errores debido a errores transitorios (de corta duración), que normalmente se corrigen después de un breve período de tiempo. La implementación de una estrategia de reintento ayuda a un servicio nativo de la nube a mitigar estos escenarios.

El [patrón Retry](/azure/architecture/patterns/retry) permite a un servicio volver a intentar una operación de solicitud con error un número (configurable) de veces con un tiempo de espera que aumenta exponencialmente. En la figura 6-2 se muestra una acción de reintento.

![Patrón de reintento en acción](./media/retry-pattern.png)

**Figura 6-2**. Patrón de reintento en acción

En la ilustración anterior, se ha implementado un patrón de reintento para una operación de solicitud. Está configurado para permitir hasta cuatro reintentos antes de que se produzca un error en un intervalo de retroceso (tiempo de espera) a partir de dos segundos, lo que se duplica exponencialmente para cada intento posterior.

- Se produce un error en la primera invocación y se devuelve un código de Estado HTTP de 500. La aplicación espera dos segundos y vuelve a intentar la llamada.
- También se produce un error en la segunda invocación y se devuelve un código de Estado HTTP de 500. La aplicación ahora duplica el intervalo de retroceso en cuatro segundos y vuelve a intentar la llamada.
- Por último, la tercera llamada se realiza correctamente.
- En este escenario, la operación de reintento habría intentado hasta cuatro reintentos mientras doblaba la duración de la interrupción antes de que se produjera un error en la llamada.
- Si se produjo un error en el cuarto intento de reintento, se invocaría una directiva de reserva para controlar correctamente el problema.

Es importante aumentar el período de interrupción antes de reintentar la llamada para permitir que el tiempo de servicio se corrija automáticamente. Se recomienda implementar un retroceso que aumenta exponencialmente (duplicando el período en cada reintento) para permitir el tiempo de corrección adecuado.

## <a name="circuit-breaker-pattern"></a>Patrón de disyuntor

Aunque el patrón de reintento puede ayudar a salvar una solicitud en un error parcial, existen situaciones en las que los errores pueden deberse a eventos imprevistos que requerirán períodos más largos de tiempo para resolverse. La gravedad de estos errores puede abarcar desde una pérdida parcial de la conectividad hasta la total detención de un servicio. En estas situaciones, es poco puntual que una aplicación vuelva a intentar continuamente una operación que es improbable que se realice correctamente.

Para empeorar todo, la ejecución de operaciones de reintento continuo en un servicio que no responde puede pasar a un escenario de denegación de servicio autoimpuesta en el que se inunda el servicio con llamadas continuas que agotan los recursos como la memoria, los subprocesos y las conexiones de base de datos, lo que provoca errores en partes no relacionadas del sistema que usan los mismos recursos.

En estas situaciones, sería preferible que la operación produjera un error inmediatamente y solo intentara invocar el servicio si es probable que se realizara correctamente.

El [patrón](/azure/architecture/patterns/circuit-breaker) de disyuntor puede impedir que una aplicación intente ejecutar repetidamente una operación que es probable que produzca un error. Después de un número predefinido de llamadas erróneas, bloquea todo el tráfico al servicio. De forma periódica, permitirá una llamada de prueba para determinar si el error se ha resuelto. En la figura 6-3 se muestra el patrón de disyuntor en acción.

![Patrón de disyuntor en acción](./media/circuit-breaker-pattern.png)

**Figura 6-3**. Patrón de disyuntor en acción

En la ilustración anterior, se ha agregado un patrón de disyuntor al patrón de reintento original. Observe que, después de 100 solicitudes con error, los disyuntores se abren y ya no permiten llamadas al servicio. El valor CheckCircuit, establecido en 30 segundos, especifica la frecuencia con la que la biblioteca permite que una solicitud continúe en el servicio. Si la llamada se realiza correctamente, el circuito se cierra y el servicio vuelve a estar disponible para el tráfico.

Tenga en cuenta que la intención del patrón de disyuntor es *diferente* de la del patrón de reintento. El patrón de reintento permite que una aplicación vuelva a intentar una operación en la expectativa de que se realizará correctamente. El patrón de disyuntor impide que una aplicación realice una operación que es probable que produzca un error. Normalmente, una aplicación *combinará* estos dos patrones mediante el patrón de reintento para invocar una operación a través de un disyuntor.

## <a name="testing-for-resiliency"></a>Pruebas de resistencia

Las pruebas de resistencia no siempre se pueden realizar de la misma manera que se prueba la funcionalidad de la aplicación (mediante la ejecución de pruebas unitarias, pruebas de integración, etc.). En su lugar, debe probar cómo realiza la carga de trabajo de un extremo a otro en condiciones de error, que solo se producen de forma intermitente. Por ejemplo: inserción de errores mediante procesos bloqueados, certificados expirados, hacer que los servicios dependientes no estén disponibles, etc. Se pueden usar marcos como [caos-Monkey](https://github.com/Netflix/chaosmonkey) para realizar pruebas de caos.

La resistencia de la aplicación es una para controlar las operaciones solicitadas problemáticas. Pero es solo la mitad de la historia. A continuación, se tratan las características de resistencia disponibles en la nube de Azure.

>[!div class="step-by-step"]
>[Anterior](resiliency.md)
>[Siguiente](infrastructure-resiliency-azure.md)
