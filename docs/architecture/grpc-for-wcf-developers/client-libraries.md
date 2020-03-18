---
title: Crear bibliotecas de cliente gRPC - gRPC para desarrolladores de WCF
description: Discusión de bibliotecas/paquetes de cliente compartidos para servicios gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401776"
---
# <a name="create-grpc-client-libraries"></a>Crear bibliotecas de cliente gRPC

No es necesario distribuir bibliotecas de cliente para una aplicación gRPC. Puede crear una biblioteca `.proto` compartida de archivos dentro de su organización y otros equipos pueden usar esos archivos para generar código de cliente en sus propios proyectos. Pero si tiene un repositorio NuGet privado y muchos otros equipos usan .NET Core, puede crear y publicar paquetes NuGet de cliente como parte del proyecto de servicio. Esta puede ser una buena manera de compartir y promover su servicio.

Una ventaja de distribuir una biblioteca de cliente es que puede mejorar las clases gRPC y Protobuf generadas con métodos y propiedades útiles de "conveniencia". En el código de cliente, como en el `partial`servidor, todas las clases se declaran como , por lo que puede ampliarlas sin editar el código generado. Esto significa que es fácil agregar constructores, métodos y propiedades calculadas a los tipos básicos.

> [!CAUTION]
> No debe usar código personalizado para proporcionar funcionalidad esencial. No desea restringir esa funcionalidad esencial a los equipos de .NET que usan la biblioteca compartida y no proporcionarla a los equipos que utilizan otros lenguajes o plataformas, como Python o Java.

Asegúrese de que tantos equipos como sea posible puedan acceder a su servicio gRPC. La mejor manera de hacerlo `.proto` es compartir archivos para que los desarrolladores puedan generar sus propios clientes. Esto es especialmente cierto en un entorno multiplataforma, donde diferentes equipos utilizan con frecuencia diferentes lenguajes de programación y marcos de trabajo, o donde la API es accesible externamente.

## <a name="useful-extensions"></a>Extensiones útiles

Hay dos interfaces de uso común en .NET para <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>tratar con secuencias de objetos: y . A partir de .NET Core 3.0 y C- <xref:System.Collections.Generic.IAsyncEnumerable%601> 8.0, hay una `await foreach` interfaz para procesar secuencias de forma asincrónica y una sintaxis para usar la interfaz. Esta sección presenta código reutilizable para aplicar estas interfaces a secuencias gRPC.

Con las bibliotecas de cliente gRPC de `ReadAllAsync` .NET `IAsyncStreamReader<T>` Core, `IAsyncEnumerable<T>` hay un método de extensión para que cree una interfaz. Para los desarrolladores que usan programación `IObservable<T>` reactiva, un método de extensión equivalente para crear una interfaz podría ser similar al ejemplo de la sección siguiente.

### <a name="iobservable"></a>IObservable

La `IObservable<T>` interfaz es la inversa `IEnumerable<T>`"reactiva" de . En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que la secuencia inserte elementos a un suscriptor. Esto es muy similar a las secuencias gRPC, `IObservable<T>` y `IAsyncStreamReader<T>` es fácil envolver una interfaz alrededor de una interfaz.

Este código es `IAsyncEnumerable<T>` más largo que el código, ya que No tiene compatibilidad integrada para trabajar con observables. Debe crear la clase de implementación manualmente. Es una clase genérica, sin embargo, por lo que una sola implementación funciona en todos los tipos.

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
> Esta implementación observable permite llamar al `Subscribe` método una sola vez, porque tener varios suscriptores que intentan leer de la secuencia resultaría en caos. Hay operadores, `Replay` como en [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), que permiten el almacenamiento en búfer y el uso compartido repetible de observables, que se pueden utilizar con esta implementación.

La `GrpcStreamSubscription` clase controla `IAsyncStreamReader`la enumeración de:

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

Todo lo que se requiere ahora es un método de extensión simple para crear el observable desde el lector de secuencias.

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

Los `IAsyncEnumerable` `IObservable` modelos y son formas bien admitidas y bien documentadas de tratar con secuencias asincrónicas de datos en .NET. Las secuencias gRPC se asignan bien a ambos paradigmas, lo que ofrece una estrecha integración con .NET Core y estilos de programación reactivos y asíncronos.

>[!div class="step-by-step"]
>[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)
