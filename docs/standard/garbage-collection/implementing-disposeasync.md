---
title: Implementación de un método DisposeAsync
description: Obtenga información sobre cómo implementar los métodos DisposeAsync y DisposeAsyncCore para realizar una limpieza de recursos asincrónica.
author: IEvangelist
ms.author: dapine
ms.date: 08/25/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 268cea7584040ad92e2da75e5e03112480cda93c
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053183"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="16df9-103">Implementación de un método DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="16df9-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="16df9-104">La interfaz <xref:System.IAsyncDisposable?displayProperty=nameWithType> se presentó como parte de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="16df9-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="16df9-105">El método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> se implementa cuando se necesita realizar una limpieza de recursos, tal como se haría a la hora de [implementar un método Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="16df9-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="16df9-106">Sin embargo, una de las principales diferencias es que esta implementación permite operaciones de limpieza asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="16df9-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="16df9-107">El elemento <xref:System.IAsyncDisposable.DisposeAsync> devuelve un elemento <xref:System.Threading.Tasks.ValueTask> que representa la operación de eliminación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="16df9-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="16df9-108">Es habitual que, al implementar la interfaz <xref:System.IAsyncDisposable>, las clases también implementen la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="16df9-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="16df9-109">Debe prepararse un buen patrón de implementación de la interfaz <xref:System.IAsyncDisposable> para la eliminación sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="16df9-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="16df9-110">Todas las instrucciones para implementar el patrón de eliminación se aplican también a la implementación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="16df9-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="16df9-111">En este artículo se supone que ya se ha familiarizado con el modo de [implementar un método Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="16df9-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="16df9-112">DisposeAsync() y DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="16df9-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="16df9-113">La interfaz <xref:System.IAsyncDisposable> declara un único método sin parámetros: <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="16df9-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="16df9-114">Cualquier clase no sellada debe tener un método `DisposeAsyncCore()` adicional que también devuelva un elemento <xref:System.Threading.Tasks.ValueTask>.</span><span class="sxs-lookup"><span data-stu-id="16df9-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="16df9-115">Una implementación de <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> `public` que no tenga parámetros.</span><span class="sxs-lookup"><span data-stu-id="16df9-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="16df9-116">Un método `protected virtual ValueTask DisposeAsyncCore()` cuya signatura sea:</span><span class="sxs-lookup"><span data-stu-id="16df9-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="16df9-117">El método DisposeAsync()</span><span class="sxs-lookup"><span data-stu-id="16df9-117">The DisposeAsync() method</span></span>

