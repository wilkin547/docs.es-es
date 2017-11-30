---
title: "Patrón de eventos actualizado de .NET Core"
description: "Obtenga información sobre cómo el patrón de eventos de .NET Core permite la flexibilidad con la compatibilidad con versiones anteriores y cómo implementar un procesamiento de eventos seguro con suscriptores asincrónicos."
keywords: .NET, .NET Core
author: BillWagner
ms.author: wiwagn
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: cf69cbe0a7adbd274d1cb9e9544dda77d9fa1740
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="the-updated-net-core-event-pattern"></a><span data-ttu-id="db056-104">Patrón de eventos actualizado de .NET Core</span><span class="sxs-lookup"><span data-stu-id="db056-104">The Updated .NET Core Event Pattern</span></span>

[<span data-ttu-id="db056-105">Anterior</span><span class="sxs-lookup"><span data-stu-id="db056-105">Previous</span></span>](event-pattern.md)

<span data-ttu-id="db056-106">En el artículo anterior se describían los patrones de eventos más comunes.</span><span class="sxs-lookup"><span data-stu-id="db056-106">The previous article discussed the most common event patterns.</span></span> <span data-ttu-id="db056-107">.NET Core tiene un patrón menos estricto.</span><span class="sxs-lookup"><span data-stu-id="db056-107">.NET Core has a more relaxed pattern.</span></span> <span data-ttu-id="db056-108">En esta versión, la definición `EventHandler<TEventArgs>` ya no tiene la restricción que obliga a que `TEventArgs` sea una clase derivada de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="db056-108">In this version, the `EventHandler<TEventArgs>` definition no longer has the constraint that `TEventArgs` must be a class derived from `System.EventArgs`.</span></span>

<span data-ttu-id="db056-109">Esto aumenta la flexibilidad y es compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="db056-109">This increases flexibility for you, and is backwards compatible.</span></span> <span data-ttu-id="db056-110">Comencemos con la flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="db056-110">Let's start with the flexibility.</span></span> <span data-ttu-id="db056-111">La clase System.EventArgs introduce un método, `MemberwiseClone()`, que crea una copia superficial del objeto.</span><span class="sxs-lookup"><span data-stu-id="db056-111">The class System.EventArgs introduces one method: `MemberwiseClone()`, which creates a shallow copy of the object.</span></span>
<span data-ttu-id="db056-112">Dicho método debe usar la reflexión para implementar su función en cualquier clase derivada de `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="db056-112">That method must use reflection in order to implement its functionality for any class derived from `EventArgs`.</span></span> <span data-ttu-id="db056-113">Esta funcionalidad es más fácil de crear en una clase derivada concreta.</span><span class="sxs-lookup"><span data-stu-id="db056-113">That functionality is easier to create in a specific derived class.</span></span> <span data-ttu-id="db056-114">Esto significa que derivar de System.EventArgs es una restricción que limita los diseños, pero no proporciona ninguna ventaja adicional.</span><span class="sxs-lookup"><span data-stu-id="db056-114">That effectively means that deriving from System.EventArgs is a constraint that limits your designs, but does not provide any additional benefit.</span></span>
<span data-ttu-id="db056-115">De hecho, puede cambiar las definiciones de `FileFoundArgs` y `SearchDirectoryArgs` para que no deriven de `EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="db056-115">In fact, you can changes the definitions of `FileFoundArgs` and `SearchDirectoryArgs` so that they do not derive from `EventArgs`.</span></span>
<span data-ttu-id="db056-116">El programa funcionará exactamente igual.</span><span class="sxs-lookup"><span data-stu-id="db056-116">The program will work exactly the same.</span></span>

<span data-ttu-id="db056-117">También puede cambiar `SearchDirectoryArgs` a un struct si realiza un cambio más:</span><span class="sxs-lookup"><span data-stu-id="db056-117">You could also change the `SearchDirectoryArgs` to a struct, if you also make one more change:</span></span>

```csharp  
internal struct SearchDirectoryArgs  
{  
    internal string CurrentSearchDirectory { get; }  
    internal int TotalDirs { get; }  
    internal int CompletedDirs { get; }  
    
    internal SearchDirectoryArgs(string dir, int totalDirs, 
        int completedDirs) : this()  
    {  
        CurrentSearchDirectory = dir;  
        TotalDirs = totalDirs;  
        CompletedDirs = completedDirs;  
    }  
}  
```   

<span data-ttu-id="db056-118">El cambio adicional consiste en llamar al constructor predeterminado antes de entrar en el constructor que inicializa todos los campos.</span><span class="sxs-lookup"><span data-stu-id="db056-118">The additional change is to call the default constructor before entering the constructor that initializes all the fields.</span></span> <span data-ttu-id="db056-119">Sin esta adición, las reglas de C# informarán de que se está teniendo acceso a las propiedades antes de que se hayan asignado.</span><span class="sxs-lookup"><span data-stu-id="db056-119">Without that addition, the rules of C# would report that the properties are being accessed before they have been assigned.</span></span>

