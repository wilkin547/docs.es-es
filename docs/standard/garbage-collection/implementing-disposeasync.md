---
title: Implementación de un método DisposeAsync
description: ''
author: IEvangelist
ms.author: dapine
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 31c4cc9136862551e02fae030e38ebd6c2916a38
ms.sourcegitcommit: 4ad2f8920251f3744240c3b42a443ffbe0a46577
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2020
ms.locfileid: "86100930"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="7d0ec-102">Implementación de un método DisposeAsync</span><span class="sxs-lookup"><span data-stu-id="7d0ec-102">Implement a DisposeAsync method</span></span>

<span data-ttu-id="7d0ec-103">La interfaz <xref:System.IAsyncDisposable?displayProperty=nameWithType> se presentó como parte de C# 8.0.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-103">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="7d0ec-104">El método <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> se implementa cuando se necesita realizar una limpieza de recursos, tal como se haría a la hora de [implementar un método Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-104">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="7d0ec-105">Sin embargo, una de las principales diferencias es que esta implementación permite operaciones de limpieza asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-105">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="7d0ec-106">El elemento <xref:System.IAsyncDisposable.DisposeAsync> devuelve un elemento <xref:System.Threading.Tasks.ValueTask> que representa la operación de eliminación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-106">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="7d0ec-107">Resulta habitual que, al implementar la interfaz <xref:System.IAsyncDisposable>, las clases también implementen la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-107">It is typical that when implementing the <xref:System.IAsyncDisposable> interface, classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="7d0ec-108">Debe prepararse un buen patrón de implementación de la interfaz <xref:System.IAsyncDisposable> para la eliminación sincrónica o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-108">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="7d0ec-109">Todas las instrucciones para implementar el patrón de eliminación se aplican a la implementación asincrónica.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-109">All of the guidance for implementing the dispose pattern applies to the asynchronous implementation.</span></span> <span data-ttu-id="7d0ec-110">En este artículo se supone que ya se ha familiarizado con el modo de [implementar un método Dispose](implementing-dispose.md).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-110">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="7d0ec-111">DisposeAsync() y DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="7d0ec-111">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="7d0ec-112">La interfaz <xref:System.IAsyncDisposable> declara un único método sin parámetros: <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-112">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="7d0ec-113">Cualquier clase no sellada debe tener un método `DisposeAsyncCore()` adicional que también devuelva un elemento <xref:System.Threading.Tasks.ValueTask>.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-113">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="7d0ec-114">Una implementación de <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> `public` que no tenga parámetros.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-114">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="7d0ec-115">Un método `protected virtual ValueTask DisposeAsyncCore()` cuya signatura sea:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-115">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

<span data-ttu-id="7d0ec-116">El método `DisposeAsyncCore()` es `virtual` para que las clases derivadas puedan definir la limpieza adicional en sus invalidaciones.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-116">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

### <a name="the-disposeasync-method"></a><span data-ttu-id="7d0ec-117">El método DisposeAsync()</span><span class="sxs-lookup"><span data-stu-id="7d0ec-117">The DisposeAsync() method</span></span>

<span data-ttu-id="7d0ec-118">Se llama de forma implícita al método `DisposeAsync()` sin parámetros `public` en una instrucción `await using`, y su propósito consiste en liberar recursos no administrados, realizar una limpieza general e indicar que el finalizador, si existe, no necesita ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, needn't run.</span></span> <span data-ttu-id="7d0ec-119">La liberación de la memoria asociada a un objeto administrado siempre corresponde al [recolector de elementos no utilizados](index.md).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="7d0ec-120">Debido a esto, se realiza una implementación estándar:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="7d0ec-121">Una diferencia principal en el patrón de eliminación asincrónica en comparación con el patrón de eliminación es que la llamada desde <xref:System.IAsyncDisposable.DisposeAsync> al método de sobrecarga `Dispose(bool)` recibe el valor `false` como argumento.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="7d0ec-122">Sin embargo, al implementar el método <xref:System.IDisposable.Dispose?displayProperty=nameWithType>, se pasa el valor `true`.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="7d0ec-123">Esto ayuda a garantizar la equivalencia funcional con el patrón de eliminación sincrónico y garantiza aún más que se invoquen las rutas de acceso al código finalizador.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="7d0ec-124">En otras palabras, el método `DisposeAsyncCore()` eliminará los recursos administrados de forma asincrónica, por lo que no querrá eliminarlos también de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="7d0ec-125">Por tanto, llame a `Dispose(false)` en lugar de a `Dispose(true)`.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="7d0ec-126">Implementación del patrón de eliminación asincrónica</span><span class="sxs-lookup"><span data-stu-id="7d0ec-126">Implement the async dispose pattern</span></span>

