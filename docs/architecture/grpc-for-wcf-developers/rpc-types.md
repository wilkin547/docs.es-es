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
# <a name="types-of-rpc"></a><span data-ttu-id="ee6d9-103">Tipos de RPC</span><span class="sxs-lookup"><span data-stu-id="ee6d9-103">Types of RPC</span></span>

<span data-ttu-id="ee6d9-104">Como desarrollador de Windows Communication Foundation (WCF), probablemente esté acostumbrado a tratar con los siguientes tipos de llamada a procedimiento remoto (RPC):</span><span class="sxs-lookup"><span data-stu-id="ee6d9-104">As a Windows Communication Foundation (WCF) developer, you're probably used to dealing with the following types of remote procedure call (RPC):</span></span>

- <span data-ttu-id="ee6d9-105">Solicitud/respuesta</span><span class="sxs-lookup"><span data-stu-id="ee6d9-105">Request/reply</span></span>
- <span data-ttu-id="ee6d9-106">Duplex:</span><span class="sxs-lookup"><span data-stu-id="ee6d9-106">Duplex:</span></span>
  - <span data-ttu-id="ee6d9-107">Dúplex unidireccional con sesión</span><span class="sxs-lookup"><span data-stu-id="ee6d9-107">One-way duplex with session</span></span>
  - <span data-ttu-id="ee6d9-108">Dúplex completo con sesión</span><span class="sxs-lookup"><span data-stu-id="ee6d9-108">Full duplex with session</span></span>
- <span data-ttu-id="ee6d9-109">Unidireccional</span><span class="sxs-lookup"><span data-stu-id="ee6d9-109">One-way</span></span>

<span data-ttu-id="ee6d9-110">Es posible asignar estos tipos de RPC de forma bastante natural a los conceptos de gRPC existentes.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-110">It's possible to map these RPC types fairly naturally to existing gRPC concepts.</span></span> <span data-ttu-id="ee6d9-111">Este capítulo examinará cada una de estas áreas a su vez.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-111">This chapter will look at each of these areas in turn.</span></span> <span data-ttu-id="ee6d9-112">[El capítulo 5](migrate-wcf-to-grpc.md) explorará ejemplos similares en mayor profundidad.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-112">[Chapter 5](migrate-wcf-to-grpc.md) will explore similar examples in greater depth.</span></span>

| <span data-ttu-id="ee6d9-113">WCF</span><span class="sxs-lookup"><span data-stu-id="ee6d9-113">WCF</span></span> | <span data-ttu-id="ee6d9-114">gRPC</span><span class="sxs-lookup"><span data-stu-id="ee6d9-114">gRPC</span></span> |
| --- | ---- |
| <span data-ttu-id="ee6d9-115">Solicitud/respuesta regular</span><span class="sxs-lookup"><span data-stu-id="ee6d9-115">Regular request/reply</span></span> | <span data-ttu-id="ee6d9-116">Unario</span><span class="sxs-lookup"><span data-stu-id="ee6d9-116">Unary</span></span> |
| <span data-ttu-id="ee6d9-117">Servicio dúplex con sesión mediante una interfaz de devolución de llamada de cliente</span><span class="sxs-lookup"><span data-stu-id="ee6d9-117">Duplex service with session using a client callback interface</span></span> | <span data-ttu-id="ee6d9-118">Transmisión de servidores</span><span class="sxs-lookup"><span data-stu-id="ee6d9-118">Server streaming</span></span> |
| <span data-ttu-id="ee6d9-119">Servicio dúplex completo con sesión</span><span class="sxs-lookup"><span data-stu-id="ee6d9-119">Full duplex service with session</span></span> | <span data-ttu-id="ee6d9-120">Transmisión bidireccional</span><span class="sxs-lookup"><span data-stu-id="ee6d9-120">Bidirectional streaming</span></span> |
| <span data-ttu-id="ee6d9-121">Operaciones unidireccionales</span><span class="sxs-lookup"><span data-stu-id="ee6d9-121">One-way operations</span></span> | <span data-ttu-id="ee6d9-122">Transmisión de clientes</span><span class="sxs-lookup"><span data-stu-id="ee6d9-122">Client streaming</span></span> |

