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
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Migración de servicios dúplex de WCF a gRPC

Ahora que los conceptos básicos están en vigor, en esta sección se examinarán los servicios de *streaming* gRPC más complicados.

Hay varias maneras de usar los servicios dúplex en Windows Communication Foundation (WCF). El cliente inicia algunos servicios y, a continuación, transmiten los datos desde el servidor. Otros servicios de dúplex completo pueden implicar una comunicación bidireccional más continua como el ejemplo de "calculadora" clásico de la documentación de WCF. En este capítulo se tomarán dos posibles implementaciones de WCF "bursátiles" y se migrarán a gRPC: una con una RPC de streaming de servidor y la otra mediante una RPC de streaming bidireccional.

## <a name="server-streaming-rpc"></a>RPC de streaming de servidor

En la [solución WCF de ejemplo SimpleStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), *SimpleStockPriceTicker*, hay un servicio dúplex en el que el cliente inicia la conexión con una lista de símbolos bursátiles y el servidor usa la *interfaz de devolución de llamada* para enviar las actualizaciones a medida que estén disponibles. El cliente implementa esa interfaz para responder a las llamadas del servidor.

### <a name="the-wcf-solution"></a>La solución WCF

La solución WCF se implementa como un servidor de NetTCP autohospedado en una aplicación de consola de .NET Framework 4. x.

#### <a name="the-servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

El servicio tiene un único método sin tipo de valor devuelto, ya que utilizará la interfaz de devolución de llamada `ISimpleStockTickerCallback` para enviar datos al cliente en tiempo real.

#### <a name="the-callback-interface"></a>La interfaz de devolución de llamada

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Las implementaciones de estas interfaces se pueden encontrar en la solución, junto con las dependencias externas falsificadas para proporcionar datos de prueba.

### <a name="grpc-streaming"></a>streaming de gRPC

La forma gRPC de controlar los datos en tiempo real es diferente. Una llamada desde el cliente al servidor puede crear una secuencia persistente, que se puede supervisar para los mensajes que llegan de forma asincrónica. A pesar de la diferencia, los flujos pueden ser una forma más intuitiva de trabajar con estos datos y son más relevantes en la programación moderna con énfasis en LINQ, secuencias reactivas, programación funcional, etc.

La definición del servicio necesita dos mensajes: uno para la solicitud y otro para la secuencia. El servicio devuelve un flujo del mensaje de `StockTickerUpdate` mediante la palabra clave `stream` en su declaración `return`. Se recomienda agregar una `Timestamp` a la actualización para mostrar la hora exacta a la que ha cambiado el precio.

#### <a name="simple_stock_tickerproto"></a>simple_stock_ticker. proto

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

### <a name="implement-the-simplestockticker"></a>Implementación de SimpleStockTicker

Vuelva a usar el `StockPriceSubscriber` falso del proyecto WCF mediante la copia de las tres clases de la biblioteca de clases de `TraderSys.StockMarket` en una nueva biblioteca de clases de .NET Standard en la solución de destino. Para seguir los procedimientos recomendados, agregue un tipo de `Factory` para crear instancias del mismo y registrar el `IStockPriceSubscriberFactory` con los servicios de inserción de dependencias de ASP.NET Core.

#### <a name="the-factory-implementation"></a>La implementación de fábrica

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

#### <a name="registering-the-factory"></a>Registro del generador

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Ahora, esta clase se puede usar para implementar el servicio gRPC StockTicker.

#### <a name="stocktickerservicecs"></a>StockTickerService.cs

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

Como puede ver, aunque la declaración del archivo `.proto` indica que el método "devuelve" un flujo de mensajes `StockTickerUpdate`, en realidad devuelve un `Task`de vainilla. El trabajo de creación de la secuencia se controla mediante el código generado y las bibliotecas en tiempo de ejecución de gRPC, que proporcionan la secuencia de respuesta `IServerStreamWriter<StockTickerUpdate>`, lista para su uso.

A diferencia de un servicio de dúplex de WCF, en el que la instancia de la clase de servicio se mantiene activa mientras la conexión está abierta, el servicio gRPC usa la tarea devuelta para mantener el servicio activo. La tarea no debe completarse hasta que se cierre la conexión.

