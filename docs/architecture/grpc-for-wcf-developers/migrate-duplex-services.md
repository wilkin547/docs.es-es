---
title: Migración de servicios dúplex de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar diversas formas de servicio de WCF dúplex a gRPC streaming Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: 1702c9f7659f056af9009e81847f28c6e65b277c
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2019
ms.locfileid: "73841484"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="4b9ae-103">Migración de servicios dúplex de WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="4b9ae-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="4b9ae-104">Ahora que los conceptos básicos están en vigor, en esta sección se examinarán los servicios de *streaming* gRPC más complicados.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-104">Now that the basic concepts are in place, this section will look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="4b9ae-105">Hay varias maneras de usar los servicios dúplex en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="4b9ae-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="4b9ae-106">El cliente inicia algunos servicios y, a continuación, transmiten los datos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="4b9ae-107">Otros servicios de dúplex completo pueden implicar una comunicación bidireccional más continua como el ejemplo de "calculadora" clásico de la documentación de WCF.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-107">Other full-duplex services might involve more ongoing two-way communication like the classic "Calculator" example from the WCF documentation.</span></span> <span data-ttu-id="4b9ae-108">En este capítulo se tomarán dos posibles implementaciones de WCF "bursátiles" y se migrarán a gRPC: una con una RPC de streaming de servidor y la otra mediante una RPC de streaming bidireccional.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-108">This chapter will take two possible WCF "Stock Ticker" implementations and migrate them to gRPC: one using a server streaming RPC, and the other one using a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="4b9ae-109">RPC de streaming de servidor</span><span class="sxs-lookup"><span data-stu-id="4b9ae-109">Server streaming RPC</span></span>

