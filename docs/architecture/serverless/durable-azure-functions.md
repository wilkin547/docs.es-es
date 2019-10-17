---
title: 'Durable Functions de Azure: aplicaciones sin servidor'
description: Las funciones duraderas de Azure amplían el tiempo de ejecución de Azure Functions para habilitar flujos de trabajo con estado en el código.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2c0ad086640409ac187c3aa882add4d6b39b6ff9
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522856"
---
# <a name="durable-azure-functions"></a>Funciones de Azure duraderas

Al crear aplicaciones sin servidor con Azure Functions, las operaciones se diseñarán normalmente para ejecutarse sin estado. La razón de esta opción de diseño es que, a medida que se escala la plataforma, resulta difícil saber en qué servidores se está ejecutando el código. También resulta difícil saber el número de instancias activas en un momento dado. Sin embargo, hay clases de aplicaciones que requieren que se conozca el estado actual de un proceso. Tenga en cuenta el proceso de envío de un pedido a una tienda en línea. La operación de desprotección puede ser un flujo de trabajo compuesto por varias operaciones que necesitan conocer el estado del proceso. Esta información puede incluir el inventario de productos, si el cliente tiene créditos en su cuenta y también los resultados del procesamiento de la tarjeta de crédito. Estas operaciones pueden ser fácilmente sus propios flujos de trabajo internos o incluso servicios procedentes de sistemas de terceros.

Actualmente existen varios patrones que ayudan a coordinar el estado de la aplicación entre los sistemas internos y externos. Es habitual que se propongan de soluciones que dependen de sistemas de colas centralizados, almacenes de clave-valor distribuidos o bases de datos compartidas para administrar ese estado. Sin embargo, se trata de recursos adicionales que ahora deben aprovisionarse y administrarse. En un entorno sin servidor, el código podría resultar engorroso intentando coordinarse manualmente con estos recursos. Azure Functions ofrece una alternativa para crear funciones con estado llamadas Durable Functions.

Durable Functions es una extensión del tiempo de ejecución de Azure Functions que habilita la definición de flujos de trabajo con estado en el código. Al desglosar los flujos de trabajo en actividades, la extensión de Durable Functions puede administrar el estado, crear puntos de control de progreso y controlar la distribución de llamadas a funciones entre servidores. En segundo plano, hace uso de una cuenta de Azure Storage para conservar el historial de ejecución, programar funciones de actividad y recuperar respuestas. El código sin servidor nunca debe interactuar con la información almacenada en esa cuenta de almacenamiento y, por lo general, no es algo con el que los desarrolladores necesitan interactuar.

## <a name="triggering-a-stateful-workflow"></a>Desencadenar un flujo de trabajo con estado

Los flujos de trabajo con estado en Durable Functions se pueden dividir en dos componentes intrínsecos; desencadenadores de orquestación y actividad. Los desencadenadores y los enlaces son componentes principales usados por Azure Functions para permitir que las funciones sin servidor se notifiquen al iniciarse, recibir entradas y devolver resultados.

### <a name="working-with-the-orchestration-client"></a>Trabajar con el cliente de orquestación

Las orquestaciones son únicas en comparación con otros estilos de operaciones desencadenadas en Azure Functions. Durable Functions permite la ejecución de funciones que pueden tardar horas o incluso días en completarse. Ese tipo de comportamiento viene con la necesidad de comprobar el estado de una orquestación en ejecución, finalizar de forma preventiva o enviar notificaciones de eventos externos.

En estos casos, la extensión de Durable Functions proporciona la clase `DurableOrchestrationClient` que permite interactuar con funciones organizadas. Puede obtener acceso al cliente de orquestación mediante el enlace `OrchestrationClientAttribute`. Por lo general, incluiría este atributo con otro tipo de desencadenador, como `HttpTrigger` o `ServiceBusTrigger`. Una vez que se ha desencadenado la función de origen, se puede usar el cliente de orquestación para iniciar una función de orquestador.

```csharp
[FunctionName("KickOff")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient<orchestrationClient>)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

### <a name="the-orchestrator-function"></a>La función de orquestador

Al anotar una función con OrchestrationTriggerAttribute en Azure Functions se marca esa función como una función de orquestador. Es responsable de administrar las distintas actividades que componen el flujo de trabajo con estado.

Las funciones de orquestador no pueden hacer uso de enlaces distintos de OrchestrationTriggerAttribute. Este atributo solo se puede usar con un tipo de parámetro de DurableOrchestrationContext. No se puede usar ninguna otra entrada, ya que no se admite la deserialización de entradas en la signatura de la función. Para obtener las entradas proporcionadas por el cliente de orquestación, se debe usar el método GetInput @ no__t-0T @ no__t-1.

Además, los tipos devueltos de las funciones de orquestación deben ser void, Task o un valor serializable de JSON.

> *El código de control de errores se ha dejado por brevedad*

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<string>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

Se pueden iniciar y ejecutar varias instancias de una orquestación al mismo tiempo. Al llamar al método `StartNewAsync` en el `DurableOrchestrationClient` se inicia una nueva instancia de la orquestación. El método devuelve un `Task<string>` que se completa cuando se inicia la orquestación. Se produce una excepción de tipo `TimeoutException` si la orquestación no se ha iniciado en un plazo de 30 segundos.

La @no__t completada-0 de `StartNewAsync` debe contener el identificador único de la instancia de orquestación. Este identificador de instancia se puede utilizar para invocar operaciones en esa orquestación específica. Se puede consultar la orquestación para obtener el estado o enviar notificaciones de eventos.

### <a name="the-activity-functions"></a>Las funciones de actividad

Las funciones de actividad son las operaciones discretas que se componen juntas dentro de una función de orquestación para crear el flujo de trabajo. Aquí es donde se realizará la mayor parte del trabajo real. Representan la lógica de negocios, los procesos de ejecución prolongada y las piezas del rompecabezas en una solución más grande.

El `ActivityTriggerAttribute` se usa para anotar un parámetro de función de tipo `DurableActivityContext`. El uso de la anotación informa al tiempo de ejecución de que la función está diseñada para usarse como una función de actividad. Los valores de entrada para las funciones de actividad se recuperan mediante el método `GetInput<T>` del parámetro `DurableActivityContext`.

De forma similar a las funciones de orquestación, los tipos de valor devueltos de las funciones de actividad deben ser void, Task o un valor serializable de JSON.

Las excepciones no controladas que se producen en las funciones de actividad se enviarán hasta la función de orquestador que realiza la llamada y se presentarán como `TaskFailedException`. En este momento, el error puede detectarse y registrarse en el orquestador, y se puede volver a intentar la actividad.

```csharp
[FunctionName("CheckAndReserveInventory")]
public static bool CheckAndReserveInventory([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    // Connect to inventory system and try to reserve items
    return true;
}
```

## <a name="recommended-resources"></a>Recursos recomendados

- [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Enlaces para Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
- [Administrar instancias en Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Anterior](event-grid.md)
>[Siguiente](orchestration-patterns.md)
