---
title: 'Creación de bibliotecas de cliente de gRPC: gRPC para desarrolladores de WCF'
description: Explicación de los paquetes o bibliotecas de cliente compartidos para gRPC Services.
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: b403e7e1638496947ac7f6fc976cbeab2f435bbf
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73842066"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="24264-103">Creación de bibliotecas de cliente de gRPC</span><span class="sxs-lookup"><span data-stu-id="24264-103">Create gRPC client libraries</span></span>

<span data-ttu-id="24264-104">No es necesario distribuir bibliotecas de cliente para una aplicación de gRPC.</span><span class="sxs-lookup"><span data-stu-id="24264-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="24264-105">Puede crear una biblioteca compartida de archivos de `.proto` dentro de la organización y otros equipos pueden usar esos archivos para generar el código de cliente en sus propios proyectos.</span><span class="sxs-lookup"><span data-stu-id="24264-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="24264-106">Pero si tiene un repositorio de NuGet privado y muchos otros equipos están usando .NET Core, la creación y publicación de paquetes NuGet de cliente como parte del proyecto de servicio puede ser una buena forma de compartir y promocionar el servicio.</span><span class="sxs-lookup"><span data-stu-id="24264-106">But if you have a private NuGet repository and many other teams are using .NET Core, creating and publishing client NuGet packages as part of your service project may be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="24264-107">Una ventaja de la distribución de una biblioteca de cliente es que puede mejorar las clases gRPC y protobuf generadas con útiles métodos y propiedades útiles.</span><span class="sxs-lookup"><span data-stu-id="24264-107">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="24264-108">En el código de cliente, al igual que en el servidor, todas las clases se declaran como `partial` para que pueda ampliarlas sin editar el código generado.</span><span class="sxs-lookup"><span data-stu-id="24264-108">In the client code, as in the server, all the classes are declared as `partial` so you can extend them without editing the generated code.</span></span> <span data-ttu-id="24264-109">Esto significa que es fácil agregar constructores, métodos, propiedades calculadas y más a los tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="24264-109">This means it's easy to add constructors, methods, calculated properties, and more to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="24264-110">**No** debe usar código personalizado para proporcionar funcionalidad esencial, ya que esto significaría que la funcionalidad se restringiría a los equipos de .net que usan la biblioteca compartida y no a los equipos que usan otros lenguajes o plataformas, como Python o Java.</span><span class="sxs-lookup"><span data-stu-id="24264-110">You should **not** use custom code to provide essential functionality, as this would mean that functionality would be restricted to .NET teams using the shared library, and not to teams using other languages or platforms such as Python or Java.</span></span>

<span data-ttu-id="24264-111">En un entorno multiplataforma en el que los distintos equipos usan con frecuencia distintos lenguajes y marcos de programación, o donde la API es accesible externamente, basta con compartir archivos de `.proto` para que los desarrolladores puedan generar sus propios clientes es la mejor manera de asegurarse de que tantos equipos como sea posible puedan tener acceso al servicio de gRPC.</span><span class="sxs-lookup"><span data-stu-id="24264-111">In a multi-platform environment where different teams frequently use different programming languages and frameworks, or where your API is externally accessible, simply sharing `.proto` files so developers can generate their own clients is the best way to ensure as many teams as possible can access your gRPC service.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="24264-112">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="24264-112">Useful extensions</span></span>

<span data-ttu-id="24264-113">Hay dos interfaces de uso frecuente en .NET para trabajar con secuencias de objetos: <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="24264-113">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="24264-114">A partir de .NET Core 3,0 C# y 8,0, hay una interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601> para procesar secuencias de forma asincrónica y una sintaxis `await foreach` para usar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="24264-114">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="24264-115">En esta sección se presenta código reutilizable para aplicar estas interfaces a las secuencias de gRPC.</span><span class="sxs-lookup"><span data-stu-id="24264-115">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="24264-116">Con las bibliotecas de cliente de .NET Core gRPC, hay un método de extensión de `ReadAllAsync` para `IAsyncStreamReader<T>` que crea una `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="24264-116">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>`.</span></span> <span data-ttu-id="24264-117">Para los desarrolladores que usan programación reactiva, un método de extensión equivalente para crear un `IObservable<T>` podría ser similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="24264-117">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` might look like this.</span></span>

### <a name="iobservable"></a><span data-ttu-id="24264-118">IObservable</span><span class="sxs-lookup"><span data-stu-id="24264-118">IObservable</span></span>

<span data-ttu-id="24264-119">La interfaz de `IObservable<T>` es el inverso "reactivo" de `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="24264-119">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="24264-120">En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que los elementos de la secuencia se inserten en un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="24264-120">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="24264-121">Esto es muy similar a gRPC streams, y es fácil ajustar un `IObservable<T>` alrededor de un `IAsyncStreamReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="24264-121">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` around an `IAsyncStreamReader<T>`.</span></span>

<span data-ttu-id="24264-122">Este código es más largo que el código `IAsyncEnumerable<T>` C# porque no tiene compatibilidad integrada para trabajar con observables, por lo que la clase de implementación debe crearse manualmente.</span><span class="sxs-lookup"><span data-stu-id="24264-122">This code is longer than the `IAsyncEnumerable<T>` code because C# doesn't have built-in support for working with observables, so the implementation class has to be created manually.</span></span> <span data-ttu-id="24264-123">Sin embargo, es una clase genérica, por lo que una sola implementación funcionará en todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="24264-123">It's a generic class, though, so a single implementation will work across all types.</span></span>

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
> <span data-ttu-id="24264-124">Esta implementación observable solo permite llamar al método `Subscribe` una vez, ya que el hecho de que varios suscriptores intenten leer el flujo daría como resultado un caos.</span><span class="sxs-lookup"><span data-stu-id="24264-124">This observable implementation only allows the `Subscribe` method to be called once, as having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="24264-125">Hay operadores como `Replay` en [System. reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq) que habilitan el almacenamiento en búfer y el uso compartido repetible de observables, que se puede usar con esta implementación.</span><span class="sxs-lookup"><span data-stu-id="24264-125">There are operators such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq) that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="24264-126">La clase `GrpcStreamSubscription` controla la enumeración de la `IAsyncStreamReader`.</span><span class="sxs-lookup"><span data-stu-id="24264-126">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`.</span></span>

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

<span data-ttu-id="24264-127">Lo único que se necesita ahora es un método de extensión simple para crear el objeto observable desde el lector de secuencias.</span><span class="sxs-lookup"><span data-stu-id="24264-127">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="24264-128">Resumen</span><span class="sxs-lookup"><span data-stu-id="24264-128">Summary</span></span>

<span data-ttu-id="24264-129">Los modelos `IAsyncEnumerable` y `IObservable` son formas bien documentadas y bien documentadas de trabajar con secuencias de datos asincrónicas en .NET.</span><span class="sxs-lookup"><span data-stu-id="24264-129">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="24264-130">gRPC streams se asigna bien a ambos paradigmas, lo que ofrece una estrecha integración con el marco de trabajo .NET Core moderno y estilos de programación reactivos y asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="24264-130">gRPC streams map well to both paradigms, offering close integration with the modern .NET Core framework and reactive/asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="24264-131">[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)</span><span class="sxs-lookup"><span data-stu-id="24264-131">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
