---
title: 'Expresiones de coincidencia (F #)'
description: 'Obtenga información sobre cómo la expresión de coincidencia en F # proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.'
ms.date: 04/19/2018
ms.openlocfilehash: e4cb82f20fe82bff562736557c2346562c557f59
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2018
ms.locfileid: "44221849"
---
# <a name="match-expressions"></a><span data-ttu-id="481f7-103">Expresiones de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="481f7-103">Match expressions</span></span>

<span data-ttu-id="481f7-104">El `match` expresión proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="481f7-104">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="481f7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="481f7-105">Syntax</span></span>

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a><span data-ttu-id="481f7-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="481f7-106">Remarks</span></span>

<span data-ttu-id="481f7-107">Las expresiones de coincidencia de patrón permiten bifurcaciones complejas basadas en la comparación de una expresión de prueba con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="481f7-107">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="481f7-108">En el `match` expresión, el *expresión de prueba* se compara con cada modelo a su vez, y cuando se encuentra una coincidencia, la correspondiente *expresión de resultado* se evalúa y el valor resultante es se devuelve como el valor de la expresión de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="481f7-108">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="481f7-109">El patrón de coincidencia de función que se muestra en la sintaxis anterior es una expresión lambda en el patrón de coincidencia se realiza inmediatamente en el argumento.</span><span class="sxs-lookup"><span data-stu-id="481f7-109">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="481f7-110">El patrón de coincidencia de función que se muestra en la sintaxis anterior es equivalente a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="481f7-110">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

<span data-ttu-id="481f7-111">Para obtener más información sobre las expresiones lambda, vea [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="481f7-111">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="481f7-112">El conjunto completo de patrones debe cubrir a todas las coincidencias de la variable de entrada.</span><span class="sxs-lookup"><span data-stu-id="481f7-112">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="481f7-113">Con frecuencia, puede usar el patrón de carácter comodín (`_`) como el último patrón para que coincida con los valores de entrada anteriormente no coincidentes.</span><span class="sxs-lookup"><span data-stu-id="481f7-113">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="481f7-114">El código siguiente muestra algunas de las formas en que el `match` se usa la expresión.</span><span class="sxs-lookup"><span data-stu-id="481f7-114">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="481f7-115">Para obtener una referencia y ejemplos de todos los posibles modelos que se pueden usar, consulte [coincidencia de patrones](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="481f7-115">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="481f7-116">Protecciones en los modelos</span><span class="sxs-lookup"><span data-stu-id="481f7-116">Guards on patterns</span></span>

<span data-ttu-id="481f7-117">Puede usar un `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón.</span><span class="sxs-lookup"><span data-stu-id="481f7-117">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="481f7-118">Una cláusula de ese tipo se conoce como un *protegerse*.</span><span class="sxs-lookup"><span data-stu-id="481f7-118">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="481f7-119">La expresión que sigue el `when` palabra clave no se evalúa a menos que se realiza una coincidencia para el modelo asociado a esa restricción.</span><span class="sxs-lookup"><span data-stu-id="481f7-119">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="481f7-120">El ejemplo siguiente muestra el uso de una restricción para especificar un intervalo numérico para un modelo de variable.</span><span class="sxs-lookup"><span data-stu-id="481f7-120">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="481f7-121">Tenga en cuenta que se combinan varias condiciones mediante operadores booleanos.</span><span class="sxs-lookup"><span data-stu-id="481f7-121">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="481f7-122">Tenga en cuenta que dado que no se puede usar valores distintos de literales en el patrón, debe usar un `when` cláusula si tiene alguna parte de la entrada con un valor de comparación.</span><span class="sxs-lookup"><span data-stu-id="481f7-122">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="481f7-123">Esto se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="481f7-123">This is shown in the following code:</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

<span data-ttu-id="481f7-124">Tenga en cuenta que cuando un patrón de unión está cubierto por una restricción, la protección se aplica a **todas** de los patrones, no solo la última de ellas.</span><span class="sxs-lookup"><span data-stu-id="481f7-124">Note that when a union pattern is covered by a guard, the guard applies to **all** of the patterns, not just the last one.</span></span> <span data-ttu-id="481f7-125">Por ejemplo, dado el código siguiente, el guardián `when a > 12` se aplica a ambos `A a` y `B a`:</span><span class="sxs-lookup"><span data-stu-id="481f7-125">For example, given the following code, the guard `when a > 12` applies to both `A a` and `B a`:</span></span>

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a><span data-ttu-id="481f7-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="481f7-126">See also</span></span>

- [<span data-ttu-id="481f7-127">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="481f7-127">F# Language Reference</span></span>](index.md)  
- [<span data-ttu-id="481f7-128">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="481f7-128">Active Patterns</span></span>](active-patterns.md)  
- [<span data-ttu-id="481f7-129">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="481f7-129">Pattern Matching</span></span>](pattern-matching.md)  