## <a name="requestreply"></a><span data-ttu-id="ee6d9-123">Solicitud/respuesta</span><span class="sxs-lookup"><span data-stu-id="ee6d9-123">Request/reply</span></span>

<span data-ttu-id="ee6d9-124">Para métodos simples de solicitud/respuesta que toman y devuelven pequeñas cantidades de datos, utilice el patrón gRPC más simple, el RPC unario.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-124">For simple request/reply methods that take and return small amounts of data, use the simplest gRPC pattern, the unary RPC.</span></span>

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

<span data-ttu-id="ee6d9-125">Como puede ver, implementar un método de servicio RPC unario gRPC es similar a implementar una operación WCF.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-125">As you can see, implementing a gRPC unary RPC service method is similar to implementing a WCF operation.</span></span> <span data-ttu-id="ee6d9-126">La diferencia es que con gRPC, se reemplaza un método de clase base en lugar de implementar una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-126">The difference is that with gRPC, you override a base class method instead of implementing an interface.</span></span> <span data-ttu-id="ee6d9-127">En el servidor, los métodos base gRPC siempre devuelven, <xref:System.Threading.Tasks.Task%601>aunque el cliente proporciona métodos asincrónicos y de bloqueo para llamar al servicio.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-127">On the server, gRPC base methods always return <xref:System.Threading.Tasks.Task%601>, although the client provides both async and blocking methods to call the service.</span></span>

## <a name="wcf-duplex-one-way-to-client"></a><span data-ttu-id="ee6d9-128">Dúplex WCF, una forma de llegar al cliente</span><span class="sxs-lookup"><span data-stu-id="ee6d9-128">WCF duplex, one way to client</span></span>

<span data-ttu-id="ee6d9-129">Las aplicaciones WCF (con determinados enlaces) pueden crear una conexión persistente entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-129">WCF applications (with certain bindings) can create a persistent connection between client and server.</span></span> <span data-ttu-id="ee6d9-130">El servidor puede enviar datos de forma asincrónica al cliente hasta que se <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> cierre la conexión mediante una *interfaz* de devolución de llamada especificada en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-130">The server can asynchronously send data to the client until the connection is closed, by using a *callback interface* specified in the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A?displayProperty=nameWithType> property.</span></span>

<span data-ttu-id="ee6d9-131">Los servicios gRPC proporcionan una funcionalidad similar con secuencias de mensajes.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-131">gRPC services provide similar functionality with message streams.</span></span> <span data-ttu-id="ee6d9-132">Las secuencias no se asignan *exactamente* a los servicios dúplex DE WCF en términos de implementación, pero puede lograr los mismos resultados.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-132">Streams don't map *exactly* to WCF duplex services in terms of implementation, but you can achieve the same results.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="ee6d9-133">gRPC streaming</span><span class="sxs-lookup"><span data-stu-id="ee6d9-133">gRPC streaming</span></span>

<span data-ttu-id="ee6d9-134">gRPC admite la creación de secuencias persistentes de cliente a servidor y de servidor a cliente.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-134">gRPC supports the creation of persistent streams from client to server, and from server to client.</span></span> <span data-ttu-id="ee6d9-135">Ambos tipos de secuencia pueden estar activos simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-135">Both types of stream can be active concurrently.</span></span> <span data-ttu-id="ee6d9-136">Esta capacidad se denomina transmisión bidireccional.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-136">This ability is called bidirectional streaming.</span></span>

<span data-ttu-id="ee6d9-137">Puede usar secuencias para mensajería asincrónica arbitraria a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-137">You can use streams for arbitrary, asynchronous messaging over time.</span></span> <span data-ttu-id="ee6d9-138">O bien, puede usarlos para pasar conjuntos de datos grandes que son demasiado grandes para generar y enviar una sola solicitud o respuesta.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-138">Or you can use them for passing large datasets that are too big to generate and send in a single request or response.</span></span>

<span data-ttu-id="ee6d9-139">En el ejemplo siguiente se muestra un RPC de streaming de servidor.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-139">The following example shows a server-streaming RPC.</span></span>

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

