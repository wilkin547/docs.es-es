---
title: 'Creación de bibliotecas de cliente de gRPC: gRPC para desarrolladores de WCF'
description: Explicación de los paquetes o bibliotecas de cliente compartidos para gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: 2135fe8b24a2311a31cb2bed191d290b1112bc66
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967876"
---
# <a name="create-grpc-client-libraries"></a>Creación de bibliotecas de cliente de gRPC

No es necesario distribuir bibliotecas de cliente para una aplicación de gRPC. Puede crear una biblioteca compartida de archivos de `.proto` dentro de la organización y otros equipos pueden usar esos archivos para generar el código de cliente en sus propios proyectos. Pero si tiene un repositorio de NuGet privado y muchos otros equipos están usando .NET Core, la creación y publicación de paquetes NuGet de cliente como parte del proyecto de servicio puede ser una buena forma de compartir y promocionar el servicio.

Una ventaja de la distribución de una biblioteca de cliente es que puede mejorar las clases gRPC y protobuf generadas con útiles métodos y propiedades útiles. En el código de cliente, al igual que en el servidor, todas las clases se declaran como `partial` para que pueda ampliarlas sin editar el código generado. Esto significa que es fácil agregar constructores, métodos, propiedades calculadas y más a los tipos básicos.

> [!CAUTION]
> **No** debe usar código personalizado para proporcionar funcionalidad esencial, ya que esto significaría que la funcionalidad se restringiría a los equipos de .net que usan la biblioteca compartida y no a los equipos que usan otros lenguajes o plataformas, como Python o Java.

En un entorno multiplataforma en el que los distintos equipos usan con frecuencia distintos lenguajes y marcos de programación, o donde la API es accesible externamente, basta con compartir archivos de `.proto` para que los desarrolladores puedan generar sus propios clientes es la mejor manera de asegurarse de que tantos equipos como sea posible puedan tener acceso al servicio de gRPC.

## <a name="useful-extensions"></a>Extensiones útiles

Hay dos interfaces de uso frecuente en .NET para trabajar con secuencias de objetos: <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IObservable%601>. A partir de .NET Core 3,0 C# y 8,0, hay una interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601> para procesar secuencias de forma asincrónica y una sintaxis `await foreach` para usar la interfaz. En esta sección se presenta código reutilizable para aplicar estas interfaces a las secuencias de gRPC.

Con las bibliotecas de cliente de .NET Core gRPC, hay un método de extensión de `ReadAllAsync` para `IAsyncStreamReader<T>` que crea una `IAsyncEnumerable<T>`. Para los desarrolladores que usan programación reactiva, un método de extensión equivalente para crear un `IObservable<T>` podría ser similar al siguiente.

### <a name="iobservable"></a>IObservable

La interfaz de `IObservable<T>` es el inverso "reactivo" de `IEnumerable<T>`. En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que los elementos de la secuencia se inserten en un suscriptor. Esto es muy similar a gRPC streams, y es fácil ajustar un `IObservable<T>` alrededor de un `IAsyncStreamReader<T>`.

Este código es más largo que el código `IAsyncEnumerable<T>` C# porque no tiene compatibilidad integrada para trabajar con observables, por lo que la clase de implementación debe crearse manualmente. Sin embargo, es una clase genérica, por lo que una sola implementación funcionará en todos los tipos.

```csharp
using System;
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public class GrpcStreamObservable<T> : IObservable<T>
    {
        private readonly IAsyncStreamReader<T> _reader;
        private readonly CancellationToken _token;
        private int _used;

        public Observable(IAsyncStreamReader<T> reader, CancellationToken token = default)
        {
            _reader = reader;
            _token = token;
            _used = 0;
        }

        public IDisposable Subscribe(IObserver<T> observer) =>
            Interlocked.Exchange(ref _used, 1) == 0
                ? new GrpcStreamSubscription(_reader, observer, _token)
                : throw new InvalidOperationException("Subscribe can only be called once.");

    }
}
```

> [!IMPORTANT]
> Esta implementación observable solo permite llamar al método `Subscribe` una vez, ya que el hecho de que varios suscriptores intenten leer el flujo daría como resultado un caos. Hay operadores como `Replay` en [System. reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq) que habilitan el almacenamiento en búfer y el uso compartido repetible de observables, que se puede usar con esta implementación.

La clase `GrpcStreamSubscription` controla la enumeración de la `IAsyncStreamReader`.

```csharp
public class GrpcStreamSubscription : IDisposable
{
    private readonly Task _task;
    private readonly CancellationTokenSource _tokenSource;
    private bool _completed;

    public Subscription(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        Debug.Assert(reader != null);
        Debug.Assert(observer != null);
        _tokenSource = new CancellationTokenSource();
        token.Register(_tokenSource.Cancel);
        _task = Run(reader, observer, _tokenSource.Token);
    }

    private async Task Run(IAsyncStreamReader<T> reader, IObserver<T> observer, CancellationToken token)
    {
        while (!token.IsCancellationRequested)
        {
            try
            {
                if (!await reader.MoveNext(token)) break;
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
                observer.OnError(e);
                _completed = true;
                return;
            }

            observer.OnNext(reader.Current);
        }

        _completed = true;
        observer.OnCompleted();
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
using System.Diagnostics;
using System.Threading;
using System.Threading.Tasks;

namespace Grpc.Core
{
    public static class AsyncStreamReaderObservableExtensions
    {
        public static IObservable<T> AsObservable<T>(this IAsyncStreamReader<T> reader) =>
            new GrpcStreamObservable<T>(reader);
    }
}
```

## <a name="summary"></a>Resumen

Los modelos `IAsyncEnumerable` y `IObservable` son formas bien documentadas y bien documentadas de trabajar con secuencias de datos asincrónicas en .NET. gRPC streams se asigna bien a ambos paradigmas, lo que ofrece una estrecha integración con el marco de trabajo .NET Core moderno y estilos de programación reactivos y asincrónicos.

>[!div class="step-by-step"]
>[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)
