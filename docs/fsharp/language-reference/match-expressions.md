---
title: Expresiones match (F#)
description: "Obtenga información acerca de cómo la expresión de coincidencia de F # proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8854b713-255a-408d-942a-e80ab52fd2a4
ms.openlocfilehash: c8b9be744cfa7bc76f0d663b12abd66f8757fc56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="match-expressions"></a><span data-ttu-id="97b00-104">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="97b00-104">Match Expressions</span></span>

<span data-ttu-id="97b00-105">El `match` expresión proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="97b00-105">The `match` expression provides branching control that is based on the comparison of an expression with a set of patterns.</span></span>

## <a name="syntax"></a><span data-ttu-id="97b00-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="97b00-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="97b00-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="97b00-107">Remarks</span></span>

<span data-ttu-id="97b00-108">Las expresiones de búsqueda de coincidencias de patrón permiten bifurcaciones complejas basadas en la comparación de una expresión de prueba con un conjunto de patrones.</span><span class="sxs-lookup"><span data-stu-id="97b00-108">The pattern matching expressions allow for complex branching based on the comparison of a test expression with a set of patterns.</span></span> <span data-ttu-id="97b00-109">En el `match` expresión, el *expresión de prueba* se compara con cada modelo a su vez, y cuando se encuentra una coincidencia, la correspondiente *expresión de resultado* se evalúa y el valor resultante es se devuelve como el valor de la expresión match.</span><span class="sxs-lookup"><span data-stu-id="97b00-109">In the `match` expression, the *test-expression* is compared with each pattern in turn, and when a match is found, the corresponding *result-expression* is evaluated and the resulting value is returned as the value of the match expression.</span></span>

<span data-ttu-id="97b00-110">El patrón de coincidencia de función que se muestra en la sintaxis anterior es una expresión lambda en qué modelo de búsqueda de coincidencias se realiza inmediatamente en el argumento.</span><span class="sxs-lookup"><span data-stu-id="97b00-110">The pattern matching function shown in the previous syntax is a lambda expression in which pattern matching is performed immediately on the argument.</span></span> <span data-ttu-id="97b00-111">La coincidencia de función que se muestra en la sintaxis anterior es equivalente a la siguiente.</span><span class="sxs-lookup"><span data-stu-id="97b00-111">The pattern matching function shown in the previous syntax is equivalent to the following.</span></span>

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```    

<span data-ttu-id="97b00-112">Para obtener más información sobre las expresiones lambda, vea [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md).</span><span class="sxs-lookup"><span data-stu-id="97b00-112">For more information about lambda expressions, see [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md).</span></span>

<span data-ttu-id="97b00-113">El conjunto de modelos debe cubrir a todas las posibles coincidencias de la variable de entrada.</span><span class="sxs-lookup"><span data-stu-id="97b00-113">The whole set of patterns should cover all the possible matches of the input variable.</span></span> <span data-ttu-id="97b00-114">Con frecuencia, puede usar el patrón de carácter comodín (`_`) como el último modelo para que coincida con los valores de entrada anteriormente no coincidentes.</span><span class="sxs-lookup"><span data-stu-id="97b00-114">Frequently, you use the wildcard pattern (`_`) as the last pattern to match any previously unmatched input values.</span></span>

<span data-ttu-id="97b00-115">El código siguiente muestra algunas de las formas en que el `match` se utiliza la expresión.</span><span class="sxs-lookup"><span data-stu-id="97b00-115">The following code illustrates some of the ways in which the `match` expression is used.</span></span> <span data-ttu-id="97b00-116">Para obtener una referencia y ejemplos de todos los posibles modelos que se pueden usar, vea [coincidencia de patrones](pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="97b00-116">For a reference and examples of all the possible patterns that can be used, see [Pattern Matching](pattern-matching.md).</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a><span data-ttu-id="97b00-117">Protecciones en los modelos</span><span class="sxs-lookup"><span data-stu-id="97b00-117">Guards on Patterns</span></span>

<span data-ttu-id="97b00-118">Puede usar un `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón.</span><span class="sxs-lookup"><span data-stu-id="97b00-118">You can use a `when` clause to specify an additional condition that the variable must satisfy to match a pattern.</span></span> <span data-ttu-id="97b00-119">Una cláusula de ese tipo se conoce como un *protegerse*.</span><span class="sxs-lookup"><span data-stu-id="97b00-119">Such a clause is referred to as a *guard*.</span></span> <span data-ttu-id="97b00-120">La expresión que sigue el `when` palabra clave no se evalúa a menos que se encuentre una coincidencia con el modelo asociado a esa protección.</span><span class="sxs-lookup"><span data-stu-id="97b00-120">The expression following the `when` keyword is not evaluated unless a match is made to the pattern associated with that guard.</span></span>

<span data-ttu-id="97b00-121">En el ejemplo siguiente se muestra el uso de una restricción para especificar un intervalo numérico para un variable (modelo).</span><span class="sxs-lookup"><span data-stu-id="97b00-121">The following example illustrates the use of a guard to specify a numeric range for a variable pattern.</span></span> <span data-ttu-id="97b00-122">Tenga en cuenta que se combinan varias condiciones mediante operadores booleanos.</span><span class="sxs-lookup"><span data-stu-id="97b00-122">Note that multiple conditions are combined by using Boolean operators.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

<span data-ttu-id="97b00-123">Tenga en cuenta que dado que no se puede usar valores distintos de literales en el modelo, debe utilizar un `when` cláusula si tiene alguna parte de la entrada con un valor de comparación.</span><span class="sxs-lookup"><span data-stu-id="97b00-123">Note that because values other than literals cannot be used in the pattern, you must use a `when` clause if you have to compare some part of the input against a value.</span></span> <span data-ttu-id="97b00-124">Esto se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="97b00-124">This is shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

## <a name="see-also"></a><span data-ttu-id="97b00-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="97b00-125">See Also</span></span>

[<span data-ttu-id="97b00-126">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="97b00-126">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="97b00-127">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="97b00-127">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="97b00-128">Coincidencia de patrones</span><span class="sxs-lookup"><span data-stu-id="97b00-128">Pattern Matching</span></span>](pattern-matching.md)
