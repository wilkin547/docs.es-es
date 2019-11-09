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
# <a name="types-of-rpc"></a><span data-ttu-id="c8181-103">Tipos de RPC</span><span class="sxs-lookup"><span data-stu-id="c8181-103">Types of RPC</span></span>

<span data-ttu-id="c8181-104">Como desarrollador de Windows Communication Foundation (WCF), es probable que se use para trabajar con los siguientes tipos de llamada a procedimiento remoto (RPC):</span><span class="sxs-lookup"><span data-stu-id="c8181-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of Remote Procedure Call (RPC):</span></span>

- <span data-ttu-id="c8181-105">Solicitud/Respuesta</span><span class="sxs-lookup"><span data-stu-id="c8181-105">Request/Reply</span></span>
- <span data-ttu-id="c8181-106">D</span><span class="sxs-lookup"><span data-stu-id="c8181-106">Duplex:</span></span>
  - <span data-ttu-id="c8181-107">Dúplex unidireccional con sesión</span><span class="sxs-lookup"><span data-stu-id="c8181-107">One-way duplex with session</span></span>
  - <span data-ttu-id="c8181-108">Dúplex completo con sesión</span><span class="sxs-lookup"><span data-stu-id="c8181-108">Full duplex with session</span></span>
- <span data-ttu-id="c8181-109">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="c8181-109">One-way</span></span>

<span data-ttu-id="c8181-110">Es posible asignar estos tipos de RPC de forma bastante natural a los conceptos de gRPC existentes y este capítulo examinará cada una de estas áreas a su vez.</span><span class="sxs-lookup"><span data-stu-id="c8181-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts and this chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="c8181-111">Los ejemplos similares se explorarán con mucha mayor profundidad en el [capítulo 5](migrate-wcf-to-grpc.md).</span><span class="sxs-lookup"><span data-stu-id="c8181-111">Similar examples will be explored in much greater depth in [Chapter 5](migrate-wcf-to-grpc.md).</span></span>

| <span data-ttu-id="c8181-112">WCF</span><span class="sxs-lookup"><span data-stu-id="c8181-112">WCF</span></span> | <span data-ttu-id="c8181-113">gRPC</span><span class="sxs-lookup"><span data-stu-id="c8181-113">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="c8181-114">Solicitud/respuesta normal</span><span class="sxs-lookup"><span data-stu-id="c8181-114">Regular request/reply</span></span> | <span data-ttu-id="c8181-115">Unario</span><span class="sxs-lookup"><span data-stu-id="c8181-115">Unary</span></span> |
| <span data-ttu-id="c8181-116">Servicio dúplex con sesión mediante una interfaz de devolución de llamada de cliente</span><span class="sxs-lookup"><span data-stu-id="c8181-116">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="c8181-117">Streaming de servidor</span><span class="sxs-lookup"><span data-stu-id="c8181-117">Server streaming</span></span> |
| <span data-ttu-id="c8181-118">Servicio dúplex completo con sesión</span><span class="sxs-lookup"><span data-stu-id="c8181-118">Full duplex service with session</span></span> | <span data-ttu-id="c8181-119">Streaming bidireccional</span><span class="sxs-lookup"><span data-stu-id="c8181-119">Bidirectional streaming</span></span> |
| <span data-ttu-id="c8181-120">Operaciones unidireccionales</span><span class="sxs-lookup"><span data-stu-id="c8181-120">One-way operations</span></span> | <span data-ttu-id="c8181-121">Streaming de cliente</span><span class="sxs-lookup"><span data-stu-id="c8181-121">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="c8181-122">Solicitud/respuesta</span><span class="sxs-lookup"><span data-stu-id="c8181-122">Request/reply</span></span>

<span data-ttu-id="c8181-123">Para los métodos de solicitud/respuesta simples que toman y devuelven pequeñas cantidades de datos, use el patrón gRPC más sencillo, el RPC unario.</span><span class="sxs-lookup"><span data-stu-id="c8181-123">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="c8181-124">Como puede ver, la implementación de un método de servicio RPC unario de gRPC es muy similar a la implementación de una operación de WCF, salvo que con gRPC, invalide un método de clase base en lugar de implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="c8181-124">As you can see, implementing a gRPC unary RPC service method is very similar to implementing a WCF operation, except that with gRPC you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="c8181-125">Tenga en cuenta que, en el servidor, los métodos base de gRPC siempre devuelven un <xref:System.Threading.Tasks.Task%601>, aunque el cliente proporciona métodos asincrónicos y de bloqueo para llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="c8181-125">Note that on the server, gRPC base methods always return a <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="c8181-126">Dúplex de WCF, unidireccional a cliente</span><span class="sxs-lookup"><span data-stu-id="c8181-126">WCF duplex, one-way to client</span></span>

