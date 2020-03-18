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
# <a name="create-grpc-client-libraries"></a><span data-ttu-id="fcb82-103">Crear bibliotecas de cliente gRPC</span><span class="sxs-lookup"><span data-stu-id="fcb82-103">Create gRPC client libraries</span></span>

<span data-ttu-id="fcb82-104">No es necesario distribuir bibliotecas de cliente para una aplicación gRPC.</span><span class="sxs-lookup"><span data-stu-id="fcb82-104">It isn't necessary to distribute client libraries for a gRPC application.</span></span> <span data-ttu-id="fcb82-105">Puede crear una biblioteca `.proto` compartida de archivos dentro de su organización y otros equipos pueden usar esos archivos para generar código de cliente en sus propios proyectos.</span><span class="sxs-lookup"><span data-stu-id="fcb82-105">You can create a shared library of `.proto` files within your organization, and other teams can use those files to generate client code in their own projects.</span></span> <span data-ttu-id="fcb82-106">Pero si tiene un repositorio NuGet privado y muchos otros equipos usan .NET Core, puede crear y publicar paquetes NuGet de cliente como parte del proyecto de servicio.</span><span class="sxs-lookup"><span data-stu-id="fcb82-106">But if you have a private NuGet repository and many other teams are using .NET Core, you can create and publish client NuGet packages as part of your service project.</span></span> <span data-ttu-id="fcb82-107">Esta puede ser una buena manera de compartir y promover su servicio.</span><span class="sxs-lookup"><span data-stu-id="fcb82-107">This can be a good way of sharing and promoting your service.</span></span>

<span data-ttu-id="fcb82-108">Una ventaja de distribuir una biblioteca de cliente es que puede mejorar las clases gRPC y Protobuf generadas con métodos y propiedades útiles de "conveniencia".</span><span class="sxs-lookup"><span data-stu-id="fcb82-108">One advantage of distributing a client library is that you can enhance the generated gRPC and Protobuf classes with helpful "convenience" methods and properties.</span></span> <span data-ttu-id="fcb82-109">En el código de cliente, como en el `partial`servidor, todas las clases se declaran como , por lo que puede ampliarlas sin editar el código generado.</span><span class="sxs-lookup"><span data-stu-id="fcb82-109">In the client code, as in the server, all the classes are declared as `partial`, so you can extend them without editing the generated code.</span></span> <span data-ttu-id="fcb82-110">Esto significa que es fácil agregar constructores, métodos y propiedades calculadas a los tipos básicos.</span><span class="sxs-lookup"><span data-stu-id="fcb82-110">This means it's easy to add constructors, methods, and calculated properties to the basic types.</span></span>

> [!CAUTION]
> <span data-ttu-id="fcb82-111">No debe usar código personalizado para proporcionar funcionalidad esencial.</span><span class="sxs-lookup"><span data-stu-id="fcb82-111">You shouldn't use custom code to provide essential functionality.</span></span> <span data-ttu-id="fcb82-112">No desea restringir esa funcionalidad esencial a los equipos de .NET que usan la biblioteca compartida y no proporcionarla a los equipos que utilizan otros lenguajes o plataformas, como Python o Java.</span><span class="sxs-lookup"><span data-stu-id="fcb82-112">You don't want to restrict that essential functionality to .NET teams that use the shared library, and not provide it to teams that use other languages or platforms, such as Python or Java.</span></span>

<span data-ttu-id="fcb82-113">Asegúrese de que tantos equipos como sea posible puedan acceder a su servicio gRPC.</span><span class="sxs-lookup"><span data-stu-id="fcb82-113">Ensure that as many teams as possible can access your gRPC service.</span></span> <span data-ttu-id="fcb82-114">La mejor manera de hacerlo `.proto` es compartir archivos para que los desarrolladores puedan generar sus propios clientes.</span><span class="sxs-lookup"><span data-stu-id="fcb82-114">The best way to do this is to share `.proto` files so developers can generate their own clients.</span></span> <span data-ttu-id="fcb82-115">Esto es especialmente cierto en un entorno multiplataforma, donde diferentes equipos utilizan con frecuencia diferentes lenguajes de programación y marcos de trabajo, o donde la API es accesible externamente.</span><span class="sxs-lookup"><span data-stu-id="fcb82-115">This is particularly true in a multi-platform environment, where different teams frequently use different programming languages and frameworks, or where your API is externally accessible.</span></span>

## <a name="useful-extensions"></a><span data-ttu-id="fcb82-116">Extensiones útiles</span><span class="sxs-lookup"><span data-stu-id="fcb82-116">Useful extensions</span></span>

<span data-ttu-id="fcb82-117">Hay dos interfaces de uso común en .NET para <xref:System.Collections.Generic.IEnumerable%601> <xref:System.IObservable%601>tratar con secuencias de objetos: y .</span><span class="sxs-lookup"><span data-stu-id="fcb82-117">There are two commonly used interfaces in .NET for dealing with streams of objects: <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.IObservable%601>.</span></span> <span data-ttu-id="fcb82-118">A partir de .NET Core 3.0 y C- <xref:System.Collections.Generic.IAsyncEnumerable%601> 8.0, hay una `await foreach` interfaz para procesar secuencias de forma asincrónica y una sintaxis para usar la interfaz.</span><span class="sxs-lookup"><span data-stu-id="fcb82-118">Starting with .NET Core 3.0 and C# 8.0, there's an <xref:System.Collections.Generic.IAsyncEnumerable%601> interface for processing streams asynchronously, and an `await foreach` syntax for using the interface.</span></span> <span data-ttu-id="fcb82-119">Esta sección presenta código reutilizable para aplicar estas interfaces a secuencias gRPC.</span><span class="sxs-lookup"><span data-stu-id="fcb82-119">This section presents reusable code for applying these interfaces to gRPC streams.</span></span>

