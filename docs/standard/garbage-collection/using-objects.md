---
title: Uso de objetos que implementan IDisposable
description: Aprenda a usar objetos que implementan la interfaz IDisposable en .NET. Los tipos que usan recursos no administrados implementan IDisposable para permitir la recuperación de recursos.
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 7d5d4080f22aab6870a230d495b4a4b9ebcb3b96
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599859"
---
# <a name="using-objects-that-implement-idisposable"></a><span data-ttu-id="6ab0c-104">Uso de objetos que implementan IDisposable</span><span class="sxs-lookup"><span data-stu-id="6ab0c-104">Using objects that implement IDisposable</span></span>

<span data-ttu-id="6ab0c-105">El recolector de elementos no utilizados de Common Language Runtime reclama la memoria utilizada por los objetos administrados, aunque los tipos que usan recursos no administrados implementan la interfaz <xref:System.IDisposable> para permitir que se reclamen los recursos que necesitan estos recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-105">The common language runtime's garbage collector reclaims the memory used by managed objects, but types that use unmanaged resources implement the <xref:System.IDisposable> interface to allow the resources needed by these unmanaged resources to be reclaimed.</span></span> <span data-ttu-id="6ab0c-106">Cuando termine de usar un objeto que implemente <xref:System.IDisposable>, debe llamar a la implementación <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> del objeto.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-106">When you finish using an object that implements <xref:System.IDisposable>, you should call the object's <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> implementation.</span></span> <span data-ttu-id="6ab0c-107">Hay dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="6ab0c-107">You can do this in one of two ways:</span></span>

- <span data-ttu-id="6ab0c-108">Con la instrucción `using` de C# (`Using` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="6ab0c-108">With the C# `using` statement (`Using` in Visual Basic).</span></span>
- <span data-ttu-id="6ab0c-109">Mediante la implementación de un bloque `try/finally` y una llamada a <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> en `finally`.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-109">By implementing a `try/finally` block, and calling the <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in the `finally`.</span></span>

## <a name="the-using-statement"></a><span data-ttu-id="6ab0c-110">La instrucción using</span><span class="sxs-lookup"><span data-stu-id="6ab0c-110">The using statement</span></span>

<span data-ttu-id="6ab0c-111">La instrucción [`using` ](../../csharp/language-reference/keywords/using-statement.md) de C# y la instrucción [`Using`](../../visual-basic/language-reference/statements/using-statement.md) de Visual Basic simplifican el código que se debe escribir para limpiar un objeto.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-111">The [`using` statement](../../csharp/language-reference/keywords/using-statement.md) in C# and the [`Using` statement](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic simplify the code that you must write to cleanup an object.</span></span> <span data-ttu-id="6ab0c-112">La instrucción `using` obtiene uno o más recursos, ejecuta las instrucciones especificadas y desecha el objeto automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-112">The `using` statement obtains one or more resources, executes the statements that you specify, and automatically disposes of the object.</span></span> <span data-ttu-id="6ab0c-113">Pero la instrucción `using` solo resulta útil para los objetos que se usan dentro del ámbito del método en el que se construyen.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-113">However, the `using` statement is useful only for objects that are used within the scope of the method in which they are constructed.</span></span>

<span data-ttu-id="6ab0c-114">En el ejemplo siguiente se utiliza la instrucción `using` para crear y liberar un objeto <xref:System.IO.StreamReader?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-114">The following example uses the `using` statement to create and release a <xref:System.IO.StreamReader?displayProperty=nameWithType> object.</span></span>

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

<span data-ttu-id="6ab0c-115">Aunque la clase <xref:System.IO.StreamReader> implementa la interfaz <xref:System.IDisposable>, que indica que usa un recurso no administrado, en el ejemplo no se llama al método <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-115">Although the <xref:System.IO.StreamReader> class implements the <xref:System.IDisposable> interface, which indicates that it uses an unmanaged resource, the example doesn't explicitly call the <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="6ab0c-116">Cuando el compilador de C# o de Visual Basic encuentra la instrucción `using`, emite un lenguaje intermedio (IL), que equivale al código siguiente que contiene un bloque `try/finally` de manera explícita.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-116">When the C# or Visual Basic compiler encounters the `using` statement, it emits intermediate language (IL) that is equivalent to the following code that explicitly contains a `try/finally` block.</span></span>

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

<span data-ttu-id="6ab0c-117">La instrucción `using` de C# también permite adquirir varios recursos en una sola instrucción, lo que internamente equivale a instrucciones `using` anidadas.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-117">The C# `using` statement also allows you to acquire multiple resources in a single statement, which is internally equivalent to nested `using` statements.</span></span> <span data-ttu-id="6ab0c-118">En el ejemplo siguiente se crean instancias de dos objetos <xref:System.IO.StreamReader> para leer el contenido de dos archivos.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-118">The following example instantiates two <xref:System.IO.StreamReader> objects to read the contents of two different files.</span></span>

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a><span data-ttu-id="6ab0c-119">Bloque try/finally</span><span class="sxs-lookup"><span data-stu-id="6ab0c-119">Try/finally block</span></span>

