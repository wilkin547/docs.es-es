---
title: Uso de objetos que implementan IDisposable
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fd78c2f99ca5c8ffe3c753e158ceba3e0c458c5b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="5294b-102">Uso de objetos que implementan IDisposable</span><span class="sxs-lookup"><span data-stu-id="5294b-102">Using objects that implement IDisposable</span></span>

<span data-ttu-id="5294b-103">Recolector de elementos no utilizados de common language runtime reclama la memoria utilizada por los objetos administrados, pero los tipos que utilizan recursos no administrados que implementan el <xref:System.IDisposable> interfaz para permitir que la memoria asignada a estos recursos no administrados utilizados reclame.</span><span class="sxs-lookup"><span data-stu-id="5294b-103">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the memory allocated to these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="5294b-104">Cuando termine de usar un objeto que implemente <xref:System.IDisposable>, debe llamar a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> del objeto.</span><span class="sxs-lookup"><span data-stu-id="5294b-104">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="5294b-105">Hay dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="5294b-105">You can do this in one of two ways:</span></span>  
  
* <span data-ttu-id="5294b-106">Mediante la instrucción `using` de C# o la instrucción `Using` de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5294b-106">With the C# `using` statement or the Visual Basic `Using` statement.</span></span>  
  
* <span data-ttu-id="5294b-107">Mediante la implementación de un bloque `try/finally`.</span><span class="sxs-lookup"><span data-stu-id="5294b-107">By implementing a `try/finally` block.</span></span>  

## <a name="the-using-statement"></a><span data-ttu-id="5294b-108">La instrucción using</span><span class="sxs-lookup"><span data-stu-id="5294b-108">The using statement</span></span>

<span data-ttu-id="5294b-109">Las instrucciones `using` de C# y `Using` de Visual Basic simplifican el código que se debe escribir para crear y limpiar un objeto.</span><span class="sxs-lookup"><span data-stu-id="5294b-109">The `using` statement in C# and the `Using` statement in Visual Basic simplify the code that you must write to create and clean up an object.</span></span> <span data-ttu-id="5294b-110">La instrucción `using` obtiene uno o más recursos, ejecuta las instrucciones especificadas y desecha el objeto automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5294b-110">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="5294b-111">Pero la instrucción `using` solo resulta útil para los objetos que se usan dentro del ámbito del método en el que se construyen.</span><span class="sxs-lookup"><span data-stu-id="5294b-111">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>  
  
<span data-ttu-id="5294b-112">En el ejemplo siguiente se utiliza la instrucción `using` para crear y liberar un objeto <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="5294b-112">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
<span data-ttu-id="5294b-113">Si bien la clase <xref:System.IO.StreamReader> implementa la interfaz <xref:System.IDisposable>, que indica que utiliza un recurso no administrado, en el ejemplo no se llama al método <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="5294b-113">Note that although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="5294b-114">Cuando el compilador de C# o de Visual Basic encuentra la instrucción `using`, emite un lenguaje intermedio (IL), que equivale al código siguiente que contiene un bloque `try/finally` de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="5294b-114">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
<span data-ttu-id="5294b-115">C# `using` instrucción también permite adquirir varios recursos en una sola instrucción, lo que internamente equivale a nested `using` instrucciones.</span><span class="sxs-lookup"><span data-stu-id="5294b-115">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="5294b-116">En el ejemplo siguiente se crean instancias de dos objetos <xref:System.IO.StreamReader> para leer el contenido de dos archivos.</span><span class="sxs-lookup"><span data-stu-id="5294b-116">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="5294b-117">Bloque try/finally</span><span class="sxs-lookup"><span data-stu-id="5294b-117">Try/finally block</span></span>

<span data-ttu-id="5294b-118">En lugar de ajustar un bloque `try/finally` en una instrucción `using`, puede elegir implementar el bloque `try/finally` directamente.</span><span class="sxs-lookup"><span data-stu-id="5294b-118">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="5294b-119">Puede adoptar este estilo como su método de codificación personal, o bien puede hacer esto por una de las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5294b-119">This may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>  
  
* <span data-ttu-id="5294b-120">Para incluir un bloque `catch` para controlar las excepciones producidas en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="5294b-120">To include a `catch` block to handle any exceptions thrown in the `try` block.</span></span> <span data-ttu-id="5294b-121">De lo contrario, las excepciones que produzca la instrucción `using` no se controlan, al igual que las excepciones producidas dentro del bloque `using` si no hay ningún bloque `try/catch` presente.</span><span class="sxs-lookup"><span data-stu-id="5294b-121">Otherwise, any exceptions thrown by the `using` statement are unhandled, as are any exceptions thrown within the `using` block if a `try/catch` block isn't present.</span></span>  
  
* <span data-ttu-id="5294b-122">Para crear instancias de un objeto que implementa <xref:System.IDisposable> cuyo ámbito no es local en el bloque en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="5294b-122">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>  
  
<span data-ttu-id="5294b-123">En el ejemplo siguiente es similar al ejemplo anterior, salvo que usa un `try/catch/finally` bloque para crear una instancia, usar y eliminar una <xref:System.IO.StreamReader> objeto y para controlar las excepciones producidas por la <xref:System.IO.StreamReader> constructor y su <xref:System.IO.StreamReader.ReadToEnd%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5294b-123">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="5294b-124">Observe que el código del bloque `finally` comprueba que el objeto que implementa <xref:System.IDisposable> no es `null` antes de llamar al método <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="5294b-124">Note that the code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="5294b-125">Si no se realiza este paso, se puede producir una excepción <xref:System.NullReferenceException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5294b-125">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
<span data-ttu-id="5294b-126">Puede seguir este patrón básico si elige implementar o debe implementar un `try/finally` bloquearse, porque el lenguaje de programación no es compatible con un `using` instrucción pero sí llamadas directas a la <xref:System.IDisposable.Dispose%2A> método.</span><span class="sxs-lookup"><span data-stu-id="5294b-126">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="5294b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5294b-127">See also</span></span>

<span data-ttu-id="5294b-128">[Limpiar recursos no administrados](../../../docs/standard/garbage-collection/unmanaged.md) </span><span class="sxs-lookup"><span data-stu-id="5294b-128">[Cleaning Up Unmanaged Resources](../../../docs/standard/garbage-collection/unmanaged.md) </span></span>  
<span data-ttu-id="5294b-129">[uso de instrucción (referencia de C#)](~/docs/csharp/language-reference/keywords/using-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5294b-129">[using Statement (C# Reference)](~/docs/csharp/language-reference/keywords/using-statement.md) </span></span>  
[<span data-ttu-id="5294b-130">Uso de la instrucción (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5294b-130">Using Statement (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/statements/using-statement.md)
