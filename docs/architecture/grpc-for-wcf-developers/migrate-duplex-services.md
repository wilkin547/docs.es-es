---
title: Migración de servicios dúplex de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar varias formas de servicios dúplex de WCF a gRPC streaming Services.
ms.date: 09/02/2019
ms.openlocfilehash: 5737f02044ab9e4064f632164db764541a9c4d31
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628545"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a><span data-ttu-id="2a886-103">Migración de servicios dúplex de WCF a gRPC</span><span class="sxs-lookup"><span data-stu-id="2a886-103">Migrate WCF duplex services to gRPC</span></span>

<span data-ttu-id="2a886-104">Ahora que tiene una idea de los conceptos básicos, en esta sección, examinará los servicios de *streaming* gRPC más complicados.</span><span class="sxs-lookup"><span data-stu-id="2a886-104">Now that you have a sense of the basic concepts, in this section, you'll look at the more complicated *streaming* gRPC services.</span></span>

<span data-ttu-id="2a886-105">Hay varias maneras de usar los servicios dúplex en Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2a886-105">There are multiple ways to use duplex services in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="2a886-106">El cliente inicia algunos servicios y, a continuación, transmiten los datos desde el servidor.</span><span class="sxs-lookup"><span data-stu-id="2a886-106">Some services are initiated by the client and then they stream data from the server.</span></span> <span data-ttu-id="2a886-107">Otros servicios de dúplex completo pueden implicar una comunicación bidireccional más continua, como el ejemplo de la calculadora clásico en la documentación de WCF.</span><span class="sxs-lookup"><span data-stu-id="2a886-107">Other full-duplex services might involve more ongoing two-way communication, like the classic Calculator example in the WCF documentation.</span></span> <span data-ttu-id="2a886-108">En este capítulo se tomarán dos posibles implementaciones de tablero de cotizaciones de WCF y se migrarán a gRPC: una que usa una RPC de streaming de servidor y otra que usa una RPC de streaming bidireccional.</span><span class="sxs-lookup"><span data-stu-id="2a886-108">This chapter will take two possible WCF stock ticker implementations and migrate them to gRPC: one that uses a server streaming RPC and another one that uses a bidirectional streaming RPC.</span></span>

## <a name="server-streaming-rpc"></a><span data-ttu-id="2a886-109">RPC de streaming de servidor</span><span class="sxs-lookup"><span data-stu-id="2a886-109">Server streaming RPC</span></span>

