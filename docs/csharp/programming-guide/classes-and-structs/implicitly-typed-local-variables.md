---
title: Variables locales con asignación implícita de tipos (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 91020886e381d8410358cae9511107e28c51452a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43464913"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="df7f3-102">Variables locales con asignación implícita de tipos (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="df7f3-102">Implicitly Typed Local Variables (C# Programming Guide)</span></span>
<span data-ttu-id="df7f3-103">Las variables locales pueden declararse sin proporcionar un tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="df7f3-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="df7f3-104">La palabra clave `var` indica al compilador que infiera el tipo de la variable a partir de la expresión de la derecha de la instrucción de inicialización.</span><span class="sxs-lookup"><span data-stu-id="df7f3-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="df7f3-105">El tipo inferido puede ser un tipo integrado, un tipo anónimo, un tipo definido por el usuario o un tipo definido en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="df7f3-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="df7f3-106">Para obtener más información sobre cómo inicializar las matrices con `var`, vea [Matrices con tipo implícito](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span><span class="sxs-lookup"><span data-stu-id="df7f3-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md).</span></span>  
  
 <span data-ttu-id="df7f3-107">Los ejemplos siguientes muestran distintas formas en que se pueden declarar variables locales con `var`:</span><span class="sxs-lookup"><span data-stu-id="df7f3-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#43](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_1.cs)]  
  
 <span data-ttu-id="df7f3-108">Es importante comprender que la palabra clave `var` no significa "variant" ni indica que la variable esté débilmente tipada o esté enlazada en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="df7f3-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="df7f3-109">Solo significa que el compilador determina y asigna el tipo más adecuado.</span><span class="sxs-lookup"><span data-stu-id="df7f3-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>  
  
 <span data-ttu-id="df7f3-110">La palabra clave `var` se puede usar en los contextos siguientes:</span><span class="sxs-lookup"><span data-stu-id="df7f3-110">The `var` keyword may be used in the following contexts:</span></span>  
  
-   <span data-ttu-id="df7f3-111">En variables locales (variables declaradas en el ámbito del método), tal y como se muestra en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="df7f3-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>  
  
-   <span data-ttu-id="df7f3-112">En una instrucción de inicialización [for](../../../csharp/language-reference/keywords/for.md).</span><span class="sxs-lookup"><span data-stu-id="df7f3-112">In a [for](../../../csharp/language-reference/keywords/for.md) initialization statement.</span></span>  
  
    ```csharp  
    for(var x = 1; x < 10; x++)  
    ```  
  