<span data-ttu-id="7d0ec-127">Todas las clases no selladas deben considerarse una clase base potencial, ya que se podrían heredar.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-127">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="7d0ec-128">Cuando se implementa el patrón de eliminación asincrónica para cualquier clase base potencial, se debe proporcionar el método `protected virtual ValueTask DisposeAsyncCore()`.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-128">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="7d0ec-129">Este es un ejemplo de implementación del patrón de eliminación asincrónica que usa un elemento <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-129">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="7d0ec-130">En el ejemplo anterior se usaba el elemento <xref:System.Text.Json.Utf8JsonWriter>. Para obtener más información sobre `System.Text.Json`, consulte [migración de Newtonsoft.Json a System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-130">The previous example used the <xref:System.Text.Json.Utf8JsonWriter>, for more information on `System.Text.Json`, see, [migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="7d0ec-131">Uso de la eliminación asincrónica</span><span class="sxs-lookup"><span data-stu-id="7d0ec-131">Using async disposable</span></span>

<span data-ttu-id="7d0ec-132">Para usar correctamente un objeto que implementa la interfaz <xref:System.IAsyncDisposable>, utilice las palabras clave [await](../../csharp/language-reference/operators/await.md) y [using](../../csharp/language-reference/keywords/using.md) juntas.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-132">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using.md) keywords together.</span></span> <span data-ttu-id="7d0ec-133">Tenga en cuenta el ejemplo siguiente, donde se crea una instancia de la clase `ExampleAsyncDisposable` y, a continuación, se encapsula en una instrucción `await using`.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-133">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated, then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="7d0ec-134">Use el método de extensión <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> de la interfaz <xref:System.IAsyncDisposable> para configurar el modo en que se serializa la continuación de la tarea en su contexto o programador original.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-134">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="7d0ec-135">Para obtener más información sobre `ConfigureAwait`, consulte las [preguntas más frecuentes sobre ConfigureAwait](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-135">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="7d0ec-136">En situaciones en las que no se necesita el uso de `ConfigureAwait`, la instrucción `await using` se podría simplificar de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-136">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="7d0ec-137">Además, se podría escribir para utilizar el ámbito implícito de una [declaración "using"](../../csharp/whats-new/csharp-8.md#using-declarations).</span><span class="sxs-lookup"><span data-stu-id="7d0ec-137">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="7d0ec-138">Declaraciones "using" apiladas</span><span class="sxs-lookup"><span data-stu-id="7d0ec-138">Stacked usings</span></span>

<span data-ttu-id="7d0ec-139">En situaciones en las que se crean y se utilizan varios objetos que implementan <xref:System.IAsyncDisposable>, es posible que el apilamiento de instrucciones `using` en condiciones errantes pudiera impedir la realización de llamadas a <xref:System.IAsyncDisposable.DisposeAsync>.</span><span class="sxs-lookup"><span data-stu-id="7d0ec-139">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="7d0ec-140">Para ayudar a evitar un posible problema, debe evitar el apilamiento y, en su lugar, seguir este patrón de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7d0ec-140">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="7d0ec-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d0ec-141">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