<span data-ttu-id="16df9-118">Se llama de forma implícita al método `DisposeAsync()` sin parámetros `public` en una instrucción `await using`, y su propósito consiste en liberar los recursos no administrados, realizar una limpieza general e indicar que el finalizador, si existe, no necesita ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="16df9-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="16df9-119">La liberación de la memoria asociada a un objeto administrado siempre corresponde al [recolector de elementos no utilizados](index.md).</span><span class="sxs-lookup"><span data-stu-id="16df9-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="16df9-120">Debido a esto, se realiza una implementación estándar:</span><span class="sxs-lookup"><span data-stu-id="16df9-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="16df9-121">Una diferencia principal en el patrón de eliminación asincrónica en comparación con el patrón de eliminación es que la llamada desde <xref:System.IAsyncDisposable.DisposeAsync> al método de sobrecarga `Dispose(bool)` recibe el valor `false` como argumento.</span><span class="sxs-lookup"><span data-stu-id="16df9-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="16df9-122">Sin embargo, al implementar el método <xref:System.IDisposable.Dispose?displayProperty=nameWithType>, se pasa el valor `true`.</span><span class="sxs-lookup"><span data-stu-id="16df9-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="16df9-123">Esto ayuda a garantizar la equivalencia funcional con el patrón de eliminación sincrónico y garantiza aún más que se invoquen las rutas de acceso al código finalizador.</span><span class="sxs-lookup"><span data-stu-id="16df9-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="16df9-124">En otras palabras, el método `DisposeAsyncCore()` eliminará los recursos administrados de forma asincrónica, por lo que no querrá eliminarlos también de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="16df9-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="16df9-125">Por tanto, llame a `Dispose(false)` en lugar de a `Dispose(true)`.</span><span class="sxs-lookup"><span data-stu-id="16df9-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="16df9-126">Método DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="16df9-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="16df9-127">El método `DisposeAsyncCore()` está diseñado para realizar la limpieza asincrónica de los recursos administrados o para hacer llamadas en cascada a `DisposeAsync()`.</span><span class="sxs-lookup"><span data-stu-id="16df9-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="16df9-128">Encapsula las operaciones de limpieza asincrónica comunes cuando una subclase hereda una clase base que es una implementación de <xref:System.IAsyncDisposable>.</span><span class="sxs-lookup"><span data-stu-id="16df9-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="16df9-129">El método `DisposeAsyncCore()` es `virtual` para que las clases derivadas puedan definir la limpieza adicional en sus invalidaciones.</span><span class="sxs-lookup"><span data-stu-id="16df9-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="16df9-130">Si una implementación de <xref:System.IAsyncDisposable> es `sealed`, el método `DisposeAsyncCore()` no es necesario y la limpieza asincrónica se puede realizar directamente en el método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16df9-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="16df9-131">Implementación del patrón de eliminación asincrónica</span><span class="sxs-lookup"><span data-stu-id="16df9-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="16df9-132">Todas las clases no selladas deben considerarse una clase base potencial, ya que se podrían heredar.</span><span class="sxs-lookup"><span data-stu-id="16df9-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="16df9-133">Cuando se implementa el patrón de eliminación asincrónica para cualquier clase base potencial, se debe proporcionar el método `protected virtual ValueTask DisposeAsyncCore()`.</span><span class="sxs-lookup"><span data-stu-id="16df9-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="16df9-134">Este es un ejemplo de implementación del patrón de eliminación asincrónica que usa un elemento <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16df9-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="16df9-135">En el ejemplo anterior se usa <xref:System.Text.Json.Utf8JsonWriter>.</span><span class="sxs-lookup"><span data-stu-id="16df9-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="16df9-136">Para obtener más información sobre `System.Text.Json`, vea [Migración desde Newtonsoft.json a System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="16df9-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="16df9-137">Uso de la eliminación asincrónica</span><span class="sxs-lookup"><span data-stu-id="16df9-137">Using async disposable</span></span>

<span data-ttu-id="16df9-138">Para usar correctamente un objeto que implementa la interfaz <xref:System.IAsyncDisposable>, utilice las palabras clave [await](../../csharp/language-reference/operators/await.md) y [using](../../csharp/language-reference/keywords/using-statement.md) juntas.</span><span class="sxs-lookup"><span data-stu-id="16df9-138">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="16df9-139">Tenga en cuenta el ejemplo siguiente, donde se crea una instancia de la clase `ExampleAsyncDisposable` y después se encapsula en una instrucción `await using`.</span><span class="sxs-lookup"><span data-stu-id="16df9-139">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="16df9-140">Use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> de la interfaz <xref:System.IAsyncDisposable> para configurar el modo en que se serializa la continuación de la tarea en su contexto o programador original.</span><span class="sxs-lookup"><span data-stu-id="16df9-140">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="16df9-141">Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="16df9-141">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="16df9-142">En situaciones en las que no se necesita el uso de `ConfigureAwait`, la instrucción `await using` se podría simplificar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="16df9-142">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="16df9-143">Además, se podría escribir para utilizar el ámbito implícito de una [declaración "using"](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="16df9-143">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="16df9-144">Declaraciones "using" apiladas</span><span class="sxs-lookup"><span data-stu-id="16df9-144">Stacked usings</span></span>

<span data-ttu-id="16df9-145">En situaciones en las que se crean y se utilizan varios objetos que implementan <xref:System.IAsyncDisposable>, es posible que el apilamiento de instrucciones `using` en condiciones errantes pudiera impedir la realización de llamadas a <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="16df9-145">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="16df9-146">Para ayudar a evitar un posible problema, debe evitar el apilamiento y, en su lugar, seguir este patrón de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="16df9-146">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="16df9-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="16df9-147">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