<span data-ttu-id="4b9ae-110">En la [solución WCF de ejemplo SimpleStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, hay un servicio dúplex en el que el cliente inicia la conexión con una lista de símbolos bursátiles y el servidor usa la *interfaz de devolución de llamada* para enviar las actualizaciones a medida que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, there's a duplex service where the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="4b9ae-111">El cliente implementa esa interfaz para responder a las llamadas del servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="4b9ae-112">La solución WCF</span><span class="sxs-lookup"><span data-stu-id="4b9ae-112">The WCF solution</span></span>

<span data-ttu-id="4b9ae-113">La solución WCF se implementa como un servidor de NetTCP autohospedado en una aplicación de consola de .NET Framework 4. x.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-113">The WCF solution is implemented as a self-hosted NetTCP server in a .NET Framework 4.x console application.</span></span>

#### <a name="the-servicecontract"></a><span data-ttu-id="4b9ae-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="4b9ae-114">The ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="4b9ae-115">El servicio tiene un único método sin tipo de valor devuelto, ya que utilizará la interfaz de devolución de llamada `ISimpleStockTickerCallback` para enviar datos al cliente en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-115">The service has a single method with no return type, because it will be using the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="4b9ae-116">La interfaz de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="4b9ae-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="4b9ae-117">Las implementaciones de estas interfaces se pueden encontrar en la solución, junto con las dependencias externas falsificadas para proporcionar datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-117">The implementations of these interfaces can be found in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="4b9ae-118">streaming de gRPC</span><span class="sxs-lookup"><span data-stu-id="4b9ae-118">gRPC streaming</span></span>

<span data-ttu-id="4b9ae-119">La forma gRPC de controlar los datos en tiempo real es diferente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-119">The gRPC way of handling real-time data is different.</span></span> <span data-ttu-id="4b9ae-120">Una llamada desde el cliente al servidor puede crear una secuencia persistente, que se puede supervisar para los mensajes que llegan de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-120">A call from client to server can create a persistent stream, which can be monitored for messages arriving asynchronously.</span></span> <span data-ttu-id="4b9ae-121">A pesar de la diferencia, los flujos pueden ser una forma más intuitiva de trabajar con estos datos y son más relevantes en la programación moderna con énfasis en LINQ, secuencias reactivas, programación funcional, etc.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming with the emphasis on LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="4b9ae-122">La definición del servicio necesita dos mensajes: uno para la solicitud y otro para la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-122">The service definition needs two messages: one for the request, and one for the stream.</span></span> <span data-ttu-id="4b9ae-123">El servicio devuelve un flujo del mensaje de `StockTickerUpdate` mediante la palabra clave `stream` en su declaración `return`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-123">The service returns a stream of the `StockTickerUpdate` message using the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="4b9ae-124">Se recomienda agregar una `Timestamp` a la actualización para mostrar la hora exacta a la que ha cambiado el precio.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-124">It's recommended that you add a `Timestamp` to the update to show the exact time the price changed.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="4b9ae-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="4b9ae-125">simple_stock_ticker.proto</span></span>

```protobuf
syntax = "proto3";

option csharp_namespace = "TraderSys.SimpleStockTickerServer.Protos";

import "google/protobuf/timestamp.proto";

package SimpleStockTickerServer;

service SimpleStockTicker {
  rpc Subscribe (SubscribeRequest) returns (stream StockTickerUpdate);
}

message SubscribeRequest {
  repeated string symbols = 1;
}

message StockTickerUpdate {
  string symbol = 1;
  int32 price_cents = 2;
  google.protobuf.Timestamp time = 3;
}
```

### <a name="implement-the-simplestockticker"></a><span data-ttu-id="4b9ae-126">Implementación de SimpleStockTicker</span><span class="sxs-lookup"><span data-stu-id="4b9ae-126">Implement the SimpleStockTicker</span></span>

<span data-ttu-id="4b9ae-127">Vuelva a usar el `StockPriceSubscriber` falso del proyecto WCF mediante la copia de las tres clases de la biblioteca de clases de `TraderSys.StockMarket` en una nueva biblioteca de clases de .NET Standard en la solución de destino.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="4b9ae-128">Para seguir los procedimientos recomendados, agregue un tipo de `Factory` para crear instancias del mismo y registrar el `IStockPriceSubscriberFactory` con los servicios de inserción de dependencias de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-128">To better follow best practices, add a `Factory` type to create instances of it and register the `IStockPriceSubscriberFactory` with ASP.NET Core's dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="4b9ae-129">La implementación de fábrica</span><span class="sxs-lookup"><span data-stu-id="4b9ae-129">The factory implementation</span></span>

```csharp
public interface IStockPriceSubscriberFactory
{
    IStockPriceSubscriber GetSubscriber(string[] symbols);
}

public class StockPriceSubscriberFactory : IStockPriceSubscriberFactory
{
    public IStockPriceSubscriber GetSubscriber(string[] symbols)
    {
        return new StockPriceSubscriber(symbols);
    }
}
```

#### <a name="registering-the-factory"></a><span data-ttu-id="4b9ae-130">Registro del generador</span><span class="sxs-lookup"><span data-stu-id="4b9ae-130">Registering the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="4b9ae-131">Ahora, esta clase se puede usar para implementar el servicio gRPC StockTicker.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-131">Now, this class can be used to implement the gRPC StockTicker service.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="4b9ae-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="4b9ae-132">StockTickerService.cs</span></span>

```csharp
public class StockTickerService : Protos.SimpleStockTicker.SimpleStockTickerBase
{
    private readonly IStockPriceSubscriberFactory _subscriberFactory;

    public StockTickerService(IStockPriceSubscriberFactory subscriberFactory)
    {
        _subscriberFactory = subscriberFactory;
    }

    public override async Task Subscribe(SubscribeRequest request, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
    {
        var subscriber = _subscriberFactory.GetSubscriber(request.Symbols.ToArray());

        subscriber.Update += async (sender, args) =>
            await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

        await AwaitCancellation(context.CancellationToken);
    }

    private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
    {
        try
        {
            await stream.WriteAsync(new StockTickerUpdate
            {
                Symbol = symbol,
                PriceCents = (int)(price * 100),
                Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
            });
        }
        catch (Exception e)
        {
            // Handle any errors due to broken connection etc.
            _logger.LogError($"Failed to write message: {e.Message}");
        }
    }

    private static Task AwaitCancellation(CancellationToken token)
    {
        var completion = new TaskCompletionSource<object>();
        token.Register(() => completion.SetResult(null));
        return completion.Task;
    }
}
```

<span data-ttu-id="4b9ae-133">Como puede ver, aunque la declaración del archivo `.proto` indica que el método "devuelve" un flujo de mensajes `StockTickerUpdate`, en realidad devuelve un `Task`de vainilla.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-133">As you can see, although the declaration in the `.proto` file says the method "returns" a stream of `StockTickerUpdate` messages, in fact it returns a vanilla `Task`.</span></span> <span data-ttu-id="4b9ae-134">El trabajo de creación de la secuencia se controla mediante el código generado y las bibliotecas en tiempo de ejecución de gRPC, que proporcionan la secuencia de respuesta `IServerStreamWriter<StockTickerUpdate>`, lista para su uso.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="4b9ae-135">A diferencia de un servicio de dúplex de WCF, en el que la instancia de la clase de servicio se mantiene activa mientras la conexión está abierta, el servicio gRPC usa la tarea devuelta para mantener el servicio activo.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned Task to keep the service alive.</span></span> <span data-ttu-id="4b9ae-136">La tarea no debe completarse hasta que se cierre la conexión.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-136">The Task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="4b9ae-137">El servicio puede indicar cuándo el cliente ha cerrado la conexión mediante el `CancellationToken` del `ServerCallContext`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="4b9ae-138">Un método estático simple, `AwaitCancellation`, se usa para crear una tarea que se completa cuando se cancela el token.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-138">A simple static method, `AwaitCancellation`, is used to create a Task that completes when the token is canceled.</span></span>

<span data-ttu-id="4b9ae-139">En el método `Subscribe`, obtenga un `StockPriceSubscriber` y agregue un controlador de eventos que escriba en la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="4b9ae-140">Después, espere a que se cierre la conexión, antes de eliminar inmediatamente el `subscriber` para evitar que intente escribir datos en el flujo cerrado.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-140">Then wait for the connection to be closed, before immediately disposing the `subscriber` to prevent it trying to write data to the closed stream.</span></span>

<span data-ttu-id="4b9ae-141">El método `WriteUpdateAsync` tiene un `try`/`catch` bloque para controlar los errores que puedan producirse al escribir un mensaje en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when writing a message to the stream.</span></span> <span data-ttu-id="4b9ae-142">Esta es una consideración importante en las conexiones persistentes a través de redes, que podrían romperse en cualquier milisegundo, ya sea intencionadamente o debido a un error en algún lugar.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-142">This is an important consideration in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="using-the-stocktickerservice-from-a-client-application"></a><span data-ttu-id="4b9ae-143">Usar StockTickerService desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="4b9ae-143">Using the StockTickerService from a client application</span></span>

<span data-ttu-id="4b9ae-144">Siga los mismos pasos de la sección anterior para crear una biblioteca de clases de cliente que se pueda compartir desde el archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="4b9ae-145">En el ejemplo, hay una aplicación de consola de .NET Core 3,0 que muestra cómo usar el cliente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="4b9ae-146">Ejemplo de Program.cs</span><span class="sxs-lookup"><span data-stu-id="4b9ae-146">Example Program.cs</span></span>

```csharp
class Program
{
    static async Task Main(string[] args)
    {
        using var channel = GrpcChannel.ForAddress("https://localhost:5001");
        var client = new SimpleStockTicker.SimpleStockTickerClient(channel);

        var request = new SubscribeRequest();
        request.Symbols.AddRange(args);

        using var stream = client.Subscribe(request);

        var tokenSource = new CancellationTokenSource();

        var task = DisplayAsync(stream.ResponseStream, tokenSource.Token);

        WaitForExitKey();

        tokenSource.Cancel();
        await task;
    }
}
```

<span data-ttu-id="4b9ae-147">En este caso, el método de `Subscribe` en el cliente generado no es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="4b9ae-148">La secuencia se crea y se puede usar inmediatamente, porque su método `MoveNext` es asincrónico y la primera vez que se le llama no se completará hasta que la conexión esté activa.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-148">The stream is created and usable right away, because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="4b9ae-149">La secuencia se pasa a un método `DisplayAsync` asincrónico; a continuación, la aplicación espera a que el usuario presione una tecla y, a continuación, cancela el método `DisplayAsync` y espera a que la tarea se complete antes de salir.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-149">The stream is passed to an async `DisplayAsync` method; the application then waits for the user to press a key, then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9ae-150">Este código usa la nueva C# sintaxis de "Declaración de uso" para desechar la secuencia y el canal cuando finaliza el método de `Main`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-150">This code is using the new C# 8 "using declaration" syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="4b9ae-151">Se trata de un pequeño cambio, pero una buena que reduce las sangrías y las líneas vacías.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-151">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="4b9ae-152">Consumo de la secuencia</span><span class="sxs-lookup"><span data-stu-id="4b9ae-152">Consume the stream</span></span>

<span data-ttu-id="4b9ae-153">Interfaces de devolución de llamada usadas por WCF para permitir que el servidor llame a métodos directamente en el cliente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-153">WCF used callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="4b9ae-154">las secuencias gRPC funcionan de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-154">gRPC streams work differently.</span></span> <span data-ttu-id="4b9ae-155">El cliente recorre en iteración el flujo devuelto y procesa los mensajes, como si se hubieran devuelto desde un método local que devuelve un `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-155">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="4b9ae-156">El tipo de `IAsyncStreamReader<T>` funciona de forma muy similar a un `IEnumerator<T>`: hay un método `MoveNext` que devolverá True siempre que haya más datos y una propiedad `Current` que devuelva el valor más reciente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-156">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`: there's a `MoveNext` method that will return true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="4b9ae-157">La única diferencia es que el método `MoveNext` devuelve un `Task<bool>` en lugar de un `bool`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-157">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="4b9ae-158">El método de extensión `ReadAllAsync` encapsula el flujo en un `IAsyncEnumerable` C# estándar 8 que se puede usar con la nueva sintaxis de `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-158">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

```csharp
static async Task DisplayAsync(IAsyncStreamReader<StockTickerUpdate> stream, CancellationToken token)
{
    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            Console.WriteLine($"{update.Symbol}: {update.Price}");
        }
    }
    catch (RpcException e) when (e.StatusCode == StatusCode.Cancelled)
    {
        return;
    }
    catch (OperationCanceledException)
    {
        Console.WriteLine("Finished.");
    }
}
```

> [!TIP]
> <span data-ttu-id="4b9ae-159">En la sección acerca de las [bibliotecas de cliente](client-libraries.md#iobservable) al final de este capítulo se describe cómo agregar un método de extensión y clases para ajustar `IAsyncStreamReader<T>` en una `IObservable<T>` para desarrolladores que usan patrones de programación reactiva.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-159">The section on [client libraries](client-libraries.md#iobservable) at the end of this chapter looks at how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>` for developers using reactive programming patterns.</span></span>

<span data-ttu-id="4b9ae-160">De nuevo, tenga cuidado de detectar las excepciones aquí debido a la posibilidad de que se produzca un error en la red, así como del <xref:System.OperationCanceledException> que se producirá inevitablemente porque el código usa un <xref:System.Threading.CancellationToken> para interrumpir el bucle.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-160">Again, be careful to catch exceptions here because of the possibility of network failure, as well as the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="4b9ae-161">El tipo de `RpcException` tiene mucha información útil sobre los errores de tiempo de ejecución de gRPC, incluido el `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-161">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="4b9ae-162">Para obtener más información, vea [ *control de errores* en el capítulo 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="4b9ae-162">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="4b9ae-163">Streaming bidireccional</span><span class="sxs-lookup"><span data-stu-id="4b9ae-163">Bidirectional streaming</span></span>

<span data-ttu-id="4b9ae-164">Un servicio de dúplex completo de WCF permite la mensajería asincrónica en tiempo real en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-164">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="4b9ae-165">En el ejemplo de streaming del servidor, el cliente inicia una solicitud y, a continuación, recibe un flujo de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-165">In the server streaming example, the client starts a request, then receives a stream of updates.</span></span> <span data-ttu-id="4b9ae-166">Una versión mejor de ese servicio permitiría al cliente agregar y quitar acciones de la lista sin tener que detener y crear una nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-166">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="4b9ae-167">Esa funcionalidad se ha implementado en la [solución de ejemplo FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="4b9ae-167">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="4b9ae-168">La interfaz `IFullStockTickerService` proporciona tres métodos:</span><span class="sxs-lookup"><span data-stu-id="4b9ae-168">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="4b9ae-169">`Subscribe` inicia la conexión.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-169">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="4b9ae-170">`AddSymbol` agrega un símbolo de cotización para verlo.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-170">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="4b9ae-171">`RemoveSymbol` quita un símbolo de la lista de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-171">`RemoveSymbol` removes a symbol from the watched list.</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(IFullStockTickerCallback))]
public interface IFullStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe();

    [OperationContract(IsOneWay = true)]
    void AddSymbol(string symbol);

    [OperationContract(IsOneWay = true)]
    void RemoveSymbol(string symbol);
}
```

<span data-ttu-id="4b9ae-172">La interfaz de devolución de llamada sigue siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-172">The callback interface remains the same.</span></span>

<span data-ttu-id="4b9ae-173">La implementación de este patrón en gRPC es menos sencilla, ya que ahora hay dos flujos de datos con mensajes que se pasan: uno de cliente a servidor y otro de servidor a cliente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-173">Implementing this pattern in gRPC is less straightforward, because there are now two streams of data with messages being passed: one from client to server, and another from server to client.</span></span> <span data-ttu-id="4b9ae-174">No es posible usar varios métodos para implementar la operación de agregar y quitar, pero se puede pasar más de un tipo de mensaje en una única secuencia, mediante el `Any` tipo o la palabra clave `oneof`, que se trataron en el [capítulo 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="4b9ae-174">It isn't possible to use multiple methods to implement the Add and Remove operation, but more than one type of message can be passed on a single stream, using either the `Any` type or `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="4b9ae-175">Para un caso en el que hay un conjunto específico de tipos que son aceptables, `oneof` es una mejor manera de ir.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-175">For a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="4b9ae-176">Use una `ActionMessage` que puede contener un `AddSymbolRequest` o un `RemoveSymbolRequest`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-176">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`.</span></span>

```protobuf
message ActionMessage {
  oneof action {
    AddSymbolRequest add = 1;
    RemoveSymbolRequest remove = 2;
  }
}