El servicio puede indicar cuándo el cliente ha cerrado la conexión mediante el `CancellationToken` del `ServerCallContext`. Un método estático simple, `AwaitCancellation`, se usa para crear una tarea que se completa cuando se cancela el token.

En el método `Subscribe`, obtenga un `StockPriceSubscriber` y agregue un controlador de eventos que escriba en la secuencia de respuesta. Después, espere a que se cierre la conexión, antes de eliminar inmediatamente el `subscriber` para evitar que intente escribir datos en el flujo cerrado.

El método `WriteUpdateAsync` tiene un `try`/`catch` bloque para controlar los errores que puedan producirse al escribir un mensaje en la secuencia. Esta es una consideración importante en las conexiones persistentes a través de redes, que podrían romperse en cualquier milisegundo, ya sea intencionadamente o debido a un error en algún lugar.

### <a name="using-the-stocktickerservice-from-a-client-application"></a>Usar StockTickerService desde una aplicación cliente

Siga los mismos pasos de la sección anterior para crear una biblioteca de clases de cliente que se pueda compartir desde el archivo de `.proto`. En el ejemplo, hay una aplicación de consola de .NET Core 3,0 que muestra cómo usar el cliente.

#### <a name="example-programcs"></a>Ejemplo de Program.cs

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

En este caso, el método de `Subscribe` en el cliente generado no es asincrónico. La secuencia se crea y se puede usar inmediatamente, porque su método `MoveNext` es asincrónico y la primera vez que se le llama no se completará hasta que la conexión esté activa.

La secuencia se pasa a un método `DisplayAsync` asincrónico; a continuación, la aplicación espera a que el usuario presione una tecla y, a continuación, cancela el método `DisplayAsync` y espera a que la tarea se complete antes de salir.

> [!NOTE]
> Este código usa la nueva C# sintaxis de "Declaración de uso" para desechar la secuencia y el canal cuando finaliza el método de `Main`. Se trata de un pequeño cambio, pero una buena que reduce las sangrías y las líneas vacías.

#### <a name="consume-the-stream"></a>Consumo de la secuencia

Interfaces de devolución de llamada usadas por WCF para permitir que el servidor llame a métodos directamente en el cliente. las secuencias gRPC funcionan de manera diferente. El cliente recorre en iteración el flujo devuelto y procesa los mensajes, como si se hubieran devuelto desde un método local que devuelve un `IEnumerable`.

