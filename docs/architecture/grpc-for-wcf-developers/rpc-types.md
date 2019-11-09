---
title: Tipos de RPC-gRPC para desarrolladores de WCF
description: Revisión de los tipos de llamadas a procedimientos remotos admitidas por WCF y sus equivalentes en gRPC
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: ce5bf03b01dff3f7bb201ff08c9065abc2e58360
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841382"
---
# <a name="types-of-rpc"></a>Tipos de RPC

Como desarrollador de Windows Communication Foundation (WCF), es probable que se use para trabajar con los siguientes tipos de llamada a procedimiento remoto (RPC):

- Solicitud/Respuesta
- D
  - Dúplex unidireccional con sesión
  - Dúplex completo con sesión
- Unidireccional

Es posible asignar estos tipos de RPC de forma bastante natural a los conceptos de gRPC existentes y este capítulo examinará cada una de estas áreas a su vez. Los ejemplos similares se explorarán con mucha mayor profundidad en el [capítulo 5](migrate-wcf-to-grpc.md).

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

Como puede ver, la implementación de un método de servicio RPC unario de gRPC es muy similar a la implementación de una operación de WCF, salvo que con gRPC, invalide un método de clase base en lugar de implementar una interfaz. Tenga en cuenta que, en el servidor, los métodos base de gRPC siempre devuelven un <xref:System.Threading.Tasks.Task%601>, aunque el cliente proporciona métodos asincrónicos y de bloqueo para llamar al servicio.

## <a name="wcf-duplex-one-way-to-client"></a>Dúplex de WCF, unidireccional a cliente

Las aplicaciones WCF (con ciertos enlaces) pueden crear una conexión persistente entre el cliente y el servidor, y el servidor puede enviar datos de forma asincrónica al cliente hasta que se cierre la conexión, mediante una *interfaz de devolución de llamada* especificada en la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.

los servicios de gRPC proporcionan una funcionalidad similar con las secuencias de mensajes. Las secuencias no se asignan *exactamente* a los servicios dúplex de WCF en términos de implementación, pero se pueden lograr los mismos resultados.

### <a name="grpc-streaming"></a>streaming de gRPC

gRPC admite la creación de secuencias persistentes del cliente al servidor y del servidor al cliente. Ambos tipos de flujo pueden estar activos simultáneamente. Esto se denomina streaming bidireccional. Los flujos se pueden usar para mensajería arbitraria o asincrónica a lo largo del tiempo, o para pasar grandes conjuntos de datos que son demasiado grandes para generarlos y enviarlos en una sola solicitud o respuesta.

En el ejemplo siguiente se muestra un RPC de streaming de servidor.

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

Esta secuencia de servidor podría consumirse desde una aplicación cliente como se muestra en el código siguiente:

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
> Las RPC de streaming de servidor son útiles para los servicios de estilo de suscripción, así como para enviar conjuntos de datasets muy grandes cuando sería ineficaz o imposible crear todo el conjunto de conjuntos de servidores en la memoria. Sin embargo, las respuestas de streaming no son tan rápidas como el envío de `repeated` campos en un solo mensaje, por lo que no debe usarse un streaming de reglas para conjuntos de valores pequeños.

### <a name="differences-to-wcf"></a>Diferencias con WCF

Un servicio de dúplex de WCF usa una interfaz de devolución de llamada de cliente que puede tener varios métodos. Un servicio de streaming de gRPC Server solo puede enviar mensajes a través de un único flujo. Si necesita varios métodos, use un tipo de mensaje con un [campo cualquier o un campo](protobuf-any-oneof.md) para enviar diferentes mensajes, y escriba código en el cliente para controlarlos.

En WCF, la clase [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sesión se mantiene activa hasta que se cierra la conexión y se puede llamar a varios métodos dentro de la sesión. En gRPC, el `Task` devuelto por el método de implementación no debe completarse hasta que se cierre la conexión.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operaciones unidireccionales de WCF y transmisión por secuencias de cliente gRPC

WCF proporciona operaciones unidireccionales (marcadas con `[OperationContract(IsOneWay = true)]`) que devuelven una confirmación específica del transporte. los métodos de servicio gRPC siempre devuelven una respuesta, incluso si está vacía, y el cliente siempre debe esperar esa respuesta. En el caso de la mensajería de estilo "desencadenar y olvidar" en gRPC, puede crear un servicio de streaming de cliente.

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

De nuevo, las RPC de streaming de cliente se pueden usar para mensajería de desencadenamiento y olvidar, tal como se muestra en el ejemplo anterior, pero también para enviar conjuntos de valores de gran tamaño al servidor. Se aplica la misma advertencia sobre el rendimiento: para conjuntos de información más pequeños, use `repeated` campos en los mensajes normales.

## <a name="wcf-full-duplex-services"></a>Servicios dúplex completo de WCF

El enlace dúplex de WCF admite varias operaciones unidireccionales en la interfaz de servicio y la interfaz de devolución de llamada de cliente, lo que permite conversaciones en curso entre el cliente y el servidor. gRPC admite algo similar a las RPC de streaming bidireccional, donde ambos parámetros se marcan con el modificador `stream`.

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

En el ejemplo anterior, puede ver que el método de implementación recibe una secuencia de solicitud (`IAsyncStreamReader<MessageRequest>`) y una secuencia de respuesta (`IServerStreamWriter<MessageResponse>`) y puede leer y escribir mensajes hasta que se cierre la conexión.

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