-   <span data-ttu-id="df7f3-113">En una instrucción de inicialización [foreach](../../../csharp/language-reference/keywords/foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="df7f3-113">In a [foreach](../../../csharp/language-reference/keywords/foreach-in.md) initialization statement.</span></span>  
  
    ```csharp  
    foreach(var item in list){...}  
    ```  
  
-   <span data-ttu-id="df7f3-114">En una instrucción [using](../../../csharp/language-reference/keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="df7f3-114">In a [using](../../../csharp/language-reference/keywords/using-statement.md) statement.</span></span>  
  
    ```csharp  
    using (var file = new StreamReader("C:\\myfile.txt")) {...}  
    ```  
  
 <span data-ttu-id="df7f3-115">Para obtener más información, vea [Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span><span class="sxs-lookup"><span data-stu-id="df7f3-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>  
  
## <a name="var-and-anonymous-types"></a><span data-ttu-id="df7f3-116">var y tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="df7f3-116">var and Anonymous Types</span></span>  
 <span data-ttu-id="df7f3-117">En muchos casos, el uso de `var` es opcional y es simplemente una comodidad sintáctica.</span><span class="sxs-lookup"><span data-stu-id="df7f3-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="df7f3-118">Pero cuando una variable se inicializa con un tipo anónimo, la variable se debe declarar como `var` si necesita acceder más adelante a las propiedades del objeto.</span><span class="sxs-lookup"><span data-stu-id="df7f3-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="df7f3-119">Se trata de un escenario común en expresiones de consulta [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df7f3-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="df7f3-120">Para obtener más información, consulte [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md) (Tipos anónimos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="df7f3-120">For more information, see [Anonymous Types](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).</span></span>  
  
 <span data-ttu-id="df7f3-121">Desde el punto de vista del código fuente, un tipo anónimo no tiene nombre.</span><span class="sxs-lookup"><span data-stu-id="df7f3-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="df7f3-122">Por lo tanto, si una variable de consulta se ha inicializado con `var`, la única manera de tener acceso a las propiedades de la secuencia de objetos devuelta consiste en usar `var` como el tipo de la variable de iteración en la instrucción `foreach`.</span><span class="sxs-lookup"><span data-stu-id="df7f3-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#44](../../../csharp/programming-guide/arrays/codesnippet/CSharp/implicitly-typed-local-variables_2.cs)]  
  
## <a name="remarks"></a><span data-ttu-id="df7f3-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="df7f3-123">Remarks</span></span>  
 <span data-ttu-id="df7f3-124">Las siguientes restricciones se aplican a las declaraciones de variable con tipo implícito:</span><span class="sxs-lookup"><span data-stu-id="df7f3-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>  
  
-   <span data-ttu-id="df7f3-125">`var` solo se puede usar cuando una variable local se declara e inicializa en la misma instrucción; la variable no se puede inicializar en null ni en un grupo de métodos o una función anónima.</span><span class="sxs-lookup"><span data-stu-id="df7f3-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>  
  
-   <span data-ttu-id="df7f3-126">`var` no se puede usar en campos en el ámbito de clase.</span><span class="sxs-lookup"><span data-stu-id="df7f3-126">`var` cannot be used on fields at class scope.</span></span>  
  
-   <span data-ttu-id="df7f3-127">Las variables declaradas con `var` no se pueden usar en la expresión de inicialización.</span><span class="sxs-lookup"><span data-stu-id="df7f3-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="df7f3-128">En otras palabras, esta expresión es válida `: int i = (i = 20);`, pero esta expresión genera un error en tiempo de compilación: `var i = (i = 20);`</span><span class="sxs-lookup"><span data-stu-id="df7f3-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>  
  
-   <span data-ttu-id="df7f3-129">No se pueden inicializar varias variables con tipo implícito en la misma instrucción.</span><span class="sxs-lookup"><span data-stu-id="df7f3-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>  
  
-   <span data-ttu-id="df7f3-130">Si en el ámbito se encuentra un tipo con nombre `var`, la palabra clave `var` se resolverá en ese nombre de tipo y no se tratará como parte de una declaración de variable local con tipo implícito.</span><span class="sxs-lookup"><span data-stu-id="df7f3-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>  
  
 <span data-ttu-id="df7f3-131">Es posible que `var` también pueda resultar útil con expresiones de consulta en las que es difícil determinar el tipo construido exacto de la variable de consulta.</span><span class="sxs-lookup"><span data-stu-id="df7f3-131">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="df7f3-132">Esto puede ocurrir con las operaciones de agrupamiento y ordenación.</span><span class="sxs-lookup"><span data-stu-id="df7f3-132">This can occur with grouping and ordering operations.</span></span>  
  
 <span data-ttu-id="df7f3-133">La palabra clave `var` también puede ser útil cuando resulte tedioso escribir el tipo específico de la variable en el teclado, o sea obvio o no aumente la legibilidad del código.</span><span class="sxs-lookup"><span data-stu-id="df7f3-133">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="df7f3-134">Un ejemplo en el que `var` resulta útil de esta manera es cuando se usa con tipos genéricos anidados, como los que se emplean con las operaciones de grupo.</span><span class="sxs-lookup"><span data-stu-id="df7f3-134">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="df7f3-135">En la siguiente consulta, el tipo de la variable de consulta es `IEnumerable<IGrouping<string, Student>>`.</span><span class="sxs-lookup"><span data-stu-id="df7f3-135">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="df7f3-136">Siempre que usted y otras personas que deban mantener el código comprendan esto, no hay ningún problema con el uso de tipos implícitos por comodidad y brevedad.</span><span class="sxs-lookup"><span data-stu-id="df7f3-136">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>  
  
 [!code-csharp[cscsrefQueryKeywords#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/implicitly-typed-local-variables_3.cs)]  
  
 <span data-ttu-id="df7f3-137">Pero el uso de `var` supone al menos la posibilidad de que el código sea más difícil de comprender para otros programadores.</span><span class="sxs-lookup"><span data-stu-id="df7f3-137">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="df7f3-138">Por ese motivo, la documentación de C# por lo general solo usa `var` cuando es necesario.</span><span class="sxs-lookup"><span data-stu-id="df7f3-138">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7f3-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="df7f3-139">See Also</span></span>  
 [<span data-ttu-id="df7f3-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="df7f3-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="df7f3-141">Matrices con tipo implícito</span><span class="sxs-lookup"><span data-stu-id="df7f3-141">Implicitly Typed Arrays</span></span>](../../../csharp/programming-guide/arrays/implicitly-typed-arrays.md)  
 [<span data-ttu-id="df7f3-142">Cómo: Usar matrices y variables locales con tipo implícito en expresiones de consulta</span><span class="sxs-lookup"><span data-stu-id="df7f3-142">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)  
 [<span data-ttu-id="df7f3-143">Tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="df7f3-143">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="df7f3-144">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="df7f3-144">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 [<span data-ttu-id="df7f3-145">var</span><span class="sxs-lookup"><span data-stu-id="df7f3-145">var</span></span>](../../../csharp/language-reference/keywords/var.md)  
 [<span data-ttu-id="df7f3-146">Expresiones de consulta LINQ</span><span class="sxs-lookup"><span data-stu-id="df7f3-146">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [<span data-ttu-id="df7f3-147">LINQ (Language Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="df7f3-147">LINQ (Language-Integrated Query)</span></span>](../../../csharp/linq/index.md)  
 [<span data-ttu-id="df7f3-148">for</span><span class="sxs-lookup"><span data-stu-id="df7f3-148">for</span></span>](../../../csharp/language-reference/keywords/for.md)  
 [<span data-ttu-id="df7f3-149">foreach, in</span><span class="sxs-lookup"><span data-stu-id="df7f3-149">foreach, in</span></span>](../../../csharp/language-reference/keywords/foreach-in.md)  
 [<span data-ttu-id="df7f3-150">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="df7f3-150">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
