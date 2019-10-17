---
title: 'Consideraciones sobre la arquitectura sin servidor: aplicaciones sin servidor'
description: Comprenda los desafíos de diseñar aplicaciones sin servidor, desde la administración de Estados y el almacenamiento persistente hasta escalado, registro, seguimiento y diagnóstico.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: c856683cf6910be98661e634246cd003b93a6d76
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522430"
---
# <a name="serverless-architecture-considerations"></a>Consideraciones sobre la arquitectura sin servidor

La adopción de una arquitectura sin servidor conlleva algunos desafíos. En esta sección se analizan algunas de las consideraciones más comunes que se deben tener en cuenta. Todos estos desafíos tienen soluciones. Al igual que con todas las opciones de arquitectura, la decisión de ir sin servidor debe realizarse solo después de considerar cuidadosamente las ventajas y desventajas. En función de las necesidades de la aplicación, puede decidir que una implementación sin servidor no es la solución adecuada para determinados componentes.

## <a name="managing-state"></a>Administración del estado

Las funciones sin servidor, al igual que con los microservicios en general, no tienen estado de forma predeterminada. Evitar el estado permite que el servidor sin servidor sea efímero, se escale horizontalmente y proporcione resistencia sin un punto central de error. En algunas circunstancias, los procesos empresariales requieren el estado. Si el proceso requiere el estado, tiene dos opciones. Puede adoptar un modelo distinto de sin servidor o interactuar con un servicio independiente que proporcione el estado. Agregar estado puede complicar la solución y hacer que sea más difícil de escalar y, potencialmente, crear un único punto de error. Considere detenidamente si la función requiere un estado. Si la respuesta es "sí", determine si sigue teniendo sentido implementarlo con sin servidor.

Hay varias soluciones para adoptar el estado sin poner en peligro las ventajas de sin servidor. Algunas de las soluciones más populares son:

- Usar un almacén de datos temporal o una caché distribuida, como Redis
- Almacenar el estado en una base de datos, como SQL o CosmosDB
- Controlar el estado a través de un motor de flujo de trabajo como durable Functions

La línea inferior es que debe tener en cuenta la necesidad de cualquier administración de Estados dentro de los procesos que está pensando en implementar sin servidor.

## <a name="long-running-processes"></a>Procesos de ejecución prolongada

Muchas de las ventajas de Serverless dependen de que los procesos sean efímeros. Los tiempos de ejecución breves facilitan que el proveedor sin servidor libere recursos a medida que las funciones finalizan y comparten funciones entre los hosts. La mayoría de los proveedores de nube limitan el tiempo total que la función puede ejecutar hasta unos 10 minutos. Si el proceso puede tardar más tiempo, puede considerar una implementación alternativa.

Hay algunas excepciones y soluciones. Una solución puede ser dividir el proceso en componentes más pequeños que, de forma individual, tardan menos tiempo en ejecutarse. Si el proceso se ejecuta durante mucho tiempo debido a las dependencias, también puede considerar un flujo de trabajo asincrónico mediante una solución como durable functions. Durable Functions pausa y mantiene el estado del proceso mientras está esperando a que finalice un proceso externo. El control asincrónico reduce el tiempo que se ejecuta el proceso real.

## <a name="startup-time"></a>Tiempo de inicio

Un posible problema con las implementaciones sin servidor es el tiempo de inicio. Para conservar recursos, muchos proveedores sin servidor crean la infraestructura "a petición". Cuando una función sin servidor se desencadena después de un período de tiempo, es posible que sea necesario crear o reiniciar los recursos para hospedar la función. En algunas situaciones, los inicios en frío pueden dar lugar a retrasos de varios segundos. El tiempo de inicio varía entre proveedores y niveles de servicio. Hay algunos enfoques para abordar el tiempo de inicio si es importante minimizar el éxito de la aplicación.

- Algunos proveedores permiten a los usuarios pagar por los niveles de servicio que garantizan que la infraestructura esté "siempre activada".
- Implemente un mecanismo Keep-Alive (haga ping en el punto de conexión para mantenerlo "activo").
- Use la orquestación como Kubernetes con un enfoque de función en contenedor (el host ya se está ejecutando, por lo que la ejecución de nuevas instancias es sumamente rápida).

## <a name="database-updates-and-migrations"></a>Actualizaciones y migraciones de bases de datos

Una ventaja de código sin servidor es que puede liberar nuevas funciones sin tener que volver a implementar toda la aplicación. Esta ventaja puede ser una desventaja cuando hay una base de datos relacional implicada. Los cambios en los esquemas de base de datos son difíciles de sincronizar con las actualizaciones sin servidor. Se plantean desafíos adicionales cuando se produce un error y se deben revertir los cambios. La integridad de los datos es una de las razones por las que un procedimiento recomendado para los microservicios y las funciones sin servidor es que poseen sus propios datos. Es posible implementar los cambios como una sola unidad de proceso y datos. La realidad es que muchos sistemas heredados incluyen una base de datos de back-end grande que se debe conciliar con la arquitectura sin servidor.

Un enfoque popular para resolver el control de versiones de esquemas es no modificar nunca las propiedades y columnas existentes, sino agregar información nueva. Por ejemplo, considere un cambio para pasar de una marca booleana "completado" para una lista de tareas pendientes a una "fecha de finalización". En lugar de quitar el campo anterior, el cambio de la base de datos hará lo siguiente:

1. Agregue un nuevo campo "fecha de finalización".
1. Transforme el campo booleano "completado" en una función calculada que evalúe si la fecha de finalización es posterior a la fecha actual.
1. Agregue un desencadenador para establecer la fecha de finalización en la fecha actual cuando el valor booleano completado esté establecido en true.

