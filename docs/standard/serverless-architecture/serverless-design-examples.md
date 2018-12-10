---
title: Ejemplos de diseño sin servidor - aplicaciones sin servidor
description: Comprender la variedad de escenarios admitidos por las arquitecturas sin servidor y de programación y procesamiento basado en eventos a los desencadenadores de archivo y el proceso de flujo.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: cf46c601ac6aa401c7c37bd64c1f8981589ebd2e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53146717"
---
# <a name="serverless-design-examples"></a>Ejemplos de diseño sin servidor

Hay muchos patrones de diseño que existen para sin servidor. Esta sección presenta algunos escenarios comunes que utilizan sin servidor. Lo que todos los ejemplos tienen en común es la combinación de una evento desencadenador y la lógica empresarial fundamental.

## <a name="scheduling"></a>La programación

Programación de tareas es una función común. El siguiente diagrama muestra una base de datos heredado que no tiene las comprobaciones de integridad adecuado. La base de datos debe eliminarse periódicamente. La función sin servidor busca datos no válidos y limpia. El desencadenador es un temporizador que se ejecuta el código según una programación.

![Programación sin servidor](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Comando y Query Responsibility Segregation (CQRS)

Comando y Query Responsibility Segregation (CQRS) es un patrón que proporciona datos de distintas interfaces para leer (o consultar) y las operaciones que modifican datos. Aborda varios problemas comunes. En los sistemas tradicionales de creación de lectura actualización eliminación (CRUD) en función, pueden surgir conflictos de gran volumen de lecturas y escrituras en el mismo almacén de datos. Es posible que con frecuencia se producen y bloqueo ralentizar considerablemente las lecturas. A menudo, los datos se presentan como una composición de varios objetos de dominio y las operaciones de lectura debe combinar datos de entidades diferentes.

Uso de CQRS, una lectura puede implicar una entidad de "plana" especial que modela los datos de la manera en que se consume. La lectura se controla de forma diferente a cómo se almacenan. Por ejemplo, aunque la base de datos puede almacenar un contacto como un registro de encabezado con un registro de direcciones secundarias, la lectura podría conllevar una entidad con el encabezado y propiedades de dirección. Existen innumerables enfoques para crear el modelo de lectura. Es posible que se puede materializar lo de vistas. Las operaciones de actualización se pueden encapsular como eventos aislados que, a continuación, desencadenan actualizaciones a dos modelos diferentes. Existen modelos independientes para leer y escribir.

![Ejemplo CQRS](./media/cqrs-example.png)

Sin servidor puede alojar el patrón CQRS, ya que proporciona los puntos de conexión segregadas. Las consultas o las lecturas contempla una función sin servidor y una función sin servidor diferente o un conjunto de funciones controla las operaciones de actualización. Una función sin servidor también puede ser responsable de mantener actualizado el modelo de lectura y se puede activar la base de datos [fuente de cambios](https://docs.microsoft.com/azure/cosmos-db/change-feed). Desarrollo de front-end se ha simplificado para conectarse a los extremos necesarios. Controla el procesamiento de eventos en el back-end. Este modelo también se ajusta bien a proyectos de gran tamaño dado que diferentes equipos pueden funcionar en diferentes operaciones.

## <a name="event-based-processing"></a>Procesamiento basado en eventos

En sistemas basados en mensajes, los eventos se recopilan con frecuencia en colas o temas de publicador y suscriptor que se debe actuar. Estos eventos pueden desencadenar las funciones sin servidor para ejecutar una parte de la lógica de negocios. Un ejemplo de procesamiento basado en eventos es sistemas de origen de eventos. Se genera un "evento" para marcar una tarea como completada. Una función sin servidor que desencadenó el evento actualizará el documento de base de datos adecuada. Una segunda función sin servidor puede usar el evento para actualizar el modelo de lectura para el sistema. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) proporciona una manera de integrar los eventos con funciones como suscriptores.

> Los eventos son mensajes informativos. Para obtener más información, consulte [patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Los desencadenadores de archivo y transformaciones

Extraer, transformar y carga (ETL) es una función empresarial común. Sin servidor es una excelente solución para ETL porque permite código que se desencadenan como parte de una canalización. Los componentes de código individuales pueden abordar diversos aspectos. Una función sin servidor puede descargar el archivo, sí aplica la transformación y otra carga los datos. El código puede probar e implementar de forma independiente, facilitando la tarea de mantener y escalar cuando sea necesario.

![Las transformaciones y los desencadenadores de archivo sin servidor](./media/serverless-file-triggers.png)

En el diagrama, "almacenamiento de acceso esporádico" proporciona los datos que se analizan en [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics). Los problemas encontrados en el flujo de datos desencadenan una función de Azure para abordar las anomalías.

## <a name="asynchronous-background-processing-and-messaging"></a>Procesamiento asincrónico en segundo plano y mensajería

Mensajería asincrónica y procesamiento en segundo plano permiten a las aplicaciones a fin de iniciar los procesos sin tener que esperar. Un ejemplo de procesamiento asincrónico es una aplicación de reconocimiento óptico de caracteres. Una imagen se envía y se ponen en cola para su procesamiento. Digitalizar la imagen para extraer el texto puede tardar tiempo y se envía una vez finalizada una notificación. La invocación y el resultado en este escenario, puede controlar sin servidor.

## <a name="web-apps-and-apis"></a>Las API y aplicaciones web.

Un escenario popular para sin servidor es N-tier aplicaciones, con más frecuencia en las que la capa de interfaz de usuario es una aplicación web. La popularidad de las aplicaciones de página única (SPA) se disparó recientemente. Aplicaciones SPA representan una sola página, a continuación, se basan en las llamadas de API y los datos devueltos para representar dinámicamente la nueva interfaz de usuario sin volver a cargar una página completa. Representación del lado cliente proporciona una aplicación mucho más rápida, mayor capacidad de respuesta al usuario final.

Los puntos de conexión sin servidor desencadenadas mediante llamadas HTTP pueden utilizarse para controlar las solicitudes de API. Por ejemplo, una empresa de servicios de ad puede llamar a una función sin servidor con información de perfil de usuario para solicitar la publicidad personalizada. La función sin servidor devuelve ad personalizado y lo representa la página web.

![API de web sin servidor](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Canalización de datos

Funciones sin servidor se pueden usar para facilitar una canalización de datos. En este ejemplo, un archivo desencadena una función para convertir datos en un archivo CSV para las filas de datos en una tabla. La tabla organizada permite que un panel de Power BI para análisis de presentar al usuario final.

![Canalización de datos sin servidor](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Procesamiento de Stream

Dispositivos y sensores suelen generan flujos de datos que se deben procesar en tiempo real. Hay una serie de tecnologías que pueden capturar los mensajes y secuencias de [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) y [IoT Hub](https://docs.microsoft.com/azure/iot-hub) a [Service Bus](/service-bus). Independientemente del transporte, sin servidor es un mecanismo ideal para procesar los mensajes y los flujos de datos tal y como vienen. Sin servidor puede escalar con rapidez para satisfacer la demanda de grandes volúmenes de datos. El código sin servidor puede aplicar la lógica de negocios para analizar los datos y la salida en un formato estructurado para el análisis y acción.

![Procesamiento de secuencias sin servidor](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Puerta de enlace de API

Una puerta de enlace de API proporciona un único punto de entrada para los clientes y, a continuación, enruta las solicitudes de forma inteligente a servicios back-end. Es útil administrar grandes conjuntos de servicios. También puede controlar las versiones y simplificar el desarrollo conectando fácilmente los clientes con entornos diferentes. Puede controlar sin servidor back-end escalado de los microservicios individuales, mientras presenta un único front-end a través de una puerta de enlace de API.

![Puerta de enlace de API sin servidor](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Recursos recomendados

* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [IoT Hub de Azure](https://docs.microsoft.com/azure/iot-hub)
* [Desafíos y soluciones de la administración de datos distribuidos](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md)
* [Diseño de microservicios: identificación de los límites del microservicio](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
* [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
* [Patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
* [Implementar el patrón de interruptor](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md)
* [Centro de IoT](https://docs.microsoft.com/azure/iot-hub)
* [Bus de servicio](https://docs.microsoft.com/azure/service-bus)
* [Trabajar con el cambio de compatibilidad con la fuente en Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Anterior](serverless-architecture-considerations.md)
>[Siguiente](azure-serverless-platform.md)