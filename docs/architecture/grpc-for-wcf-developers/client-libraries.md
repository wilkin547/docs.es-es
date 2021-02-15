---
title: 'Creación de bibliotecas de cliente de gRPC: gRPC para desarrolladores de WCF'
description: Explicación de los paquetes o bibliotecas de cliente compartidos para gRPC Services.
ms.date: 01/06/2021
ms.openlocfilehash: dee62bc793ab384f2556f1b3ff2fcb856c040f3a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427575"
---
# <a name="create-grpc-client-libraries"></a>Creación de bibliotecas de cliente de gRPC

No es necesario distribuir bibliotecas de cliente para una aplicación de gRPC. Puede crear una biblioteca compartida de `.proto` archivos dentro de la organización y otros equipos pueden usar esos archivos para generar el código de cliente en sus propios proyectos. Pero si tiene un repositorio de NuGet privado y muchos otros equipos usan .NET, puede crear y publicar paquetes NuGet de cliente como parte del proyecto de servicio. Este enfoque puede ser una buena forma de compartir y promocionar el servicio.

Una ventaja de la distribución de una biblioteca de cliente es que puede mejorar las clases gRPC y protobuf generadas con útiles métodos y propiedades útiles. En el código de cliente, al igual que en el servidor, todas las clases se declaran como `partial` , por lo que puede ampliarlas sin editar el código generado. Este comportamiento significa que es fácil agregar constructores, métodos y propiedades calculadas a los tipos básicos.

> [!CAUTION]
> No debe utilizar código personalizado para proporcionar una funcionalidad esencial. No quiere restringir esa funcionalidad esencial a los equipos de .NET que usan la biblioteca compartida y no proporcionar a los equipos que usan otros lenguajes o plataformas, como Python o Java.

Asegúrese de que tantos equipos como sea posible puedan tener acceso al servicio de gRPC. La mejor manera de realizar esta funcionalidad es compartir `.proto` archivos para que los desarrolladores puedan generar sus propios clientes. Este enfoque es especialmente cierto en un entorno de varias plataformas, donde los distintos equipos usan con frecuencia diferentes lenguajes de programación y marcos, o donde la API es externamente accesible.

## <a name="useful-extensions"></a>Extensiones útiles

Hay dos interfaces de uso frecuente en .NET para tratar con secuencias de objetos: <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IObservable%601> . A partir de .NET Core 3,0 y C# 8,0, hay una <xref:System.Collections.Generic.IAsyncEnumerable%601> interfaz para procesar secuencias de forma asincrónica y una `await foreach` sintaxis para usar la interfaz. En esta sección se presenta código reutilizable para aplicar estas interfaces a las secuencias de gRPC.

Con las bibliotecas de cliente de .NET gRPC, hay un `ReadAllAsync` método de extensión para `IAsyncStreamReader<T>` que crea una `IAsyncEnumerable<T>` interfaz. Para los desarrolladores que usan programación reactiva, un método de extensión equivalente para crear una `IObservable<T>` interfaz podría ser similar al del ejemplo de la sección siguiente.

### <a name="iobservable"></a>IObservable

La `IObservable<T>` interfaz es el inverso "reactivo" de `IEnumerable<T>` . En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que los elementos de la secuencia se inserten en un suscriptor. Este comportamiento es muy similar a las secuencias gRPC y es fácil encapsular una `IObservable<T>` interfaz alrededor de una `IAsyncStreamReader<T>` interfaz.

Este código es más largo que el `IAsyncEnumerable<T>` código, ya que C# no tiene compatibilidad integrada para trabajar con observables. Debe crear la clase de implementación manualmente. Sin embargo, es una clase genérica, por lo que una sola implementación funciona en todos los tipos.

```csharp
using System;
using System.Threading;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public GrpcStreamObservable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader ?? throw new ArgumentNullException(nameof(reader));
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription<T>(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> Esta implementación observable permite `Subscribe` llamar al método solo una vez, ya que el hecho de que varios suscriptores intenten leer el flujo daría como resultado un caos. Hay operadores, como `Replay` en [System. reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq), que habilitan el almacenamiento en búfer y el uso compartido repetible de observables, que se puede usar con esta implementación.

La `GrpcStreamSubscription` clase controla la enumeración de `IAsyncStreamReader` :

```csharp
public class GrpcStreamSubscription<T> : IDisposable
{
    private readonly IAsyncStreamReader<T> _reader;
    private readonly IObserver<T> _observer;

    private readonly CancellationTokenSource _tokenSource;

    private readonly Task _task;

    private bool _completed;

    public GrpcStreamSubscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token = default)
    {
        _reader = reader ?? throw new ArgumentNullException(nameof(reader));
        _observer = observer ?? throw new ArgumentNullException(nameof(observer));

        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);

        _task = Run(_tokenSource.Token);
    }

    private async Task Run(CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await _reader.MoveNext(token)) break;
            }
            catch (RpcException e) when (e.StatusCode == Grpc.Core.StatusCode.NotFound)
            {
                break;
            }
            catch (OperationCanceledException)
            {
                break;
            }
            catch (Exception e)
            {
                _observer.OnError(e);
                _completed = true;
                return;
            }

            _observer.OnNext(_reader.Current);
        }

        _completed = true;
        _observer.OnCompleted();
    }

    public void Dispose()
    {
        if (!_completed && !_tokenSource.IsCancellationRequested)
        {
            _tokenSource.Cancel();
        }

        _tokenSource.Dispose();
        _task.Dispose();
    }

}
```

Lo único que se necesita ahora es un método de extensión simple para crear el objeto observable desde el lector de secuencias.

```csharp
using System;
using System.Threading;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(
            this IAsyncStreamReader<T> reader,
            CancellationToken cancellationToken = default) =>
            new GrpcStreamObservable<T>(reader, cancellationToken);
    }
}
```

## <a name="summary"></a>Resumen

Los <xref:System.Collections.Generic.IAsyncEnumerable%601> <xref:System.IObservable%601> modelos y son formas bien documentadas y bien documentadas de tratar con flujos de datos asincrónicos en .net. gRPC streams se asigna bien a ambos paradigmas, ofreciendo una estrecha integración con .NET y estilos de programación reactivo y asincrónico.

>[!div class="step-by-step"]
>[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)