<span data-ttu-id="fcb82-120">Con las bibliotecas de cliente gRPC de `ReadAllAsync` .NET `IAsyncStreamReader<T>` Core, `IAsyncEnumerable<T>` hay un método de extensión para que cree una interfaz.</span><span class="sxs-lookup"><span data-stu-id="fcb82-120">With the .NET Core gRPC client libraries, there's a `ReadAllAsync` extension method for `IAsyncStreamReader<T>` that creates an `IAsyncEnumerable<T>` interface.</span></span> <span data-ttu-id="fcb82-121">Para los desarrolladores que usan programación `IObservable<T>` reactiva, un método de extensión equivalente para crear una interfaz podría ser similar al ejemplo de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="fcb82-121">For developers using reactive programming, an equivalent extension method to create an `IObservable<T>` interface might look like the example in the following section.</span></span>

### <a name="iobservable"></a><span data-ttu-id="fcb82-122">IObservable</span><span class="sxs-lookup"><span data-stu-id="fcb82-122">IObservable</span></span>

<span data-ttu-id="fcb82-123">La `IObservable<T>` interfaz es la inversa `IEnumerable<T>`"reactiva" de .</span><span class="sxs-lookup"><span data-stu-id="fcb82-123">The `IObservable<T>` interface is the "reactive" inverse of `IEnumerable<T>`.</span></span> <span data-ttu-id="fcb82-124">En lugar de extraer elementos de una secuencia, el enfoque reactivo permite que la secuencia inserte elementos a un suscriptor.</span><span class="sxs-lookup"><span data-stu-id="fcb82-124">Rather than pulling items from a stream, the reactive approach lets the stream push items to a subscriber.</span></span> <span data-ttu-id="fcb82-125">Esto es muy similar a las secuencias gRPC, `IObservable<T>` y `IAsyncStreamReader<T>` es fácil envolver una interfaz alrededor de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="fcb82-125">This is very similar to gRPC streams, and it's easy to wrap an `IObservable<T>` interface around an `IAsyncStreamReader<T>` interface.</span></span>

<span data-ttu-id="fcb82-126">Este código es `IAsyncEnumerable<T>` más largo que el código, ya que No tiene compatibilidad integrada para trabajar con observables.</span><span class="sxs-lookup"><span data-stu-id="fcb82-126">This code is longer than the `IAsyncEnumerable<T>` code, because C# doesn't have built-in support for working with observables.</span></span> <span data-ttu-id="fcb82-127">Debe crear la clase de implementación manualmente.</span><span class="sxs-lookup"><span data-stu-id="fcb82-127">You have to create the implementation class manually.</span></span> <span data-ttu-id="fcb82-128">Es una clase genérica, sin embargo, por lo que una sola implementación funciona en todos los tipos.</span><span class="sxs-lookup"><span data-stu-id="fcb82-128">It's a generic class, though, so a single implementation works across all types.</span></span>

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
> <span data-ttu-id="fcb82-129">Esta implementación observable permite llamar al `Subscribe` método una sola vez, porque tener varios suscriptores que intentan leer de la secuencia resultaría en caos.</span><span class="sxs-lookup"><span data-stu-id="fcb82-129">This observable implementation allows the `Subscribe` method to be called only once, because having multiple subscribers trying to read from the stream would result in chaos.</span></span> <span data-ttu-id="fcb82-130">Hay operadores, `Replay` como en [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), que permiten el almacenamiento en búfer y el uso compartido repetible de observables, que se pueden utilizar con esta implementación.</span><span class="sxs-lookup"><span data-stu-id="fcb82-130">There are operators, such as `Replay` in the [System.Reactive.Linq](https://www.nuget.org/packages/System.Reactive.Linq), that enable buffering and repeatable sharing of observables, which can be used with this implementation.</span></span>

<span data-ttu-id="fcb82-131">La `GrpcStreamSubscription` clase controla `IAsyncStreamReader`la enumeración de:</span><span class="sxs-lookup"><span data-stu-id="fcb82-131">The `GrpcStreamSubscription` class handles the enumeration of the `IAsyncStreamReader`:</span></span>

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

<span data-ttu-id="fcb82-132">Todo lo que se requiere ahora es un método de extensión simple para crear el observable desde el lector de secuencias.</span><span class="sxs-lookup"><span data-stu-id="fcb82-132">All that is required now is a simple extension method to create the observable from the stream reader.</span></span>

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

## <a name="summary"></a><span data-ttu-id="fcb82-133">Resumen</span><span class="sxs-lookup"><span data-stu-id="fcb82-133">Summary</span></span>

<span data-ttu-id="fcb82-134">Los `IAsyncEnumerable` `IObservable` modelos y son formas bien admitidas y bien documentadas de tratar con secuencias asincrónicas de datos en .NET.</span><span class="sxs-lookup"><span data-stu-id="fcb82-134">The `IAsyncEnumerable` and `IObservable` models are both well-supported and well-documented ways of dealing with asynchronous streams of data in .NET.</span></span> <span data-ttu-id="fcb82-135">Las secuencias gRPC se asignan bien a ambos paradigmas, lo que ofrece una estrecha integración con .NET Core y estilos de programación reactivos y asíncronos.</span><span class="sxs-lookup"><span data-stu-id="fcb82-135">gRPC streams map well to both paradigms, offering close integration with .NET Core, and reactive and asynchronous programming styles.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fcb82-136">[Anterior](streaming-versus-repeated.md)
>[Siguiente](security.md)</span><span class="sxs-lookup"><span data-stu-id="fcb82-136">[Previous](streaming-versus-repeated.md)
[Next](security.md)</span></span>
