---
title: Migración de servicios dúplex de WCF a gRPC-gRPC para desarrolladores de WCF
description: Obtenga información sobre cómo migrar varias formas de servicios dúplex de WCF a gRPC streaming Services.
ms.date: 12/15/2020
ms.openlocfilehash: 4741e5ad5c12fa358853381d4f2c286add14f8f5
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938031"
---
# <a name="migrate-wcf-duplex-services-to-grpc"></a>Migración de servicios dúplex de WCF a gRPC

Ahora que tiene una idea de los conceptos básicos, en esta sección, examinará los servicios de *streaming* gRPC más complicados.

Hay varias maneras de usar los servicios dúplex en Windows Communication Foundation (WCF). El cliente inicia algunos servicios y, a continuación, transmiten los datos desde el servidor. Otros servicios de dúplex completo pueden implicar una comunicación bidireccional más continua, como el ejemplo de la calculadora clásico en la documentación de WCF. En este capítulo se tomarán dos posibles implementaciones de tablero de cotizaciones de WCF y se migrarán a gRPC: una que usa una RPC de streaming de servidor y otra que usa una RPC de streaming bidireccional.

## <a name="server-streaming-rpc"></a>RPC de streaming de servidor

En la [solución WCF de ejemplo SimpleStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/SimpleStockTickerSample/wcf/SimpleStockTicker), SimpleStockPriceTicker, hay un servicio dúplex para el que el cliente inicia la conexión con una lista de símbolos bursátiles y el servidor usa la *interfaz de devolución de llamada* para enviar las actualizaciones a medida que estén disponibles. El cliente implementa esa interfaz para responder a las llamadas del servidor.

### <a name="the-wcf-solution"></a>La solución WCF

La solución WCF se implementa como un servidor net. TCP autohospedado en un .NET Framework 4. aplicación de consola *x* .

#### <a name="servicecontract"></a>ServiceContract

```csharp
[ServiceContract(SessionMode = SessionMode.Required, CallbackContract = typeof(ISimpleStockTickerCallback))]
public interface ISimpleStockTickerService
{
    [OperationContract(IsOneWay = true)]
    void Subscribe(string[] symbols);
}
```

El servicio tiene un único método sin tipo de valor devuelto porque utiliza la interfaz de devolución de llamada `ISimpleStockTickerCallback` para enviar datos al cliente en tiempo real.

#### <a name="the-callback-interface"></a>La interfaz de devolución de llamada

```csharp
[ServiceContract]
public interface ISimpleStockTickerCallback
{
    [OperationContract(IsOneWay = true)]
    void Update(string symbol, decimal price);
}
```

Puede encontrar las implementaciones de estas interfaces en la solución, junto con las dependencias externas falsificadas para proporcionar datos de prueba.

### <a name="grpc-streaming"></a>streaming de gRPC

El proceso gRPC para administrar datos en tiempo real es diferente del proceso WCF. Una llamada desde el cliente al servidor puede crear una secuencia persistente, que se puede supervisar para los mensajes que llegan de forma asincrónica. A pesar de la diferencia, los flujos pueden ser una forma más intuitiva de trabajar con estos datos y son más relevantes en la programación moderna, que resalta LINQ, flujos reactivos, programación funcional, etc.

La definición del servicio necesita dos mensajes: uno para la solicitud y otro para la secuencia. El servicio devuelve una secuencia del `StockTickerUpdate` mensaje con la `stream` palabra clave en su `return` declaración. Se recomienda agregar `Timestamp` a la actualización para mostrar la hora exacta del cambio de precio.

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

### <a name="implement-simplestockticker"></a>Implementación de SimpleStockTicker

Vuelva a usar el falso del `StockPriceSubscriber` proyecto WCF mediante la copia de las tres clases de la `TraderSys.StockMarket` biblioteca de clases en una nueva biblioteca de clases de .net Standard en la solución de destino. Para seguir los procedimientos recomendados, agregue un `Factory` tipo para crear instancias del mismo y registre `IStockPriceSubscriberFactory` con los servicios de inserción de dependencias ASP.net Core.

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

#### <a name="register-the-factory"></a>Registrar el generador

```csharp
public void ConfigureServices(IServiceCollection services)
{
    services.AddGrpc();
    services.AddSingleton<IStockPriceSubscriberFactory, StockPriceSubscriberFactory>();
}
```

Esta clase se puede usar ahora para implementar gRPC `StockTickerService` .

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

