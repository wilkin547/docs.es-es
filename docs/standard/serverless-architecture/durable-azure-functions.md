---
title: 'Durable functions de Azure: aplicaciones sin servidor'
description: Las funciones de Azure duraderas amplían el tiempo de ejecución de Azure Functions para habilitar los flujos de trabajo con estado en el código.
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 8ad354e1708eb88f016130f8235f534b967eb122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776017"
---
# <a name="durable-azure-functions"></a>Funciones de Azure duraderas

Al crear aplicaciones sin servidor con Azure Functions, las operaciones normalmente se ha diseñado para ejecutarse de forma independiente. La razón de esta opción de diseño es que como las escalas de la plataforma, resulta difícil saber qué se está ejecutando el código en los servidores. También resulta difícil saber cuántas instancias están activas en un momento dado. Sin embargo, hay clases de aplicaciones que requieren el estado actual de un proceso que se conoce. Tenga en cuenta el proceso de enviar un pedido a una tienda en línea. La operación de desprotección podría ser un flujo de trabajo que se compone de varias operaciones que debe conocer el estado del proceso. Dicha información puede incluir el inventario de productos, si el cliente tiene los créditos de su cuenta, además de los resultados del procesamiento de la tarjeta de crédito. Estas operaciones podrían ser fácilmente sus propios flujos de trabajo internos o incluso servicios de sistemas de terceros.

Existen diversos patrones actualmente que ayudan a con la coordinación de estado de la aplicación entre sistemas internos y externos. Es habitual encontrar a soluciones que se basan en los sistemas centralizados de puesta en cola, los almacenes de pares clave-valor distribuidos o bases de datos compartidos para administrar dicho estado. Sin embargo, estos son los recursos adicionales que necesitan ahora se aprovisionan y administran. En un entorno sin servidor, el código podría ser complicado intentar coordinar con estos recursos manualmente. Las funciones de Azure ofrece una alternativa para la creación de funciones con estado de Durable Functions.

Durable Functions es una extensión de Azure Functions runtime que permite la definición de flujos de trabajo con estado en el código. Al dividir los flujos de trabajo en las actividades, la extensión Durable Functions puede administrar el estado, crear puntos de control de progreso y controlar la distribución de llamadas de función entre servidores. En segundo plano, permite usar una cuenta de Azure Storage para conservar el historial de ejecución, programar las funciones de actividad y recuperar las respuestas. El código sin servidor nunca debe interactuar con la información guardada en esa cuenta de almacenamiento y normalmente no es algo con lo que los desarrolladores necesitan interactuar.

## <a name="triggering-a-stateful-workflow"></a>Desencadenar un flujo de trabajo con estado

Los flujos de trabajo con estado en Durable Functions pueden dividirse en dos componentes intrínsecos; desencadenadores de orquestación y la actividad. Desencadenadores y enlaces son los componentes principales utilizados por las funciones de Azure para habilitar las funciones sin servidor para recibir una notificación cuando se inicie, recibir de entrada y da como resultado la devolución.

### <a name="working-with-the-orchestration-client"></a>Trabajar con el cliente de orquestación

Las orquestaciones son únicas en comparación con otros estilos de las operaciones desencadenadas en Azure Functions. Durable Functions permite la ejecución de funciones que pueden requerir horas o incluso días en completarse. Ese tipo de comportamiento viene de forma preventiva terminar con la necesidad de realizar la comprobación del estado de una orquestación en ejecución, o enviar notificaciones de eventos externos.

En tales casos, la extensión Durable Functions proporciona el `DurableOrchestrationClient` organizados de clase que le permite interactuar con las funciones. Obtener acceso al cliente de orquestación mediante el `OrchestrationClientAttribute` enlace. Por lo general, debe incluir este atributo con otro tipo de desencadenador, como un `HttpTrigger` o `ServiceBusTrigger`. Una vez que se desencadenó la función de origen, el cliente de orquestación se puede usar para iniciar una función de orquestador.

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

Anotar una función con el OrchestrationTriggerAttribute en marcas de Azure Functions que funcionan como una función de orquestador. Es responsable de administrar las diversas actividades que constituyen el flujo de trabajo con estado.

Las funciones de orquestador son no se puede hacer uso de enlaces que no sea el OrchestrationTriggerAttribute. Este atributo solo puede usarse con un tipo de parámetro de DurableOrchestrationContext. Puesto que no se admite la deserialización de entradas en la firma de función, no se pueden usar ningún otras entradas. Para obtener las entradas proporcionadas por el cliente de orquestación, el GetInput\<T\> se debe usar el método.

Además, los tipos devueltos de las funciones de orquestación deben ser void, Task o un valor serializable de JSON.

> *Código de control de errores se ha omitido por razones de brevedad*

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

Varias instancias de una orquestación pueden ser iniciado y en ejecución al mismo tiempo. Una llamada a la `StartNewAsync` método en el `DurableOrchestrationClient` inicia una nueva instancia de la orquestación. El método devuelve un `Task<string>` que se completa cuando se inició la orquestación. Una excepción de tipo `TimeoutException` cuando se genera si no se ha iniciado la orquestación en 30 segundos.

Completado `Task<string>` desde `StartNewAsync` debe contener el identificador único de la instancia de orquestación. Este Id. de instancia puede usarse para invocar operaciones en esa orquestación específica. La orquestación se puede consultar el estado o envía notificaciones de eventos.

### <a name="the-activity-functions"></a>Las funciones de actividad

Las funciones de actividad son las operaciones discretas que obtengan compondrán juntos dentro de una función de orquestación para crear el flujo de trabajo. Aquí es donde la mayoría del trabajo real tendrá lugar. Representan la lógica de negocios, largos procesos en ejecución y las piezas del rompecabezas para una solución mayor.

El `ActivityTriggerAttribute` se usa para anotar un parámetro de función de tipo `DurableActivityContext`. Mediante la anotación indica el tiempo de ejecución que la función está pensada para usarse como una función de actividad. Se recuperan valores de entrada a las funciones de actividad mediante la `GetInput<T>` método de la `DurableActivityContext` parámetro.

Al igual que las funciones de orquestación, los tipos devueltos de funciones de actividad deben ser void, Task o un valor serializable de JSON.

Las excepciones no controladas que se producen dentro de las funciones de actividad obtendrá enviadas a la función de orquestador que realiza la llamada y se presenta como un `TaskFailedException`. En este momento, el error se puede detectar y registrar en el orquestador, y se puede reintentar la actividad.

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

* [Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Enlaces para Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-bindings)
* [Administración de instancias con Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-instance-management)

>[!div class="step-by-step"]
>[Anterior](event-grid.md)
>[Siguiente](orchestration-patterns.md)