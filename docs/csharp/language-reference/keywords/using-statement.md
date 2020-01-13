---
title: using (Instrucción, Referencia de C#)
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 52cde99fd029ce50f159b2a87fbfbf47fc79dccc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712967"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="c0ed4-102">using (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="c0ed4-102">using statement (C# Reference)</span></span>

<span data-ttu-id="c0ed4-103">Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="c0ed4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0ed4-104">Example</span></span>

<span data-ttu-id="c0ed4-105">En el ejemplo siguiente se muestra cómo usar la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

<span data-ttu-id="c0ed4-106">A partir de C# 8.0, puede usar la siguiente sintaxis alternativa para la instrucción `using` que no requiere llaves:</span><span class="sxs-lookup"><span data-stu-id="c0ed4-106">Beginning with C# 8.0, you can use the following alternative syntax for the `using` statement that doesn't require braces:</span></span>

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a><span data-ttu-id="c0ed4-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c0ed4-107">Remarks</span></span>

<span data-ttu-id="c0ed4-108"><xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="c0ed4-108"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="c0ed4-109">Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-109">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="c0ed4-110">Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-110">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="c0ed4-111">Cuando la duración de un objeto `IDisposable` se limita a un único método, debe declarar y crear instancias del mismo en la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-111">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="c0ed4-112">La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-112">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="c0ed4-113">Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-113">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="c0ed4-114">La instrucción `using` asegura que se llama al método <xref:System.IDisposable.Dispose%2A> incluso cuando se produzca una excepción en el bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-114">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="c0ed4-115">Puede lograr el mismo resultado colocando el objeto dentro de un bloque `try` y llamando luego a <xref:System.IDisposable.Dispose%2A> en un bloque `finally`; de hecho, es así cómo el compilador traduce la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-115">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="c0ed4-116">El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):</span><span class="sxs-lookup"><span data-stu-id="c0ed4-116">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="c0ed4-117">La nueva sintaxis de la instrucción `using` se traduce en un código muy similar.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-117">The newer `using` statement syntax translates to very similar code.</span></span> <span data-ttu-id="c0ed4-118">Se abre el bloque `try` en el que se declara la variable.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-118">The `try` block opens where the variable is declared.</span></span> <span data-ttu-id="c0ed4-119">El bloque `finally` se agrega al cierre del bloque de inclusión, normalmente, al final de un método.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-119">The `finally` block is added at the close of the enclosing block, typically at the end of a method.</span></span>

<span data-ttu-id="c0ed4-120">Vea el tema [try-finally](try-finally.md) para obtener más información sobre la instrucción `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-120">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="c0ed4-121">Se pueden declarar varias instancias de un tipo en la instrucción `using`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0ed4-121">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="c0ed4-122">Puede combinar varias declaraciones del mismo tipo con la nueva sintaxis introducida con C# 8 también.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-122">You can combine multiple declarations of the same type using the new syntax introduced with C# 8 as well.</span></span> <span data-ttu-id="c0ed4-123">Esto se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c0ed4-123">This is shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

<span data-ttu-id="c0ed4-124">Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-124">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="c0ed4-125">En este caso, después de que el control abandone el bloque `using` el objeto permanece en el ámbito, pero probablemente ya no tenga acceso a sus recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-125">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="c0ed4-126">En otras palabras, ya no se inicializa totalmente.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-126">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="c0ed4-127">Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-127">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="c0ed4-128">Por este motivo, suele ser mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-128">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="c0ed4-129">Para obtener más información sobre cómo eliminar objetos `IDisposable`, vea [Uso de objetos que implementan IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="c0ed4-129">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c0ed4-130">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c0ed4-130">C# language specification</span></span>

<span data-ttu-id="c0ed4-131">Para obtener más información, vea el apartado [Instrucción using](~/_csharplang/spec/statements.md#the-using-statement) en la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="c0ed4-131">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="c0ed4-132">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="c0ed4-132">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0ed4-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0ed4-133">See also</span></span>

- [<span data-ttu-id="c0ed4-134">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="c0ed4-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c0ed4-135">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c0ed4-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c0ed4-136">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="c0ed4-136">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c0ed4-137">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="c0ed4-137">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="c0ed4-138">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="c0ed4-138">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="c0ed4-139">Uso de objetos que implementan IDisposable</span><span class="sxs-lookup"><span data-stu-id="c0ed4-139">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- <span data-ttu-id="c0ed4-140">[IDisposable interface](xref:System.IDisposable) (Interfaz IDisposable)</span><span class="sxs-lookup"><span data-stu-id="c0ed4-140">[IDisposable interface](xref:System.IDisposable)</span></span>
- [<span data-ttu-id="c0ed4-141">Instrucción using en C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c0ed4-141">using statement in C# 8.0</span></span>](~/_csharplang/proposals/csharp-8.0/using.md)