Como puede ver, aunque la declaración en el `.proto` archivo indica que el método devuelve una secuencia de `StockTickerUpdate` mensajes, en realidad devuelve un objeto `Task` . El trabajo de creación de la secuencia se controla mediante el código generado y las bibliotecas en tiempo de ejecución de gRPC, que proporcionan la `IServerStreamWriter<StockTickerUpdate>` secuencia de respuesta, lista para su uso.

A diferencia de un servicio de dúplex de WCF, en el que la instancia de la clase de servicio se mantiene activa mientras la conexión está abierta, el servicio gRPC usa la tarea devuelta para mantener el servicio activo. La tarea no debe completarse hasta que se cierre la conexión.

El servicio puede indicar cuándo el cliente ha cerrado la conexión mediante el `CancellationToken` desde `ServerCallContext` . Se usa un método estático simple, `AwaitCancellation` , para crear una tarea que se completa cuando se cancela el token.

En el `Subscribe` método, obtenga `StockPriceSubscriber` y agregue un controlador de eventos que escriba en la secuencia de respuesta. A continuación, espere a que la conexión se cierre antes de desechar inmediatamente `subscriber` para impedir que intente escribir datos en el flujo cerrado.

El `WriteUpdateAsync` método tiene un `try` / `catch` bloque para controlar los errores que pueden producirse cuando se escribe un mensaje en la secuencia. Esta consideración es importante en las conexiones persistentes a través de redes, que podrían romperse en cualquier milisegundo, ya sea intencionadamente o debido a un error en alguna parte.

### <a name="use-stocktickerservice-from-a-client-application"></a>Usar StockTickerService desde una aplicación cliente

Siga los mismos pasos de la sección anterior para crear una biblioteca de clases de cliente que se pueda compartir desde el `.proto` archivo. En el ejemplo, hay una aplicación de consola de .NET que muestra cómo usar el cliente.

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

En este caso, el `Subscribe` método en el cliente generado no es asincrónico. La secuencia se crea y se puede usar de inmediato porque su `MoveNext` método es asincrónico y la primera vez que se le llama no se completará hasta que la conexión esté activa.

La secuencia se pasa a un método asincrónico `DisplayAsync` . A continuación, la aplicación espera a que el usuario presione una tecla y, a continuación, cancela el `DisplayAsync` método y espera a que la tarea se complete antes de salir.

> [!NOTE]
> Este código usa la nueva `using` Sintaxis de declaración de C# 8 para desechar la secuencia y el canal cuando el `Main` método finaliza. Se trata de un pequeño cambio, pero una buena que reduce las sangrías y las líneas vacías.

#### <a name="consume-the-stream"></a>Consumo de la secuencia

WCF usa interfaces de devolución de llamada para permitir que el servidor llame a métodos directamente en el cliente. las secuencias gRPC funcionan de manera diferente. El cliente recorre en iteración el flujo devuelto y procesa los mensajes, como si se hubieran devuelto desde un método local que devuelve un `IEnumerable` .

