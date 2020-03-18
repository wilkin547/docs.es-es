---
title: 'Ejemplos de diseño sin servidor: aplicaciones sin servidor'
description: Comprenda la variedad de escenarios admitidos por las arquitecturas sin servidor, desde la programación y el procesamiento basado en eventos hasta los desencadenadores de archivos y el proceso de flujo.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4e8fda0c1423c881c0807602e11f7c49ff7cfe4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "73093556"
---
# <a name="serverless-design-examples"></a>Ejemplos de diseño sin servidor

Hay muchos patrones de diseño que existen para el modo sin servidor. En esta sección se capturan algunos escenarios comunes en los que se usa este modelo. Lo que todos los ejemplos tienen en común es la combinación fundamental de un desencadenador de eventos y una lógica de negocios.

## <a name="scheduling"></a>Scheduling

Las tareas de programación es una función común. En el diagrama siguiente se muestra una base de datos heredada que no tiene comprobaciones de integridad adecuadas. La base de datos debe limpiarse periódicamente. La función sin servidor busca datos no válidos y los limpia. El desencadenador es un temporizador que ejecuta el código de forma programada.

![Programación sin servidor](./media/serverless-scheduling.png)

## <a name="command-and-query-responsibility-segregation-cqrs"></a>Segregación de responsabilidades de consultas y comandos (CQRS)

La segregación de responsabilidades de comandos y consultas (CQRS) es un patrón que proporciona diferentes interfaces para leer (o consultar) los datos y las operaciones que modifican los datos. Aborda varios problemas comunes. En los sistemas tradicionales basados CRUD (crear, leer, actualizar y eliminar), pueden surgir conflictos del gran volumen de lecturas y escrituras en el mismo almacén de datos. El bloqueo puede producirse con frecuencia, con lo que se ralentizan considerablemente las lecturas. A menudo, los datos se presentan como una composición de varios objetos de dominio y las operaciones de lectura deben combinar datos de distintas entidades.

Con CQRS, una lectura puede implicar una entidad especial "aplanada" que modela los datos de la forma en que se consumen. La lectura se trata de forma diferente a como se almacena. Por ejemplo, aunque la base de datos puede almacenar un contacto como un registro de encabezado con un registro de dirección secundario, la lectura puede implicar una entidad con propiedades de encabezado y dirección. Existen infinidad enfoques para la creación del modelo de lectura. Podría materializarse a partir de vistas. Las operaciones de actualización se pueden encapsular como eventos aislados que luego desencadenan actualizaciones en dos modelos diferentes. Existen modelos independientes para lectura y escritura.

![Ejemplo de CQRS](./media/cqrs-example.png)