message AddSymbolRequest {
  string symbol = 1;
}

message RemoveSymbolRequest {
  string symbol = 1;
}
```

<span data-ttu-id="4b9ae-177">Declare un servicio de streaming bidireccional que toma un flujo de mensajes `ActionMessage`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-177">Declare a bi-directional streaming service that takes a stream of `ActionMessage` messages.</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="4b9ae-178">La implementación de este servicio es similar al ejemplo anterior, excepto que el primer parámetro del método `Subscribe` es ahora un `IAsyncStreamReader<ActionMessage>`, que se puede usar para controlar las solicitudes de `Add` y `Remove`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-178">The implementation for this service is similar to the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests.</span></span>

```csharp
public override async Task Subscribe(IAsyncStreamReader<ActionMessage> requestStream, IServerStreamWriter<StockTickerUpdate> responseStream, ServerCallContext context)
{
    using var subscriber = _subscriberFactory.GetSubscriber();

    subscriber.Update += async (sender, args) =>
        await WriteUpdateAsync(responseStream, args.Symbol, args.Price);

    var actionsTask = HandleActions(requestStream, subscriber, context.CancellationToken);

    _logger.LogInformation("Subscription started.");
    await AwaitCancellation(context.CancellationToken);

    try { await actionsTask; } catch { /* Ignored */ }

    _logger.LogInformation("Subscription finished.");
}