<span data-ttu-id="db056-120">No debe cambiar `FileFoundArgs` de una clase (tipo de referencia) a un struct (tipo de valor).</span><span class="sxs-lookup"><span data-stu-id="db056-120">You should not change the `FileFoundArgs` from a class (reference type) to a struct (value type).</span></span> <span data-ttu-id="db056-121">Esto se debe a que el protocolo para controlar la cancelación requiere que los argumentos de evento se pasen por referencia.</span><span class="sxs-lookup"><span data-stu-id="db056-121">That's because the protocol for handling cancel requires that the event arguments are passed by reference.</span></span> <span data-ttu-id="db056-122">Si realizase el mismo cambio, la clase de búsqueda de archivos no podría observar nunca los cambios realizados por ninguno de los suscriptores de eventos.</span><span class="sxs-lookup"><span data-stu-id="db056-122">If you made the same change, the file search class could never observe any changes made by any of the event subscribers.</span></span> <span data-ttu-id="db056-123">Se usaría una nueva copia de la estructura para cada suscriptor, y dicha copia sería diferente de la que ve el objeto de búsqueda de archivos.</span><span class="sxs-lookup"><span data-stu-id="db056-123">A new copy of the structure would be used for each subscriber, and that copy would be a different copy than the one seen by the file search object.</span></span>

<span data-ttu-id="db056-124">Ahora veamos cómo este cambio puede ser compatible con versiones anteriores.</span><span class="sxs-lookup"><span data-stu-id="db056-124">Next, let's consider how this change can be backwards compatible.</span></span>
<span data-ttu-id="db056-125">La eliminación de la restricción no afecta al código existente.</span><span class="sxs-lookup"><span data-stu-id="db056-125">The removal of the constraint does not affect any existing code.</span></span> <span data-ttu-id="db056-126">Los tipos de argumento de evento existentes siguen derivando de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="db056-126">Any existing event argument types do still derive from `System.EventArgs`.</span></span>
<span data-ttu-id="db056-127">La compatibilidad con versiones anteriores es uno de los motivos principales por los que siguen derivando de `System.EventArgs`.</span><span class="sxs-lookup"><span data-stu-id="db056-127">Backwards compatibility is one major reason why they will continue to derive from `System.EventArgs`.</span></span> <span data-ttu-id="db056-128">Los suscriptores de eventos existentes serán suscriptores a un evento que haya seguido el patrón clásico.</span><span class="sxs-lookup"><span data-stu-id="db056-128">Any existing event subscribers will be subscribers to an event that followed the classic pattern.</span></span>

<span data-ttu-id="db056-129">Según una lógica similar, cualquier tipo de argumento de evento creado ahora no tendría ningún suscriptor en el código base existente.</span><span class="sxs-lookup"><span data-stu-id="db056-129">Following similar logic, any event argument type created now would not have any subscribers in any existing codebases.</span></span> <span data-ttu-id="db056-130">Los nuevos tipos de evento que no deriven de `System.EventArgs` no interrumpirán ese código base.</span><span class="sxs-lookup"><span data-stu-id="db056-130">New event types that do not derive from `System.EventArgs` will not break those codebases.</span></span>

## <a name="events-with-async-subscribers"></a><span data-ttu-id="db056-131">Eventos con suscriptores Async</span><span class="sxs-lookup"><span data-stu-id="db056-131">Events with Async subscribers</span></span>

<span data-ttu-id="db056-132">Todavía debe aprender un último patrón: cómo escribir correctamente suscriptores de eventos que llaman a código asincrónico.</span><span class="sxs-lookup"><span data-stu-id="db056-132">You have one final pattern to learn: How to correctly write event subscribers that call async code.</span></span> <span data-ttu-id="db056-133">Este reto se describe en el artículo sobre [async y await](async.md).</span><span class="sxs-lookup"><span data-stu-id="db056-133">The challenge is described in the article on [async and await](async.md).</span></span> <span data-ttu-id="db056-134">Los métodos asincrónicos pueden tener un tipo de valor devuelto void, pero esto no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="db056-134">Async methods can have a void return type, but that is strongly discouraged.</span></span> <span data-ttu-id="db056-135">Cuando el código de suscriptor de eventos llama a un método asincrónico, no le queda otra opción que crear un método `async void`,</span><span class="sxs-lookup"><span data-stu-id="db056-135">When your event subscriber code calls an async method, you have no choice but to create an `async void` method.</span></span> <span data-ttu-id="db056-136">ya que lo requiere la firma del controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="db056-136">The event handler signature requires it.</span></span>

