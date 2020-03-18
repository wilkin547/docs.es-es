---
title: Tipos de RPC - gRPC para desarrolladores de WCF
description: Una revisión de los tipos de llamada a procedimiento remoto admitidos por WCF y sus equivalentes en gRPC
ms.date: 09/02/2019
ms.openlocfilehash: b9d4ce7cae693ed7904229483cbccfe3b299b640
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401788"
---
# <a name="types-of-rpc"></a>Tipos de RPC

Como desarrollador de Windows Communication Foundation (WCF), probablemente esté acostumbrado a tratar con los siguientes tipos de llamada a procedimiento remoto (RPC):

- Solicitud/respuesta
- Duplex:
  - Dúplex unidireccional con sesión
  - Dúplex completo con sesión
- Unidireccional

Es posible asignar estos tipos de RPC de forma bastante natural a los conceptos de gRPC existentes. Este capítulo examinará cada una de estas áreas a su vez. [El capítulo 5](migrate-wcf-to-grpc.md) explorará ejemplos similares en mayor profundidad.

| WCF | gRPC |
| --- | ---- |
| Solicitud/respuesta regular | Unario |
| Servicio dúplex con sesión mediante una interfaz de devolución de llamada de cliente | Transmisión de servidores |
| Servicio dúplex completo con sesión | Transmisión bidireccional |
| Operaciones unidireccionales | Transmisión de clientes |

## <a name="requestreply"></a>Solicitud/respuesta

Para métodos simples de solicitud/respuesta que toman y devuelven pequeñas cantidades de datos, utilice el patrón gRPC más simple, el RPC unario.

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

Como puede ver, implementar un método de servicio RPC unario gRPC es similar a implementar una operación WCF. La diferencia es que con gRPC, se reemplaza un método de clase base en lugar de implementar una interfaz. En el servidor, los métodos base gRPC siempre devuelven, <xref:System.Threading.Tasks.Task%601>aunque el cliente proporciona métodos asincrónicos y de bloqueo para llamar al servicio.

## <a name="wcf-duplex-one-way-to-client"></a>Dúplex WCF, una forma de llegar al cliente

Las aplicaciones WCF (con determinados enlaces) pueden crear una conexión persistente entre el cliente y el servidor. El servidor puede enviar datos de forma asincrónica al cliente hasta que se <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> cierre la conexión mediante una *interfaz* de devolución de llamada especificada en la propiedad.

Los servicios gRPC proporcionan una funcionalidad similar con secuencias de mensajes. Las secuencias no se asignan *exactamente* a los servicios dúplex DE WCF en términos de implementación, pero puede lograr los mismos resultados.

### <a name="grpc-streaming"></a>gRPC streaming

gRPC admite la creación de secuencias persistentes de cliente a servidor y de servidor a cliente. Ambos tipos de secuencia pueden estar activos simultáneamente. Esta capacidad se denomina transmisión bidireccional.

Puede usar secuencias para mensajería asincrónica arbitraria a lo largo del tiempo. O bien, puede usarlos para pasar conjuntos de datos grandes que son demasiado grandes para generar y enviar una sola solicitud o respuesta.

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

Esta secuencia de servidor se puede consumir desde una aplicación cliente, como se muestra en el código siguiente:

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
> Las RPC de streaming de servidor son útiles para los servicios de estilo de suscripción. También son útiles para enviar conjuntos de datos grandes cuando sería ineficiente o imposible crear todo el conjunto de datos en memoria. Sin embargo, las respuestas de `repeated` streaming no son tan rápidas como enviar campos en un solo mensaje. Por regla general, la transmisión por secuencias no debe usarse para conjuntos de datos pequeños.

### <a name="differences-from-wcf"></a>Diferencias con WCF

Un servicio dúplex WCF usa una interfaz de devolución de llamada de cliente que puede tener varios métodos. Un servicio de streaming de servidor gRPC solo puede enviar mensajes a través de una sola secuencia. Si necesita varios métodos, use un tipo de mensaje con [un campo Any o uno de ellos](protobuf-any-oneof.md) para enviar mensajes diferentes y escriba código en el cliente para controlarlos.

En WCF, la clase [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sesión se mantiene activa hasta que se cierra la conexión. Se pueden llamar a varios métodos dentro de la sesión. En gRPC, `Task` el que devuelve el método de implementación no debe finalizar hasta que se cierra la conexión.

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a>Operaciones unidireccionales de WCF y streaming de cliente gRPC

WCF proporciona operaciones unidireccionales `[OperationContract(IsOneWay = true)]`(marcadas con ) que devuelven una confirmación específica del transporte. Los métodos de servicio gRPC siempre devuelven una respuesta, incluso si está vacía. El cliente siempre debe esperar esa respuesta. Para el estilo de mensajería "fire-and-forget" en gRPC, puede crear un servicio de streaming de cliente.

### <a name="thing_logproto"></a>thing_log.proto

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

### <a name="thinglog-client-example"></a>Ejemplo de cliente de ThingLog

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

Puede utilizar RPC de transmisión de cliente para la mensajería fire-and-forget, como se muestra en el ejemplo anterior. También puede usarlos para enviar conjuntos de datos muy grandes al servidor. Se aplica la misma advertencia sobre el `repeated` rendimiento: para conjuntos de datos más pequeños, utilice campos en mensajes normales.

## <a name="wcf-full-duplex-services"></a>Servicios dúplex completo de WCF

El enlace dúplex WCF admite varias operaciones unidireccionales tanto en la interfaz de servicio como en la interfaz de devolución de llamada del cliente. Este soporte permite conversaciones en curso entre el cliente y el servidor. gRPC admite algo similar con RPC de streaming bidireccionales, `stream` donde ambos parámetros se marcan con el modificador.

### <a name="chatproto"></a>chat.proto

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

En el ejemplo anterior, puede ver que el método`IAsyncStreamReader<MessageRequest>`de implementación recibe`IServerStreamWriter<MessageResponse>`una secuencia de solicitudes ( ) y una secuencia de respuesta ( ). El método puede leer y escribir mensajes hasta que se cierra la conexión.

### <a name="chatter-client"></a>Cliente de Chatter

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
