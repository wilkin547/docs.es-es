---
title: Finalizadores - Guía de programación de C#
ms.date: 10/08/2018
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
ms.openlocfilehash: 9c00f14da9d79418e4fb204bac30e539b234197f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715015"
---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="6079b-102">Finalizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6079b-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="6079b-103">Los finalizadores (también denominados **destructores**) se usan para realizar cualquier limpieza final necesaria cuando el recolector de elementos no utilizados recopila una instancia de clase.</span><span class="sxs-lookup"><span data-stu-id="6079b-103">Finalizers (which are also called **destructors**) are used to perform any necessary final clean-up when a class instance is being collected by the garbage collector.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6079b-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6079b-104">Remarks</span></span>  
  
- <span data-ttu-id="6079b-105">Los finalizadores no se pueden definir en structs.</span><span class="sxs-lookup"><span data-stu-id="6079b-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="6079b-106">Solo se usan con clases.</span><span class="sxs-lookup"><span data-stu-id="6079b-106">They are only used with classes.</span></span>  
  
- <span data-ttu-id="6079b-107">Una clase solo puede tener un finalizador.</span><span class="sxs-lookup"><span data-stu-id="6079b-107">A class can only have one finalizer.</span></span>  
  
- <span data-ttu-id="6079b-108">Los finalizadores no se pueden heredar ni sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="6079b-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
- <span data-ttu-id="6079b-109">No se puede llamar a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="6079b-109">Finalizers cannot be called.</span></span> <span data-ttu-id="6079b-110">Se invocan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6079b-110">They are invoked automatically.</span></span>  
  