<span data-ttu-id="ee6d9-140">Esta secuencia de servidor se puede consumir desde una aplicación cliente, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee6d9-140">This server stream can be consumed from a client application, as shown in the following code:</span></span>

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
> <span data-ttu-id="ee6d9-141">Las RPC de streaming de servidor son útiles para los servicios de estilo de suscripción.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-141">Server-streaming RPCs are useful for subscription-style services.</span></span> <span data-ttu-id="ee6d9-142">También son útiles para enviar conjuntos de datos grandes cuando sería ineficiente o imposible crear todo el conjunto de datos en memoria.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-142">They're also useful for sending large datasets when it would be inefficient or impossible to build the entire dataset in memory.</span></span> <span data-ttu-id="ee6d9-143">Sin embargo, las respuestas de `repeated` streaming no son tan rápidas como enviar campos en un solo mensaje.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-143">However, streaming responses isn't as fast as sending `repeated` fields in a single message.</span></span> <span data-ttu-id="ee6d9-144">Por regla general, la transmisión por secuencias no debe usarse para conjuntos de datos pequeños.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-144">As a rule, streaming shouldn't be used for small datasets.</span></span>

### <a name="differences-from-wcf"></a><span data-ttu-id="ee6d9-145">Diferencias con WCF</span><span class="sxs-lookup"><span data-stu-id="ee6d9-145">Differences from WCF</span></span>

<span data-ttu-id="ee6d9-146">Un servicio dúplex WCF usa una interfaz de devolución de llamada de cliente que puede tener varios métodos.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-146">A WCF duplex service uses a client callback interface that can have multiple methods.</span></span> <span data-ttu-id="ee6d9-147">Un servicio de streaming de servidor gRPC solo puede enviar mensajes a través de una sola secuencia.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-147">A gRPC server-streaming service can only send messages over a single stream.</span></span> <span data-ttu-id="ee6d9-148">Si necesita varios métodos, use un tipo de mensaje con [un campo Any o uno de ellos](protobuf-any-oneof.md) para enviar mensajes diferentes y escriba código en el cliente para controlarlos.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-148">If you need multiple methods, use a message type with either [an Any field or a oneof field](protobuf-any-oneof.md) to send different messages, and write code in the client to handle them.</span></span>

<span data-ttu-id="ee6d9-149">En WCF, la clase [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) con la sesión se mantiene activa hasta que se cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-149">In WCF, the [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) class with the session is kept alive until the connection is closed.</span></span> <span data-ttu-id="ee6d9-150">Se pueden llamar a varios métodos dentro de la sesión.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-150">Multiple methods can be called within the session.</span></span> <span data-ttu-id="ee6d9-151">En gRPC, `Task` el que devuelve el método de implementación no debe finalizar hasta que se cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-151">In gRPC, the `Task` that the implementation method returns shouldn't finish until the connection is closed.</span></span>

## <a name="wcf-one-way-operations-and-grpc-client-streaming"></a><span data-ttu-id="ee6d9-152">Operaciones unidireccionales de WCF y streaming de cliente gRPC</span><span class="sxs-lookup"><span data-stu-id="ee6d9-152">WCF one-way operations and gRPC client streaming</span></span>

<span data-ttu-id="ee6d9-153">WCF proporciona operaciones unidireccionales `[OperationContract(IsOneWay = true)]`(marcadas con ) que devuelven una confirmación específica del transporte.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-153">WCF provides one-way operations (marked with `[OperationContract(IsOneWay = true)]`) that return a transport-specific acknowledgement.</span></span> <span data-ttu-id="ee6d9-154">Los métodos de servicio gRPC siempre devuelven una respuesta, incluso si está vacía.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-154">gRPC service methods always return a response, even if it's empty.</span></span> <span data-ttu-id="ee6d9-155">El cliente siempre debe esperar esa respuesta.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-155">The client should always await that response.</span></span> <span data-ttu-id="ee6d9-156">Para el estilo de mensajería "fire-and-forget" en gRPC, puede crear un servicio de streaming de cliente.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-156">For the "fire-and-forget" style of messaging in gRPC, you can create a client streaming service.</span></span>

### <a name="thing_logproto"></a><span data-ttu-id="ee6d9-157">thing_log.proto</span><span class="sxs-lookup"><span data-stu-id="ee6d9-157">thing_log.proto</span></span>

