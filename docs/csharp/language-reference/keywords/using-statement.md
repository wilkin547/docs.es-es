---
title: using (Instrucción, Referencia de C#)
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: e1a1a960fa69be593ea01cab51be576b0055fd5e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632898"
---
# <a name="using-statement-c-reference"></a><span data-ttu-id="cab34-102">using (Instrucción, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="cab34-102">using statement (C# Reference)</span></span>

<span data-ttu-id="cab34-103">Ofrece una sintaxis adecuada que garantiza el uso correcto de objetos <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="cab34-103">Provides a convenient syntax that ensures the correct use of <xref:System.IDisposable> objects.</span></span>

## <a name="example"></a><span data-ttu-id="cab34-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cab34-104">Example</span></span>

<span data-ttu-id="cab34-105">En el ejemplo siguiente se muestra cómo usar la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="cab34-105">The following example shows how to use the `using` statement.</span></span>

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

## <a name="remarks"></a><span data-ttu-id="cab34-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cab34-106">Remarks</span></span>

<span data-ttu-id="cab34-107"><xref:System.IO.File> y <xref:System.Drawing.Font> son ejemplos de tipos administrados que acceden a recursos no administrados (en este caso, identificadores de archivo y contextos de dispositivo).</span><span class="sxs-lookup"><span data-stu-id="cab34-107"><xref:System.IO.File> and <xref:System.Drawing.Font> are examples of managed types that access unmanaged resources (in this case file handles and device contexts).</span></span> <span data-ttu-id="cab34-108">Hay muchos otros tipos de recursos no administrados y tipos de la biblioteca de clases que los encapsulan.</span><span class="sxs-lookup"><span data-stu-id="cab34-108">There are many other kinds of unmanaged resources and class library types that encapsulate them.</span></span> <span data-ttu-id="cab34-109">Todos estos tipos deben implementar la interfaz <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="cab34-109">All such types must implement the <xref:System.IDisposable> interface.</span></span>

<span data-ttu-id="cab34-110">Cuando la duración de un objeto `IDisposable` se limita a un único método, debe declarar y crear instancias del mismo en la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="cab34-110">When the lifetime of an `IDisposable` object is limited to a single method, you should declare and instantiate it in the `using` statement.</span></span> <span data-ttu-id="cab34-111">La instrucción `using` llama al método <xref:System.IDisposable.Dispose%2A> del objeto de forma correcta y (cuando se usa tal y como se muestra anteriormente) también hace que el propio objeto salga del ámbito en cuanto se llame a <xref:System.IDisposable.Dispose%2A>.</span><span class="sxs-lookup"><span data-stu-id="cab34-111">The `using` statement calls the <xref:System.IDisposable.Dispose%2A> method on the object in the correct way, and (when you use it as shown earlier) it also causes the object itself to go out of scope as soon as <xref:System.IDisposable.Dispose%2A> is called.</span></span> <span data-ttu-id="cab34-112">Dentro del bloque `using`, el objeto es de solo lectura y no se puede modificar ni reasignar.</span><span class="sxs-lookup"><span data-stu-id="cab34-112">Within the `using` block, the object is read-only and cannot be modified or reassigned.</span></span>

<span data-ttu-id="cab34-113">La instrucción `using` asegura que se llama al método <xref:System.IDisposable.Dispose%2A> incluso cuando se produzca una excepción en el bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="cab34-113">The `using` statement ensures that <xref:System.IDisposable.Dispose%2A> is called even if an exception occurs within the `using` block.</span></span> <span data-ttu-id="cab34-114">Puede lograr el mismo resultado colocando el objeto dentro de un bloque `try` y llamando luego a <xref:System.IDisposable.Dispose%2A> en un bloque `finally`; de hecho, es así cómo el compilador traduce la instrucción `using`.</span><span class="sxs-lookup"><span data-stu-id="cab34-114">You can achieve the same result by putting the object inside a `try` block and then calling <xref:System.IDisposable.Dispose%2A> in a `finally` block; in fact, this is how the `using` statement is translated by the compiler.</span></span> <span data-ttu-id="cab34-115">El ejemplo de código anterior se extiende al siguiente código en tiempo de compilación (tenga en cuenta las llaves adicionales para crear el ámbito limitado del objeto):</span><span class="sxs-lookup"><span data-stu-id="cab34-115">The code example earlier expands to the following code at compile time (note the extra curly braces to create the limited scope for the object):</span></span>

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

<span data-ttu-id="cab34-116">Vea el tema [try-finally](try-finally.md) para obtener más información sobre la instrucción `try`-`finally`.</span><span class="sxs-lookup"><span data-stu-id="cab34-116">For more information about the `try`-`finally` statement, see the [try-finally](try-finally.md) topic.</span></span>

<span data-ttu-id="cab34-117">Se pueden declarar varias instancias de un tipo en la instrucción `using`, tal y como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cab34-117">Multiple instances of a type can be declared in the `using` statement, as shown in the following example:</span></span>

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

<span data-ttu-id="cab34-118">Puede crear una instancia del objeto de recurso y luego pasar la variable a la instrucción `using`, pero esto no es un procedimiento recomendado.</span><span class="sxs-lookup"><span data-stu-id="cab34-118">You can instantiate the resource object and then pass the variable to the `using` statement, but this is not a best practice.</span></span> <span data-ttu-id="cab34-119">En este caso, después de que el control abandone el bloque `using` el objeto permanece en el ámbito, pero probablemente ya no tenga acceso a sus recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="cab34-119">In this case, after control leaves the `using` block, the object remains in scope but probably has no access to its unmanaged resources.</span></span> <span data-ttu-id="cab34-120">En otras palabras, ya no se inicializa totalmente.</span><span class="sxs-lookup"><span data-stu-id="cab34-120">In other words, it's not fully initialized anymore.</span></span> <span data-ttu-id="cab34-121">Si intenta usar el objeto fuera del bloque `using`, corre el riesgo de iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="cab34-121">If you try to use the object outside the `using` block, you risk causing an exception to be thrown.</span></span> <span data-ttu-id="cab34-122">Por este motivo, suele ser mejor crear una instancia del objeto en la instrucción `using` y limitar su ámbito al bloque `using`.</span><span class="sxs-lookup"><span data-stu-id="cab34-122">For this reason, it's generally better to instantiate the object in the `using` statement and limit its scope to the `using` block.</span></span>

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

<span data-ttu-id="cab34-123">Para obtener más información sobre cómo eliminar objetos `IDisposable`, vea [Uso de objetos que implementan IDisposable](../../../standard/garbage-collection/using-objects.md).</span><span class="sxs-lookup"><span data-stu-id="cab34-123">For more information about disposing of `IDisposable` objects, see [Using objects that implement IDisposable](../../../standard/garbage-collection/using-objects.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="cab34-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="cab34-124">C# language specification</span></span>

<span data-ttu-id="cab34-125">Para obtener más información, vea el apartado [Instrucción using](~/_csharplang/spec/statements.md#the-using-statement) en la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="cab34-125">For more information, see [The using statement](~/_csharplang/spec/statements.md#the-using-statement) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="cab34-126">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="cab34-126">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="cab34-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="cab34-127">See also</span></span>

- [<span data-ttu-id="cab34-128">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cab34-128">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cab34-129">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cab34-129">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cab34-130">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="cab34-130">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="cab34-131">using (directiva)</span><span class="sxs-lookup"><span data-stu-id="cab34-131">using Directive</span></span>](using-directive.md)
- [<span data-ttu-id="cab34-132">Recolección de elementos no utilizados</span><span class="sxs-lookup"><span data-stu-id="cab34-132">Garbage Collection</span></span>](../../../standard/garbage-collection/index.md)
- [<span data-ttu-id="cab34-133">Uso de objetos que implementan IDisposable</span><span class="sxs-lookup"><span data-stu-id="cab34-133">Using objects that implement IDisposable</span></span>](../../../standard/garbage-collection/using-objects.md)
- <span data-ttu-id="cab34-134">[IDisposable interface](xref:System.IDisposable) (Interfaz IDisposable)</span><span class="sxs-lookup"><span data-stu-id="cab34-134">[IDisposable interface](xref:System.IDisposable)</span></span>