El modo sin servidor puede alojar el patrón CQRS al proporcionar los puntos de conexión segregados. Una función sin servidor admite consultas o lecturas, y otra función o conjunto de funciones sin servidor controla las operaciones de actualización. Una función sin servidor también puede ser responsable de mantener actualizado el modelo de lectura y lo puede desencadenar la [fuente de cambios](https://docs.microsoft.com/azure/cosmos-db/change-feed) de la base de datos. El desarrollo de front-end se ha simplificado para conectarse a los puntos de conexión necesarios. El procesamiento de eventos se controla en el back-end. Este modelo también se escala bien para los proyectos de gran tamaño porque diferentes equipos pueden trabajar en distintas operaciones.

## <a name="event-based-processing"></a>Procesamiento basado en eventos

En los sistemas basados en mensajes, los eventos se suelen recopilar en las colas o en los temas del publicador y del suscriptor sobre los que se va a actuar. Estos eventos pueden desencadenar funciones sin servidor para ejecutar una lógica de negocios. Un ejemplo de procesamiento basado en eventos son los sistemas de origen de eventos. Se genera un "evento" para marcar una tarea como completada. Una función sin servidor desencadenada por el evento actualiza el documento de base de datos adecuado. Una segunda función sin servidor puede usar el evento para actualizar el modelo de lectura para el sistema. [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview) proporciona una manera de integrar eventos con funciones como suscriptores.

> Los eventos son mensajes informativos. Para más información, consulte [Patrón de origen de eventos](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing).

## <a name="file-triggers-and-transformations"></a>Desencadenadores y transformaciones de archivos

La función de extracción, transformación y carga de datos (ETL) es una función empresarial común. El modo sin servidor es una excelente solución para ETL porque permite que el código se desencadene como parte de una canalización. Los componentes de código individuales pueden abordar diversos aspectos. Una función sin servidor puede descargar el archivo, otra aplica la transformación y otra carga los datos. El código se puede probar e implementar de forma independiente, lo que facilita el mantenimiento y la escala cuando sea necesario.

![Desencadenadores y transformaciones de archivos sin servidor](./media/serverless-file-triggers.png)

En el diagrama, "almacenamiento de acceso esporádico" proporciona los datos que se analizan en [Azure Stream Analytics](https://docs.microsoft.com/azure/stream-analytics). Cualquier problema encontrado en el flujo de datos desencadena una función de Azure para resolver la anomalía.

## <a name="asynchronous-background-processing-and-messaging"></a>Mensajería y procesamiento en segundo plano asincrónicos

La mensajería y el procesamiento en segundo plano asincrónicos permiten a las aplicaciones iniciar procesos sin tener que esperar. Un ejemplo de procesamiento asincrónico es una aplicación de OCR. Se envía una imagen y se pone en cola para su procesamiento. El análisis de la imagen para extraer texto puede tardar tiempo y, una vez finalizado, se envía una notificación. El modo sin servidor puede controlar tanto la invocación como el resultado en este escenario.

## <a name="web-apps-and-apis"></a>Web Apps y API

Un escenario popular para un modo sin servidor son las aplicaciones de n niveles, que suelen ser donde la capa de la interfaz de usuario es una aplicación web. La popularidad de las aplicaciones de página única (SPA) ha surgido recientemente. Las aplicaciones SPA representan una sola página y luego confían en las llamadas API y en los datos devueltos para representar dinámicamente la nueva interfaz de usuario sin volver a cargar una página completa. La representación del lado cliente proporciona una aplicación mucho más rápida y con mayor capacidad de respuesta para el usuario final.

Se pueden usar los puntos de conexión sin servidor desencadenados por llamadas HTTP para controlar las solicitudes de API. Por ejemplo, una empresa de servicios de anuncios publicitarios puede llamar a una función sin servidor con información del perfil de usuario para solicitar publicidad personalizada. La función sin servidor devuelve el anuncio personalizado y la página web lo representa.

![API de web sin servidor](./media/serverless-web-api.png)

## <a name="data-pipeline"></a>Canalización de datos

Las funciones sin servidor se pueden usar para facilitar una canalización de datos. En este ejemplo, un archivo desencadena una función para convertir los datos de un archivo CSV en filas de datos de una tabla. La tabla organizada permite que un panel de Power BI presente el análisis al usuario final.

![Canalización de datos sin servidor](./media/serverless-data-pipeline.png)

## <a name="stream-processing"></a>Procesamiento de flujos

Los dispositivos y sensores suelen generar flujos de datos que se deben procesar en tiempo real. Hay una serie de tecnologías que pueden capturar mensajes y flujos de [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)e [IoT Hub](https://docs.microsoft.com/azure/iot-hub) a [Service Bus](https://docs.microsoft.com/azure/service-bus). Independientemente del transporte, el modo sin servidor es un mecanismo ideal para procesar los mensajes y los flujos de datos a medida que llegan. El modo sin servidor se puede escalar rápidamente para satisfacer la demanda de grandes volúmenes de datos. El código sin servidor puede aplicar la lógica de negocios para analizar los datos y la salida en un formato estructurado para la acción y el análisis.

![Procesamiento de flujo sin servidor](./media/serverless-stream-processing.png)

## <a name="api-gateway"></a>Puerta de enlace de API

Una puerta de enlace de API proporciona un único punto de entrada para los clientes y, a continuación, enruta de forma inteligente las solicitudes a los servicios back-end. Resulta útil para administrar grandes conjuntos de servicios. También puede tratar el control de versiones y simplificar el desarrollo mediante la conexión sencilla de clientes a entornos dispares. El modo sin servidor puede controlar el escalado de back-end de microservicios individuales, a la vez que presenta un único front-end mediante una puerta de enlace de API.

![Puerta de enlace de API sin servidor](./media/serverless-api-gateway.png)

## <a name="recommended-resources"></a>Recursos recomendados

- [Azure Event Grid](https://docs.microsoft.com/azure/event-grid/overview)
- [Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Desafíos y soluciones de la administración de datos distribuidos](../microservices/architect-microservice-container-applications/distributed-data-management.md)
- [Diseño de microservicios: identificación de los límites de los microservicios](https://docs.microsoft.com/azure/architecture/microservices/microservice-boundaries)
- [Event Hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-what-is-event-hubs)
- [Patrón Event Sourcing](https://docs.microsoft.com/azure/architecture/patterns/event-sourcing)
- [Implementar el patrón de interruptor](../microservices/implement-resilient-applications/implement-circuit-breaker-pattern.md)
- [IoT Hub](https://docs.microsoft.com/azure/iot-hub)
- [Service Bus](https://docs.microsoft.com/azure/service-bus)
- [Compatibilidad con la fuente de cambios en Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/change-feed)

>[!div class="step-by-step"]
>[Anterior](serverless-architecture-considerations.md)
>[Siguiente](azure-serverless-platform.md)