<span data-ttu-id="c8181-127">Las aplicaciones WCF (con ciertos enlaces) pueden crear una conexión persistente entre el cliente y el servidor, y el servidor puede enviar datos de forma asincrónica al cliente hasta que se cierre la conexión, mediante una *interfaz de devolución de llamada* especificada en la propiedad <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c8181-127">WCF applications (with certain bindings) can create a persistent connection between client and server, and the server can asynchronously send data to the client until the connection is closed, using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="c8181-128">los servicios de gRPC proporcionan una funcionalidad similar con las secuencias de mensajes.</span><span class="sxs-lookup"><span data-stu-id="c8181-128">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="c8181-129">Las secuencias no se asignan *exactamente* a los servicios dúplex de WCF en términos de implementación, pero se pueden lograr los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="c8181-129">Streams don't map *exactly* to WCF duplex services in terms of implementation, but the same results can be achieved.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="c8181-130">streaming de gRPC</span><span class="sxs-lookup"><span data-stu-id="c8181-130">gRPC streaming</span></span>

<span data-ttu-id="c8181-131">gRPC admite la creación de secuencias persistentes del cliente al servidor y del servidor al cliente.</span><span class="sxs-lookup"><span data-stu-id="c8181-131">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="c8181-132">Ambos tipos de flujo pueden estar activos simultáneamente. Esto se denomina streaming bidireccional.</span><span class="sxs-lookup"><span data-stu-id="c8181-132">Both types of stream may be active concurrently; this is called bidirectional streaming.</span></span> <span data-ttu-id="c8181-133">Los flujos se pueden usar para mensajería arbitraria o asincrónica a lo largo del tiempo, o para pasar grandes conjuntos de datos que son demasiado grandes para generarlos y enviarlos en una sola solicitud o respuesta.</span><span class="sxs-lookup"><span data-stu-id="c8181-133">Streams can be used for arbitrary, asynchronous messaging over time, or for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="c8181-134">En el ejemplo siguiente se muestra un RPC de streaming de servidor.</span><span class="sxs-lookup"><span data-stu-id="c8181-134">The following example shows a server streaming RPC.</span></span>

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

<span data-ttu-id="c8181-135">Esta secuencia de servidor podría consumirse desde una aplicación cliente como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8181-135">This server stream could be consumed from a client application as shown in the following code:</span></span>

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
> <span data-ttu-id="c8181-136">Las RPC de streaming de servidor son útiles para los servicios de estilo de suscripción, así como para enviar conjuntos de datasets muy grandes cuando sería ineficaz o imposible crear todo el conjunto de conjuntos de servidores en la memoria.</span><span class="sxs-lookup"><span data-stu-id="c8181-136">Server streaming RPCs are useful for subscription-style services, and also for sending very large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="c8181-137">Sin embargo, las respuestas de streaming no son tan rápidas como el envío de `repeated` campos en un solo mensaje, por lo que no debe usarse un streaming de reglas para conjuntos de valores pequeños.</span><span class="sxs-lookup"><span data-stu-id="c8181-137">However, streaming responses isn't as fast as sending `repeated` fields in a single message, so as a rule streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-to-wcf"></a><span data-ttu-id="c8181-138">Diferencias con WCF</span><span class="sxs-lookup"><span data-stu-id="c8181-138">Differences to WCF</span></span>