La secuencia de cambios garantiza que el código heredado continúe ejecutándose "tal cual", mientras que las funciones sin servidor más recientes pueden aprovechar el nuevo campo.

Para obtener más información sobre los datos de las arquitecturas sin servidor, vea [desafíos y soluciones para la administración de datos distribuidos](../microservices/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Cambiar escala

Es una idea equivocada habitual que sin servidor significa "no hay servidor". En realidad, es "menos servidor". El hecho de que haya una infraestructura de respaldo es importante comprender cuándo se va a escalar. La mayoría de las plataformas sin servidor proporcionan un conjunto de controles para controlar cómo se debe escalar la infraestructura cuando aumenta la densidad de eventos. Puede elegir entre varias opciones, pero su estrategia puede variar en función de la función. Además, las funciones se ejecutan normalmente en un host relacionado, de modo que las funciones en el mismo host tengan las mismas opciones de escala. Por lo tanto, es necesario organizar y planear las funciones que se hospedan juntas en función de los requisitos de escala.

Las reglas suelen especificar cómo realizar el escalado vertical (aumentar los recursos del host) y el escalado horizontal (aumentar el número de instancias de host) en función de los parámetros variables. Los desencadenadores para las escalas pueden incluir programación, tasas de solicitudes, uso de CPU y uso de memoria. A menudo, el rendimiento es mayor. Es posible que los enfoques más económicos basados en el consumo no escalen con rapidez cuando la tasa de solicitudes aumente repentinamente. Hay un equilibrio entre el pago por adelantado del "costo de seguro" frente al pago estricto de "a medida que avanza" y el riesgo de respuestas más lentas debido a aumentos repentinos de la demanda.

## <a name="monitoring-tracing-and-logging"></a>Supervisión, seguimiento y registro

Un aspecto que a menudo se pasa por alto de DevOps es la supervisión de las aplicaciones una vez implementadas. Es importante tener una estrategia para supervisar las funciones sin servidor. El mayor desafío suele ser la correlación o reconocer cuándo un usuario llama a varias funciones como parte de la misma interacción. La mayoría de las plataformas sin servidor permiten el registro de la consola que se puede importar en herramientas de terceros. También hay opciones para automatizar la recopilación de telemetría, generar y realizar un seguimiento de los identificadores de correlación y supervisar acciones específicas para proporcionar información detallada. Azure proporciona la [plataforma de Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) avanzada para la supervisión y el análisis.

## <a name="inter-service-dependencies"></a>Dependencias entre servicios

Una arquitectura sin servidor puede incluir funciones que dependen de otras funciones. De hecho, no es raro que una arquitectura sin servidor tenga varios servicios que se llamen entre sí como parte de una interacción o transacción distribuida. Para evitar el acoplamiento fuerte, se recomienda que los servicios no se hagan referencia entre sí directamente. Cuando el extremo de un servicio debe cambiar, las referencias directas pueden dar lugar a una refactorización importante. Una solución sugerida es proporcionar un mecanismo de detección de servicios, como un registro, que proporcione el extremo adecuado para un tipo de solicitud. Otra solución consiste en aprovechar servicios de mensajería como colas o temas para la comunicación entre servicios.

## <a name="managing-failure-and-providing-resiliency"></a>Administrar errores y proporcionar resistencia

También es importante tener en cuenta el *patrón*de disyuntor: Si, por alguna razón, un servicio sigue produciendo errores, no es aconsejable llamar a ese servicio repetidamente. En su lugar, se llama a un servicio alternativo o se devuelve un mensaje hasta que se restablece el estado del servicio dependiente. La arquitectura sin servidor debe tener en cuenta la estrategia para resolver y administrar las dependencias entre servicios.

Para continuar con el patrón de disyuntor, los servicios deben ser tolerantes a errores y resistentes. La tolerancia a errores hace referencia a la capacidad de la aplicación de seguir ejecutándose incluso después de encontrar excepciones inesperadas o Estados no válidos. La tolerancia a errores suele ser una función del propio código y cómo se escribe para controlar las excepciones. La resistencia hace referencia al modo en que la aplicación se encuentra en recuperación ante errores. La plataforma sin servidor suele administrar la resistencia. La plataforma debe ser capaz de poner en marcha una nueva instancia de función sin servidor cuando se produce un error en la existente. La plataforma también debe ser lo suficientemente inteligente como para detener la marcha de nuevas instancias cuando se produce un error en cada nueva instancia.

Para obtener más información, vea [implementar el patrón de disyuntor](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Versiones y implementaciones verdes/azules

Una ventaja importante de Serverless es la capacidad de actualizar una función específica sin tener que volver a implementar toda la aplicación. Para que las actualizaciones se realicen correctamente, las funciones deben tener versiones para que los servicios que las llaman se enruten a la versión correcta del código. También es importante una estrategia para implementar nuevas versiones. Un enfoque común es usar "implementaciones verdes/azules". La implementación verde es la función actual. Una nueva versión "azul" se implementa en producción y se prueba. Cuando se superan las pruebas, las versiones verde y azul se intercambian, por lo que la nueva versión entra en marcha. Si se detecta algún problema, se pueden intercambiar de nuevo. La compatibilidad con el control de versiones y las implementaciones verdes/azules requiere una combinación de creación de las funciones para acomodar los cambios de versión y trabajar con la plataforma sin servidor para administrar las implementaciones. Un posible enfoque consiste en usar servidores proxy, que se describen en el capítulo [plataforma sin servidor de Azure](azure-functions.md#proxies) .

>[!div class="step-by-step"]
>[Anterior](serverless-architecture.md)
>[Siguiente](serverless-design-examples.md)