El `IAsyncStreamReader<T>` tipo funciona de forma muy parecida a `IEnumerator<T>` . Hay un `MoveNext` método que devuelve true siempre que haya más datos y una `Current` propiedad que devuelva el valor más reciente. La única diferencia es que el `MoveNext` método devuelve un `Task<bool>` en lugar de simplemente un `bool` . El `ReadAllAsync` método de extensión ajusta la secuencia en un C# 8 estándar `IAsyncEnumerable` que se puede usar con la nueva `await foreach` Sintaxis.

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
> Para los desarrolladores que usan patrones de programación reactiva, la sección sobre [bibliotecas de cliente](client-libraries.md#iobservable) al final de este capítulo muestra cómo agregar un método de extensión y las clases que se van a ajustar `IAsyncStreamReader<T>` en un `IObservable<T>` .

De nuevo, asegúrese de detectar las excepciones aquí debido a la posibilidad de que se produzca un error en la red y debido a <xref:System.OperationCanceledException> que inevitablemente se producirá porque el código está usando un <xref:System.Threading.CancellationToken> para interrumpir el bucle. El `RpcException` tipo tiene mucha información útil acerca de los errores de tiempo de ejecución de gRPC, incluido `StatusCode` . Para obtener más información, vea [ *control de errores* en el capítulo 4](error-handling.md).

## <a name="bidirectional-streaming"></a>Streaming bidireccional

Un servicio de dúplex completo de WCF permite la mensajería asincrónica en tiempo real en ambas direcciones. En el ejemplo de streaming del servidor, el cliente inicia una solicitud y, a continuación, recibe un flujo de actualizaciones. Una versión mejor de ese servicio permitiría al cliente agregar y quitar acciones de la lista sin tener que detener y crear una nueva suscripción. Esa funcionalidad se ha implementado en la [solución de ejemplo FullStockTicker](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/wcf/FullStockTicker).

La `IFullStockTickerService` interfaz proporciona tres métodos:

- `Subscribe` inicia la conexión.
- `AddSymbol` agrega un símbolo de cotización para ver.
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

La implementación de este patrón en gRPC es menos sencilla porque ahora hay dos flujos de datos con mensajes que se pasan: uno del cliente al servidor y otro del servidor al cliente. No es posible utilizar varios métodos para implementar las operaciones de agregar y quitar, pero se puede pasar más de un tipo de mensaje en una única secuencia utilizando el `Any` tipo o la `oneof` palabra clave, que se trataron en el [capítulo 3](protobuf-any-oneof.md).

En un caso en el que hay un conjunto específico de tipos que son aceptables, `oneof` es una mejor manera de ir. Use un `ActionMessage` que pueda contener `AddSymbolRequest` o un `RemoveSymbolRequest` :

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

Declare un servicio de streaming bidireccional que toma un flujo de `ActionMessage` mensajes:

```protobuf
service FullStockTicker {
  rpc Subscribe (stream ActionMessage) returns (stream StockTickerUpdate);
}
```

La implementación de este servicio es similar a la del ejemplo anterior, excepto que el primer parámetro del `Subscribe` método es ahora un `IAsyncStreamReader<ActionMessage>` , que se puede usar para controlar las `Add` solicitudes y `Remove` :

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

La `ActionMessage` clase que gRPC ha generado garantiza que solo `Add` `Remove` se puede establecer una de las propiedades y. La búsqueda de la que no `null` es una manera válida de determinar qué tipo de mensaje se usa, pero hay una manera mejor. La generación de código también crea `enum ActionOneOfCase` en la `ActionMessage` clase, que tiene el siguiente aspecto:

```csharp
public enum ActionOneofCase {
    None = 0,
    Add = 1,
    Remove = 2,
}
```

La propiedad `ActionCase` del `ActionMessage` objeto se puede utilizar con una `switch` instrucción para determinar qué campo se establece:

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
> La `switch` instrucción tiene un `default` caso que registra una advertencia si encuentra un `ActionOneOfCase` valor desconocido. Esto puede ser útil para indicar que un cliente está usando una versión posterior del `.proto` archivo que ha agregado más acciones. Esta es una de las razones por las que el uso de un `switch` es mejor que las pruebas de `null` en los campos conocidos.

### <a name="use-fullstocktickerservice-from-a-client-application"></a>Usar FullStockTickerService desde una aplicación cliente

Hay una sencilla aplicación de WPF de .NET que muestra el uso de este cliente más complejo. Puede encontrar la aplicación completa en [GitHub](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/FullStockTickerSample/grpc/FullStockTicker).

El cliente se usa en la `MainWindowViewModel` clase, que obtiene una instancia del `FullStockTicker.FullStockTickerClient` tipo a partir de la inserción de dependencias:

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

El objeto devuelto por el `client.Subscribe()` método es ahora una instancia del tipo de biblioteca gRPC `AsyncDuplexStreamingCall<TRequest, TResponse>` , que proporciona un `RequestStream` para enviar solicitudes al servidor y un `ResponseStream` para controlar las respuestas.

La secuencia de solicitud se usa desde algunos `ICommand` métodos de WPF para agregar y quitar símbolos. Para cada operación, establezca el campo correspondiente en un `ActionMessage` objeto:

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
> Al establecer el `oneof` valor de un campo en un mensaje, se borran automáticamente los campos que se han establecido previamente.

La secuencia de respuestas se administra en un `async` método. La `Task` devolución se mantiene para que se elimine cuando se cierre la ventana:

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

### <a name="client-cleanup"></a>Limpieza de cliente

Cuando se cierra la ventana y `MainWindowViewModel` se desecha (desde el `Closed` evento de `MainWindow` ), se recomienda que elimine correctamente el `AsyncDuplexStreamingCall` objeto. En concreto, `CompleteAsync` se debe llamar al método en el `RequestStream` para cerrar correctamente el flujo en el servidor. En este ejemplo se muestra el `DisposeAsync` método del ejemplo de vista-modelo:

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

El cierre de las secuencias de solicitud permite al servidor desechar sus propios recursos de manera puntual. Esto mejora la eficiencia y escalabilidad de los servicios y evita excepciones.

>[!div class="step-by-step"]
>[Anterior](migrate-request-reply.md)
>[Siguiente](streaming-versus-repeated.md)
