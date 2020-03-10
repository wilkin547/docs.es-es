---
title: Tipos de RPC-gRPC para desarrolladores de WCF
description: Revisión de los tipos de llamadas a procedimientos remotos admitidas por WCF y sus equivalentes en gRPC
ms.date: 09/02/2019
ms.openlocfilehash: 58f097bac61395e6810155e8ae9a6bbf2219ec5e
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675157"
---
# <a name="types-of-rpc"></a>Tipos de RPC

Como desarrollador de Windows Communication Foundation (WCF), es probable que se use para trabajar con los siguientes tipos de llamada a procedimiento remoto (RPC):

- Solicitud/respuesta
- D
  - Dúplex unidireccional con sesión
  - Dúplex completo con sesión
- Unidireccional

Es posible asignar estos tipos de RPC de forma bastante natural a conceptos de gRPC existentes. En este capítulo se examinará cada una de estas áreas a su vez. En el [capítulo 5](migrate-wcf-to-grpc.md) se explorarán ejemplos similares con mayor profundidad.

| WCF | gRPC |
| --- | ---- |
| Solicitud/respuesta normal | Unario |
| Servicio dúplex con sesión mediante una interfaz de devolución de llamada de cliente | Streaming de servidor |
| Servicio dúplex completo con sesión | Streaming bidireccional |
| Operaciones unidireccionales | Streaming de cliente |

## <a name="requestreply"></a>Solicitud/respuesta

Para los métodos de solicitud/respuesta simples que toman y devuelven pequeñas cantidades de datos, use el patrón gRPC más sencillo, el RPC unario.

```protobuf
service Things {
    rpc Get(GetThingRequest) returns (GetThingResponse);
}
```

```csharp
public class ThingService : Things.ThingsBase
{
    public override async Task<GetThingResponse> Get(GetThingRequest request, ServerCallContext context)
    {
        // Get thing from database
        return new GetThingResponse { Thing = thing };
    }
}
```

```csharp
public async Task ShowThing(int thingId)
{
    var thing = await _thingsClient.GetAsync(new GetThingRequest { ThingId = thingId });
    Console.WriteLine($"{thing.Name}");
}
```

Como puede ver, la implementación de un método de servicio RPC unario de gRPC es similar a la implementación de una operación de WCF. La diferencia es que con gRPC, invalida un método de clase base en lugar de implementar una interfaz. En el servidor, los métodos base de gRPC siempre devuelven <xref:System.Threading.Tasks.Task%601>, aunque el cliente proporciona métodos asincrónicos y de bloqueo para llamar al servicio.

## <a name="wcf-duplex-one-way-to-client"></a>Dúplex de WCF, una manera de cliente

Las aplicaciones WCF (con ciertos enlaces) pueden crear una conexión persistente entre el cliente y el servidor. El servidor puede enviar datos de forma asincrónica al cliente hasta que se cierre la conexión mediante una *interfaz de devolución de llamada* especificada en la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.

los servicios de gRPC proporcionan una funcionalidad similar con las secuencias de mensajes. Las secuencias no se asignan *exactamente* a los servicios dúplex de WCF en términos de implementación, pero puede lograr los mismos resultados.

### <a name="grpc-streaming"></a>streaming de gRPC

gRPC admite la creación de secuencias persistentes del cliente al servidor y del servidor al cliente. Ambos tipos de flujo pueden estar activos simultáneamente. Esta capacidad se denomina streaming bidireccional. 

Puede usar secuencias para la mensajería arbitraria y asincrónica a lo largo del tiempo. También puede usarlos para pasar grandes conjuntos de datos que son demasiado grandes para generarlos y enviarlos en una sola solicitud o respuesta.

En el ejemplo siguiente se muestra una RPC de streaming de servidor.

```protobuf
service ClockStreamer {
    rpc Subscribe(ClockSubscribeRequest) returns (stream ClockMessage);
}
```

```csharp
public class ClockStreamerService : ClockStreamer.ClockStreamerBase
{
    public override async Task Subscribe(ClockSubscribeRequest request,
        IServerStreamWriter<ClockMessage> responseStream,
        ServerCallContext context)
    {
        while (!context.CancellationToken.IsCancellationRequested)
        {
            var time = DateTimeOffset.UtcNow;
            await responseStream.WriteAsync(new ClockMessage { message = $"The time is {time:t}." });
            await Task.Delay(TimeSpan.FromSeconds(10), context.CancellationToken);
        }
    }
}
```

Esta secuencia del servidor se puede usar desde una aplicación cliente, tal y como se muestra en el código siguiente:

```csharp
public async Task TellTheTimeAsync(CancellationToken token)
{
    var channel = GrpcChannel.ForAddress("https://localhost:5001");
    var client = new ClockStreamer.ClockStreamerClient(channel);

    var request = new ClockSubscribeRequest();
    var response = client.Subscribe(request);

    await foreach (var update in response.ResponseStream.ReadAllAsync(token))
    {
        Console.WriteLine(update.Message);
    }
}
```

> [!NOTE]
> Las RPC de streaming de servidor son útiles para los servicios de estilo de suscripción. También resultan útiles para el envío de grandes conjuntos de valores cuando sería ineficaz o imposible compilar todo el conjunto de datasets en la memoria. Sin embargo, las respuestas de streaming no son tan rápidas como el envío de `repeated` campos en un solo mensaje. Como regla, no se debe usar la transmisión por secuencias para conjuntos de valores pequeños.

### <a name="differences-from-wcf"></a>Diferencias con WCF