private async Task WriteUpdateAsync(IServerStreamWriter<StockTickerUpdate> stream, string symbol, decimal price)
{
    try
    {
        await stream.WriteAsync(new StockTickerUpdate
        {
            Symbol = symbol,
            PriceCents = (int)(price * 100),
            Time = Timestamp.FromDateTimeOffset(DateTimeOffset.UtcNow)
        });
    }
    catch (Exception e)
    {
        // Handle any errors due to broken connection etc.
        _logger.LogError($"Failed to write message: {e.Message}");
    }
}

private static Task AwaitCancellation(CancellationToken token)
{
    var completion = new TaskCompletionSource<object>();
    token.Register(() => completion.SetResult(null));
    return completion.Task;
}
```

<span data-ttu-id="4b9ae-179">La clase de `ActionMessage` que gRPC ha generado para nosotros garantiza que solo se puede establecer una de las propiedades `Add` y `Remove`, y la búsqueda de la que no está `null` es una manera válida de buscar el tipo de mensaje que se usa, pero hay una manera mejor.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-179">The `ActionMessage` class that gRPC has generated for us guarantees that only one of the `Add` and `Remove` properties can be set, and finding which one isn't `null` is a valid way of finding which type of message is used, but there's a better way.</span></span> <span data-ttu-id="4b9ae-180">La generación de código también crea un `enum ActionOneOfCase` en la clase `ActionMessage`, que tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="4b9ae-180">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="4b9ae-181">La propiedad `ActionCase` en el objeto de `ActionMessage` se puede utilizar con una instrucción `switch` para determinar qué campo está establecido.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-181">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set.</span></span>

```csharp
private async Task HandleActions(IAsyncStreamReader<ActionMessage> requestStream, IFullStockPriceSubscriber subscriber, CancellationToken token)
{
    await foreach (var action in requestStream.ReadAllAsync(token))
    {
        switch (action.ActionCase)
        {
            case ActionMessage.ActionOneofCase.None:
                _logger.LogWarning("No Action specified.");
                break;
            case ActionMessage.ActionOneofCase.Add:
                subscriber.Add(action.Add.Symbol);
                break;
            case ActionMessage.ActionOneofCase.Remove:
                subscriber.Remove(action.Remove.Symbol);
                break;
            default:
                _logger.LogWarning($"Unknown Action '{action.ActionCase}'.");
                break;
        }
    }
}
```

> [!TIP]
> <span data-ttu-id="4b9ae-182">La instrucción `switch` tiene un caso `default` que registra una advertencia si se encuentra un valor de `ActionOneOfCase` desconocido.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-182">The `switch` statement has a `default` case that logs a warning if an unknown `ActionOneOfCase` value is encountered.</span></span> <span data-ttu-id="4b9ae-183">Esto podría ser útil para indicar que un cliente está usando una versión posterior del archivo `.proto` que ha agregado más acciones.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-183">This could be useful in indicating that a client is using a later version of the `.proto` file which has added more actions.</span></span> <span data-ttu-id="4b9ae-184">Esta es una de las razones por las que el uso de un `switch` es mejor que las pruebas de `null` en los campos conocidos.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-184">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="4b9ae-185">Usar FullStockTickerService desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="4b9ae-185">Use the FullStockTickerService from a client application</span></span>

<span data-ttu-id="4b9ae-186">Hay una sencilla aplicación WPF de .NET Core 3,0 para demostrar el uso de este cliente más complejo.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-186">There's a simple .NET Core 3.0 WPF application to demonstrate use of this more complex client.</span></span> <span data-ttu-id="4b9ae-187">La aplicación completa se puede encontrar [en github](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="4b9ae-187">The full application can be found [on GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="4b9ae-188">El cliente se usa en la clase `MainWindowViewModel`, que obtiene una instancia del tipo de `FullStockTicker.FullStockTickerClient` de la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-188">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection.</span></span>

```csharp
public class MainWindowViewModel : IAsyncDisposable, INotifyPropertyChanged
{
    private readonly FullStockTicker.FullStockTickerClient _client;
    private readonly AsyncDuplexStreamingCall<ActionMessage, StockTickerUpdate> _duplexStream;
    private readonly CancellationTokenSource _cancellationTokenSource;
    private readonly Task _responseTask;
    private string _addSymbol;

