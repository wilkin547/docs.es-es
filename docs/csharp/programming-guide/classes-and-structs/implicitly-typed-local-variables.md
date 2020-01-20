---
title: Variables locales con asignación implícita de tipos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 692a0f8ad933f3ba4bef50681cb3487fa0a7eea9
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714829"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="fe6a1-102">Variables locales con asignación implícita de tipos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="fe6a1-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="fe6a1-103">Las variables locales pueden declararse sin proporcionar un tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="fe6a1-104">La palabra clave `var` indica al compilador que infiera el tipo de la variable a partir de la expresión de la derecha de la instrucción de inicialización.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="fe6a1-105">El tipo inferido puede ser un tipo integrado, un tipo anónimo, un tipo definido por el usuario o un tipo definido en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="fe6a1-106">Para obtener más información sobre cómo inicializar las matrices con `var`, vea [Matrices con tipo implícito](../arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="fe6a1-107">Los ejemplos siguientes muestran distintas formas en que se pueden declarar variables locales con `var`:</span><span class="sxs-lookup"><span data-stu-id="fe6a1-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="fe6a1-108">Es importante comprender que la palabra clave `var` no significa "variant" ni indica que la variable esté débilmente tipada o esté enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="fe6a1-109">Solo significa que el compilador determina y asigna el tipo más adecuado.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="fe6a1-110">La palabra clave `var` se puede usar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe6a1-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="fe6a1-111">En variables locales (variables declaradas en el ámbito del método), tal y como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="fe6a1-112">En una instrucción de inicialización [for](../../language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for (var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="fe6a1-113">En una instrucción de inicialización [foreach](../../language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach (var item in list) {...}
    ```

- <span data-ttu-id="fe6a1-114">En una instrucción [using](../../language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="fe6a1-115">Para obtener más información, vea [Procedimiento para usar matrices y variables locales con tipo implícito en expresiones de consulta](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-115">For more information, see [How to use implicitly typed local variables and arrays in a query expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="fe6a1-116">var y tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="fe6a1-116">var and anonymous types</span></span>

<span data-ttu-id="fe6a1-117">En muchos casos, el uso de `var` es opcional y es simplemente una comodidad sintáctica.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="fe6a1-118">Pero cuando una variable se inicializa con un tipo anónimo, la variable se debe declarar como `var` si necesita acceder más adelante a las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="fe6a1-119">Se trata de un escenario común en expresiones de consulta LINQ.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-119">This is a common scenario in LINQ query expressions.</span></span> <span data-ttu-id="fe6a1-120">Para más información, vea [Tipos anónimos](anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="fe6a1-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="fe6a1-121">Desde el punto de vista del código fuente, un tipo anónimo no tiene nombre.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="fe6a1-122">Por lo tanto, si una variable de consulta se ha inicializado con `var`, la única manera de tener acceso a las propiedades de la secuencia de objetos devuelta consiste en usar `var` como el tipo de la variable de iteración en la instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="fe6a1-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fe6a1-123">Remarks</span></span>

<span data-ttu-id="fe6a1-124">Las siguientes restricciones se aplican a las declaraciones de variable con tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="fe6a1-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="fe6a1-125">`var` solo se puede usar cuando una variable local se declara e inicializa en la misma instrucción; la variable no se puede inicializar en null ni en un grupo de métodos o una función anónima.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="fe6a1-126">`var` no se puede usar en campos en el ámbito de clase.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="fe6a1-127">Las variables declaradas con `var` no se pueden usar en la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="fe6a1-128">En otras palabras, esta expresión es válida: `int i = (i = 20);`, pero esta expresión genera un error en tiempo de compilación: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="fe6a1-128">In other words, this expression is legal: `int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="fe6a1-129">No se pueden inicializar varias variables con tipo implícito en la misma instrucción.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="fe6a1-130">Si en el ámbito se encuentra un tipo con nombre `var`, la palabra clave `var` se resolverá en ese nombre de tipo y no se tratará como parte de una declaración de variable local con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="fe6a1-131">El establecimiento de tipos implícitos con la palabra clave `var` solo puede aplicarse a variables en el ámbito del método local.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-131">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="fe6a1-132">El establecimiento de tipos implícitos no está disponible para los campos de clase ya que el compilador C# encontraría una paradoja lógica al procesar el código: el compilador necesita conocer el tipo de campo, pero no puede determinar el tipo hasta que se analiza la expresión de asignación, y no se puede evaluar la expresión sin conocer el tipo.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-132">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="fe6a1-133">Observe el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe6a1-133">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="fe6a1-134">`bookTitles` es un campo de clase dado el tipo `var`.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-134">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="fe6a1-135">Como el campo no tiene ninguna expresión que evaluar, es imposible que el compilador pueda inferir el tipo `bookTitles` que se supone que es.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-135">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="fe6a1-136">Además, agregar una expresión al campo (como se haría con una variable local) también es suficiente:</span><span class="sxs-lookup"><span data-stu-id="fe6a1-136">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="fe6a1-137">Cuando el compilador encuentra campos durante la compilación de código, registra el tipo de cada campo antes de procesar las expresiones asociadas a él.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-137">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="fe6a1-138">El compilador encuentra la misma paradoja intentando analizar `bookTitles`: necesita saber el tipo de campo, pero el compilador normalmente determinaría el tipo de `var` analizando la expresión, lo que no es posible sin conocer de antemano el tipo.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-138">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="fe6a1-139">Es posible que `var` también pueda resultar útil con expresiones de consulta en las que es difícil determinar el tipo construido exacto de la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-139">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="fe6a1-140">Esto puede ocurrir con las operaciones de agrupamiento y ordenación.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-140">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="fe6a1-141">La palabra clave `var` también puede ser útil cuando resulte tedioso escribir el tipo específico de la variable en el teclado, o sea obvio o no aumente la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-141">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="fe6a1-142">Un ejemplo en el que `var` resulta útil de esta manera es cuando se usa con tipos genéricos anidados, como los que se emplean con las operaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-142">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="fe6a1-143">En la siguiente consulta, el tipo de la variable de consulta es `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-143">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="fe6a1-144">Siempre que usted y otras personas que deban mantener el código comprendan esto, no hay ningún problema con el uso de tipos implícitos por comodidad y brevedad.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-144">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="fe6a1-145">Pero el uso de `var` supone al menos la posibilidad de que el código sea más difícil de comprender para otros programadores.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-145">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="fe6a1-146">Por ese motivo, la documentación de C# por lo general solo usa `var` cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="fe6a1-146">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe6a1-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe6a1-147">See also</span></span>

- [<span data-ttu-id="fe6a1-148">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="fe6a1-148">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="fe6a1-149">Matrices con tipo implícito</span><span class="sxs-lookup"><span data-stu-id="fe6a1-149">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="fe6a1-150">Procedimiento para usar matrices y variables locales con tipo implícito en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="fe6a1-150">How to use implicitly typed local variables and arrays in a query expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="fe6a1-151">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="fe6a1-151">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="fe6a1-152">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="fe6a1-152">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="fe6a1-153">var</span><span class="sxs-lookup"><span data-stu-id="fe6a1-153">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="fe6a1-154">LINQ en C#</span><span class="sxs-lookup"><span data-stu-id="fe6a1-154">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="fe6a1-155">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="fe6a1-155">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="fe6a1-156">for</span><span class="sxs-lookup"><span data-stu-id="fe6a1-156">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="fe6a1-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="fe6a1-157">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="fe6a1-158">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="fe6a1-158">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
