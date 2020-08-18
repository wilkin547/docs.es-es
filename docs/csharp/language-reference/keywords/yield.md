---
title: yield (Palabra clave contextual, Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- yield
- yield_CSharpKeyword
helpviewer_keywords:
- yield keyword [C#]
ms.assetid: 1089194f-9e53-46a2-8642-53ccbe9d414d
ms.openlocfilehash: ec1058d1590d64fa8d8786b3118ecf9733c55d6f
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063151"
---
# <a name="yield-c-reference"></a><span data-ttu-id="578d0-102">yield (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="578d0-102">yield (C# Reference)</span></span>

<span data-ttu-id="578d0-103">Cuando se usa la `yield` [palabra clave contextual](index.md#contextual-keywords) en una instrucción, se indica que el método, el operador o el descriptor de acceso `get` en el que aparece es un iterador.</span><span class="sxs-lookup"><span data-stu-id="578d0-103">When you use the `yield` [contextual keyword](index.md#contextual-keywords) in a statement, you indicate that the method, operator, or `get` accessor in which it appears is an iterator.</span></span> <span data-ttu-id="578d0-104">Al usar `yield` para definir un iterador ya no es necesaria una clase adicional explícita (la clase que retiene el estado para una enumeración, consulte <xref:System.Collections.Generic.IEnumerator%601> para ver un ejemplo) al implementar los patrones <xref:System.Collections.IEnumerable> y <xref:System.Collections.IEnumerator> para un tipo de colección personalizado.</span><span class="sxs-lookup"><span data-stu-id="578d0-104">Using `yield` to define an iterator removes the need for an explicit extra class (the class that holds the state for an enumeration, see <xref:System.Collections.Generic.IEnumerator%601> for an example) when you implement the <xref:System.Collections.IEnumerable> and <xref:System.Collections.IEnumerator> pattern for a custom collection type.</span></span>

<span data-ttu-id="578d0-105">En el ejemplo siguiente se muestran las dos formas de la instrucción `yield`.</span><span class="sxs-lookup"><span data-stu-id="578d0-105">The following example shows the two forms of the `yield` statement.</span></span>

```csharp
yield return <expression>;
yield break;
```

## <a name="remarks"></a><span data-ttu-id="578d0-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="578d0-106">Remarks</span></span>

<span data-ttu-id="578d0-107">Utilice una instrucción `yield return` para devolver cada elemento de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="578d0-107">You use a `yield return` statement to return each element one at a time.</span></span>

<span data-ttu-id="578d0-108">La secuencia devuelta desde un método iterador se puede consumir mediante la instrucción [foreach](foreach-in.md) o una consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="578d0-108">The sequence returned from an iterator method can be consumed by using a [foreach](foreach-in.md) statement or LINQ query.</span></span> <span data-ttu-id="578d0-109">Cada iteración del bucle `foreach` llama al método iterador.</span><span class="sxs-lookup"><span data-stu-id="578d0-109">Each iteration of the `foreach` loop calls the iterator method.</span></span> <span data-ttu-id="578d0-110">Cuando se alcanza una instrucción `yield return` en el método iterador, se devuelve `expression` y se conserva la ubicación actual en el código.</span><span class="sxs-lookup"><span data-stu-id="578d0-110">When a `yield return` statement is reached in the iterator method, `expression` is returned, and the current location in code is retained.</span></span> <span data-ttu-id="578d0-111">La ejecución se reinicia desde esa ubicación la próxima vez que se llama a la función del iterador.</span><span class="sxs-lookup"><span data-stu-id="578d0-111">Execution is restarted from that location the next time that the iterator function is called.</span></span>

<span data-ttu-id="578d0-112">Puede usar una instrucción `yield break` para finalizar la iteración.</span><span class="sxs-lookup"><span data-stu-id="578d0-112">You can use a `yield break` statement to end the iteration.</span></span>

<span data-ttu-id="578d0-113">Para obtener más información sobre los iteradores, vea [Iteradores](../../iterators.md).</span><span class="sxs-lookup"><span data-stu-id="578d0-113">For more information about iterators, see [Iterators](../../iterators.md).</span></span>

## <a name="iterator-methods-and-get-accessors"></a><span data-ttu-id="578d0-114">Métodos de iterador y descriptores de acceso get</span><span class="sxs-lookup"><span data-stu-id="578d0-114">Iterator methods and get accessors</span></span>

<span data-ttu-id="578d0-115">La declaración de un iterador debe cumplir los requisitos siguientes:</span><span class="sxs-lookup"><span data-stu-id="578d0-115">The declaration of an iterator must meet the following requirements:</span></span>

- <span data-ttu-id="578d0-116">El tipo de valor devuelto debe ser <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> o <xref:System.Collections.Generic.IEnumerator%601>.</span><span class="sxs-lookup"><span data-stu-id="578d0-116">The return type must be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

- <span data-ttu-id="578d0-117">La declaración no puede tener ningún parámetro [in](in-parameter-modifier.md) [ref](ref.md) o [out](out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="578d0-117">The declaration can't have any [in](in-parameter-modifier.md) [ref](ref.md) or [out](out-parameter-modifier.md) parameters.</span></span>

<span data-ttu-id="578d0-118">El tipo `yield` de un iterador que devuelve <xref:System.Collections.IEnumerable> o <xref:System.Collections.IEnumerator> es `object`.</span><span class="sxs-lookup"><span data-stu-id="578d0-118">The `yield` type of an iterator that returns <xref:System.Collections.IEnumerable> or <xref:System.Collections.IEnumerator> is `object`.</span></span>  <span data-ttu-id="578d0-119">Si el iterador devuelve <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Collections.Generic.IEnumerator%601>, debe haber una conversión implícita del tipo de la expresión en la instrucción `yield return` al parámetro de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="578d0-119">If the iterator returns <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Collections.Generic.IEnumerator%601>, there must be an implicit conversion from the type of the expression in the `yield return` statement to the generic type parameter .</span></span>

<span data-ttu-id="578d0-120">No puede incluir una instrucción `yield return` ni `yield break` en:</span><span class="sxs-lookup"><span data-stu-id="578d0-120">You can't include a `yield return` or `yield break` statement in:</span></span>

- <span data-ttu-id="578d0-121">[Expresiones lambda](../operators/lambda-expressions.md) y [métodos anónimos](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="578d0-121">[Lambda expressions](../operators/lambda-expressions.md) and [anonymous methods](../operators/delegate-operator.md).</span></span>

- <span data-ttu-id="578d0-122">Métodos que contienen bloques inseguros.</span><span class="sxs-lookup"><span data-stu-id="578d0-122">Methods that contain unsafe blocks.</span></span> <span data-ttu-id="578d0-123">Para obtener más información, vea [unsafe](unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="578d0-123">For more information, see [unsafe](unsafe.md).</span></span>

## <a name="exception-handling"></a><span data-ttu-id="578d0-124">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="578d0-124">Exception handling</span></span>

<span data-ttu-id="578d0-125">Una instrucción `yield return` no puede encontrarse en un bloque try-catch.</span><span class="sxs-lookup"><span data-stu-id="578d0-125">A `yield return` statement can't be located in a try-catch block.</span></span> <span data-ttu-id="578d0-126">Una instrucción `yield return` puede encontrarse en el bloque try de una instrucción try-finally.</span><span class="sxs-lookup"><span data-stu-id="578d0-126">A `yield return` statement can be located in the try block of a try-finally statement.</span></span>

<span data-ttu-id="578d0-127">Una instrucción `yield break` puede encontrarse en un bloque try o un bloque catch, pero no en un bloque finally.</span><span class="sxs-lookup"><span data-stu-id="578d0-127">A `yield break` statement can be located in a try block or a catch block but not a finally block.</span></span>

<span data-ttu-id="578d0-128">Si el cuerpo `foreach` (fuera del método iterador) produce una excepción, se ejecuta un bloque `finally` en el método iterador.</span><span class="sxs-lookup"><span data-stu-id="578d0-128">If the `foreach` body (outside of the iterator method) throws an exception, a `finally` block in the iterator method is executed.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="578d0-129">Implementación técnica</span><span class="sxs-lookup"><span data-stu-id="578d0-129">Technical implementation</span></span>

<span data-ttu-id="578d0-130">El código siguiente devuelve un valor `IEnumerable<string>` desde un método iterador y, a continuación, recorre sus elementos en iteración.</span><span class="sxs-lookup"><span data-stu-id="578d0-130">The following code returns an `IEnumerable<string>` from an iterator method and then iterates through its elements.</span></span>

```csharp
IEnumerable<string> elements = MyIteratorMethod();
foreach (string element in elements)
{
   ...
}
```

<span data-ttu-id="578d0-131">La llamada a `MyIteratorMethod` no ejecuta el cuerpo del método.</span><span class="sxs-lookup"><span data-stu-id="578d0-131">The call to `MyIteratorMethod` doesn't execute the body of the method.</span></span> <span data-ttu-id="578d0-132">En su lugar, la llamada devuelve un valor `IEnumerable<string>` en la variable `elements`.</span><span class="sxs-lookup"><span data-stu-id="578d0-132">Instead the call returns an `IEnumerable<string>` into the `elements` variable.</span></span>

<span data-ttu-id="578d0-133">En una iteración del bucle `foreach`, se llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> para `elements`.</span><span class="sxs-lookup"><span data-stu-id="578d0-133">On an iteration of the `foreach` loop, the <xref:System.Collections.IEnumerator.MoveNext%2A> method is called for `elements`.</span></span> <span data-ttu-id="578d0-134">Esta llamada ejecuta el cuerpo de `MyIteratorMethod` hasta que se alcanza la siguiente instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="578d0-134">This call executes the body of `MyIteratorMethod` until the next `yield return` statement is reached.</span></span> <span data-ttu-id="578d0-135">La expresión devuelta por la instrucción `yield return` determina no solo el valor de la variable `element` para que la utilice el cuerpo del bucle, sino también la propiedad <xref:System.Collections.Generic.IEnumerator%601.Current%2A> de `elements`, que es un valor `IEnumerable<string>`.</span><span class="sxs-lookup"><span data-stu-id="578d0-135">The expression returned by the `yield return` statement determines not only the value of the `element` variable for consumption by the loop body but also the <xref:System.Collections.Generic.IEnumerator%601.Current%2A> property of `elements`, which is an `IEnumerable<string>`.</span></span>

<span data-ttu-id="578d0-136">En cada iteración subsiguiente del bucle `foreach`, la ejecución del cuerpo del iterador continúa desde donde se dejó, deteniéndose de nuevo al alcanzar una instrucción `yield return`.</span><span class="sxs-lookup"><span data-stu-id="578d0-136">On each subsequent iteration of the `foreach` loop, the execution of the iterator body continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="578d0-137">El bucle `foreach` se completa al alcanzar el fin del método iterador o una instrucción `yield break`.</span><span class="sxs-lookup"><span data-stu-id="578d0-137">The `foreach` loop completes when the end of the iterator method or a `yield break` statement is reached.</span></span>

## <a name="example"></a><span data-ttu-id="578d0-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="578d0-138">Example</span></span>

<span data-ttu-id="578d0-139">El ejemplo siguiente tiene una instrucción `yield return` que está dentro de un bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="578d0-139">The following example has a `yield return` statement that's inside a `for` loop.</span></span> <span data-ttu-id="578d0-140">Cada iteración del cuerpo de instrucción `foreach` en el método `Main` crea una llamada a la función de iterador `Power`.</span><span class="sxs-lookup"><span data-stu-id="578d0-140">Each iteration of the `foreach` statement body in the `Main` method creates a call to the `Power` iterator function.</span></span> <span data-ttu-id="578d0-141">Cada llamada a la función de iterador prosigue con la siguiente ejecución de la instrucción `yield return`, que se produce durante la siguiente iteración del bucle `for`.</span><span class="sxs-lookup"><span data-stu-id="578d0-141">Each call to the iterator function proceeds to the next execution of the `yield return` statement, which occurs during the next iteration of the `for` loop.</span></span>

<span data-ttu-id="578d0-142">El tipo de valor devuelto del método iterador es <xref:System.Collections.IEnumerable>, que es un tipo de interfaz de iteradores.</span><span class="sxs-lookup"><span data-stu-id="578d0-142">The return type of the iterator method is <xref:System.Collections.IEnumerable>, which is an iterator interface type.</span></span> <span data-ttu-id="578d0-143">Cuando se llama al método iterador, este devuelve un objeto enumerable que contiene las potencias de un número.</span><span class="sxs-lookup"><span data-stu-id="578d0-143">When the iterator method is called, it returns an enumerable object that contains the powers of a number.</span></span>

[!code-csharp[csrefKeywordsContextual#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#5)]

## <a name="example"></a><span data-ttu-id="578d0-144">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="578d0-144">Example</span></span>

<span data-ttu-id="578d0-145">En el ejemplo siguiente se muestra un descriptor de acceso `get` que es un iterador.</span><span class="sxs-lookup"><span data-stu-id="578d0-145">The following example demonstrates a `get` accessor that is an iterator.</span></span> <span data-ttu-id="578d0-146">En el ejemplo, cada una de las instrucciones `yield return` devuelve una instancia de una clase definida por el usuario.</span><span class="sxs-lookup"><span data-stu-id="578d0-146">In the example, each `yield return` statement returns an instance of a user-defined class.</span></span>

[!code-csharp[csrefKeywordsContextual#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#21)]

## <a name="c-language-specification"></a><span data-ttu-id="578d0-147">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="578d0-147">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="578d0-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="578d0-148">See also</span></span>

- [<span data-ttu-id="578d0-149">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="578d0-149">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="578d0-150">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="578d0-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="578d0-151">foreach, in</span><span class="sxs-lookup"><span data-stu-id="578d0-151">foreach, in</span></span>](foreach-in.md)
- [<span data-ttu-id="578d0-152">Iteradores</span><span class="sxs-lookup"><span data-stu-id="578d0-152">Iterators</span></span>](../../iterators.md)