<span data-ttu-id="2a886-110">En la [solución WCF de ejemplo SimpleStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, hay un servicio dúplex para el que el cliente inicia la conexión con una lista de símbolos bursátiles y el servidor usa la *interfaz de devolución de llamada* para enviar las actualizaciones a medida que estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="2a886-110">In the [sample SimpleStockTicker WCF solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, there's a duplex service for which the client starts the connection with a list of stock symbols, and the server uses the *callback interface* to send updates as they become available.</span></span> <span data-ttu-id="2a886-111">El cliente implementa esa interfaz para responder a las llamadas del servidor.</span><span class="sxs-lookup"><span data-stu-id="2a886-111">The client implements that interface to respond to calls from the server.</span></span>

### <a name="the-wcf-solution"></a><span data-ttu-id="2a886-112">La solución WCF</span><span class="sxs-lookup"><span data-stu-id="2a886-112">The WCF solution</span></span>

<span data-ttu-id="2a886-113">La solución WCF se implementa como un servidor net. TCP autohospedado en un .NET Framework 4. aplicación de consola *x* .</span><span class="sxs-lookup"><span data-stu-id="2a886-113">The WCF solution is implemented as a self-hosted Net.TCP server in a .NET Framework 4.*x* console application.</span></span>

#### <a name="servicecontract"></a><span data-ttu-id="2a886-114">ServiceContract</span><span class="sxs-lookup"><span data-stu-id="2a886-114">ServiceContract</span></span>

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

<span data-ttu-id="2a886-115">El servicio tiene un único método sin tipo de valor devuelto porque utiliza la interfaz de devolución de llamada `ISimpleStockTickerCallback` para enviar datos al cliente en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="2a886-115">The service has a single method with no return type because it uses the callback interface `ISimpleStockTickerCallback` to send data to the client in real time.</span></span>

#### <a name="the-callback-interface"></a><span data-ttu-id="2a886-116">La interfaz de devolución de llamada</span><span class="sxs-lookup"><span data-stu-id="2a886-116">The callback interface</span></span>

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

<span data-ttu-id="2a886-117">Puede encontrar las implementaciones de estas interfaces en la solución, junto con las dependencias externas falsificadas para proporcionar datos de prueba.</span><span class="sxs-lookup"><span data-stu-id="2a886-117">You can find the implementations of these interfaces in the solution, along with faked external dependencies to provide test data.</span></span>

### <a name="grpc-streaming"></a><span data-ttu-id="2a886-118">streaming de gRPC</span><span class="sxs-lookup"><span data-stu-id="2a886-118">gRPC streaming</span></span>

<span data-ttu-id="2a886-119">El proceso gRPC para administrar datos en tiempo real es diferente del proceso WCF.</span><span class="sxs-lookup"><span data-stu-id="2a886-119">The gRPC process for handling real-time data is different from the WCF process.</span></span> <span data-ttu-id="2a886-120">Una llamada desde el cliente al servidor puede crear una secuencia persistente, que se puede supervisar para los mensajes que llegan de forma asincrónica.</span><span class="sxs-lookup"><span data-stu-id="2a886-120">A call from client to server can create a persistent stream, which can be monitored for messages that arrive asynchronously.</span></span> <span data-ttu-id="2a886-121">A pesar de la diferencia, los flujos pueden ser una forma más intuitiva de trabajar con estos datos y son más relevantes en la programación moderna, que resalta LINQ, flujos reactivos, programación funcional, etc.</span><span class="sxs-lookup"><span data-stu-id="2a886-121">Despite the difference, streams can be a more intuitive way of dealing with this data and are more relevant in modern programming, which emphasizes LINQ, Reactive Streams, functional programming, and so on.</span></span>

<span data-ttu-id="2a886-122">La definición del servicio necesita dos mensajes: uno para la solicitud y otro para la secuencia.</span><span class="sxs-lookup"><span data-stu-id="2a886-122">The service definition needs two messages: one for the request and one for the stream.</span></span> <span data-ttu-id="2a886-123">El servicio devuelve una secuencia del mensaje de `StockTickerUpdate` con la palabra clave `stream` en su declaración de `return`.</span><span class="sxs-lookup"><span data-stu-id="2a886-123">The service returns a stream of the `StockTickerUpdate` message with the `stream` keyword in its `return` declaration.</span></span> <span data-ttu-id="2a886-124">Se recomienda agregar una `Timestamp` a la actualización para mostrar la hora exacta del cambio de precio.</span><span class="sxs-lookup"><span data-stu-id="2a886-124">We recommend that you add a `Timestamp` to the update to show the exact time of the price change.</span></span>

#### <a name="simple_stock_tickerproto"></a><span data-ttu-id="2a886-125">simple_stock_ticker. proto</span><span class="sxs-lookup"><span data-stu-id="2a886-125">simple_stock_ticker.proto</span></span>

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

### <a name="implement-simplestockticker"></a><span data-ttu-id="2a886-126">Implementación de SimpleStockTicker</span><span class="sxs-lookup"><span data-stu-id="2a886-126">Implement SimpleStockTicker</span></span>

<span data-ttu-id="2a886-127">Vuelva a usar el `StockPriceSubscriber` falso del proyecto WCF mediante la copia de las tres clases de la biblioteca de clases de `TraderSys.StockMarket` en una nueva biblioteca de clases de .NET Standard en la solución de destino.</span><span class="sxs-lookup"><span data-stu-id="2a886-127">Reuse the fake `StockPriceSubscriber` from the WCF project by copying the three classes from the `TraderSys.StockMarket` class library into a new .NET Standard class library in the target solution.</span></span> <span data-ttu-id="2a886-128">Para seguir los procedimientos recomendados, agregue un tipo de `Factory` para crear instancias del mismo y registre el `IStockPriceSubscriberFactory` con los servicios de inserción de dependencias ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="2a886-128">To better follow best practices, add a `Factory` type to create instances of it, and register the `IStockPriceSubscriberFactory` with the ASP.NET Core dependency injection services.</span></span>

#### <a name="the-factory-implementation"></a><span data-ttu-id="2a886-129">La implementación de fábrica</span><span class="sxs-lookup"><span data-stu-id="2a886-129">The factory implementation</span></span>

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

#### <a name="register-the-factory"></a><span data-ttu-id="2a886-130">Registrar el generador</span><span class="sxs-lookup"><span data-stu-id="2a886-130">Register the factory</span></span>

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

<span data-ttu-id="2a886-131">Esta clase se puede usar ahora para implementar el `StockTickerService`gRPC.</span><span class="sxs-lookup"><span data-stu-id="2a886-131">This class can now be used to implement the gRPC `StockTickerService`.</span></span>

#### <a name="stocktickerservicecs"></a><span data-ttu-id="2a886-132">StockTickerService.cs</span><span class="sxs-lookup"><span data-stu-id="2a886-132">StockTickerService.cs</span></span>

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
            // Handle any errors caused by broken connection, etc.
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

<span data-ttu-id="2a886-133">Como puede ver, aunque la declaración en el archivo `.proto` indica que el método devuelve un flujo de mensajes `StockTickerUpdate`, en realidad devuelve una `Task`.</span><span class="sxs-lookup"><span data-stu-id="2a886-133">As you can see, although the declaration in the `.proto` file says the method returns a stream of `StockTickerUpdate` messages, it actually returns a `Task`.</span></span> <span data-ttu-id="2a886-134">El trabajo de creación de la secuencia se controla mediante el código generado y las bibliotecas en tiempo de ejecución de gRPC, que proporcionan la secuencia de respuesta `IServerStreamWriter<StockTickerUpdate>`, lista para su uso.</span><span class="sxs-lookup"><span data-stu-id="2a886-134">The job of creating the stream is handled by the generated code and the gRPC runtime libraries, which provide the `IServerStreamWriter<StockTickerUpdate>` response stream, ready to use.</span></span>

<span data-ttu-id="2a886-135">A diferencia de un servicio de dúplex de WCF, en el que la instancia de la clase de servicio se mantiene activa mientras la conexión está abierta, el servicio gRPC usa la tarea devuelta para mantener el servicio activo.</span><span class="sxs-lookup"><span data-stu-id="2a886-135">Unlike a WCF duplex service, where the instance of the service class is kept alive while the connection is open, the gRPC service uses the returned task to keep the service alive.</span></span> <span data-ttu-id="2a886-136">La tarea no debe completarse hasta que se cierre la conexión.</span><span class="sxs-lookup"><span data-stu-id="2a886-136">The task shouldn't complete until the connection is closed.</span></span>

<span data-ttu-id="2a886-137">El servicio puede indicar cuándo el cliente ha cerrado la conexión mediante el `CancellationToken` del `ServerCallContext`.</span><span class="sxs-lookup"><span data-stu-id="2a886-137">The service can tell when the client has closed the connection by using the `CancellationToken` from the `ServerCallContext`.</span></span> <span data-ttu-id="2a886-138">Un método estático simple, `AwaitCancellation`, se usa para crear una tarea que se completa cuando se cancela el token.</span><span class="sxs-lookup"><span data-stu-id="2a886-138">A simple static method, `AwaitCancellation`, is used to create a task that completes when the token is canceled.</span></span>

<span data-ttu-id="2a886-139">En el método `Subscribe`, obtenga un `StockPriceSubscriber` y agregue un controlador de eventos que escriba en la secuencia de respuesta.</span><span class="sxs-lookup"><span data-stu-id="2a886-139">In the `Subscribe` method, then, get a `StockPriceSubscriber` and add an event handler that writes to the response stream.</span></span> <span data-ttu-id="2a886-140">A continuación, espere a que se cierre la conexión antes de eliminar inmediatamente el `subscriber` para evitar que intente escribir datos en el flujo cerrado.</span><span class="sxs-lookup"><span data-stu-id="2a886-140">Then wait for the connection to be closed before immediately disposing the `subscriber` to prevent it from trying to write data to the closed stream.</span></span>

<span data-ttu-id="2a886-141">El método `WriteUpdateAsync` tiene un `try`/`catch` bloque para controlar los errores que pueden producirse cuando se escribe un mensaje en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="2a886-141">The `WriteUpdateAsync` method has a `try`/`catch` block to handle any errors that might happen when a message is written to the stream.</span></span> <span data-ttu-id="2a886-142">Esta consideración es importante en las conexiones persistentes a través de redes, que podrían romperse en cualquier milisegundo, ya sea intencionadamente o debido a un error en alguna parte.</span><span class="sxs-lookup"><span data-stu-id="2a886-142">This consideration is important in persistent connections over networks, which could be broken at any millisecond, whether intentionally or because of a failure somewhere.</span></span>

### <a name="use-stocktickerservice-from-a-client-application"></a><span data-ttu-id="2a886-143">Usar StockTickerService desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="2a886-143">Use StockTickerService from a client application</span></span>

<span data-ttu-id="2a886-144">Siga los mismos pasos de la sección anterior para crear una biblioteca de clases de cliente que se pueda compartir desde el archivo de `.proto`.</span><span class="sxs-lookup"><span data-stu-id="2a886-144">Follow the same steps in the previous section to create a shareable client class library from the `.proto` file.</span></span> <span data-ttu-id="2a886-145">En el ejemplo, hay una aplicación de consola de .NET Core 3,0 que muestra cómo usar el cliente.</span><span class="sxs-lookup"><span data-stu-id="2a886-145">In the sample, there's a .NET Core 3.0 console application that demonstrates how to use the client.</span></span>

#### <a name="example-programcs"></a><span data-ttu-id="2a886-146">Ejemplo de Program.cs</span><span class="sxs-lookup"><span data-stu-id="2a886-146">Example Program.cs</span></span>

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

<span data-ttu-id="2a886-147">En este caso, el método de `Subscribe` en el cliente generado no es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="2a886-147">In this case, the `Subscribe` method on the generated client isn't asynchronous.</span></span> <span data-ttu-id="2a886-148">La secuencia se crea y se puede usar de inmediato porque su método `MoveNext` es asincrónico y la primera vez que se le llama no se completará hasta que la conexión esté activa.</span><span class="sxs-lookup"><span data-stu-id="2a886-148">The stream is created and usable right away because its `MoveNext` method is asynchronous and the first time it's called it won't complete until the connection is alive.</span></span>

<span data-ttu-id="2a886-149">La secuencia se pasa a un método de `DisplayAsync` asincrónico.</span><span class="sxs-lookup"><span data-stu-id="2a886-149">The stream is passed to an asynchronous `DisplayAsync` method.</span></span> <span data-ttu-id="2a886-150">A continuación, la aplicación espera a que el usuario presione una tecla y, a continuación, cancela el método `DisplayAsync` y espera a que la tarea se complete antes de salir.</span><span class="sxs-lookup"><span data-stu-id="2a886-150">The application then waits for the user to press a key, and then cancels the `DisplayAsync` method and waits for the task to complete before exiting.</span></span>

> [!NOTE]
> <span data-ttu-id="2a886-151">Este código usa la nueva C# sintaxis de declaración 8 `using` para desechar la secuencia y el canal cuando el método `Main` sale.</span><span class="sxs-lookup"><span data-stu-id="2a886-151">This code uses the new C# 8 `using` declaration syntax to dispose of the stream and the channel when the `Main` method exits.</span></span> <span data-ttu-id="2a886-152">Se trata de un pequeño cambio, pero una buena que reduce las sangrías y las líneas vacías.</span><span class="sxs-lookup"><span data-stu-id="2a886-152">It's a small change, but a nice one that reduces indentations and empty lines.</span></span>

#### <a name="consume-the-stream"></a><span data-ttu-id="2a886-153">Consumo de la secuencia</span><span class="sxs-lookup"><span data-stu-id="2a886-153">Consume the stream</span></span>

<span data-ttu-id="2a886-154">WCF usa interfaces de devolución de llamada para permitir que el servidor llame a métodos directamente en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2a886-154">WCF uses callback interfaces to allow the server to call methods directly on the client.</span></span> <span data-ttu-id="2a886-155">las secuencias gRPC funcionan de manera diferente.</span><span class="sxs-lookup"><span data-stu-id="2a886-155">gRPC streams work differently.</span></span> <span data-ttu-id="2a886-156">El cliente recorre en iteración el flujo devuelto y procesa los mensajes, como si se hubieran devuelto desde un método local que devuelve un `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="2a886-156">The client iterates over the returned stream and processes messages, just as though they were returned from a local method returning an `IEnumerable`.</span></span>

<span data-ttu-id="2a886-157">El tipo de `IAsyncStreamReader<T>` funciona de forma muy similar a un `IEnumerator<T>`.</span><span class="sxs-lookup"><span data-stu-id="2a886-157">The `IAsyncStreamReader<T>` type works much like an `IEnumerator<T>`.</span></span> <span data-ttu-id="2a886-158">Hay un método `MoveNext` que devuelve true siempre que haya más datos y una propiedad `Current` que devuelva el valor más reciente.</span><span class="sxs-lookup"><span data-stu-id="2a886-158">There's a `MoveNext` method that returns true as long as there's more data, and a `Current` property that returns the latest value.</span></span> <span data-ttu-id="2a886-159">La única diferencia es que el método `MoveNext` devuelve un `Task<bool>` en lugar de un `bool`.</span><span class="sxs-lookup"><span data-stu-id="2a886-159">The only difference is that the `MoveNext` method returns a `Task<bool>` instead of just a `bool`.</span></span> <span data-ttu-id="2a886-160">El método de extensión `ReadAllAsync` encapsula el flujo en un `IAsyncEnumerable` C# estándar 8 que se puede usar con la nueva sintaxis de `await foreach`.</span><span class="sxs-lookup"><span data-stu-id="2a886-160">The `ReadAllAsync` extension method wraps the stream in a standard C# 8 `IAsyncEnumerable` that can be used with the new `await foreach` syntax.</span></span>

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
> <span data-ttu-id="2a886-161">Para los desarrolladores que usan patrones de programación reactiva, la sección sobre [bibliotecas de cliente](client-libraries.md#iobservable) al final de este capítulo muestra cómo agregar un método de extensión y clases para ajustar `IAsyncStreamReader<T>` en un `IObservable<T>`.</span><span class="sxs-lookup"><span data-stu-id="2a886-161">For developers using reactive programming patterns, the section on [client libraries](client-libraries.md#iobservable) at the end of this chapter shows how to add an extension method and classes to wrap `IAsyncStreamReader<T>` in an `IObservable<T>`.</span></span>

<span data-ttu-id="2a886-162">De nuevo, asegúrese de detectar las excepciones aquí debido a la posibilidad de que se produzca un error en la red y debido a la <xref:System.OperationCanceledException> que se producirá inevitablemente porque el código usa un <xref:System.Threading.CancellationToken> para interrumpir el bucle.</span><span class="sxs-lookup"><span data-stu-id="2a886-162">Again, be sure to catch exceptions here because of the possibility of network failure, and because of the <xref:System.OperationCanceledException> that will inevitably be thrown because the code is using a <xref:System.Threading.CancellationToken> to break the loop.</span></span> <span data-ttu-id="2a886-163">El tipo de `RpcException` tiene mucha información útil sobre los errores de tiempo de ejecución de gRPC, incluido el `StatusCode`.</span><span class="sxs-lookup"><span data-stu-id="2a886-163">The `RpcException` type has a lot of useful information about gRPC runtime errors, including the `StatusCode`.</span></span> <span data-ttu-id="2a886-164">Para obtener más información, vea [ *control de errores* en el capítulo 4](error-handling.md).</span><span class="sxs-lookup"><span data-stu-id="2a886-164">For more information, see [*Error handling* in Chapter 4](error-handling.md).</span></span>

## <a name="bidirectional-streaming"></a><span data-ttu-id="2a886-165">Streaming bidireccional</span><span class="sxs-lookup"><span data-stu-id="2a886-165">Bidirectional streaming</span></span>

<span data-ttu-id="2a886-166">Un servicio de dúplex completo de WCF permite la mensajería asincrónica en tiempo real en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="2a886-166">A WCF full-duplex service allows for asynchronous, real-time messaging in both directions.</span></span> <span data-ttu-id="2a886-167">En el ejemplo de streaming del servidor, el cliente inicia una solicitud y, a continuación, recibe un flujo de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="2a886-167">In the server streaming example, the client starts a request and then receives a stream of updates.</span></span> <span data-ttu-id="2a886-168">Una versión mejor de ese servicio permitiría al cliente agregar y quitar acciones de la lista sin tener que detener y crear una nueva suscripción.</span><span class="sxs-lookup"><span data-stu-id="2a886-168">A better version of that service would allow the client to add and remove stocks from the list without having to stop and create a new subscription.</span></span> <span data-ttu-id="2a886-169">Esa funcionalidad se ha implementado en la [solución de ejemplo FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="2a886-169">That functionality has been implemented in the [FullStockTicker sample solution](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).</span></span>

<span data-ttu-id="2a886-170">La interfaz `IFullStockTickerService` proporciona tres métodos:</span><span class="sxs-lookup"><span data-stu-id="2a886-170">The `IFullStockTickerService` interface provides three methods:</span></span>

- <span data-ttu-id="2a886-171">`Subscribe` inicia la conexión.</span><span class="sxs-lookup"><span data-stu-id="2a886-171">`Subscribe` starts the connection.</span></span>
- <span data-ttu-id="2a886-172">`AddSymbol` agrega un símbolo de cotización para verlo.</span><span class="sxs-lookup"><span data-stu-id="2a886-172">`AddSymbol` adds a stock symbol to watch.</span></span>
- <span data-ttu-id="2a886-173">`RemoveSymbol` quita un símbolo de la lista de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2a886-173">`RemoveSymbol` removes a symbol from the watched list.</span></span>

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

<span data-ttu-id="2a886-174">La interfaz de devolución de llamada sigue siendo la misma.</span><span class="sxs-lookup"><span data-stu-id="2a886-174">The callback interface remains the same.</span></span>

<span data-ttu-id="2a886-175">La implementación de este patrón en gRPC es menos sencilla porque ahora hay dos flujos de datos con mensajes que se pasan: uno del cliente al servidor y otro del servidor al cliente.</span><span class="sxs-lookup"><span data-stu-id="2a886-175">Implementing this pattern in gRPC is less straightforward because there are now two streams of data with messages being passed: one from client to server and another from server to client.</span></span> <span data-ttu-id="2a886-176">No es posible utilizar varios métodos para implementar las operaciones de agregar y quitar, pero se puede pasar más de un tipo de mensaje en una única secuencia mediante el `Any` tipo o la palabra clave `oneof`, que se trataron en el [capítulo 3](protobuf-any-oneof.md).</span><span class="sxs-lookup"><span data-stu-id="2a886-176">It isn't possible to use multiple methods to implement the add and remove operations, but you can pass more than one type of message on a single stream by using either the `Any` type or the `oneof` keyword, which were covered in [Chapter 3](protobuf-any-oneof.md).</span></span>

<span data-ttu-id="2a886-177">En un caso en el que hay un conjunto específico de tipos que son aceptables, `oneof` es una mejor manera de ir.</span><span class="sxs-lookup"><span data-stu-id="2a886-177">In a case where there's a specific set of types that are acceptable, `oneof` is a better way to go.</span></span> <span data-ttu-id="2a886-178">Use una `ActionMessage` que pueda contener un `AddSymbolRequest` o un `RemoveSymbolRequest`:</span><span class="sxs-lookup"><span data-stu-id="2a886-178">Use an `ActionMessage` that can hold either an `AddSymbolRequest` or a `RemoveSymbolRequest`:</span></span>

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

<span data-ttu-id="2a886-179">Declare un servicio de streaming bidireccional que toma un flujo de mensajes `ActionMessage`:</span><span class="sxs-lookup"><span data-stu-id="2a886-179">Declare a bidirectional streaming service that takes a stream of `ActionMessage` messages:</span></span>

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

<span data-ttu-id="2a886-180">La implementación de este servicio es similar a la del ejemplo anterior, excepto que el primer parámetro del método `Subscribe` es ahora un `IAsyncStreamReader<ActionMessage>`, que se puede usar para controlar las solicitudes de `Add` y `Remove`:</span><span class="sxs-lookup"><span data-stu-id="2a886-180">The implementation for this service is similar to that of the previous example, except the first parameter of the `Subscribe` method is now an `IAsyncStreamReader<ActionMessage>`, which can be used to handle the `Add` and `Remove` requests:</span></span>

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
        // Handle any errors caused by broken connection, etc.
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

<span data-ttu-id="2a886-181">La clase `ActionMessage` que gRPC ha generado garantiza que solo se puede establecer una de las propiedades `Add` y `Remove`.</span><span class="sxs-lookup"><span data-stu-id="2a886-181">The `ActionMessage` class that gRPC has generated guarantees that only one of the `Add` and `Remove` properties can be set.</span></span> <span data-ttu-id="2a886-182">La búsqueda de la que no está `null` es una manera válida de determinar qué tipo de mensaje se usa, pero hay una manera mejor.</span><span class="sxs-lookup"><span data-stu-id="2a886-182">Finding which one isn't `null` is a valid way to determine which type of message is used, but there's a better way.</span></span> <span data-ttu-id="2a886-183">La generación de código también crea un `enum ActionOneOfCase` en la clase `ActionMessage`, que tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="2a886-183">The code generation also created an `enum ActionOneOfCase` in the `ActionMessage` class, which looks like this:</span></span>

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

<span data-ttu-id="2a886-184">La propiedad `ActionCase` en el objeto de `ActionMessage` se puede utilizar con una instrucción `switch` para determinar qué campo se establece:</span><span class="sxs-lookup"><span data-stu-id="2a886-184">The property `ActionCase` on the `ActionMessage` object can be used with a `switch` statement to determine which field is set:</span></span>

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
> <span data-ttu-id="2a886-185">La instrucción `switch` tiene un caso `default` que registra una advertencia si encuentra un valor de `ActionOneOfCase` desconocido.</span><span class="sxs-lookup"><span data-stu-id="2a886-185">The `switch` statement has a `default` case that logs a warning if it encounters an unknown `ActionOneOfCase` value.</span></span> <span data-ttu-id="2a886-186">Esto puede ser útil para indicar que un cliente está usando una versión posterior del archivo `.proto` que ha agregado más acciones.</span><span class="sxs-lookup"><span data-stu-id="2a886-186">This could be useful to indicate that a client is using a later version of the `.proto` file that has added more actions.</span></span> <span data-ttu-id="2a886-187">Esta es una de las razones por las que el uso de un `switch` es mejor que las pruebas de `null` en los campos conocidos.</span><span class="sxs-lookup"><span data-stu-id="2a886-187">This is one reason why using a `switch` is better than testing for `null` on known fields.</span></span>

### <a name="use-fullstocktickerservice-from-a-client-application"></a><span data-ttu-id="2a886-188">Usar FullStockTickerService desde una aplicación cliente</span><span class="sxs-lookup"><span data-stu-id="2a886-188">Use FullStockTickerService from a client application</span></span>

<span data-ttu-id="2a886-189">Hay una sencilla aplicación WPF de .NET Core 3,0 que muestra el uso de este cliente más complejo.</span><span class="sxs-lookup"><span data-stu-id="2a886-189">There's a simple .NET Core 3.0 WPF application that demonstrates the use of this more complex client.</span></span> <span data-ttu-id="2a886-190">Puede encontrar la aplicación completa en [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span><span class="sxs-lookup"><span data-stu-id="2a886-190">You can find the full application on [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).</span></span>

<span data-ttu-id="2a886-191">El cliente se usa en la clase `MainWindowViewModel`, que obtiene una instancia del tipo de `FullStockTicker.FullStockTickerClient` a partir de la inserción de dependencias:</span><span class="sxs-lookup"><span data-stu-id="2a886-191">The client is used in the `MainWindowViewModel` class, which gets an instance of the `FullStockTicker.FullStockTickerClient` type from dependency injection:</span></span>

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

<span data-ttu-id="2a886-192">El objeto devuelto por el método `client.Subscribe()` es ahora una instancia del tipo de biblioteca gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, que proporciona un `RequestStream` para enviar solicitudes al servidor y un `ResponseStream` para controlar las respuestas.</span><span class="sxs-lookup"><span data-stu-id="2a886-192">The object returned by the `client.Subscribe()` method is now an instance of the gRPC library type `AsyncDuplexStreamingCall<TRequest, TResponse>`, which provides a `RequestStream` for sending requests to the server and a `ResponseStream` for handling responses.</span></span>

<span data-ttu-id="2a886-193">La secuencia de solicitud se usa desde algunos métodos de `ICommand` de WPF para agregar y quitar símbolos.</span><span class="sxs-lookup"><span data-stu-id="2a886-193">The request stream is used from some WPF `ICommand` methods to add and remove symbols.</span></span> <span data-ttu-id="2a886-194">Para cada operación, establezca el campo correspondiente en un objeto de `ActionMessage`:</span><span class="sxs-lookup"><span data-stu-id="2a886-194">For each operation, set the relevant field on an `ActionMessage` object:</span></span>

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
> <span data-ttu-id="2a886-195">Al establecer el valor de un campo de `oneof` en un mensaje, se borran automáticamente los campos que se han establecido previamente.</span><span class="sxs-lookup"><span data-stu-id="2a886-195">Setting a `oneof` field's value on a message automatically clears any fields that have been set previously.</span></span>

<span data-ttu-id="2a886-196">La secuencia de respuestas se controla en un método `async`.</span><span class="sxs-lookup"><span data-stu-id="2a886-196">The stream of responses is handled in an `async` method.</span></span> <span data-ttu-id="2a886-197">El `Task` devuelto se mantiene para que se elimine cuando se cierre la ventana:</span><span class="sxs-lookup"><span data-stu-id="2a886-197">The `Task` it returns is held to be disposed when the window is closed:</span></span>

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

### <a name="client-cleanup"></a><span data-ttu-id="2a886-198">Limpieza de cliente</span><span class="sxs-lookup"><span data-stu-id="2a886-198">Client cleanup</span></span>

<span data-ttu-id="2a886-199">Cuando se cierra la ventana y se desecha el `MainWindowViewModel` (desde el evento de `Closed` de `MainWindow`), se recomienda eliminar correctamente el objeto de `AsyncDuplexStreamingCall`.</span><span class="sxs-lookup"><span data-stu-id="2a886-199">When the window is closed and the `MainWindowViewModel` is disposed (from the `Closed` event of `MainWindow`), we recommend that you properly dispose the `AsyncDuplexStreamingCall` object.</span></span> <span data-ttu-id="2a886-200">En concreto, se debe llamar al método `CompleteAsync` en el `RequestStream` para cerrar correctamente el flujo en el servidor.</span><span class="sxs-lookup"><span data-stu-id="2a886-200">In particular, the `CompleteAsync` method on the `RequestStream` should be called to gracefully close the stream on the server.</span></span> <span data-ttu-id="2a886-201">En este ejemplo se muestra el método `DisposeAsync` de la vista de ejemplo-modelo:</span><span class="sxs-lookup"><span data-stu-id="2a886-201">This example shows the `DisposeAsync` method from the sample view-model:</span></span>

```csharp
public async ValueTask DisposeAsync()
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

<span data-ttu-id="2a886-202">El cierre de las secuencias de solicitud permite al servidor desechar sus propios recursos de manera puntual.</span><span class="sxs-lookup"><span data-stu-id="2a886-202">Closing request streams enables the server to dispose of its own resources in a timely way.</span></span> <span data-ttu-id="2a886-203">Esto mejora la eficiencia y escalabilidad de los servicios y evita excepciones.</span><span class="sxs-lookup"><span data-stu-id="2a886-203">This improves the efficiency and scalability of services and prevents exceptions.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2a886-204">[Anterior](migrate-request-reply.md)
>[Siguiente](streaming-versus-repeated.md)</span><span class="sxs-lookup"><span data-stu-id="2a886-204">[Previous](migrate-request-reply.md)
[Next](streaming-versus-repeated.md)</span></span>
