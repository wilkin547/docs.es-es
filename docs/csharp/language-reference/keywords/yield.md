---
description: yield (Palabra clave contextual, Referencia de C#)
title: yield (Palabra clave contextual, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: e0efad959d5212f6c07d4c4b5344761490018a4c
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899670"
---
# <a name="yield-c-reference"></a><span data-ttu-id="1cb6b-103">yield (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="1cb6b-103">yield (C# Reference)</span></span>

<span data-ttu-id="1cb6b-104">Cuando se usa la `yield` [palabra clave contextual](index.md#contextual-keywords) en una instrucción, se indica que el método, el operador o el descriptor de acceso `get` en el que aparece es un iterador.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-104">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="1cb6b-105">Al usar `yield` para definir un iterador ya no es necesaria una clase adicional explícita (la clase que retiene el estado para una enumeración, consulte <xref:System.Collections.Generic.IEnumerator%601> para ver un ejemplo) al implementar los patrones <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para un tipo de colección personalizado.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-105">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="1cb6b-106">En el ejemplo siguiente se muestran las dos formas de la instrucción `yield`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-106">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="1cb6b-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cb6b-107">Remarks</span></span>

<span data-ttu-id="1cb6b-108">Utilice una instrucción `yield return` para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-108">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="1cb6b-109">La secuencia devuelta desde un método iterador se puede consumir mediante la instrucción [foreach](foreach-in.md) o una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-109">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="1cb6b-110">Cada iteración del bucle `foreach` llama al método iterador.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-110">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="1cb6b-111">Cuando se alcanza una instrucción `yield return` en el método iterador, se devuelve `expression` y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-111">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="1cb6b-112">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-112">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="1cb6b-113">Puede usar una instrucción `yield break` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-113">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="1cb6b-114">Para obtener más información sobre los iteradores, vea [Iteradores](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-114">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="1cb6b-115">Métodos de iterador y descriptores de acceso get</span><span class="sxs-lookup"><span data-stu-id="1cb6b-115">Iterator methods and get accessors</span></span>

<span data-ttu-id="1cb6b-116">La declaración de un iterador debe cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="1cb6b-116">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="1cb6b-117">El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-117">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="1cb6b-118">La declaración no puede tener ningún parámetro [in](in-parameter-modifier.md), [ref](ref.md) o [out](out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-118">The declaration can't have any [in](in-parameter-modifier.md), [ref](ref.md), or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="1cb6b-119">El tipo `yield` de un iterador que devuelve <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> es `object`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-119">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="1cb6b-120">Si el iterador devuelve <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, debe haber una conversión implícita del tipo de la expresión en la instrucción `yield return` al parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-120">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="1cb6b-121">No puede incluir una instrucción `yield return` ni `yield break` en:</span><span class="sxs-lookup"><span data-stu-id="1cb6b-121">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="1cb6b-122">[Expresiones lambda](../operators/lambda-expressions.md) y [métodos anónimos](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-122">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="1cb6b-123">Métodos que contienen bloques inseguros.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-123">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="1cb6b-124">Para obtener más información, vea [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="1cb6b-124">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="1cb6b-125">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="1cb6b-125">Exception handling</span></span>

<span data-ttu-id="1cb6b-126">Una instrucción `yield return` no puede encontrarse en un bloque try-catch.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-126">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="1cb6b-127">Una instrucción `yield return` puede encontrarse en el bloque try de una instrucción try-finally.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-127">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="1cb6b-128">Una instrucción `yield break` puede encontrarse en un bloque try o un bloque catch, pero no en un bloque finally.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-128">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="1cb6b-129">Si el cuerpo `foreach` (fuera del método iterador) produce una excepción, se ejecuta un bloque `finally` en el método iterador.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-129">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="1cb6b-130">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="1cb6b-130">Technical implementation</span></span>

<span data-ttu-id="1cb6b-131">El código siguiente devuelve un valor `IEnumerable<string>` desde un método iterador y, a continuación, recorre sus elementos en iteración.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-131">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="1cb6b-132">La llamada a `MyIteratorMethod` no ejecuta el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-132">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="1cb6b-133">En su lugar, la llamada devuelve un valor `IEnumerable<string>` en la variable `elements`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-133">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="1cb6b-134">En una iteración del bucle `foreach`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-134">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="1cb6b-135">Esta llamada ejecuta el cuerpo de `MyIteratorMethod` hasta que se alcanza la siguiente instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-135">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="1cb6b-136">La expresión devuelta por la instrucción `yield return` determina no solo el valor de la variable `element` para que la utilice el cuerpo del bucle, sino también la propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de `elements`, que es un valor `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-136">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="1cb6b-137">En cada iteración subsiguiente del bucle `foreach`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-137">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="1cb6b-138">El bucle `foreach` se completa al alcanzar el fin del método iterador o una instrucción `yield break`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-138">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="1cb6b-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cb6b-139">Example</span></span>

<span data-ttu-id="1cb6b-140">El ejemplo siguiente tiene una instrucción `yield return` que está dentro de un bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-140">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="1cb6b-141">Cada iteración del cuerpo de instrucción `foreach` en el método `Main` crea una llamada a la función de iterador `Power`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-141">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="1cb6b-142">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `yield return`, que se produce durante la siguiente iteración del bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-142">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="1cb6b-143">El tipo de valor devuelto del método iterador es <xref:System.Collections.IEnumerable>, que es un tipo de interfaz de iteradores.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-143">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="1cb6b-144">Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-144">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="1cb6b-145">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cb6b-145">Example</span></span>

<span data-ttu-id="1cb6b-146">En el ejemplo siguiente se muestra un descriptor de acceso `get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-146">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="1cb6b-147">En el ejemplo, cada una de las instrucciones `yield return` devuelve una instancia de una clase definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="1cb6b-147">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="1cb6b-148">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="1cb6b-148">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1cb6b-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1cb6b-149">See also</span></span>

- [<span data-ttu-id="1cb6b-150">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="1cb6b-150">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1cb6b-151">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="1cb6b-151">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1cb6b-152">foreach, in</span><span class="sxs-lookup"><span data-stu-id="1cb6b-152">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="1cb6b-153">Iteradores</span><span class="sxs-lookup"><span data-stu-id="1cb6b-153">Iterators</span></span>](../../iterators.md)