```protobuf
service ThingLog {
  rpc OpenConnection(stream Thing) returns (ConnectionClosedResponse);
}
```

### <a name="thinglogservicecs"></a><span data-ttu-id="ee6d9-158">ThingLogService.cs</span><span class="sxs-lookup"><span data-stu-id="ee6d9-158">ThingLogService.cs</span></span>

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

### <a name="thinglog-client-example"></a><span data-ttu-id="ee6d9-159">Ejemplo de cliente de ThingLog</span><span class="sxs-lookup"><span data-stu-id="ee6d9-159">ThingLog client example</span></span>

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

<span data-ttu-id="ee6d9-160">Puede utilizar RPC de transmisión de cliente para la mensajería fire-and-forget, como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-160">You can use client-streaming RPCs for fire-and-forget messaging, as shown in the previous example.</span></span> <span data-ttu-id="ee6d9-161">También puede usarlos para enviar conjuntos de datos muy grandes al servidor.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-161">You can also use them for sending very large datasets to the server.</span></span> <span data-ttu-id="ee6d9-162">Se aplica la misma advertencia sobre el `repeated` rendimiento: para conjuntos de datos más pequeños, utilice campos en mensajes normales.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-162">The same warning about performance applies: for smaller datasets, use `repeated` fields in regular messages.</span></span>

## <a name="wcf-full-duplex-services"></a><span data-ttu-id="ee6d9-163">Servicios dúplex completo de WCF</span><span class="sxs-lookup"><span data-stu-id="ee6d9-163">WCF full-duplex services</span></span>

<span data-ttu-id="ee6d9-164">El enlace dúplex WCF admite varias operaciones unidireccionales tanto en la interfaz de servicio como en la interfaz de devolución de llamada del cliente.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-164">WCF duplex binding supports multiple one-way operations on both the service interface and the client callback interface.</span></span> <span data-ttu-id="ee6d9-165">Este soporte permite conversaciones en curso entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-165">This support allows ongoing conversations between client and server.</span></span> <span data-ttu-id="ee6d9-166">gRPC admite algo similar con RPC de streaming bidireccionales, `stream` donde ambos parámetros se marcan con el modificador.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-166">gRPC supports something similar with bidirectional streaming RPCs, where both parameters are marked with the `stream` modifier.</span></span>

### <a name="chatproto"></a><span data-ttu-id="ee6d9-167">chat.proto</span><span class="sxs-lookup"><span data-stu-id="ee6d9-167">chat.proto</span></span>

```protobuf
service Chatter {
    rpc Connect(stream IncomingMessage) returns (stream OutgoingMessage);
}
```

### <a name="chatterservicecs"></a><span data-ttu-id="ee6d9-168">ChatterService.cs</span><span class="sxs-lookup"><span data-stu-id="ee6d9-168">ChatterService.cs</span></span>

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

<span data-ttu-id="ee6d9-169">En el ejemplo anterior, puede ver que el método`IAsyncStreamReader<MessageRequest>`de implementación recibe`IServerStreamWriter<MessageResponse>`una secuencia de solicitudes ( ) y una secuencia de respuesta ( ).</span><span class="sxs-lookup"><span data-stu-id="ee6d9-169">In the previous example, you can see that the implementation method receives both a request stream (`IAsyncStreamReader<MessageRequest>`) and a response stream (`IServerStreamWriter<MessageResponse>`).</span></span> <span data-ttu-id="ee6d9-170">El método puede leer y escribir mensajes hasta que se cierra la conexión.</span><span class="sxs-lookup"><span data-stu-id="ee6d9-170">The method can read and write messages until the connection is closed.</span></span>

### <a name="chatter-client"></a><span data-ttu-id="ee6d9-171">Cliente de Chatter</span><span class="sxs-lookup"><span data-stu-id="ee6d9-171">Chatter client</span></span>

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
><span data-ttu-id="ee6d9-172">[Anterior](wcf-bindings.md)
>[Siguiente](metadata.md)</span><span class="sxs-lookup"><span data-stu-id="ee6d9-172">[Previous](wcf-bindings.md)
[Next](metadata.md)</span></span>
