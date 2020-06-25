---
title: Finalizadores - Guía de programación de C#
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 62fc531a8064a8a5cb144a89aa9975b3199db976
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990120"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="8f343-102">Finalizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8f343-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="8f343-103">Los finalizadores (también denominados **destructores**) se usan para realizar cualquier limpieza final necesaria cuando el recolector de elementos no utilizados recopila una instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="8f343-103">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f343-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8f343-104">Remarks</span></span>  
  
- <span data-ttu-id="8f343-105">Los finalizadores no se pueden definir en structs.</span><span class="sxs-lookup"><span data-stu-id="8f343-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="8f343-106">Solo se usan con clases.</span><span class="sxs-lookup"><span data-stu-id="8f343-106">They are only used with classes.</span></span>  
  
- <span data-ttu-id="8f343-107">Una clase solo puede tener un finalizador.</span><span class="sxs-lookup"><span data-stu-id="8f343-107">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="8f343-108">Los finalizadores no se pueden heredar ni sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="8f343-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="8f343-109">No se puede llamar a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="8f343-109">Finalizers cannot be called.</span></span> <span data-ttu-id="8f343-110">Se invocan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8f343-110">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="8f343-111">Un finalizador no permite modificadores ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="8f343-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="8f343-112">Por ejemplo, el siguiente código muestra una declaración de un finalizador para la clase `Car`.</span><span class="sxs-lookup"><span data-stu-id="8f343-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="8f343-113">Un finalizador también puede implementarse como una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="8f343-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="8f343-114">El finalizador llama implícitamente a <xref:System.Object.Finalize%2A> en la clase base del objeto.</span><span class="sxs-lookup"><span data-stu-id="8f343-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="8f343-115">Por lo tanto, una llamada a un finalizador se convierte implícitamente al siguiente código:</span><span class="sxs-lookup"><span data-stu-id="8f343-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
```csharp  
protected override void Finalize()  
{  
    try  
    {  
        // Cleanup statements...  
    }  
    finally  
    {  
        base.Finalize();  
    }  
}  
```  
  
 <span data-ttu-id="8f343-116">Este diseño significa que se realizan llamadas al método `Finalize` de manera recursiva para todas las instancias de la cadena de herencia, desde la más a la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="8f343-116">This design means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8f343-117">Los finalizadores vacíos no deben usarse.</span><span class="sxs-lookup"><span data-stu-id="8f343-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="8f343-118">Cuando una clase contiene un finalizador, se crea una entrada en la cola `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="8f343-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="8f343-119">Cuando se llama al finalizador, se invoca al recolector de elementos no utilizados para procesar la cola.</span><span class="sxs-lookup"><span data-stu-id="8f343-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="8f343-120">Un finalizador vacío simplemente produce una pérdida de rendimiento innecesaria.</span><span class="sxs-lookup"><span data-stu-id="8f343-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="8f343-121">El programador no puede controlar cuándo se llama al finalizador; es el recolector de elementos no utilizados el que decide cuándo hacerlo.</span><span class="sxs-lookup"><span data-stu-id="8f343-121">The programmer has no control over when the finalizer is called; the garbage collector decides when to call it.</span></span> <span data-ttu-id="8f343-122">El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo usados por ninguna aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f343-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="8f343-123">Si considera un objeto elegible para su finalización, llama al finalizador (si existe) y reclama la memoria usada para almacenar el objeto.</span><span class="sxs-lookup"><span data-stu-id="8f343-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span>

 <span data-ttu-id="8f343-124">En las aplicaciones de .NET Framework (pero no en las de .NET Core), cuando se cierra el programa también se llama a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="8f343-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span>
  
 <span data-ttu-id="8f343-125">Es posible forzar la recolección de elementos no utilizados si se llama a <xref:System.GC.Collect%2A>, pero debe evitarse esta llamada porque puede dar lugar a problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8f343-125">It's possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this call should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="8f343-126">Uso de finalizadores para liberar recursos</span><span class="sxs-lookup"><span data-stu-id="8f343-126">Using finalizers to release resources</span></span>  
 <span data-ttu-id="8f343-127">En general, C# no requiere tanta administración de memoria por parte del desarrollador como los lenguajes que no están diseñados para un runtime con recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="8f343-127">In general, C# does not require as much memory management on the part of the developer as languages that don't target a runtime with garbage collection.</span></span> <span data-ttu-id="8f343-128">Esto es debido a que el recolector de elementos no utilizados de .NET administra implícitamente la asignación y liberación de memoria para los objetos.</span><span class="sxs-lookup"><span data-stu-id="8f343-128">This is because the .NET garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="8f343-129">En cambio, cuando la aplicación encapsule recursos no administrados, como ventanas, archivos y conexiones de red, debería usar finalizadores para liberar dichos recursos.</span><span class="sxs-lookup"><span data-stu-id="8f343-129">However, when your application encapsulates unmanaged resources, such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="8f343-130">Cuando el objeto cumple los requisitos para su finalización, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.</span><span class="sxs-lookup"><span data-stu-id="8f343-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="8f343-131">Liberación explícita de recursos</span><span class="sxs-lookup"><span data-stu-id="8f343-131">Explicit release of resources</span></span>  
 <span data-ttu-id="8f343-132">Si la aplicación usa un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto.</span><span class="sxs-lookup"><span data-stu-id="8f343-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="8f343-133">Para liberar el recurso, implemente un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza necesaria del objeto.</span><span class="sxs-lookup"><span data-stu-id="8f343-133">To release the resource, implement a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="8f343-134">Esto puede mejorar considerablemente el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8f343-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="8f343-135">Aun con este control explícito sobre los recursos, el finalizador se convierte en una salvaguarda para limpiar recursos si se produce un error en la llamada al método `Dispose`.</span><span class="sxs-lookup"><span data-stu-id="8f343-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method fails.</span></span>  
  
 <span data-ttu-id="8f343-136">Para obtener más información sobre la limpieza de recursos, vea los siguientes artículos:</span><span class="sxs-lookup"><span data-stu-id="8f343-136">For more information about cleaning up resources, see the following articles:</span></span>  
  
- [<span data-ttu-id="8f343-137">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="8f343-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="8f343-138">Implementación de un método Dispose</span><span class="sxs-lookup"><span data-stu-id="8f343-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="8f343-139">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="8f343-139">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="8f343-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f343-140">Example</span></span>  
 <span data-ttu-id="8f343-141">En el siguiente ejemplo se crean tres clases que forman una cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="8f343-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="8f343-142">La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`.</span><span class="sxs-lookup"><span data-stu-id="8f343-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="8f343-143">Los tres tienen finalizadores.</span><span class="sxs-lookup"><span data-stu-id="8f343-143">All three have finalizers.</span></span> <span data-ttu-id="8f343-144">En `Main`, se crea una instancia de la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="8f343-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="8f343-145">Cuando ejecute el programa, observe que se llama a los finalizadores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="8f343-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="8f343-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8f343-146">C# language specification</span></span>  

<span data-ttu-id="8f343-147">Para más información, vea la sección sobre [destructores](~/_csharplang/spec/classes.md#destructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="8f343-147">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8f343-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f343-148">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="8f343-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8f343-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8f343-150">Constructores</span><span class="sxs-lookup"><span data-stu-id="8f343-150">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="8f343-151">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="8f343-151">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