<span data-ttu-id="db056-137">Debe conciliar estas instrucciones contradictorias.</span><span class="sxs-lookup"><span data-stu-id="db056-137">You need to reconcile this opposing guidance.</span></span> <span data-ttu-id="db056-138">De alguna manera, debe crear un método `async void` seguro.</span><span class="sxs-lookup"><span data-stu-id="db056-138">Somehow, you must create a safe `async void` method.</span></span> <span data-ttu-id="db056-139">A continuación se muestran los aspectos básicos del patrón que debe implementar:</span><span class="sxs-lookup"><span data-stu-id="db056-139">The basics of the pattern you need to implement are below:</span></span>

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

<span data-ttu-id="db056-140">En primer lugar, observe que el controlador está marcado como un controlador asincrónico.</span><span class="sxs-lookup"><span data-stu-id="db056-140">First, notice that the handler is marked as an async handler.</span></span> <span data-ttu-id="db056-141">Dado que se va a asignar a un tipo de delegado de controlador de eventos, tendrá un tipo de valor devuelto void.</span><span class="sxs-lookup"><span data-stu-id="db056-141">Because it is being assigned to an event handler delegate type, it will have a void return type.</span></span> <span data-ttu-id="db056-142">Esto significa que debe seguir el patrón que se muestra en el controlador y no debe permitir que se produzca ninguna excepción fuera del contexto del controlador asincrónico.</span><span class="sxs-lookup"><span data-stu-id="db056-142">That means you must follow the pattern shown in the handler, and not allow any exceptions to be thrown out of the context of the async handler.</span></span> <span data-ttu-id="db056-143">Como no devuelve una tarea, no hay ninguna tarea que pueda notificar el error entrando en el estado de error.</span><span class="sxs-lookup"><span data-stu-id="db056-143">Because it does not return a task, there is no task that can report the error by entering the faulted state.</span></span> <span data-ttu-id="db056-144">Dado que el método es asincrónico, no puede producir la excepción.</span><span class="sxs-lookup"><span data-stu-id="db056-144">Because the method is async, the method can't simply throw the exception.</span></span> <span data-ttu-id="db056-145">(El método de llamada ha continuado con la ejecución porque es `async`). El comportamiento real en tiempo de ejecución se definirá de forma diferente para diferentes entornos.</span><span class="sxs-lookup"><span data-stu-id="db056-145">(The calling method has continued execution because it is `async`.) The actual runtime behavior will be defined differently for different environments.</span></span> <span data-ttu-id="db056-146">Puede finalizar el subproceso, finalizar el programa o dejar el programa en un estado indeterminado.</span><span class="sxs-lookup"><span data-stu-id="db056-146">It may terminate the thread, it may terminate the program, or it may leave the program in an undetermined state.</span></span> <span data-ttu-id="db056-147">Ninguno de estos resultados es bueno.</span><span class="sxs-lookup"><span data-stu-id="db056-147">None of those are good outcomes.</span></span>

<span data-ttu-id="db056-148">Por eso debe encapsular la instrucción await para la tarea asincrónica en su propio bloque try.</span><span class="sxs-lookup"><span data-stu-id="db056-148">That's why you should wrap the await statement for the async Task in your own try block.</span></span> <span data-ttu-id="db056-149">Si esto genera una tarea con error, puede registrar el error.</span><span class="sxs-lookup"><span data-stu-id="db056-149">If it does cause a faulted task, you can log the error.</span></span> <span data-ttu-id="db056-150">Si se produce un error del que no se puede recuperar la aplicación, puede salir del programa de forma rápida y correctamente.</span><span class="sxs-lookup"><span data-stu-id="db056-150">If it is an error from which your application cannot recover, you can exit the program quickly and gracefully</span></span>

<span data-ttu-id="db056-151">Estas son las principales actualizaciones del patrón de eventos de .NET.</span><span class="sxs-lookup"><span data-stu-id="db056-151">Those are the major updates to the .NET event pattern.</span></span> <span data-ttu-id="db056-152">Verá numerosos ejemplos de las versiones anteriores de las bibliotecas con las que trabaje.</span><span class="sxs-lookup"><span data-stu-id="db056-152">You will see many examples of the earlier versions in the libraries you work with.</span></span> <span data-ttu-id="db056-153">Aun así, también debe entender los patrones más recientes.</span><span class="sxs-lookup"><span data-stu-id="db056-153">However, you should understand what the latest patterns are as well.</span></span>

<span data-ttu-id="db056-154">El siguiente artículo de esta serie le ayudará a distinguir entre el uso de `delegates` y `events` en los diseños.</span><span class="sxs-lookup"><span data-stu-id="db056-154">The next article in this series helps you distinguish between using `delegates` and `events` in your designs.</span></span> <span data-ttu-id="db056-155">Dado que se trata de conceptos similares, el artículo le ayudará a tomar la mejor decisión para sus programas.</span><span class="sxs-lookup"><span data-stu-id="db056-155">They are similar concepts, and that article will help you make the best decision for your programs.</span></span>

[<span data-ttu-id="db056-156">Siguiente</span><span class="sxs-lookup"><span data-stu-id="db056-156">Next</span></span>](distinguish-delegates-events.md)