<span data-ttu-id="6ab0c-120">En lugar de ajustar un bloque `try/finally` en una instrucción `using`, puede elegir implementar el bloque `try/finally` directamente.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-120">Instead of wrapping a `try/finally` block in a `using` statement, you may choose to implement the `try/finally` block directly.</span></span> <span data-ttu-id="6ab0c-121">Puede adoptar este estilo como su método de creación de código personal, o bien puede hacer esto por una de las razones siguientes:</span><span class="sxs-lookup"><span data-stu-id="6ab0c-121">It may be your personal coding style, or you might want to do this for one of the following reasons:</span></span>

- <span data-ttu-id="6ab0c-122">Para incluir un bloque `catch` para controlar las excepciones iniciadas en el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-122">To include a `catch` block to handle exceptions thrown in the `try` block.</span></span> <span data-ttu-id="6ab0c-123">De lo contrario, las excepciones iniciadas en la instrucción `using` no se controlan.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-123">Otherwise, any exceptions thrown within the `using` statement are unhandled.</span></span>

- <span data-ttu-id="6ab0c-124">Para crear instancias de un objeto que implementa <xref:System.IDisposable> cuyo ámbito no es local en el bloque en el que se declara.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-124">To instantiate an object that implements <xref:System.IDisposable> whose scope is not local to the block within which it is declared.</span></span>

<span data-ttu-id="6ab0c-125">El siguiente ejemplo es similar al anterior, a excepción de que se usa un bloque `try/catch/finally` para crear instancias, usar y eliminar un objeto <xref:System.IO.StreamReader>, y para controlar las excepciones que produce el constructor <xref:System.IO.StreamReader> y su método <xref:System.IO.StreamReader.ReadToEnd%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-125">The following example is similar to the previous example, except that it uses a `try/catch/finally` block to instantiate, use, and dispose of a <xref:System.IO.StreamReader> object, and to handle any exceptions thrown by the <xref:System.IO.StreamReader> constructor and its <xref:System.IO.StreamReader.ReadToEnd%2A> method.</span></span> <span data-ttu-id="6ab0c-126">El código del bloque `finally` comprueba que el objeto que implementa <xref:System.IDisposable> no es `null` antes de llamar al método <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-126">The code in the `finally` block checks that the object that implements <xref:System.IDisposable> isn't `null` before it calls the <xref:System.IDisposable.Dispose%2A> method.</span></span> <span data-ttu-id="6ab0c-127">Si no se realiza este paso, se puede producir una excepción <xref:System.NullReferenceException> en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-127">Failure to do this can result in a <xref:System.NullReferenceException> exception at run time.</span></span>

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

<span data-ttu-id="6ab0c-128">Puede seguir este patrón básico si elige implementar o debe implementar un bloque `try/finally`, ya que el lenguaje de programación no admite una instrucción `using` pero sí llamadas directas al método <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-128">You can follow this basic pattern if you choose to implement or must implement a `try/finally` block, because your programming language doesn't support a `using` statement but does allow direct calls to the <xref:System.IDisposable.Dispose%2A> method.</span></span>

## <a name="idisposable-instance-members"></a><span data-ttu-id="6ab0c-129">Miembros de instancia de IDisposable</span><span class="sxs-lookup"><span data-stu-id="6ab0c-129">IDisposable instance members</span></span>

<span data-ttu-id="6ab0c-130">Si una clase contiene una implementación de <xref:System.IDisposable> como un miembro de instancia, ya sea un campo o una propiedad, la clase también debe implementar <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="6ab0c-130">If a class holds an <xref:System.IDisposable> implementation as an instance member, either a field or a property, the class should also implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="6ab0c-131">Para más información, consulte cómo [implementar una eliminación en cascada](implementing-dispose.md#cascade-dispose-calls).</span><span class="sxs-lookup"><span data-stu-id="6ab0c-131">For more information, see [implement a cascade dispose](implementing-dispose.md#cascade-dispose-calls).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ab0c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ab0c-132">See also</span></span>

- [<span data-ttu-id="6ab0c-133">Limpieza de recursos no administrados</span><span class="sxs-lookup"><span data-stu-id="6ab0c-133">Cleaning up unmanaged resources</span></span>](unmanaged.md)
- [<span data-ttu-id="6ab0c-134">using (Instrucción) (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6ab0c-134">using Statement (C# Reference)</span></span>](../../csharp/language-reference/keywords/using-statement.md)
- [<span data-ttu-id="6ab0c-135">Using (Instrucción, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ab0c-135">Using Statement (Visual Basic)</span></span>](../../visual-basic/language-reference/statements/using-statement.md)
