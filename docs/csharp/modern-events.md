---
title: Patrón de eventos actualizado de .NET Core
description: Obtenga información sobre cómo el patrón de eventos de .NET Core permite la flexibilidad con la compatibilidad con versiones anteriores y cómo implementar un procesamiento de eventos seguro con suscriptores asincrónicos.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: c8858158ede761db8a3002beb26e521880f77feb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170441"
---
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="5e6cf-103">Patrón de eventos actualizado de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5e6cf-103">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="5e6cf-104">Anterior</span><span class="sxs-lookup"><span data-stu-id="5e6cf-104">Previous</span></span>](event-pattern.md)

<span data-ttu-id="5e6cf-105">En el artículo anterior se describían los patrones de eventos más comunes.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-105">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="5e6cf-106">.NET Core tiene un patrón menos estricto.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-106">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="5e6cf-107">En esta versión, la definición `EventHandler<TEventArgs>` ya no tiene la restricción que obliga a que `TEventArgs` sea una clase derivada de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-107">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="5e6cf-108">Esto aumenta la flexibilidad y es compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-108">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="5e6cf-109">Comencemos con la flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-109">Let's start with the flexibility.</span></span> <span data-ttu-id="5e6cf-110">La clase System.EventArgs introduce un método, `MemberwiseClone()`, que crea una copia superficial del objeto.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-110">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="5e6cf-111">Dicho método debe usar la reflexión para implementar su función en cualquier clase derivada de `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-111">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="5e6cf-112">Esta funcionalidad es más fácil de crear en una clase derivada concreta.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-112">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="5e6cf-113">Esto significa que derivar de System.EventArgs es una restricción que limita los diseños, pero no proporciona ninguna ventaja adicional.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-113">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="5e6cf-114">De hecho, puede cambiar las definiciones de `FileFoundArgs` y `SearchDirectoryArgs` para que no deriven de `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-114">In fact, you can change the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="5e6cf-115">El programa funcionará exactamente igual.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-115">The program will work exactly the same.</span></span>

<span data-ttu-id="5e6cf-116">También puede cambiar `SearchDirectoryArgs` a un struct si realiza un cambio más:</span><span class="sxs-lookup"><span data-stu-id="5e6cf-116">You could also change the `SearchDirectoryArgs` to a struct, if you make one more change:</span></span>

```csharp
internal struct SearchDirectoryArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs) : this()
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
```

<span data-ttu-id="5e6cf-117">El cambio adicional consiste en llamar al constructor sin parámetros antes de entrar en el constructor que inicializa todos los campos.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-117">The additional change is to call the parameterless constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="5e6cf-118">Sin esta adición, las reglas de C# informarán de que se está teniendo acceso a las propiedades antes de que se hayan asignado.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-118">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="5e6cf-119">No debe cambiar `FileFoundArgs` de una clase (tipo de referencia) a un struct (tipo de valor).</span><span class="sxs-lookup"><span data-stu-id="5e6cf-119">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="5e6cf-120">Esto se debe a que el protocolo para controlar la cancelación requiere que los argumentos de evento se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-120">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="5e6cf-121">Si realizase el mismo cambio, la clase de búsqueda de archivos no podría observar nunca los cambios realizados por ninguno de los suscriptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-121">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="5e6cf-122">Se usaría una nueva copia de la estructura para cada suscriptor, y dicha copia sería diferente de la que ve el objeto de búsqueda de archivos.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-122">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="5e6cf-123">Ahora veamos cómo este cambio puede ser compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-123">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="5e6cf-124">La eliminación de la restricción no afecta al código existente.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-124">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="5e6cf-125">Los tipos de argumento de evento existentes siguen derivando de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-125">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="5e6cf-126">La compatibilidad con versiones anteriores es uno de los motivos principales por los que siguen derivando de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-126">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="5e6cf-127">Los suscriptores de eventos existentes serán suscriptores a un evento que haya seguido el patrón clásico.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-127">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="5e6cf-128">Según una lógica similar, cualquier tipo de argumento de evento creado ahora no tendría ningún suscriptor en el código base existente.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-128">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="5e6cf-129">Los nuevos tipos de evento que no deriven de `System.EventArgs` no interrumpirán ese código base.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-129">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="5e6cf-130">Eventos con suscriptores Async</span><span class="sxs-lookup"><span data-stu-id="5e6cf-130">Events with Async subscribers</span></span>

