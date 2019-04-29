---
title: 'Consideraciones de arquitectura sin servidor: aplicaciones sin servidor'
description: Comprender los desafíos de la arquitectura de aplicaciones sin servidor, desde el almacenamiento persistente para escalar y la administración del estado de registro, seguimiento y diagnóstico.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b12a09c0fcef7e7ff954a3f959fb9e3080a6e859
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940951"
---
# <a name="serverless-architecture-considerations"></a>Consideraciones sobre la arquitectura sin servidor

Adoptar una arquitectura sin servidor incluyen algunos desafíos. Esta sección explora algunas de las consideraciones más comunes a tener en cuenta. Todos estos desafíos tienen soluciones. Al igual que con todas las opciones de arquitectura, la decisión de cambiar a sin servidor debe realizarse después de considerar cuidadosamente las ventajas y desventajas. Según las necesidades de su aplicación, puede decidir que una implementación sin servidor no es la solución adecuada para ciertos componentes.

## <a name="managing-state"></a>Estado de administración

Funciones sin servidor, al igual que con los microservicios en general, no tienen estadas de forma predeterminada. Estado evitando permite sin servidor sea efímera, para escalar horizontalmente y para proporcionar resistencia sin un punto central de error. En algunas circunstancias, los procesos empresariales requieren el estado. Si el proceso requiere el estado, tiene dos opciones. Puede adoptar un modelo que no sea sin servidor, o interactuar con un servicio independiente que proporciona el estado. Agregar estado puede complicar la solución y que sea más difícil de escalar lo que puede crear un único punto de error. Considere detenidamente si la función requiere absolutamente estado. Si la respuesta es "Sí", determine si todavía tiene sentido implementarla con sin servidor.

Existen varias soluciones para adoptar el estado sin poner en peligro las ventajas de sin servidor. Algunas de las soluciones más populares son:

* Usar un almacén de datos temporal o una caché distribuida, como Redis
* Estado de Store en una base de datos, como SQL o CosmosDB
* Administrar el estado a través de un motor de flujo de trabajo como durable functions

La conclusión es que debe tener en cuenta la necesidad de administración de cualquier estado dentro de los procesos que se está considerando la posibilidad de implementar con sin servidor.

## <a name="long-running-processes"></a>Procesos de larga ejecución

Muchas de las ventajas de sin servidor se basan en los procesos que se va a efímero. Tiempos de ejecución breves facilitan el proveedor sin servidor liberar los recursos que las funciones funciones final y recurso compartido a través de hosts. La mayoría de los proveedores de nube limita el tiempo total que se puede ejecutar la función a unos 10 minutos. Si el proceso puede tardar más tiempo, es posible que considere la posibilidad de una implementación alternativa.

Hay algunas excepciones y las soluciones. Una solución podría ser que interrumpir el proceso de componentes más pequeños que individualmente tardan menos tiempo en ejecutarse. Si se ejecuta el proceso de tiempo debido a las dependencias, también puede considerar un flujo de trabajo asincrónico mediante una solución como durable functions. Durable functions pausar y mantienen el estado del proceso mientras está en espera en un proceso externo para finalizar. Control asincrónico reduce el tiempo que se ejecuta el proceso real.

## <a name="startup-time"></a>Tiempo de inicio

Un problema potencial con implementaciones sin servidor es el tiempo de inicio. Para ahorrar recursos, muchos proveedores sin servidor crean infraestructura "a"petición. Cuando se desencadena una función sin servidor tras un período de tiempo, los recursos necesarios para hospedar la función que deba se creó o se reinició. En algunas situaciones, arranques en frío pueden provocar retrasos de varios segundos. Tiempo de inicio varía entre los proveedores y los niveles de servicio. Si es importante minimizar el éxito de la aplicación, hay varios enfoques a la hora de inicio de dirección.

* Algunos proveedores de permiten a los usuarios que pagar por los niveles de servicio que garantizan la infraestructura es "siempre activado".
* Implementar un mecanismo keep-alive (ping el punto de conexión para mantener "activo").
* Utilice la orquestación, como Kubernetes con un enfoque de la función en contenedores (el host ya se está ejecutando por lo que es extremadamente rápida marcha nuevas instancias).

## <a name="database-updates-and-migrations"></a>Las actualizaciones de la base de datos y las migraciones

Una ventaja de código sin servidor es la versión de nuevas funciones sin tener que volver a implementar toda la aplicación. Esta ventaja puede ser un inconveniente cuando hay una base de datos relacional implicada. Los cambios realizados en los esquemas de base de datos son difíciles de sincronizar con las actualizaciones sin servidor. Cuando algo va mal y se deben deshacer los cambios, se enfrenta desafíos adicionales. Integridad de los datos es una razón una práctica recomendada para los microservicios y las funciones sin servidor es que poseen sus propios datos. Es posible implementar los cambios como una sola unidad de proceso y datos. La realidad es que muchos sistemas heredados de características una gran base de datos de back-end debe ser conforme con la arquitectura sin servidor.

Un enfoque popular para resolver las versiones del esquema es nunca modificar las propiedades existentes y las columnas, pero en su lugar, agregue la nueva información. Por ejemplo, considere la posibilidad de un cambio para pasar de un valor booleano "completado" marca de una lista de tareas con una "fecha de finalización". En lugar de quitar el campo anterior, el cambio de base de datos hará lo siguiente:

1. Agregue un campo nuevo "fecha de finalización".
1. Transformar el campo booleano "completado" a una función calculada que evalúa si la fecha de finalización es posterior a la fecha actual.
1. Agregar un desencadenador para establecer la fecha de finalización en la fecha actual cuando se establece el valor booleano completado en true.