<span data-ttu-id="c8181-139">Un servicio de dúplex de WCF usa una interfaz de devolución de llamada de cliente que puede tener varios métodos.</span><span class="sxs-lookup"><span data-stu-id="c8181-139">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="c8181-140">Un servicio de streaming de gRPC Server solo puede enviar mensajes a través de un único flujo.</span><span class="sxs-lookup"><span data-stu-id="c8181-140">A gRPC server streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="c8181-141">Si necesita varios métodos, use un tipo de mensaje con un [campo cualquier o un campo](protobuf-any-oneof.md) para enviar diferentes mensajes, y escriba código en el cliente para controlarlos.</span><span class="sxs-lookup"><span data-stu-id="c8181-141">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="c8181-142">En WCF, la clase [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sesión se mantiene activa hasta que se cierra la conexión y se puede llamar a varios métodos dentro de la sesión.</span><span class="sxs-lookup"><span data-stu-id="c8181-142">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed, and multiple methods may be called within the session.</span></span> <span data-ttu-id="c8181-143">En gRPC, el `Task` devuelto por el método de implementación no debe completarse hasta que se cierre la conexión.</span><span class="sxs-lookup"><span data-stu-id="c8181-143">In gRPC, the `Task` returned by the implementation method shouldn't complete until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="c8181-144">Operaciones unidireccionales de WCF y transmisión por secuencias de cliente gRPC</span><span class="sxs-lookup"><span data-stu-id="c8181-144">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="c8181-145">WCF proporciona operaciones unidireccionales (marcadas con `[OperationContract(IsOneWay = true)]`) que devuelven una confirmación específica del transporte.</span><span class="sxs-lookup"><span data-stu-id="c8181-145">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="c8181-146">los métodos de servicio gRPC siempre devuelven una respuesta, incluso si está vacía, y el cliente siempre debe esperar esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="c8181-146">gRPC service methods always return a response, even if it's empty, and the client should always await that response.</span></span> <span data-ttu-id="c8181-147">En el caso de la mensajería de estilo "desencadenar y olvidar" en gRPC, puede crear un servicio de streaming de cliente.</span><span class="sxs-lookup"><span data-stu-id="c8181-147">For "fire-and-forget" style messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="c8181-148">thing_log. proto</span><span class="sxs-lookup"><span data-stu-id="c8181-148">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="c8181-149">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="c8181-149">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="c8181-150">Ejemplo de cliente ThingLog</span><span class="sxs-lookup"><span data-stu-id="c8181-150">ThingLog client example</span></span>

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

<span data-ttu-id="c8181-151">De nuevo, las RPC de streaming de cliente se pueden usar para mensajería de desencadenamiento y olvidar, tal como se muestra en el ejemplo anterior, pero también para enviar conjuntos de valores de gran tamaño al servidor.</span><span class="sxs-lookup"><span data-stu-id="c8181-151">Again, client streaming RPCs can be used for fire-and-forget messaging as shown in the previous example, but also for sending very large datasets to the server.</span></span> <span data-ttu-id="c8181-152">Se aplica la misma advertencia sobre el rendimiento: para conjuntos de información más pequeños, use `repeated` campos en los mensajes normales.</span><span class="sxs-lookup"><span data-stu-id="c8181-152">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="c8181-153">Servicios dúplex completo de WCF</span><span class="sxs-lookup"><span data-stu-id="c8181-153">WCF full duplex services</span></span>

<span data-ttu-id="c8181-154">El enlace dúplex de WCF admite varias operaciones unidireccionales en la interfaz de servicio y la interfaz de devolución de llamada de cliente, lo que permite conversaciones en curso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="c8181-154">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface, allowing ongoing conversations between client and server.</span></span> <span data-ttu-id="c8181-155">gRPC admite algo similar a las RPC de streaming bidireccional, donde ambos parámetros se marcan con el modificador `stream`.</span><span class="sxs-lookup"><span data-stu-id="c8181-155">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="c8181-156">chat. proto</span><span class="sxs-lookup"><span data-stu-id="c8181-156">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="c8181-157">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="c8181-157">ChatterService.cs</span></span>

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

<span data-ttu-id="c8181-158">En el ejemplo anterior, puede ver que el método de implementación recibe una secuencia de solicitud (`IAsyncStreamReader<MessageRequest>`) y una secuencia de respuesta (`IServerStreamWriter<MessageResponse>`) y puede leer y escribir mensajes hasta que se cierre la conexión.</span><span class="sxs-lookup"><span data-stu-id="c8181-158">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`), and can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="c8181-159">Cliente chatter</span><span class="sxs-lookup"><span data-stu-id="c8181-159">Chatter client</span></span>

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
><span data-ttu-id="c8181-160">[Anterior](wcf-bindings.md)
>[Siguiente](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="c8181-160">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