<span data-ttu-id="5e6cf-131">Le queda un último patrón que aprender: Cómo escribir correctamente suscriptores de eventos que llaman a código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-131">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="5e6cf-132">Este reto se describe en el artículo sobre [async y await](async.md).</span><span class="sxs-lookup"><span data-stu-id="5e6cf-132">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="5e6cf-133">Los métodos asincrónicos pueden tener un tipo de valor devuelto void, pero esto no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-133">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="5e6cf-134">Cuando el código de suscriptor de eventos llama a un método asincrónico, no le queda otra opción que crear un método `async void`,</span><span class="sxs-lookup"><span data-stu-id="5e6cf-134">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="5e6cf-135">ya que lo requiere la firma del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-135">The event handler signature requires it.</span></span>

<span data-ttu-id="5e6cf-136">Debe conciliar estas instrucciones contradictorias.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-136">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="5e6cf-137">De alguna manera, debe crear un método `async void` seguro.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-137">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="5e6cf-138">A continuación se muestran los aspectos básicos del patrón que debe implementar:</span><span class="sxs-lookup"><span data-stu-id="5e6cf-138">The basics of the pattern you need to implement are below:</span></span>

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

<span data-ttu-id="5e6cf-139">En primer lugar, observe que el controlador está marcado como un controlador asincrónico.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-139">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="5e6cf-140">Dado que se va a asignar a un tipo de delegado de controlador de eventos, tendrá un tipo de valor devuelto void.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-140">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="5e6cf-141">Esto significa que debe seguir el patrón que se muestra en el controlador y no debe permitir que se produzca ninguna excepción fuera del contexto del controlador asincrónico.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-141">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="5e6cf-142">Como no devuelve una tarea, no hay ninguna tarea que pueda notificar el error entrando en el estado de error.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-142">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="5e6cf-143">Dado que el método es asincrónico, no puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-143">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="5e6cf-144">(El método de llamada ha continuado con la ejecución porque es `async`). El comportamiento real en tiempo de ejecución se definirá de forma diferente para diferentes entornos.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-144">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="5e6cf-145">Se puede terminar el subproceso o el proceso que posee el subproceso, o dejar el proceso en un estado indeterminado.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-145">It may terminate the thread or the process that owns the thread, or leave the process in an indeterminate state.</span></span> <span data-ttu-id="5e6cf-146">Todas estas salidas potenciales son altamente no deseables.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-146">All of these potential outcomes are highly undesirable.</span></span>

<span data-ttu-id="5e6cf-147">Por eso debe encapsular la instrucción await para la tarea asincrónica en su propio bloque try.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-147">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="5e6cf-148">Si esto genera una tarea con error, puede registrar el error.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-148">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="5e6cf-149">Si se produce un error del que no se puede recuperar la aplicación, puede salir del programa de forma rápida y correctamente.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-149">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="5e6cf-150">Estas son las principales actualizaciones del patrón de eventos de .NET.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-150">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="5e6cf-151">Verá numerosos ejemplos de las versiones anteriores de las bibliotecas con las que trabaje.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-151">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="5e6cf-152">Aun así, también debe entender los patrones más recientes.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-152">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="5e6cf-153">El siguiente artículo de esta serie le ayudará a distinguir entre el uso de `delegates` y `events` en los diseños.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-153">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="5e6cf-154">Dado que se trata de conceptos similares, el artículo le ayudará a tomar la mejor decisión para sus programas.</span><span class="sxs-lookup"><span data-stu-id="5e6cf-154">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="5e6cf-155">Siguiente</span><span class="sxs-lookup"><span data-stu-id="5e6cf-155">Next</span></span>](distinguish-delegates-events.md)
