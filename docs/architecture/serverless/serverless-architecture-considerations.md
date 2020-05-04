---
title: 'Consideraciones sobre la arquitectura sin servidor: aplicaciones sin servidor'
description: Comprenda los desafíos de diseñar aplicaciones sin servidor, desde la administración de estados y el almacenamiento persistente hasta el escalado, el registro, el seguimiento y el diagnóstico.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/06/2020
ms.openlocfilehash: 3c07e1149e6af41a6b9a9317238e5c71015d2c4e
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135677"
---
# <a name="serverless-architecture-considerations"></a>Consideraciones sobre la arquitectura sin servidor

La adopción de una arquitectura sin servidor conlleva algunos desafíos. En esta sección se exploran algunas de las consideraciones más comunes que deben tenerse en cuenta. Todos estos desafíos tienen soluciones. Como ocurre con todas las opciones de arquitectura, la decisión de cambiar a sin servidor debe tomarse solo tras considerarse cuidadosamente las ventajas e inconvenientes. Dependiendo de las necesidades de su aplicación, puede decidir que una implementación sin servidor no es la solución adecuada para algunos componentes.

## <a name="managing-state"></a>Administración de estados

Las funciones sin servidor, como ocurre con los microservicios en general, carecen de estado de forma predeterminada. Evitar el estado permite a sin servidor ser efímero, escalar horizontalmente y proporcionar resistencia sin un punto de error central. En algunas circunstancias, los procesos empresariales requieren estado. Si su proceso requiere estado, tiene dos opciones. Puede adoptar un modelo distinto de sin servidor o interactuar con un servicio independiente que proporcione el estado. Agregar estado puede complicar la solución y hacer que sea más difícil de escalar, además de crear potencialmente un solo punto de error. Considere detenidamente si su función requiere, sin duda, estado. Si la respuesta es "sí", determine si aún tiene sentido implementarlo con sin servidor.

Hay varias soluciones para adoptar el estado sin poner en peligro las ventajas de sin servidor. Entre algunas de las soluciones más populares se incluyen las siguientes:

- Usar un almacén de datos temporal o una memoria caché distribuida, como Redis
- Almacenar el estado en una base de datos, como SQL o CosmosDB
- Controlar el estado a través de un motor de flujo de trabajo como [funciones duraderas](https://docs.microsoft.com/azure/azure-functions/durable/durable-functions-overview)

En resumidas cuentas, debe ser consciente de la necesidad de cualquier administración de estados en aquellos procesos que tiene en mente implementar con sin servidor.

## <a name="long-running-processes"></a>Procesos de larga ejecución

Muchas ventajas de sin servidor dependen de que los procesos sean efímeros. Los tiempos de ejecución breves facilitan al proveedor sin servidor liberar recursos a medida que finalizan las funciones y compartir funciones entre hosts. La mayoría de los proveedores de nube limitan el tiempo total que puede ejecutar su función a unos 10 minutos. Ante la posibilidad de que su proceso dure más tiempo, puede considerar una implementación alternativa.

Hay algunas excepciones y soluciones. Una solución puede ser dividir su proceso en componentes más pequeños que, individualmente, tardan menos tiempo en ejecutarse. Si su proceso se ejecuta durante mucho tiempo debido a las dependencias, también puede considerar un flujo de trabajo asincrónico mediante una solución como funciones duraderas. Las funciones duraderas pausan y mantienen el estado de su proceso mientras espera a que finalice un proceso externo. El control asincrónico reduce el tiempo de ejecución del proceso real.

## <a name="startup-time"></a>Tiempo de inicio

Una preocupación potencial con respecto a las implementaciones sin servidor es el tiempo de inicio. Para conservar los recursos, muchos proveedores sin servidor crean infraestructura "a petición". Cuando una función sin servidor se desencadena transcurrido un período de tiempo, es posible que sea necesario crear o reiniciar los recursos que van a hospedar la función. En algunas situaciones, los arranques en frío pueden dar lugar a retrasos de varios segundos. El tiempo de inicio varía entre proveedores y niveles de servicio. Hay algunos enfoques para abordar el tiempo de inicio si es importante minimizarlo para el éxito de la aplicación.

- Algunos proveedores permiten a los usuarios pagar por los niveles de servicio que garantizan que la infraestructura esté "siempre activada".
- Implemente un mecanismo de supervivencia (haga ping al punto de conexión para mantenerlo "activo").
- Use la orquestación como Kubernetes con un enfoque de función en contenedores (el host ya se está ejecutando, por lo que se ponen en marcha nuevas instancias de forma muy rápida).

## <a name="database-updates-and-migrations"></a>Migraciones y actualizaciones de la base de datos

Una ventaja del código sin servidor es que puede lanzar nuevas funciones sin tener que volver a implementar toda la aplicación. Esta ventaja puede transformarse en una desventaja si hay una base de datos relacional implicada. Los cambios en los esquemas de la base de datos son difíciles de sincronizar con las actualizaciones sin servidor. Si se producen errores y deben revertirse los cambios, se plantean desafíos adicionales. La integridad de datos es una de las razones por las que un procedimiento recomendado para microservicios y funciones sin servidor consiste en que poseen sus propios datos. Es posible implementar los cambios como una sola unidad de proceso y datos. La realidad es que muchos sistemas heredados incluyen una base de datos de back-end de gran tamaño que debe reconciliarse con la arquitectura sin servidor.

Un enfoque popular para resolver la versión del esquema es no modificar nunca las propiedades y columnas existentes, sino agregar nueva información en su lugar. Por ejemplo, considere un cambio para pasar de una marca "completada" booleana para una lista de tareas pendientes a una "fecha de finalización". En lugar de quitar el campo anterior, el cambio de base de datos hará lo siguiente:

1. Agregará un nuevo campo "fecha de finalización".
1. Transformará el campo booleano "completado" en una función calculada que evalúe si la fecha de finalización es posterior a la fecha actual.
1. Agregue un desencadenador para establecer la fecha de finalización en la fecha actual al establecerse el valor booleano completado en true.

La secuencia de cambios garantiza que el código heredado siga ejecutándose "tal cual", mientras que funciones sin servidor más recientes pueden aprovechar el nuevo campo.

Para obtener más información sobre los datos de las arquitecturas sin servidor, consulte [Desafíos y soluciones de la administración de datos distribuidos](../microservices/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Cambiar escala

Un concepto erróneo muy común es que sin servidor significa "ningún servidor". Significa, de hecho, "menos servidor". El hecho de que haya una infraestructura de respaldo es importante para comprender cuándo se trata de escalado. La mayoría de las plataformas sin servidor proporcionan un conjunto de controles para controlar cómo debe escalarse la infraestructura al aumentar la densidad de eventos. Puede elegir entre varias opciones, pero su estrategia puede variar dependiendo de la función. Además, las funciones suelen ejecutarse en un host relacionado de modo que las funciones del mismo host tengan las mismas opciones de escala. Por lo tanto, es necesario organizar y elaborar estrategias sobre qué funciones se hospedan juntas en función de los requisitos de escala.

Las reglas suelen especificar cómo escalar verticalmente (aumentar los recursos de host) y escalar horizontalmente (aumentar el número de instancias de host) en función de diferentes parámetros. Los desencadenadores para escalas pueden incluir programación, tasas de solicitudes, uso de CPU y uso de memoria. Un mayor rendimiento suele acarrear un costo más elevado. Es posible que los enfoques basados en el consumo más económicos no se escalen tan rápido cuando la tasa de solicitudes aumente de forma repentina. Existe un equilibrio entre pagar por adelantado el "costo del seguro" frente a efectuar un pago "por uso" de forma estricta y arriesgar respuestas más lentas debido a repentinos aumentos de la demanda.

## <a name="monitoring-tracing-and-logging"></a>Supervisión, seguimiento y registro

Un aspecto que a menudo se pasa por alto de DevOps es la supervisión de aplicaciones una vez implementadas. Es importante tener una estrategia para supervisar funciones sin servidor. El mayor desafío suele ser la correlación, o bien reconocer cuándo llama un usuario a varias funciones como parte de la misma interacción. La mayoría de las plataformas sin servidor permiten un registro de consolas que se puede importar en herramientas de terceros. También hay opciones para automatizar la recopilación de telemetría, generar y realizar un seguimiento de identificadores de correlación y supervisar acciones específicas para proporcionar información detallada. Azure proporciona la [plataforma de Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) avanzada para la supervisión y el análisis.

## <a name="inter-service-dependencies"></a>Dependencias entre servicios

Una arquitectura sin servidor puede incluir funciones dependientes de otras funciones. De hecho, no es raro en una arquitectura sin servidor tener varios servicios que se llamen entre sí como parte de una interacción o transacción distribuida. Para evitar un acoplamiento fuerte, se recomienda que los servicios no se hagan referencia entre sí directamente. Si es necesario que el punto de conexión para un servicio cambie, las referencias directas pueden dar lugar a una refactorización importante. Una solución recomendada consiste en proporcionar un mecanismo de detección de servicios, como un registro, que proporciona el punto de conexión adecuado para un tipo de solicitud. Otra solución es aprovechar servicios de mensajería como colas o temas para la comunicación entre servicios.

## <a name="managing-failure-and-providing-resiliency"></a>Error al administrar y provisión de resistencia

También es importante tener en cuenta el *patrón de interruptor*: Si, por algún motivo, un servicio sigue dando error, no es aconsejable llamar a ese servicio de manera repetida. En su lugar, se llama a un servicio alternativo o se devuelve un mensaje hasta que se restablece el estado del servicio dependiente. La arquitectura sin servidor debe tener en cuenta la estrategia para resolver y administrar las dependencias entre servicios.

Para proseguir con el patrón de interruptor, los servicios deben ser tolerantes a errores y resistentes. La tolerancia a errores hace referencia a la capacidad de su aplicación para seguir ejecutándose incluso después de encontrarse excepciones inesperadas o estados no válidos. La tolerancia a errores suele ser una función del propio código y cómo se escribe para controlar las excepciones. La resistencia hace referencia a la capacidad de la aplicación para recuperarse de los errores. La plataforma sin servidor suele administrar la resistencia. La plataforma debe poder poner en marcha una nueva instancia de función sin servidor cuando se produce un error en la existente. La plataforma también debe ser lo suficientemente inteligente como para poner en marcha nuevas instancias cuando se produce un error en todas las instancias nuevas.

Para más información, consulte [Implementar el patrón de interruptor](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Control de versiones e implementaciones azul-verde

Una ventaja importante de sin servidor es la capacidad de actualizar una función específica sin tener que volver a implementar toda la aplicación. Para que las actualizaciones se realicen correctamente, se deben realizar versiones de las funciones de modo que los servicios que las llaman se enruten a la versión correcta del código. Una estrategia para implementar nuevas versiones también es importante. Un enfoque habitual es usar "implementaciones azul-verde". La implementación verde es la función actual. Una nueva versión "azul" se implementa en producción y se prueba. Al superarse las pruebas, las versiones verde y azul se intercambian, de modo que la nueva versión se pone en marcha. Si se detecta algún problema, pueden volver a intercambiarse. La compatibilidad con el control de versiones y las implementaciones azul-verde requiere una combinación de creación de las funciones para alojar los cambios de versión y trabajo con la plataforma sin servidor para controlar las implementaciones.

>[!div class="step-by-step"]
>[Anterior](serverless-architecture.md)
>[Siguiente](serverless-design-examples.md)