La secuencia de cambios garantiza que continuará ejecutándose "tal cual" mientras que funciones sin servidor más reciente pueden aprovechar las ventajas del nuevo campo de código heredado.

Para obtener más información acerca de los datos en las arquitecturas sin servidor, consulte [desafíos y soluciones de administración de datos de distribuidas](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md).

## <a name="scaling"></a>Cambiar escala

Es una idea equivocada habitual que sin servidor significa "sin servidor". De hecho, es "menos server". El hecho de que hay es que una infraestructura de copia de seguridad es importante comprender que cuando se trata de escalado. Sin servidor más plataformas proporcionan un conjunto de controles para controlar cómo la infraestructura debe escalar cuando aumenta la densidad del evento. Puede elegir entre una variedad de opciones, pero la estrategia puede variar dependiendo de la función. Además, las funciones se ejecutan normalmente en un host relacionadas, para que las funciones en el mismo host tienen las mismas opciones de escalado. Por lo tanto, es necesario organizar y desarrollar estrategias para las funciones que se hospedan en función de los requisitos de escala.

A menudo, las reglas especifican cómo escalar verticalmente (aumentar los recursos del host) y la escalabilidad horizontal (aumentar el número de instancias de host) en función de parámetros diferentes. Los desencadenadores para las escalas pueden incluir programación, velocidad de solicitudes, uso de CPU y uso de memoria. A menudo un rendimiento más alto tiene un costo mayor. Los enfoques menos costosos, basado en consumo no se pueden escalar a medida que rápidamente cuando la tasa de solicitud, de repente, aumenta. Hay un equilibrio entre pago anticipado "costo seguros" frente a pagar estrictamente "que usted vaya" y corre el riesgo de las respuestas más lentas debido a aumentos repentinos en la demanda.

## <a name="monitoring-tracing-and-logging"></a>Supervisión, el seguimiento y registro

Un aspecto muy a menudo soslayado de DevOps está supervisando las aplicaciones una vez implementadas. Es importante tener una estrategia para la supervisión de funciones sin servidor. El mayor desafío es a menudo correlación o reconocer cuando un usuario llama a varias funciones como parte de la interacción con el misma. Sin servidor más plataformas permiten la consola de registro que se puede importar a las herramientas de terceros. También hay opciones para automatizar la recopilación de telemetría, generar y realizar un seguimiento de los identificadores de correlación y supervisar las acciones específicas para proporcionar información detallada. Azure proporciona el avanzado [plataforma de Application Insights](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) para la supervisión y análisis.

## <a name="inter-service-dependencies"></a>Dependencias entre servicios

Una arquitectura sin servidor puede incluir funciones que dependen de otras funciones. De hecho, no es raro en una arquitectura sin servidor tener varios servicios se llaman entre sí como parte de una interacción o la transacción distribuida. Para evitar el acoplamiento seguro, se recomienda que los servicios no hacen referencia entre sí directamente. Cuando necesita cambiar el punto de conexión para un servicio, las referencias directas podrían refactorización principales. Una solución sugerida es proporcionar un mecanismo de detección de servicio, como un registro, que proporciona el punto final adecuado para un tipo de solicitud. Otra solución consiste en aprovechar los servicios de mensajes como colas o temas para la comunicación entre servicios.

## <a name="managing-failure-and-providing-resiliency"></a>Administración de errores y proporcionar resistencia

También es importante tener en cuenta la *patrón circuit breaker*: Si por algún motivo, un servicio sigue dando error, no es aconsejable llamar repetidamente a ese servicio. En su lugar, se llama a un servicio alternativo o devuelve un mensaje hasta que se restablece el estado del servicio dependiente. La arquitectura sin servidor debe tener en cuenta la estrategia para resolver y administrar las dependencias entre servicios.

Para continuar con el patrón circuit breaker, servicios deben ser tolerante a errores y resistente. Tolerancia a errores hace referencia a la capacidad de la aplicación continúe ejecutándose incluso después de las excepciones inesperadas o Estados no válidos se encuentran. Tolerancia a errores normalmente es una función del propio código y cómo ha escrito controlar las excepciones. Resistencia se refiere a cómo compatibles con la aplicación se encuentra en recuperarse de errores. Resistencia a menudo se administra mediante la plataforma sin servidor. La plataforma debe ser capaz de poner en marcha una nueva instancia de la función sin servidor cuando se produce un error en uno existente. La plataforma también debe ser lo suficientemente inteligente como para detener marcha nuevas instancias cuando se produce un error en todas las instancias nuevas.

Para obtener más información, consulte [implementar el patrón de disyuntor](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md).

## <a name="versioning-and-greenblue-deployments"></a>Implementaciones de control de versiones y verde/azul

Una ventaja importante de sin servidor es la capacidad para actualizar una función específica sin tener que volver a implementar toda la aplicación. Las actualizaciones se realice correctamente, las funciones deben ser con control de versiones para que los servicios al llamarlas se enrutan a la versión correcta del código. Una estrategia para implementar nuevas versiones también es importante. Un enfoque común consiste en utilizar "verde/azul implementaciones." La implementación de verde es la función actual. Una nueva versión de "blue" se implementa en producción y probada. Cuando se pasan las pruebas, se intercambian las versiones de verdes y azules para que la nueva versión viene en vivo. Si se encuentra algún problema, puede intercambiar volver. Compatibilidad con control de versiones y las implementaciones azul/verde requiere una combinación de las funciones para dar cabida a los cambios de versión de creación y trabajar con la plataforma sin servidor para controlar las implementaciones. Un posible enfoque es utilizar servidores proxy, que se describen en la [plataforma sin servidor Azure](azure-functions.md#proxies) capítulo.

>[!div class="step-by-step"]
>[Anterior](serverless-architecture.md)
>[Siguiente](serverless-design-examples.md)