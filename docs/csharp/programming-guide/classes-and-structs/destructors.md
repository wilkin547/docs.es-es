---
title: "Finalizadores (Guía de programación de C#)"
ms.date: 2017-05-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- ~ [C#], in finalizers
- C# language, finalizers
- finalizers [C#]
ms.assetid: 1ae6e46d-a4b1-4a49-abe5-b97f53d9e049
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 43bb7e6488da5eda863e7ad70b25c9bf55bebb52
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="finalizers-c-programming-guide"></a><span data-ttu-id="7f6b7-102">Finalizadores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="7f6b7-102">Finalizers (C# Programming Guide)</span></span>
<span data-ttu-id="7f6b7-103">Los finalizadores se usan para destruir instancias de clases.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-103">Finalizers are used to destruct instances of classes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7f6b7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7f6b7-104">Remarks</span></span>  
  
-   <span data-ttu-id="7f6b7-105">Los finalizadores no se pueden definir en structs.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-105">Finalizers cannot be defined in structs.</span></span> <span data-ttu-id="7f6b7-106">Solo se usan con clases.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-106">They are only used with classes.</span></span>  
  
-   <span data-ttu-id="7f6b7-107">Una clase solo puede tener un finalizador.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-107">A class can only have one finalizer.</span></span>  
  
-   <span data-ttu-id="7f6b7-108">Los finalizadores no se pueden heredar ni sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-108">Finalizers cannot be inherited or overloaded.</span></span>  
  
-   <span data-ttu-id="7f6b7-109">No se puede llamar a los finalizadores.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-109">Finalizers cannot be called.</span></span> <span data-ttu-id="7f6b7-110">Se invocan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-110">They are invoked automatically.</span></span>  
  
-   <span data-ttu-id="7f6b7-111">Un finalizador no permite modificadores ni tiene parámetros.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-111">A finalizer does not take modifiers or have parameters.</span></span>  
  
 <span data-ttu-id="7f6b7-112">Por ejemplo, el siguiente código muestra una declaración de un finalizador para la clase `Car`.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-112">For example, the following is a declaration of a finalizer for the `Car` class.</span></span>
  
 <span data-ttu-id="7f6b7-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="7f6b7-113">[!code-cs[csProgGuideObjects#86](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_1.cs)]</span></span>  

<span data-ttu-id="7f6b7-114">Un finalizador también puede implementarse como una definición de cuerpo de expresión, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-114">A finalizer can also be implemented as an expression body definition, as the following example shows.</span></span>

<span data-ttu-id="7f6b7-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="7f6b7-115">[!code-cs[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]</span></span>  
  
 <span data-ttu-id="7f6b7-116">El finalizador llama implícitamente a <xref:System.Object.Finalize%2A> en la clase base del objeto.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-116">The finalizer implicitly calls <xref:System.Object.Finalize%2A> on the base class of the object.</span></span> <span data-ttu-id="7f6b7-117">Por lo tanto, una llamada a un finalizador se convierte implícitamente al siguiente código:</span><span class="sxs-lookup"><span data-stu-id="7f6b7-117">Therefore, a call to a finalizer is implicitly translated to the following code:</span></span>  
  
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
  
 <span data-ttu-id="7f6b7-118">Esto significa que se realizan llamadas al método `Finalize` de manera recursiva para todas las instancias de la cadena de herencia, desde la más a la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-118">This means that the `Finalize` method is called recursively for all instances in the inheritance chain, from the most-derived to the least-derived.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f6b7-119">Los finalizadores vacíos no deben usarse.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-119">Empty finalizers should not be used.</span></span> <span data-ttu-id="7f6b7-120">Cuando una clase contiene un finalizador, se crea una entrada en la cola `Finalize`.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-120">When a class contains a finalizer, an entry is created in the `Finalize` queue.</span></span> <span data-ttu-id="7f6b7-121">Cuando se llama al finalizador, se invoca al recolector de elementos no utilizados para procesar la cola.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-121">When the finalizer is called, the garbage collector is invoked to process the queue.</span></span> <span data-ttu-id="7f6b7-122">Un finalizador vacío simplemente produce una pérdida de rendimiento innecesaria.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-122">An empty finalizer just causes a needless loss of performance.</span></span>  
  
 <span data-ttu-id="7f6b7-123">El programador no puede controlar cuándo se llama al finalizador, porque esto lo determina el recolector de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-123">The programmer has no control over when the finalizer is called because this is determined by the garbage collector.</span></span> <span data-ttu-id="7f6b7-124">El recolector de elementos no utilizados comprueba si hay objetos que ya no están siendo usados por ninguna aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-124">The garbage collector checks for objects that are no longer being used by the application.</span></span> <span data-ttu-id="7f6b7-125">Si considera un objeto elegible para su finalización, llama al finalizador (si existe) y reclama la memoria usada para almacenar el objeto.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-125">If it considers an object eligible for finalization, it calls the finalizer (if any) and reclaims the memory used to store the object.</span></span> <span data-ttu-id="7f6b7-126">También se llama a los finalizadores cuando se cierra el programa.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-126">Finalizers are also called when the program exits.</span></span>  
  
 <span data-ttu-id="7f6b7-127">Es posible forzar la recolección de elementos no utilizados llamando a <xref:System.GC.Collect%2A>, pero en general debe evitarse su uso por razones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-127">It is possible to force garbage collection by calling <xref:System.GC.Collect%2A>, but most of the time, this should be avoided because it may create performance issues.</span></span>  
  
## <a name="using-finalizers-to-release-resources"></a><span data-ttu-id="7f6b7-128">Usar finalizadores para liberar recursos</span><span class="sxs-lookup"><span data-stu-id="7f6b7-128">Using Finalizers to Release Resources</span></span>  
 <span data-ttu-id="7f6b7-129">En general, C# no requiere tanta administración de memoria como se necesita al desarrollar con un lenguaje que no está diseñado para un runtime con recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-129">In general, C# does not require as much memory management as is needed when you develop with a language that does not target a runtime with garbage collection.</span></span> <span data-ttu-id="7f6b7-130">Esto es debido a que el recolector de elementos no utilizados de .NET Framework administra implícitamente la asignación y liberación de memoria para los objetos.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-130">This is because the .NET Framework garbage collector implicitly manages the allocation and release of memory for your objects.</span></span> <span data-ttu-id="7f6b7-131">En cambio, cuando la aplicación encapsule recursos no administrados como ventanas, archivos y conexiones de red, debería usar finalizadores para liberar dichos recursos.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-131">However, when your application encapsulates unmanaged resources such as windows, files, and network connections, you should use finalizers to free those resources.</span></span> <span data-ttu-id="7f6b7-132">Cuando el objeto cumple los requisitos para su finalización, el recolector de elementos no utilizados ejecuta el método `Finalize` del objeto.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-132">When the object is eligible for finalization, the garbage collector runs the `Finalize` method of the object.</span></span>  
  
## <a name="explicit-release-of-resources"></a><span data-ttu-id="7f6b7-133">Liberación explícita de recursos</span><span class="sxs-lookup"><span data-stu-id="7f6b7-133">Explicit Release of Resources</span></span>  
 <span data-ttu-id="7f6b7-134">Si la aplicación usa un recurso externo costoso, también es recomendable liberar explícitamente el recurso antes de que el recolector de elementos no utilizados libere el objeto.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-134">If your application is using an expensive external resource, we also recommend that you provide a way to explicitly release the resource before the garbage collector frees the object.</span></span> <span data-ttu-id="7f6b7-135">Para ello debe implementar un método `Dispose` desde la interfaz <xref:System.IDisposable> que realiza la limpieza del objeto necesaria.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-135">You do this by implementing a `Dispose` method from the <xref:System.IDisposable> interface that performs the necessary cleanup for the object.</span></span> <span data-ttu-id="7f6b7-136">Esto puede mejorar considerablemente el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-136">This can considerably improve the performance of the application.</span></span> <span data-ttu-id="7f6b7-137">Aunque controle explícitamente los recursos, el finalizador garantiza la liberación de recursos si la llamada al método `Dispose` genera un error.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-137">Even with this explicit control over resources, the finalizer becomes a safeguard to clean up resources if the call to the `Dispose` method failed.</span></span>  
  
 <span data-ttu-id="7f6b7-138">Para obtener más detalles sobre la liberación de recursos, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="7f6b7-138">For more details about cleaning up resources, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7f6b7-139">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="7f6b7-139">Cleaning Up Unmanaged Resources</span></span>](../../../standard/garbage-collection/unmanaged.md)  
  
-   [<span data-ttu-id="7f6b7-140">Implementación de un método Dispose</span><span class="sxs-lookup"><span data-stu-id="7f6b7-140">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)  
  
-   [<span data-ttu-id="7f6b7-141">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="7f6b7-141">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)  
  
## <a name="example"></a><span data-ttu-id="7f6b7-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f6b7-142">Example</span></span>  
 <span data-ttu-id="7f6b7-143">En el siguiente ejemplo se crean tres clases que forman una cadena de herencia.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-143">The following example creates three classes that make a chain of inheritance.</span></span> <span data-ttu-id="7f6b7-144">La clase `First` es la clase base, `Second` se deriva de `First` y `Third` se deriva de `Second`.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-144">The class `First` is the base class, `Second` is derived from `First`, and `Third` is derived from `Second`.</span></span> <span data-ttu-id="7f6b7-145">Los tres tienen finalizadores.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-145">All three have finalizers.</span></span> <span data-ttu-id="7f6b7-146">En `Main`, se crea una instancia de la clase más derivada.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-146">In `Main`, an instance of the most-derived class is created.</span></span> <span data-ttu-id="7f6b7-147">Cuando ejecute el programa, observe que se llama a los finalizadores de las tres clases automáticamente y en orden, desde la más derivada hasta la menos derivada.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-147">When the program runs, notice that the finalizers for the three classes are called automatically, and in order, from the most-derived to the least-derived.</span></span>  
  
 <span data-ttu-id="7f6b7-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="7f6b7-148">[!code-cs[csProgGuideObjects#85](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/destructors_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7f6b7-149">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="7f6b7-149">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f6b7-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="7f6b7-150">See Also</span></span>  
 <span data-ttu-id="7f6b7-151"><xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="7f6b7-151"><xref:System.IDisposable></span></span>   
 <span data-ttu-id="7f6b7-152">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="7f6b7-152">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="7f6b7-153">[Constructores](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span><span class="sxs-lookup"><span data-stu-id="7f6b7-153">[Constructors](../../../csharp/programming-guide/classes-and-structs/constructors.md) </span></span>  
 [<span data-ttu-id="7f6b7-154">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="7f6b7-154">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)

