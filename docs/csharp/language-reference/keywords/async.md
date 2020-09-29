---
description: 'async: Referencia de C#'
title: 'async: Referencia de C#'
ms.date: 05/22/2017
f1_keywords:
- async_CSharpKeyword
helpviewer_keywords:
- async keyword [C#]
- async method [C#]
- async [C#]
ms.assetid: 16f14f09-b2ce-42c7-a875-e4eca5d50674
ms.openlocfilehash: 78079d9940ea5363215411acea6b9ca269ff3ae1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160546"
---
# <a name="async-c-reference"></a><span data-ttu-id="ff38d-103">async (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ff38d-103">async (C# Reference)</span></span>

<span data-ttu-id="ff38d-104">Use el modificador `async` para especificar que un método, una [expresión lambda](../operators/lambda-expressions.md) o un [método anónimo](../operators/delegate-operator.md) es asincrónico.</span><span class="sxs-lookup"><span data-stu-id="ff38d-104">Use the `async` modifier to specify that a method, [lambda expression](../operators/lambda-expressions.md), or [anonymous method](../operators/delegate-operator.md) is asynchronous.</span></span> <span data-ttu-id="ff38d-105">Si usa este modificador en un método o una expresión, se hace referencia al mismo como un *método asincrónico*.</span><span class="sxs-lookup"><span data-stu-id="ff38d-105">If you use this modifier on a method or expression, it's referred to as an *async method*.</span></span> <span data-ttu-id="ff38d-106">En el ejemplo siguiente se define un método asincrónico denominado `ExampleMethodAsync`:</span><span class="sxs-lookup"><span data-stu-id="ff38d-106">The following example defines an async method named `ExampleMethodAsync`:</span></span>

```csharp
public async Task<int> ExampleMethodAsync()
{
    //...
}
```

<span data-ttu-id="ff38d-107">Si no está familiarizado con la programación asincrónica o no entiende cómo un método asincrónico usa el [operador `await`](../operators/await.md) para hacer el trabajo de larga duración sin bloquear el subproceso del autor de la llamada, lea la introducción de [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-107">If you're new to asynchronous programming or do not understand how an async method uses the [`await` operator](../operators/await.md) to do potentially long-running work without blocking the caller's thread, read the introduction in [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="ff38d-108">El siguiente código se encuentra dentro de un método asincrónico y llama al método <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="ff38d-108">The following code is found inside an async method and calls the <xref:System.Net.Http.HttpClient.GetStringAsync%2a?displayProperty=nameWithType> method:</span></span>

```csharp
string contents = await httpClient.GetStringAsync(requestUrl);
```

<span data-ttu-id="ff38d-109">Un método asincrónico se ejecuta sincrónicamente hasta alcanzar la primera expresión `await`, en la que se suspende el método hasta que se complete la tarea en espera.</span><span class="sxs-lookup"><span data-stu-id="ff38d-109">An async method runs synchronously until it reaches its first `await` expression, at which point the method is suspended until the awaited task is complete.</span></span> <span data-ttu-id="ff38d-110">Mientras tanto, el control vuelve al llamador del método, como se muestra en el ejemplo de la sección siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff38d-110">In the meantime, control returns to the caller of the method, as the example in the next section shows.</span></span>

<span data-ttu-id="ff38d-111">Si el método que la palabra clave `async` modifica no contiene una expresión o instrucción `await`, el método se ejecuta de forma sincrónica.</span><span class="sxs-lookup"><span data-stu-id="ff38d-111">If the method that the `async` keyword modifies doesn't contain an `await` expression or statement, the method executes synchronously.</span></span> <span data-ttu-id="ff38d-112">Una advertencia del compilador alerta de cualquier método asincrónico que no contenga instrucciones de `await`, porque esa situación podría indicar un error.</span><span class="sxs-lookup"><span data-stu-id="ff38d-112">A compiler warning alerts you to any async methods that don't contain `await` statements, because that situation might indicate an error.</span></span> <span data-ttu-id="ff38d-113">Vea [Advertencia del compilador (nivel 1) CS4014](../compiler-messages/cs4014.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-113">See [Compiler Warning (level 1) CS4014](../compiler-messages/cs4014.md).</span></span>

 <span data-ttu-id="ff38d-114">La palabra clave `async` es contextual en el sentido de que es una palabra clave cuando modifica un método, una expresión lambda o un método anónimo.</span><span class="sxs-lookup"><span data-stu-id="ff38d-114">The `async` keyword is contextual in that it's a keyword only when it modifies a method, a lambda expression, or an anonymous method.</span></span> <span data-ttu-id="ff38d-115">En todos los demás contextos, se interpreta como identificador.</span><span class="sxs-lookup"><span data-stu-id="ff38d-115">In all other contexts, it's interpreted as an identifier.</span></span>

## <a name="example"></a><span data-ttu-id="ff38d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff38d-116">Example</span></span>

<span data-ttu-id="ff38d-117">En el ejemplo siguiente se muestra la estructura y el flujo de control entre un controlador de eventos asincrónicos, `StartButton_Click`, y un método asincrónico, `ExampleMethodAsync`.</span><span class="sxs-lookup"><span data-stu-id="ff38d-117">The following example shows the structure and flow of control between an async event handler, `StartButton_Click`, and an async method, `ExampleMethodAsync`.</span></span> <span data-ttu-id="ff38d-118">El resultado del método asincrónico es el número de caracteres de una página web.</span><span class="sxs-lookup"><span data-stu-id="ff38d-118">The result from the async method is the number of characters of a web page.</span></span> <span data-ttu-id="ff38d-119">El código es adecuado para una aplicación Windows Presentation Foundation (WPF) o de la Tienda Windows creada en Visual Studio; vea los comentarios del código para configurar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff38d-119">The code is suitable for a Windows Presentation Foundation (WPF) app or Windows Store app that you create in Visual Studio; see the code comments for setting up the app.</span></span>

<span data-ttu-id="ff38d-120">Puede ejecutar este código en Visual Studio como una aplicación Windows Presentation Foundation (WPF) o una aplicación de la Tienda Windows.</span><span class="sxs-lookup"><span data-stu-id="ff38d-120">You can run this code in Visual Studio as a Windows Presentation Foundation (WPF) app or a Windows Store app.</span></span> <span data-ttu-id="ff38d-121">Necesita un control de botón denominado `StartButton` y un control de cuadro de texto denominado `ResultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="ff38d-121">You need a Button control named `StartButton` and a Textbox control named `ResultsTextBox`.</span></span> <span data-ttu-id="ff38d-122">Recuerde establecer los nombres y el controlador de manera que tenga algo similar a esto:</span><span class="sxs-lookup"><span data-stu-id="ff38d-122">Remember to set the names and handler so that you have something like this:</span></span>

```xaml
<Button Content="Button" HorizontalAlignment="Left" Margin="88,77,0,0" VerticalAlignment="Top" Width="75"
        Click="StartButton_Click" Name="StartButton"/>
<TextBox HorizontalAlignment="Left" Height="137" Margin="88,140,0,0" TextWrapping="Wrap"
         Text="&lt;Enter a URL&gt;" VerticalAlignment="Top" Width="310" Name="ResultsTextBox"/>
```

<span data-ttu-id="ff38d-123">Para ejecutar el código como una aplicación WPF:</span><span class="sxs-lookup"><span data-stu-id="ff38d-123">To run the code as a WPF app:</span></span>

- <span data-ttu-id="ff38d-124">Pegue este código en la clase `MainWindow` en MainWindow.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="ff38d-124">Paste this code into the `MainWindow` class in MainWindow.xaml.cs.</span></span>
- <span data-ttu-id="ff38d-125">Agregue una referencia a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="ff38d-125">Add a reference to System.Net.Http.</span></span>
- <span data-ttu-id="ff38d-126">Agregue una directiva `using` a System.Net.Http.</span><span class="sxs-lookup"><span data-stu-id="ff38d-126">Add a `using` directive for System.Net.Http.</span></span>

<span data-ttu-id="ff38d-127">Para ejecutar el código como una aplicación de la Tienda Windows:</span><span class="sxs-lookup"><span data-stu-id="ff38d-127">To run the code as a Windows Store app:</span></span>

- <span data-ttu-id="ff38d-128">Pegue este código en la clase `MainPage` en MainPage.xaml.cs.</span><span class="sxs-lookup"><span data-stu-id="ff38d-128">Paste this code into the `MainPage` class in MainPage.xaml.cs.</span></span>
- <span data-ttu-id="ff38d-129">Agregue directivas using para System.Net.Http y System.Threading.Tasks.</span><span class="sxs-lookup"><span data-stu-id="ff38d-129">Add using directives for System.Net.Http and System.Threading.Tasks.</span></span>

[!code-csharp[wpf-async](../../../../samples/snippets/csharp/language-reference/keywords/async/wpf/mainwindow.xaml.cs#1)]

> [!IMPORTANT]
> <span data-ttu-id="ff38d-130">Para obtener más información sobre las tareas y el código que se ejecuta mientras se espera la finalización de una tarea, vea [Programación asincrónica con async y await](../../programming-guide/concepts/async/index.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-130">For more information about tasks and the code that executes while waiting for a task, see [Asynchronous programming with async and await](../../programming-guide/concepts/async/index.md).</span></span> <span data-ttu-id="ff38d-131">Para ver un ejemplo completo de la consola que usa elementos similares, consulte el artículo [Iniciar varias tareas asincrónicas y procesarlas a medida que se completan (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-131">For a full console example that uses similar elements, see [Process asynchronous tasks as they complete (C#)](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).</span></span>

## <a name="return-types"></a><span data-ttu-id="ff38d-132">Tipos de valor devueltos</span><span class="sxs-lookup"><span data-stu-id="ff38d-132">Return Types</span></span>

<span data-ttu-id="ff38d-133">Un método asincrónico puede tener los siguientes tipos de valor devuelto:</span><span class="sxs-lookup"><span data-stu-id="ff38d-133">An async method can have the following return types:</span></span>

- <xref:System.Threading.Tasks.Task>
- <xref:System.Threading.Tasks.Task%601>
- <span data-ttu-id="ff38d-134">[void](../builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-134">[void](../builtin-types/void.md).</span></span> <span data-ttu-id="ff38d-135">Los métodos `async void` no suelen ser recomendables para código que no sea controladores de eventos dado que los autores de la llamada no pueden usar `await` con esos métodos y deben implementar otro mecanismo para informar sobre la finalización correcta o condiciones de error.</span><span class="sxs-lookup"><span data-stu-id="ff38d-135">`async void` methods are generally discouraged for code other than event handlers because callers cannot `await` those methods and must implement a different mechanism to report successful completion or error conditions.</span></span>
- <span data-ttu-id="ff38d-136">A partir de C# 7.0, cualquier tipo que tenga un método `GetAwaiter` accesible.</span><span class="sxs-lookup"><span data-stu-id="ff38d-136">Starting with C# 7.0, any type that has an accessible `GetAwaiter` method.</span></span> <span data-ttu-id="ff38d-137">El tipo `System.Threading.Tasks.ValueTask<TResult>` es una implementación de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="ff38d-137">The `System.Threading.Tasks.ValueTask<TResult>` type is one such implementation.</span></span> <span data-ttu-id="ff38d-138">Está disponible agregando el paquete NuGet `System.Threading.Tasks.Extensions`.</span><span class="sxs-lookup"><span data-stu-id="ff38d-138">It is available by adding the NuGet package `System.Threading.Tasks.Extensions`.</span></span>

<span data-ttu-id="ff38d-139">El método asincrónico no puede declarar ningún parámetro [in](./in-parameter-modifier.md), [ref](./ref.md) o [out](./out-parameter-modifier.md), ni puede tener un [valor devuelto de referencia](../../programming-guide/classes-and-structs/ref-returns.md), pero puede llamar a los métodos que tienen estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="ff38d-139">The async method can't declare any [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md) parameters, nor can it have a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md), but it can call methods that have such parameters.</span></span>

<span data-ttu-id="ff38d-140">Se puede especificar `Task<TResult>` como el tipo de valor devuelto de un método asincrónico si la instrucción [return](./return.md) del método especifica un operando de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="ff38d-140">You specify `Task<TResult>` as the return type of an async method if the [return](./return.md) statement of the method specifies an operand of type `TResult`.</span></span> <span data-ttu-id="ff38d-141">Utilice `Task` si no se devuelve ningún valor significativo al completarse el método.</span><span class="sxs-lookup"><span data-stu-id="ff38d-141">You use `Task` if no meaningful value is returned when the method is completed.</span></span> <span data-ttu-id="ff38d-142">Es decir, una llamada al método devuelve `Task`, pero cuando se completa `Task`, las expresiones `await` que esperan a que `Task` finalice se evalúan como `void`.</span><span class="sxs-lookup"><span data-stu-id="ff38d-142">That is, a call to the method returns a `Task`, but when the `Task` is completed, any `await` expression that's awaiting the `Task` evaluates to `void`.</span></span>

<span data-ttu-id="ff38d-143">El tipo devuelto `void` se utiliza principalmente para definir controladores de eventos, que requieren ese tipo devuelto.</span><span class="sxs-lookup"><span data-stu-id="ff38d-143">You use the `void` return type primarily to define event handlers, which require that return type.</span></span> <span data-ttu-id="ff38d-144">El llamador de un método asincrónico que devuelva `void` no puede esperar a que finalice y no puede detectar las excepciones que el método inicia.</span><span class="sxs-lookup"><span data-stu-id="ff38d-144">The caller of a `void`-returning async method can't await it and can't catch exceptions that the method throws.</span></span>

<span data-ttu-id="ff38d-145">A partir de C# 7.0, devuelve otro tipo, normalmente un tipo de valor, que tiene un método `GetAwaiter` para minimizar las asignaciones de memoria en secciones críticas de rendimiento del código.</span><span class="sxs-lookup"><span data-stu-id="ff38d-145">Starting with C# 7.0, you return another type, typically a value type, that has a `GetAwaiter` method to minimize memory allocations in performance-critical sections of code.</span></span>

<span data-ttu-id="ff38d-146">Para más información y ejemplos, vea [Tipos de valor devueltos asincrónicos](../../programming-guide/concepts/async/async-return-types.md).</span><span class="sxs-lookup"><span data-stu-id="ff38d-146">For more information and examples, see [Async Return Types](../../programming-guide/concepts/async/async-return-types.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff38d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff38d-147">See also</span></span>

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [<span data-ttu-id="ff38d-148">await</span><span class="sxs-lookup"><span data-stu-id="ff38d-148">await</span></span>](../operators/await.md)
- [<span data-ttu-id="ff38d-149">Programación asincrónica con async y await</span><span class="sxs-lookup"><span data-stu-id="ff38d-149">Asynchronous programming with async and await</span></span>](../../programming-guide/concepts/async/index.md)
- [<span data-ttu-id="ff38d-150">Procesamiento de tareas asincrónicas a medida que se completan</span><span class="sxs-lookup"><span data-stu-id="ff38d-150">Process asynchronous tasks as they complete</span></span>](../../programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)
