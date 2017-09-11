---
title: "using (Instrucción, Referencia de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: 31
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
ms.openlocfilehash: 201dde951b4f92d92b7d78b3d71a3f3cfb559507
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="using-statement-c-reference"></a><span data-ttu-id="c4f2d-102">using (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c4f2d-102">using Statement (C# Reference)</span></span>
<span data-ttu-id="c4f2d-103">Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4f2d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4f2d-104">Example</span></span>  
 <span data-ttu-id="c4f2d-105">En el ejemplo siguiente se muestra cómo usar la instrucción using.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-105">The following example shows how to use the using statement.</span></span>  
  
 <span data-ttu-id="c4f2d-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c4f2d-106">[!code-cs[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4f2d-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c4f2d-107">Remarks</span></span>  
 <span data-ttu-id="c4f2d-108"><xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="c4f2d-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="c4f2d-109">Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="c4f2d-110">Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>  
  
 <span data-ttu-id="c4f2d-111">Como regla general, cuando se usa un objeto `IDisposable`, debe declarar y crear instancias del mismo en una instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-111">As a rule, when you use an `IDisposable` object, you should declare and instantiate it in a `using` statement.</span></span> <span data-ttu-id="c4f2d-112">La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="c4f2d-113">Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>  
  
 <span data-ttu-id="c4f2d-114">La instrucción `using` garantiza que se llama a <xref:System.IDisposable.Dispose%2A> aunque se produzca una excepción mientras llama a métodos en el objeto.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs while you are calling methods on the object.</span></span> <span data-ttu-id="c4f2d-115">Puede lograr el mismo resultado colocando el objeto dentro de un bloque try y llamando luego a <xref:System.IDisposable.Dispose%2A> en un bloque finally; de hecho, es así cómo el compilador traduce la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-115">You can achieve the same result by putting the object inside a try block and then calling <xref:System.IDisposable.Dispose%2A> in a finally block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="c4f2d-116">El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):</span><span class="sxs-lookup"><span data-stu-id="c4f2d-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>  
  
 <span data-ttu-id="c4f2d-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="c4f2d-117">[!code-cs[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]</span></span>  
  
 <span data-ttu-id="c4f2d-118">Se pueden declarar varias instancias de un tipo en una instrucción `using`, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-118">Multiple instances of a type can be declared in a `using` statement, as shown in the following example.</span></span>  
  
 <span data-ttu-id="c4f2d-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="c4f2d-119">[!code-cs[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]</span></span>  
  
 <span data-ttu-id="c4f2d-120">Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-120">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="c4f2d-121">En este caso, el objeto permanece en el ámbito después de que el control abandone el bloque `using` aunque probablemente ya no tenga acceso a sus recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-121">In this case, the object remains in scope after control leaves the `using` block even though it will probably no longer have access to its unmanaged resources.</span></span> <span data-ttu-id="c4f2d-122">En otras palabras, ya no estará completamente inicializado.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-122">In other words, it will no longer be fully initialized.</span></span> <span data-ttu-id="c4f2d-123">Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-123">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="c4f2d-124">Por este motivo, suele ser mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="c4f2d-124">For this reason, it is generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>  
  
 <span data-ttu-id="c4f2d-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="c4f2d-125">[!code-cs[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c4f2d-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c4f2d-126">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4f2d-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4f2d-127">See Also</span></span>  
 <span data-ttu-id="c4f2d-128">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4f2d-128">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c4f2d-129">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4f2d-129">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c4f2d-130">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4f2d-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c4f2d-131">[using Directive](../../../csharp/language-reference/keywords/using-directive.md)  (using [Directiva, Referencia de C#])</span><span class="sxs-lookup"><span data-stu-id="c4f2d-131">[using Directive](../../../csharp/language-reference/keywords/using-directive.md) </span></span>  
 <span data-ttu-id="c4f2d-132">[Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4f2d-132">[Garbage Collection](../../../standard/garbage-collection/index.md) </span></span>  
 [<span data-ttu-id="c4f2d-133">Implementar un método Dispose</span><span class="sxs-lookup"><span data-stu-id="c4f2d-133">Implementing a Dispose Method</span></span>](../../../standard/garbage-collection/implementing-dispose.md)

