---
title: 'Creación de bibliotecas de cliente de gRPC: gRPC para desarrolladores de WCF'
description: Explicación de los paquetes o bibliotecas de cliente compartidos para gRPC Services.
ms.date: 09/02/2019
ms.openlocfilehash: bb58cb3cda4b0cbb3a5d34129961349bcb0093e9
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78675172"
---
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="89b95-103">Creación de bibliotecas de cliente de gRPC</span><span class="sxs-lookup"><span data-stu-id="89b95-103">Create gRPC client libraries</span></span>

<span data-ttu-id="89b95-104">No es necesario distribuir bibliotecas de cliente para una aplicación de gRPC.</span><span class="sxs-lookup"><span data-stu-id="89b95-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="89b95-105">Puede crear una biblioteca compartida de archivos de `.proto` dentro de la organización y otros equipos pueden usar esos archivos para generar el código de cliente en sus propios proyectos.</span><span class="sxs-lookup"><span data-stu-id="89b95-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="89b95-106">Pero si tiene un repositorio de NuGet privado y muchos otros equipos están usando .NET Core, puede crear y publicar paquetes NuGet de cliente como parte del proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="89b95-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="89b95-107">Esto puede ser una buena forma de compartir y promocionar el servicio.</span><span class="sxs-lookup"><span data-stu-id="89b95-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="89b95-108">Una ventaja de la distribución de una biblioteca de cliente es que puede mejorar las clases gRPC y protobuf generadas con útiles métodos y propiedades útiles.</span><span class="sxs-lookup"><span data-stu-id="89b95-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="89b95-109">En el código de cliente, al igual que en el servidor, todas las clases se declaran como `partial`, por lo que puede ampliarlas sin editar el código generado.</span><span class="sxs-lookup"><span data-stu-id="89b95-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="89b95-110">Esto significa que es fácil agregar constructores, métodos y propiedades calculadas a los tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="89b95-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="89b95-111">No debe utilizar código personalizado para proporcionar una funcionalidad esencial.</span><span class="sxs-lookup"><span data-stu-id="89b95-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="89b95-112">No quiere restringir esa funcionalidad esencial a los equipos de .NET que usan la biblioteca compartida y no proporcionar a los equipos que usan otros lenguajes o plataformas, como Python o Java.</span><span class="sxs-lookup"><span data-stu-id="89b95-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="89b95-113">Asegúrese de que tantos equipos como sea posible puedan tener acceso al servicio de gRPC.</span><span class="sxs-lookup"><span data-stu-id="89b95-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="89b95-114">La mejor manera de hacerlo es compartir archivos de `.proto` para que los desarrolladores puedan generar sus propios clientes.</span><span class="sxs-lookup"><span data-stu-id="89b95-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="89b95-115">Esto es especialmente cierto en un entorno de varias plataformas, donde los distintos equipos usan con frecuencia diferentes lenguajes de programación y marcos, o donde la API es externamente accesible.</span><span class="sxs-lookup"><span data-stu-id="89b95-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="89b95-116">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="89b95-116">Useful extensions</span></span>

<span data-ttu-id="89b95-117">Hay dos interfaces de uso frecuente en .NET para trabajar con secuencias de objetos: <xref:System.Collections.Generic.IEnumerable%601> y <xref:System.IObservable%601>.</span><span class="sxs-lookup"><span data-stu-id="89b95-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="89b95-118">A partir de .NET Core 3,0 C# y 8,0, hay una interfaz <xref:System.Collections.Generic.IAsyncEnumerable%601> para procesar secuencias de forma asincrónica y una sintaxis `await foreach` para usar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="89b95-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="89b95-119">En esta sección se presenta código reutilizable para aplicar estas interfaces a las secuencias de gRPC.</span><span class="sxs-lookup"><span data-stu-id="89b95-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="89b95-120">Con las bibliotecas de cliente de .NET Core gRPC, hay un método de extensión `ReadAllAsync` para `IAsyncStreamReader<T>` que crea una interfaz `IAsyncEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="89b95-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="89b95-121">Para los desarrolladores que usan programación reactiva, un método de extensión equivalente para crear una interfaz `IObservable<T>` podría ser similar al del ejemplo de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="89b95-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="89b95-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="89b95-122">IObservable</span></span>

<span data-ttu-id="89b95-123">La interfaz de `IObservable<T>` es el inverso "reactivo" de `IEnumerable<T>`.</span><span class="sxs-lookup"><span data-stu-id="89b95-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="89b95-124">En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que los elementos de la secuencia se inserten en un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="89b95-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="89b95-125">Esto es muy similar a gRPC streams, y es fácil encapsular una interfaz de `IObservable<T>` alrededor de una interfaz `IAsyncStreamReader<T>`.</span><span class="sxs-lookup"><span data-stu-id="89b95-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="89b95-126">Este código es más largo que el código `IAsyncEnumerable<T>`, C# porque no tiene compatibilidad integrada para trabajar con observables.</span><span class="sxs-lookup"><span data-stu-id="89b95-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="89b95-127">Debe crear la clase de implementación manualmente.</span><span class="sxs-lookup"><span data-stu-id="89b95-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="89b95-128">Sin embargo, es una clase genérica, por lo que una sola implementación funciona en todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="89b95-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="89b95-129">Esta implementación observable permite llamar al método `Subscribe` solo una vez, porque el hecho de que varios suscriptores intenten leer desde la secuencia daría como resultado un caos.</span><span class="sxs-lookup"><span data-stu-id="89b95-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="89b95-130">Hay operadores, como `Replay` en [System. reactive. Linq](https://www.nuget.org/packages/System.Reactive.Linq), que habilitan el almacenamiento en búfer y el uso compartido repetible de observables, que se puede usar con esta implementación.</span><span class="sxs-lookup"><span data-stu-id="89b95-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="89b95-131">La clase `GrpcStreamSubscription` controla la enumeración de la `IAsyncStreamReader`:</span><span class="sxs-lookup"><span data-stu-id="89b95-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="89b95-132">Lo único que se necesita ahora es un método de extensión simple para crear el objeto observable desde el lector de secuencias.</span><span class="sxs-lookup"><span data-stu-id="89b95-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="89b95-133">Resumen</span><span class="sxs-lookup"><span data-stu-id="89b95-133">Summary</span></span>

<span data-ttu-id="89b95-134">Los modelos `IAsyncEnumerable` y `IObservable` son formas bien documentadas y bien documentadas de trabajar con secuencias de datos asincrónicas en .NET.</span><span class="sxs-lookup"><span data-stu-id="89b95-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="89b95-135">gRPC streams se asigna bien a ambos paradigmas, ofreciendo una estrecha integración con .NET Core y estilos de programación reactivos y asincrónicos.</span><span class="sxs-lookup"><span data-stu-id="89b95-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="89b95-136">[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)</span><span class="sxs-lookup"><span data-stu-id="89b95-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
