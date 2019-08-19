---
title: 'Ejemplos de diseño sin servidor: aplicaciones sin servidor'
description: Comprenda la variedad de escenarios admitidos por las arquitecturas sin servidor, desde la programación y el procesamiento basado en eventos hasta los desencadenadores de archivos y el proceso de flujo.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 096dce6ef23bde5ef9c6ca65769f4dcc7e08a904
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "69577198"
---
# <a name="serverless-design-examples"></a>Ejemplos de diseño sin servidor

Existen muchos patrones de diseño que existen para sin servidor. En esta sección se capturan algunos escenarios comunes en los que se usa sin servidor. Lo que todos los ejemplos tienen en común es la combinación fundamental de un desencadenador de eventos y una lógica de negocios.

## <a name="scheduling"></a>Programación

La programación de tareas es una función común. En el diagrama siguiente se muestra una base de datos heredada que no tiene comprobaciones de integridad adecuadas. La base de datos debe borrarse periódicamente. La función sin servidor busca datos no válidos y los limpia. El desencadenador es un temporizador que ejecuta el código según una programación.

![Programación sin servidor](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Segregación de responsabilidades de comandos y consultas (CQRS)

Segregación de responsabilidades de comandos y consultas (CQRS) es un patrón que proporciona diferentes interfaces para leer (o consultar) los datos y las operaciones que modifican los datos. Soluciona varios problemas comunes. En los sistemas basados en creación de eliminación de actualización de lectura (CRUD) tradicionales, pueden surgir conflictos del gran volumen de lecturas y escrituras en el mismo almacén de datos. El bloqueo puede producirse con frecuencia y ralentizar considerablemente las lecturas. A menudo, los datos se presentan como una composición de varios objetos de dominio y las operaciones de lectura deben combinar datos de distintas entidades.

Con CQRS, una lectura puede implicar una entidad especial "plana" que modela los datos de la forma en que se consumen. La lectura se trata de forma diferente a como se almacena. Por ejemplo, aunque la base de datos puede almacenar un contacto como un registro de encabezado con un registro de dirección secundario, la lectura puede implicar una entidad con propiedades de encabezado y dirección. Existen infinidad de métodos para crear el modelo de lectura. Podría materializarse a partir de vistas. Las operaciones de actualización se pueden encapsular como eventos aislados que luego desencadenan actualizaciones en dos modelos diferentes. Existen modelos independientes para lectura y escritura.

![Ejemplo de CQRS](./media/cqrs-example.png)

Sin servidor puede alojar el patrón CQRS proporcionando los puntos de conexión segregados. Una función sin servidor admite consultas o lecturas, y una función o un conjunto de funciones sin servidor diferente controla las operaciones de actualización. Una función sin servidor también puede ser responsable de mantener actualizado el modelo de lectura y se puede desencadenar mediante la [fuente de cambios](https://docs.microsoft.com/azure/cosmos-db/change-feed)de la base de datos. El desarrollo de front-end se ha simplificado para conectarse a los puntos de conexión necesarios. El procesamiento de eventos se controla en el back-end. Este modelo también se escala bien para los proyectos de gran tamaño porque diferentes equipos pueden trabajar en diferentes operaciones.

## <a name="event-based-processing"></a>Procesamiento basado en eventos

En los sistemas basados en mensajes, los eventos se suelen recopilar en las colas o en los temas del publicador y del suscriptor sobre los que se va a actuar. Estos eventos pueden desencadenar funciones sin servidor para ejecutar una lógica de negocios. Un ejemplo de procesamiento basado en eventos son los sistemas de origen de eventos. Se genera un "evento" para marcar una tarea como completada. Una función sin servidor desencadenada por el evento actualiza el documento de base de datos adecuado. Una segunda función sin servidor puede usar el evento para actualizar el modelo de lectura para el sistema. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) proporciona una manera de integrar eventos con funciones como suscriptores.

> Los eventos son mensajes informativos. Para obtener más información, vea [patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Desencadenadores y transformaciones de archivos

Extraer, transformar y cargar (ETL) es una función empresarial común. Sin servidor es una excelente solución para ETL porque permite que el código se desencadene como parte de una canalización. Los componentes de código individuales pueden abordar diversos aspectos. Una función sin servidor puede descargar el archivo, otro aplica la transformación y otro carga los datos. El código se puede probar e implementar de forma independiente, lo que facilita el mantenimiento y el escalado cuando sea necesario.

![Desencadenadores y transformaciones de archivos sin servidor](./media/serverless-file-triggers.png)

En el diagrama, "almacenamiento de acceso esporádico" proporciona los datos que se analizan en [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics). Cualquier problema encontrado en el flujo de datos desencadena una función de Azure para resolver la anomalía.

## <a name="asynchronous-background-processing-and-messaging"></a>Procesamiento y mensajería en segundo plano asíncronos

La mensajería asincrónica y el procesamiento en segundo plano permiten a las aplicaciones iniciar procesos sin tener que esperar. Un ejemplo de procesamiento asincrónico es una aplicación de OCR. Se envía una imagen y se pone en cola para su procesamiento. El análisis de la imagen para extraer texto puede tardar tiempo y, una vez finalizada, se envía una notificación. Sin servidor puede controlar tanto la invocación como el resultado en este escenario.

## <a name="web-apps-and-apis"></a>Web Apps y API

Un escenario popular de sin servidor son las aplicaciones de N niveles, que suelen ser donde la capa de la interfaz de usuario es una aplicación Web. La popularidad de las aplicaciones de una sola página (SPA) ha sobrecargado recientemente. Las aplicaciones de SPA representan una sola página y luego confían en las llamadas API y los datos devueltos para representar dinámicamente la nueva interfaz de usuario sin volver a cargar una página completa. La representación del lado cliente proporciona una aplicación mucho más rápida y con mayor capacidad de respuesta para el usuario final.

Los puntos de conexión sin servidor desencadenados por llamadas HTTP se pueden usar para controlar las solicitudes de API. Por ejemplo, una empresa de servicios de ad puede llamar a una función sin servidor con información de Perfil de usuario para solicitar publicidad personalizada. La función sin servidor devuelve el anuncio personalizado y la página web lo representa.

![API Web sin servidor](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Canalización de datos

Las funciones sin servidor se pueden usar para facilitar una canalización de datos. En este ejemplo, un archivo desencadena una función para convertir los datos de un archivo CSV en filas de datos de una tabla. La tabla organizada permite que un panel de Power BI presente el análisis al usuario final.

![Canalización de datos sin servidor](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Procesamiento de flujos

Los dispositivos y sensores suelen generar flujos de datos que se deben procesar en tiempo real. Hay una serie de tecnologías que pueden capturar mensajes y secuencias de [Event hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs) y [IOT Hub](https://docs.microsoft.com/azure/iot-hub) a [Service Bus](https://docs.microsoft.com/azure/service-bus). Independientemente del transporte, el modo sin servidor es un mecanismo ideal para procesar los mensajes y los flujos de datos a medida que llegan. Sin servidor se puede escalar rápidamente para satisfacer la demanda de grandes volúmenes de datos. El código sin servidor puede aplicar la lógica de negocios para analizar los datos y la salida en un formato estructurado para la acción y el análisis.

![Procesamiento de flujos sin servidor](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Puerta de enlace de API

Una puerta de enlace de API proporciona un único punto de entrada para los clientes y, a continuación, enruta de forma inteligente las solicitudes a los servicios back-end. Resulta útil para administrar grandes conjuntos de servicios. También puede controlar el control de versiones y simplificar el desarrollo mediante la conexión sencilla de clientes a entornos dispares. Sin servidor puede controlar el escalado de back-end de microservicios individuales, a la vez que presenta un único front-end a través de una puerta de enlace de API.

![Puerta de enlace de API sin servidor](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Recursos recomendados

* [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
* [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub)
* [Desafíos y soluciones de la administración de datos distribuidos](../microservices/architect-microservice-container-applications/distributed-data-management.md)
* [Diseño de microservicios: identificación de los límites de microservicios](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
* [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
* [Patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
* [Implementar el patrón de interruptor](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
* [IoT Hub](https://docs.microsoft.com/azure/iot-hub)
* [Service Bus](https://docs.microsoft.com/azure/service-bus)
* [Trabajar con la compatibilidad con la fuente de cambios en Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Anterior](serverless-architecture-considerations.md)
>[Siguiente](azure-serverless-platform.md)
