---
title: Ejemplos de escenarios empresariales y casos de uso de aplicaciones sin servidor
description: Conozca el modo sin servidor con un enfoque práctico mediante ejemplos que van desde el procesamiento de imágenes hasta la compatibilidad con aplicaciones móviles y las canalizaciones de extracción, transformación y carga de datos (ETL).
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 04/17/2020
ms.openlocfilehash: 3cb3b73325fccc327ccf17f7298048f2eeb3577a
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158455"
---
# <a name="serverless-business-scenarios-and-use-cases"></a>Escenarios y casos de uso empresariales sin servidor

Hay muchos casos de uso y escenarios para aplicaciones sin servidor. En este capítulo se incluyen ejemplos que muestran los distintos escenarios. Los escenarios incluyen vínculos a documentación relacionada y repositorios de código fuente públicos. Los ejemplos de este capítulo le permiten empezar a trabajar en su propia creación e implementación de soluciones sin servidor.

## <a name="big-data-processing"></a>Procesamiento de macrodatos

![Diagrama de asignación/reducción](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/media/mapreducearchitecture.png)

En este ejemplo se usa un enfoque sin servidor para realizar una operación de asignación/reducción en un gran conjunto de datos. Determina la velocidad media de los viajes realizados por los taxis amarillos de Nueva York por día en 2017.

[Procesamiento de macrodatos: MapReduce sin servidor en Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)

## <a name="create-serverless-applications-hands-on-lab"></a>Creación de aplicaciones sin servidor: laboratorio práctico

Aprenda a usar Functions para ejecutar la lógica del servidor y crear arquitecturas sin servidor.

- Elección del mejor servicio de Azure para su empresa
- Creación de Azure Functions
- Uso de desencadenadores
- Encadenamiento de funciones
- Flujos de trabajo de larga ejecución
- Supervisión
- Desarrollo, pruebas e implementación