    public MainWindowViewModel(FullStockTicker.FullStockTickerClient client)
    {
        _cancellationTokenSource = new CancellationTokenSource();
        _client = client;
        _duplexStream = _client.Subscribe();
        _responseTask = HandleResponsesAsync(_cancellationTokenSource.Token);

        AddCommand = new AsyncCommand(Add, CanAdd);
    }
```

<span data-ttu-id="4b9ae-189">El objeto devuelto por el método `client.Subscribe()` es ahora una instancia del tipo de biblioteca gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, que proporciona un `RequestStream` para enviar solicitudes al servidor y un `ResponseStream` para controlar las respuestas.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-189">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server, and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="4b9ae-190">La secuencia de solicitud se usa desde algunos métodos de `ICommand` de WPF para agregar y quitar símbolos.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-190">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="4b9ae-191">Para cada operación, establezca el campo correspondiente en un objeto de `ActionMessage`:</span><span class="sxs-lookup"><span data-stu-id="4b9ae-191">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

```csharp
private async Task Add()
{
    if (CanAdd())
    {
        await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Add = new AddSymbolRequest {Symbol = AddSymbol}});
    }
}

public async Task Remove(PriceViewModel priceViewModel)
{
    await _duplexStream.RequestStream.WriteAsync(new ActionMessage {Remove = new RemoveSymbolRequest {Symbol = priceViewModel.Symbol}});
    Prices.Remove(priceViewModel);
}
```

> [!IMPORTANT]
> <span data-ttu-id="4b9ae-192">Al establecer el valor de un campo de `oneof` en un mensaje, se borran automáticamente los campos que se han establecido previamente.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-192">Setting a `oneof` field's value on a message automatically clears any fields that have been previously set.</span></span>

<span data-ttu-id="4b9ae-193">La secuencia de respuestas se administra en un método `async` y el `Task` que devuelve se mantiene para eliminarse cuando se cierra la ventana.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-193">The stream of responses is handled in an `async` method, and the `Task` it returns is held to be disposed when the window is closed.</span></span>

```csharp
private async Task HandleResponsesAsync(CancellationToken token)
{
    var stream = _duplexStream.ResponseStream;

    try
    {
        await foreach (var update in stream.ReadAllAsync(token))
        {
            var price = Prices.FirstOrDefault(p => p.Symbol.Equals(update.Symbol));
            if (price == null)
            {
                price = new PriceViewModel(this) {Symbol = update.Symbol, Price = update.PriceCents / 100m};
                Prices.Add(price);
            }
            else
            {
                price.Price = update.PriceCents / 100m;
            }
        }
    }
    catch (OperationCancelledException) { }
}
```

### <a name="client-clean-up"></a><span data-ttu-id="4b9ae-194">Limpieza de cliente</span><span class="sxs-lookup"><span data-stu-id="4b9ae-194">Client clean-up</span></span>

<span data-ttu-id="4b9ae-195">Cuando se cierra la ventana y se desecha el `MainWindowViewModel` (desde el evento de `Closed` de `MainWindow`), se recomienda que elimine correctamente el objeto `AsyncDuplexStreamingCall`.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-195">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), it's recommended that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="4b9ae-196">En concreto, se debe llamar al método `CompleteAsync` en el `RequestStream` para cerrar correctamente el flujo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-196">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="4b9ae-197">En el ejemplo siguiente se muestra el método `DisposeAsync` de la vista de ejemplo-Model:</span><span class="sxs-lookup"><span data-stu-id="4b9ae-197">The following example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public ValueTask DisposeAsync()
{
    try
    {
        await _duplexStream.RequestStream.CompleteAsync().ConfigureAwait(false);
        await _responseTask.ConfigureAwait(false);
    }
    finally
    {
        _duplexStream.Dispose();
    }
}
```

<span data-ttu-id="4b9ae-198">El cierre de las secuencias de solicitud permite al servidor desechar sus propios recursos de manera oportuna.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-198">Closing request streams enables the server to dispose of its own resources in a timely manner.</span></span> <span data-ttu-id="4b9ae-199">Esto mejora la eficiencia y escalabilidad de los servicios y evita excepciones.</span><span class="sxs-lookup"><span data-stu-id="4b9ae-199">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4b9ae-200">[Anterior](migrate-request-reply.md)
>[Siguiente](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="4b9ae-200">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