Un servicio de dúplex de WCF usa una interfaz de devolución de llamada de cliente que puede tener varios métodos. Un servicio de transmisión por secuencias de gRPC Server solo puede enviar mensajes a través de un único flujo. Si necesita varios métodos, use un tipo de mensaje con un [campo cualquier o un campo](protobuf-any-oneof.md) para enviar diferentes mensajes, y escriba código en el cliente para controlarlos.

En WCF, la clase [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sesión se mantiene activa hasta que se cierra la conexión. Se puede llamar a varios métodos dentro de la sesión. En gRPC, la `Task` que devuelve el método de implementación no debería finalizar hasta que se cierre la conexión.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operaciones unidireccionales de WCF y transmisión por secuencias de cliente gRPC

WCF proporciona operaciones unidireccionales (marcadas con `[OperationContract(IsOneWay = true)]`) que devuelven una confirmación específica del transporte. los métodos de servicio gRPC siempre devuelven una respuesta, incluso si está vacía. El cliente siempre debe esperar esa respuesta. Para el estilo de "desencadenar y olvidar" de la mensajería en gRPC, puede crear un servicio de streaming de cliente.

### <a name="thing_logproto"></a>thing_log. proto

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a>ThingLogService.cs

```csharp
public class ThingLogService : Protos.ThingLog.ThingLogBase
{
    private static readonly ConnectionClosedResponse EmptyResponse = new ConnectionClosedResponse();
    private readonly ILogger<ThingLogService> _logger;
    public ThingLogService(ILogger<ThingLogService> logger)
    {
        _logger = logger;
    }

    public override async Task<CompletedResponse> OpenConnection(IAsyncStreamReader<Thing> requestStream, ServerCallContext context)
    {
        while (await requestStream.MoveNext(context.CancellationToken))
        {
            _logger.LogInformation(requestStream.Current.Description);
        }
        return EmptyResponse;
    }
}
```

### <a name="thinglog-client-example"></a>Ejemplo de cliente ThingLog

```csharp
public class ThingLogger : IAsyncDisposable
{
    private readonly ThingLog.ThingLogClient _client;
    private readonly AsyncClientStreamingCall<ThingLogRequest, CompletedResponse> _stream;

    public ThingLogger(ThingLog.ThingLogClient client)
    {
        _client = client;
        _stream = client.OpenConnection();
    }

    public async Task WriteAsync(string description)
    {
        await _stream.RequestStream.WriteAsync(new Thing
        {
            Description = description,
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        _stream.Dispose();
    }
}
```

Puede usar RPC de streaming de cliente para mensajería de desencadenamiento y olvidar, tal como se muestra en el ejemplo anterior. También puede usarlos para enviar conjuntos de valores de gran tamaño al servidor. Se aplica la misma advertencia sobre el rendimiento: para conjuntos de información más pequeños, use `repeated` campos en los mensajes normales.

## <a name="wcf-full-duplex-services"></a>Servicios dúplex completo de WCF

El enlace dúplex de WCF admite varias operaciones unidireccionales en la interfaz de servicio y la interfaz de devolución de llamada de cliente. Esta compatibilidad permite conversaciones en curso entre el cliente y el servidor. gRPC admite algo similar a las RPC de streaming bidireccional, donde ambos parámetros se marcan con el modificador `stream`.

### <a name="chatproto"></a>chat. proto

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a>ChatterService.cs

```csharp
public class ChatterService : Chatter.ChatterBase
{
    private readonly IChatHub _hub;

    public ChatterService(IChatHub hub)
    {
        _hub = hub;
    }

    public override async Task Connect(IAsyncStreamReader<MessageRequest> requestStream, IServerStreamWriter<MessageResponse> responseStream, ServerCallContext context)
    {
        _hub.MessageReceived += async (sender, args) =>
            await responseStream.WriteAsync(new MessageResponse {Text = args.Message});

        while (await requestStream.MoveNext(context.CancellationToken))
        {
            await _hub.SendAsync(requestStream.Current.Text);
        }
    }
}
```

En el ejemplo anterior, puede ver que el método de implementación recibe una secuencia de solicitud (`IAsyncStreamReader<MessageRequest>`) y una secuencia de respuesta (`IServerStreamWriter<MessageResponse>`). El método puede leer y escribir mensajes hasta que se cierre la conexión.

### <a name="chatter-client"></a>Cliente chatter

```csharp
public class Chat : IAsyncDisposable
{
    private readonly Chatter.ChatterClient _client;
    private readonly AsyncDuplexStreamingCall<MessageRequest, MessageResponse> _stream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _readTask;

    public Chat(Chatter.ChatterClient client)
    {
        _client = client;
        _stream = _client.Connect();
        _cancellationTokenSource = new CancellationTokenSource();
        _readTask = ReadAsync(_cancellationTokenSource.Token);
    }

    public async Task SendAsync(string message)
    {
        await _stream.RequestStream.WriteAsync(new MessageRequest {Text = message});
    }

    private async Task ReadAsync(CancellationToken token)
    {
        while (await _stream.ResponseStream.MoveNext(token))
        {
            Console.WriteLine(_stream.ResponseStream.Current.Text);
        }
    }

    public async ValueTask DisposeAsync()
    {
        await _stream.RequestStream.CompleteAsync();
        await _readTask;
        _stream.Dispose();
    }
}
```

>[!div class="step-by-step"]
>[Anterior](wcf-bindings.md)
>[Siguiente](metadata.md)