[Creación de aplicaciones sin servidor](https://docs.microsoft.com/learn/paths/create-serverless-applications/)

## <a name="customer-reviews"></a>Revisiones de clientes

En este ejemplo se muestran las nuevas herramientas de Azure Functions para las bibliotecas de clases C# de Visual Studio. Cree un sitio web en el que los clientes envíen revisiones de productos que se almacenan en instancias de Azure Storage Blob y CosmosDB. Agregue una instancia de Azure Functions para realizar una moderación automatizada de las revisiones de clientes mediante Azure Cognitive Services. Use una cola de Azure Storage para desacoplar el sitio web de la función.

[Aplicación de revisiones de clientes con Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)

## <a name="docker-linux-image-support"></a>Compatibilidad con imágenes Docker de Linux

En este ejemplo se muestra cómo crear un `Dockerfile` para compilar y ejecutar Azure Functions en un contenedor Docker de Linux.

[Azure Functions en Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)

## <a name="file-processing-and-validation"></a>Procesamiento y validación de archivos

En este ejemplo se analiza un conjunto de archivos CSV de clientes hipotéticos. Esto garantiza que todos los archivos necesarios para un "lote" de un cliente estén listos y valida la estructura de cada archivo. Se presentan diferentes soluciones mediante Azure Functions, Logic Apps y Durable Functions.

[Procesamiento y validación de archivos mediante Azure Functions, Logic Apps y Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)

## <a name="game-data-visualization"></a>Visualización de datos de juegos

![Telemetría de juegos](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/media/points.png)

Este es un ejemplo de cómo un desarrollador puede implementar una solución de visualización de datos en el editor para su juego. De hecho, un complemento de Unity y un complemento de Unreal Engine 4 se desarrollaron teniendo este ejemplo como back-end. El componente de servicio es independiente del motor de juegos.

[Visualización de telemetría de juegos en el editor](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)

## <a name="graphql"></a>GraphQL

Cree una función sin servidor que expone una API de GraphQL.

[Funciones sin servidor para GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)

## <a name="internet-of-things-iot-reliable-edge-relay"></a>Retransmisión perimetral confiable de Internet de las cosas (IoT)

![Arquitectura de IoT](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/media/architecture.png)

En este ejemplo se implementa un nuevo protocolo de comunicación para habilitar la comunicación ascendente confiable desde dispositivos IoT. Automatiza la detección y reposición de lagunas de datos.

[Retransmisión perimetral confiable de IoT](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)

## <a name="microservices-reference-architecture"></a>Arquitectura de referencia de microservicios

![Arquitectura de referencia](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/media/macro-architecture.png)

Esta es una arquitectura de referencia que le guía por el proceso de toma de decisiones implicado en el diseño, el desarrollo y la entrega de la aplicación Rideshare de Relecloud, una empresa ficticia. Incluye instrucciones prácticas para configurar e implementar todos los componentes de la arquitectura.

[Arquitectura de referencia de microservicios sin servidor](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

## <a name="migrate-console-apps-to-serverless"></a>Migración de aplicaciones de consola a aplicaciones sin servidor

Este ejemplo es una función genérica (archivo `.csx`) que se puede usar para convertir cualquier aplicación de consola en un servicio web HTTP en Azure Functions. Lo único que tiene que hacer es editar un archivo de configuración y especificar qué parámetros de entrada se pasarán como argumentos a `.exe`.

[Ejecución de aplicaciones de consola en Azure Functions](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)

## <a name="serverless-for-mobile"></a>Aplicaciones sin servidor para dispositivos móviles

Azure Functions es fácil de implementar y mantener, y es accesible a través de HTTP. Es una excelente manera de implementar una API para una aplicación móvil. Microsoft ofrece excelentes herramientas multiplataforma para iOS, Android y Windows con Xamarin. Por ello, Xamarin y Azure Functions funcionan muy bien conjuntamente. En este artículo se muestra cómo implementar primero una instancia de Azure Functions en Azure Portal o en Visual Studio, y cómo compilar un cliente multiplataforma con Xamarin.Forms que se ejecute en Android, iOS y Windows.

[Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Implementación de una instancia de Azure Function con un cliente de Xamarin.Forms)

## <a name="serverless-messaging"></a>Mensajería sin servidor

En este ejemplo se muestra cómo se usa el patrón ramificado de Durable Functions para cargar un número arbitrario de mensajes en cualquier número de sesiones o particiones. Se destina a Service Bus, Event Hubs o colas de almacenamiento. El ejemplo también agrega la capacidad de usar esos mensajes con otra instancia de Azure Functions y cargar los datos de tiempo resultantes en otra instancia de Event Hubs. Posteriormente, los datos se ingieren en servicios de análisis como Azure Data Explorer.

[Generación y consumo de mensajes a través de Service Bus, Event Hubs y colas de almacenamiento con Azure Functions](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)

## <a name="recommended-resources"></a>Recursos recomendados

- [Azure Functions en Linux](https://docs.microsoft.com/samples/azure-samples/functions-linux-custom-image/azure-functions-on-linux-custom-image-tutorial-sample-project/)
- [Procesamiento de macrodatos: MapReduce sin servidor en Azure](https://docs.microsoft.com/samples/azure-samples/durablefunctions-mapreduce-dotnet/big-data-processing-serverless-mapreduce-on-azure/)
- [Creación de aplicaciones sin servidor](https://docs.microsoft.com/learn/paths/create-serverless-applications/)
- [Aplicación de revisiones de clientes con Cognitive Services](https://docs.microsoft.com/samples/azure-samples/functions-customer-reviews/customer-reviews-cognitive-services/)
- [Procesamiento y validación de archivos mediante Azure Functions, Logic Apps y Durable Functions](https://docs.microsoft.com/samples/azure-samples/serverless-file-validation/file-processing-and-validation-using-azure-functions-logic-apps-and-durable-functions/)
- [Implementing a simple Azure Function with a Xamarin.Forms client](https://docs.microsoft.com/samples/azure-samples/functions-xamarin-getting-started/implementing-a-simple-azure-function-with-a-xamarinforms-client/) (Implementación de una instancia de Azure Function con un cliente de Xamarin.Forms)
- [Visualización de telemetría de juegos en el editor](https://docs.microsoft.com/samples/azure-samples/gaming-in-editor-telemetry/in-editor-telemetry-visualization/)
- [Retransmisión perimetral confiable de IoT](https://docs.microsoft.com/samples/azure-samples/iot-reliable-edge-relay/iot-reliable-edge-relay/)
- [Generación y consumo de mensajes a través de Service Bus, Event Hubs y colas de almacenamiento con Azure Functions](https://docs.microsoft.com/samples/azure-samples/durable-functions-producer-consumer/product-consume-messages-az-functions/)
- [Ejecución de aplicaciones de consola en Azure Functions](https://docs.microsoft.com/samples/azure-samples/functions-dotnet-migrating-console-apps/run-console-apps-on-azure-functions/)
- [Funciones sin servidor para GraphQL](https://github.com/softchris/graphql-workshop-dotnet/blob/master/docs/workshop/4.md)
- [Arquitectura de referencia de microservicios sin servidor](https://docs.microsoft.com/samples/azure-samples/serverless-microservices-reference-architecture/serverless-microservices-reference-architecture/)

>[!div class="step-by-step"]
>[Anterior](orchestration-patterns.md)
>[Siguiente](serverless-conclusion.md)