El tipo de `IAsyncStreamReader<T>` funciona de forma muy similar a un `IEnumerator<T>`: hay un método `MoveNext` que devolverá True siempre que haya más datos y una propiedad `Current` que devuelva el valor más reciente. La única diferencia es que el método `MoveNext` devuelve un `Task<bool>` en lugar de un `bool`. El método de extensión `ReadAllAsync` encapsula el flujo en un `IAsyncEnumerable` C# estándar 8 que se puede usar con la nueva sintaxis de `await foreach`.

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
> En la sección acerca de las [bibliotecas de cliente](client-libraries.md#iobservable) al final de este capítulo se describe cómo agregar un método de extensión y clases para ajustar `IAsyncStreamReader<T>` en una `IObservable<T>` para desarrolladores que usan patrones de programación reactiva.

De nuevo, tenga cuidado de detectar las excepciones aquí debido a la posibilidad de que se produzca un error en la red, así como del <xref:System.OperationCanceledException> que se producirá inevitablemente porque el código usa un <xref:System.Threading.CancellationToken> para interrumpir el bucle. El tipo de `RpcException` tiene mucha información útil sobre los errores de tiempo de ejecución de gRPC, incluido el `StatusCode`. Para obtener más información, vea [ *control de errores* en el capítulo 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Streaming bidireccional

Un servicio de dúplex completo de WCF permite la mensajería asincrónica en tiempo real en ambas direcciones. En el ejemplo de streaming del servidor, el cliente inicia una solicitud y, a continuación, recibe un flujo de actualizaciones. Una versión mejor de ese servicio permitiría al cliente agregar y quitar acciones de la lista sin tener que detener y crear una nueva suscripción. Esa funcionalidad se ha implementado en la [solución de ejemplo FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

La interfaz `IFullStockTickerService` proporciona tres métodos:

- `Subscribe` inicia la conexión.
- `AddSymbol` agrega un símbolo de cotización para verlo.
- `RemoveSymbol` quita un símbolo de la lista de seguimiento.

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

La interfaz de devolución de llamada sigue siendo la misma.

La implementación de este patrón en gRPC es menos sencilla, ya que ahora hay dos flujos de datos con mensajes que se pasan: uno de cliente a servidor y otro de servidor a cliente. No es posible usar varios métodos para implementar la operación de agregar y quitar, pero se puede pasar más de un tipo de mensaje en una única secuencia, mediante el `Any` tipo o la palabra clave `oneof`, que se trataron en el [capítulo 3](protobuf-any-oneof.md).

Para un caso en el que hay un conjunto específico de tipos que son aceptables, `oneof` es una mejor manera de ir. Use una `ActionMessage` que puede contener un `AddSymbolRequest` o un `RemoveSymbolRequest`.

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

Declare un servicio de streaming bidireccional que toma un flujo de mensajes `ActionMessage`.

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

La implementación de este servicio es similar al ejemplo anterior, excepto que el primer parámetro del método `Subscribe` es ahora un `IAsyncStreamReader<ActionMessage>`, que se puede usar para controlar las solicitudes de `Add` y `Remove`.

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

La clase de `ActionMessage` que gRPC ha generado para nosotros garantiza que solo se puede establecer una de las propiedades `Add` y `Remove`, y la búsqueda de la que no está `null` es una manera válida de buscar el tipo de mensaje que se usa, pero hay una manera mejor. La generación de código también crea un `enum ActionOneOfCase` en la clase `ActionMessage`, que tiene el siguiente aspecto:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

La propiedad `ActionCase` en el objeto de `ActionMessage` se puede utilizar con una instrucción `switch` para determinar qué campo está establecido.

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
> La instrucción `switch` tiene un caso `default` que registra una advertencia si se encuentra un valor de `ActionOneOfCase` desconocido. Esto podría ser útil para indicar que un cliente está usando una versión posterior del archivo `.proto` que ha agregado más acciones. Esta es una de las razones por las que el uso de un `switch` es mejor que las pruebas de `null` en los campos conocidos.

### <a name="use-the-fullstocktickerservice-from-a-client-application"></a>Usar FullStockTickerService desde una aplicación cliente

Hay una sencilla aplicación WPF de .NET Core 3,0 para demostrar el uso de este cliente más complejo. La aplicación completa se puede encontrar [en github](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

El cliente se usa en la clase `MainWindowViewModel`, que obtiene una instancia del tipo de `FullStockTicker.FullStockTickerClient` de la inserción de dependencias.

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

El objeto devuelto por el método `client.Subscribe()` es ahora una instancia del tipo de biblioteca gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>`, que proporciona un `RequestStream` para enviar solicitudes al servidor y un `ResponseStream` para controlar las respuestas.

La secuencia de solicitud se usa desde algunos métodos de `ICommand` de WPF para agregar y quitar símbolos. Para cada operación, establezca el campo correspondiente en un objeto de `ActionMessage`:

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
> Al establecer el valor de un campo de `oneof` en un mensaje, se borran automáticamente los campos que se han establecido previamente.

La secuencia de respuestas se administra en un método `async` y el `Task` que devuelve se mantiene para eliminarse cuando se cierra la ventana.

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

### <a name="client-clean-up"></a>Limpieza de cliente

Cuando se cierra la ventana y se desecha el `MainWindowViewModel` (desde el evento de `Closed` de `MainWindow`), se recomienda que elimine correctamente el objeto `AsyncDuplexStreamingCall`. En concreto, se debe llamar al método `CompleteAsync` en el `RequestStream` para cerrar correctamente el flujo en el servidor. En el ejemplo siguiente se muestra el método `DisposeAsync` de la vista de ejemplo-Model:

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

El cierre de las secuencias de solicitud permite al servidor desechar sus propios recursos de manera oportuna. Esto mejora la eficiencia y escalabilidad de los servicios y evita excepciones.

>[!div class="step-by-step"]
>[Anterior](migrate-request-reply.md)
>[Siguiente](streaming-versus-repeated.md)
