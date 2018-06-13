---
title: using (Instrucción, Referencia de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: fa27039e8444090c8a516b92ba5ab62c7f93c51a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33285748"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="f9527-102">using (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f9527-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="f9527-103">Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="f9527-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9527-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f9527-104">Example</span></span>  
 <span data-ttu-id="f9527-105">En el ejemplo siguiente se muestra cómo usar la instrucción using.</span><span class="sxs-lookup"><span data-stu-id="f9527-105">The following example shows how to use the using statement.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="f9527-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f9527-106">Remarks</span></span>  
 <span data-ttu-id="f9527-107"><xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="f9527-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="f9527-108">Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan.</span><span class="sxs-lookup"><span data-stu-id="f9527-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="f9527-109">Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="f9527-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
<span data-ttu-id="f9527-110">Cuando la duración de un objeto `IDisposable` se limita a un único método, debe declarar y crear instancias del mismo en una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="f9527-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="f9527-111">La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="f9527-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="f9527-112">Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar.</span><span class="sxs-lookup"><span data-stu-id="f9527-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="f9527-113">La instrucción `using` garantiza que se llama a <xref:System.IDisposable.Dispose%2A> aunque se produzca una excepción mientras llama a métodos en el objeto.</span><span class="sxs-lookup"><span data-stu-id="f9527-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="f9527-114">Puede lograr el mismo resultado colocando el objeto dentro de un bloque try y llamando luego a <xref:System.IDisposable.Dispose%2A> en un bloque finally; de hecho, es así cómo el compilador traduce la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="f9527-114">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="f9527-115">El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):</span><span class="sxs-lookup"><span data-stu-id="f9527-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 <span data-ttu-id="f9527-116">Se pueden declarar varias instancias de un tipo en una instrucción `using`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f9527-116">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 <span data-ttu-id="f9527-117">Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="f9527-117">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="f9527-118">En este caso, el objeto permanece en el ámbito después de que el control abandone el bloque `using` aunque probablemente ya no tenga acceso a sus recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="f9527-118">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="f9527-119">En otras palabras, ya no estará completamente inicializado.</span><span class="sxs-lookup"><span data-stu-id="f9527-119">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="f9527-120">Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="f9527-120">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="f9527-121">Por este motivo, suele ser mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="f9527-121">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
<span data-ttu-id="f9527-122">Para más información sobre cómo eliminar objetos `IDisposable`, vea [Uso de objetos que implementan IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="f9527-122">For more information on disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f9527-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f9527-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9527-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9527-124">See Also</span></span>  
 [<span data-ttu-id="f9527-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f9527-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f9527-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f9527-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f9527-127">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f9527-127">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f9527-128">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="f9527-128">using Directive</span></span>](../../../csharp/language-reference/keywords/using-directive.md)  
 [<span data-ttu-id="f9527-129">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="f9527-129">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)  
 [<span data-ttu-id="f9527-130">Uso de objetos que implementan IDisposable</span><span class="sxs-lookup"><span data-stu-id="f9527-130">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)  
 <span data-ttu-id="f9527-131">[IDisposable interface](xref:System.IDisposable) (Interfaz IDisposable)</span><span class="sxs-lookup"><span data-stu-id="f9527-131">[IDisposable interface](xref:System.IDisposable)</span></span>