- <span data-ttu-id="6079b-111">Un finalizador no permite modificadores ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="6079b-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="6079b-112">Por ejemplo, el siguiente código muestra una declaración de un finalizador para la clase `Car`.</span><span class="sxs-lookup"><span data-stu-id="6079b-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 [!code-csharp[csProgGuideObjects#86](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#86)]  

<span data-ttu-id="6079b-113">Un finalizador también puede implementarse como una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6079b-113">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  
  
 <span data-ttu-id="6079b-114">El finalizador llama implícitamente a <xref:System.Object.Finalize%2A> en la clase base del objeto.</span><span class="sxs-lookup"><span data-stu-id="6079b-114">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="6079b-115">Por lo tanto, una llamada a un finalizador se convierte implícitamente al siguiente código:</span><span class="sxs-lookup"><span data-stu-id="6079b-115">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="6079b-116">Esto significa que se realizan llamadas al método `Finalize` de manera recursiva para todas las instancias de la cadena de herencia, desde la más a la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="6079b-116">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6079b-117">Los finalizadores vacíos no deben usarse.</span><span class="sxs-lookup"><span data-stu-id="6079b-117">Empty finalizers should not be used.</span></span> <span data-ttu-id="6079b-118">Cuando una clase contiene un finalizador, se crea una entrada en la cola `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="6079b-118">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="6079b-119">Cuando se llama al finalizador, se invoca al recolector de elementos no utilizados para procesar la cola.</span><span class="sxs-lookup"><span data-stu-id="6079b-119">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="6079b-120">Un finalizador vacío simplemente produce una pérdida de rendimiento innecesaria.</span><span class="sxs-lookup"><span data-stu-id="6079b-120">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="6079b-121">El programador no puede controlar cuándo se llama al finalizador, porque esto lo determina el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6079b-121">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="6079b-122">El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo usados por ninguna aplicación.</span><span class="sxs-lookup"><span data-stu-id="6079b-122">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="6079b-123">Si considera un objeto elegible para su finalización, llama al finalizador (si existe) y reclama la memoria usada para almacenar el objeto.</span><span class="sxs-lookup"><span data-stu-id="6079b-123">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> 
 
 <span data-ttu-id="6079b-124">En las aplicaciones de .NET Framework (pero no en las de .NET Core), cuando se cierra el programa también se llama a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="6079b-124">In .NET Framework applications (but not in .NET Core applications), finalizers are also called when the program exits.</span></span> 
  
 <span data-ttu-id="6079b-125">Es posible forzar la recolección de elementos no utilizados llamando a <xref:System.GC.Collect%2A>, pero en general debe evitarse su uso por razones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="6079b-125">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="6079b-126">Uso de finalizadores para liberar recursos</span><span class="sxs-lookup"><span data-stu-id="6079b-126">Using finalizers to release resources</span></span>  
 <span data-ttu-id="6079b-127">En general, C# no requiere tanta administración de memoria como se necesita al desarrollar con un lenguaje que no está diseñado para un runtime con recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="6079b-127">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="6079b-128">Esto es debido a que el recolector de elementos no utilizados de .NET Framework administra implícitamente la asignación y liberación de memoria para los objetos.</span><span class="sxs-lookup"><span data-stu-id="6079b-128">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="6079b-129">En cambio, cuando la aplicación encapsule recursos no administrados como ventanas, archivos y conexiones de red, debería usar finalizadores para liberar dichos recursos.</span><span class="sxs-lookup"><span data-stu-id="6079b-129">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="6079b-130">Cuando el objeto cumple los requisitos para su finalización, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.</span><span class="sxs-lookup"><span data-stu-id="6079b-130">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="6079b-131">Liberación explícita de recursos</span><span class="sxs-lookup"><span data-stu-id="6079b-131">Explicit release of resources</span></span>  
 <span data-ttu-id="6079b-132">Si la aplicación usa un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto.</span><span class="sxs-lookup"><span data-stu-id="6079b-132">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="6079b-133">Para ello debe implementar un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza del objeto necesaria.</span><span class="sxs-lookup"><span data-stu-id="6079b-133">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="6079b-134">Esto puede mejorar considerablemente el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6079b-134">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="6079b-135">Aunque controle explícitamente los recursos, el finalizador garantiza la liberación de recursos si la llamada al método `Dispose` genera un error.</span><span class="sxs-lookup"><span data-stu-id="6079b-135">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="6079b-136">Para obtener más detalles sobre la liberación de recursos, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="6079b-136">For more details about cleaning up resources, see the following topics:</span></span>  
  
- [<span data-ttu-id="6079b-137">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="6079b-137">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
- [<span data-ttu-id="6079b-138">Implementación de un método Dispose</span><span class="sxs-lookup"><span data-stu-id="6079b-138">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
- [<span data-ttu-id="6079b-139">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="6079b-139">using Statement</span></span>](../../language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="6079b-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6079b-140">Example</span></span>  
 <span data-ttu-id="6079b-141">En el siguiente ejemplo se crean tres clases que forman una cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="6079b-141">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="6079b-142">La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`.</span><span class="sxs-lookup"><span data-stu-id="6079b-142">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="6079b-143">Los tres tienen finalizadores.</span><span class="sxs-lookup"><span data-stu-id="6079b-143">All three have finalizers.</span></span> <span data-ttu-id="6079b-144">En `Main`, se crea una instancia de la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="6079b-144">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="6079b-145">Cuando ejecute el programa, observe que se llama a los finalizadores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="6079b-145">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 [!code-csharp[csProgGuideObjects#85](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#85)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6079b-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6079b-146">C# language specification</span></span>  

<span data-ttu-id="6079b-147">Para más información, vea la sección sobre [destructores](~/_csharplang/spec/classes.md#destructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="6079b-147">For more information, see the [Destructors](~/_csharplang/spec/classes.md#destructors) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6079b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="6079b-148">See also</span></span>

- <xref:System.IDisposable>
- [<span data-ttu-id="6079b-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6079b-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="6079b-150">Constructores</span><span class="sxs-lookup"><span data-stu-id="6079b-150">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="6079b-151">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="6079b-151">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
