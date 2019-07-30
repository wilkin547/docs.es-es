---
title: Coincidencia de modelos
description: Obtenga información sobre cómo se usan F# los patrones en para comparar datos con estructuras lógicas, descomponer datos en elementos constituyentes o extraer información de los datos.
ms.date: 05/16/2016
ms.openlocfilehash: 156bb670e0c494a3d515eab03e2e4672d6743dec
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627301"
---
# <a name="pattern-matching"></a><span data-ttu-id="b5d9e-103">Coincidencia de modelos</span><span class="sxs-lookup"><span data-stu-id="b5d9e-103">Pattern Matching</span></span>

<span data-ttu-id="b5d9e-104">Los patrones son reglas para transformar los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="b5d9e-105">Se usan en todo el F# lenguaje para comparar los datos con una estructura lógica o estructuras, descomponer los datos en partes constituyentes o extraer información de los datos de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="b5d9e-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b5d9e-106">Remarks</span></span>

<span data-ttu-id="b5d9e-107">Los patrones se usan en muchas construcciones de lenguaje, como la `match` expresión.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="b5d9e-108">Se utilizan cuando se procesan argumentos para funciones en `let` enlaces, expresiones lambda y en los controladores de excepciones asociados a la `try...with` expresión.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="b5d9e-109">Para obtener más información, vea [expresiones de coincidencia](match-expressions.md), [enlaces Let](./functions/let-bindings.md), [expresiones lambda: La `fun` palabra](./functions/lambda-expressions-the-fun-keyword.md)clave y[excepciones: `try...with` Expresión.](/.exception-handling/the-try-with-expression.md)</span><span class="sxs-lookup"><span data-stu-id="b5d9e-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](/.exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="b5d9e-110">Por ejemplo, en la `match` expresión, el *patrón* es lo que sigue al símbolo de canalización.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="b5d9e-111">Cada patrón actúa como una regla para transformar la entrada de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="b5d9e-112">En la `match` expresión, cada patrón se examina a su vez para ver si los datos de entrada son compatibles con el patrón.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="b5d9e-113">Si se encuentra una coincidencia, se ejecuta la expresión de resultado.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="b5d9e-114">Si no se encuentra ninguna coincidencia, se prueba la siguiente regla de patrón.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="b5d9e-115">La parte de *condición* opcional when se explica en [expresiones de coincidencia](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="b5d9e-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="b5d9e-116">Los patrones admitidos se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="b5d9e-117">En tiempo de ejecución, la entrada se prueba con cada uno de los patrones siguientes en el orden indicado en la tabla y los patrones se aplican de forma recursiva, de la primera a la última como aparecen en el código y de izquierda a derecha para los patrones de cada línea.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="b5d9e-118">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b5d9e-118">Name</span></span>|<span data-ttu-id="b5d9e-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b5d9e-119">Description</span></span>|<span data-ttu-id="b5d9e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="b5d9e-121">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="b5d9e-121">Constant pattern</span></span>|<span data-ttu-id="b5d9e-122">Cualquier literal numérico, de carácter o de cadena, una constante de enumeración o un identificador literal definido</span><span class="sxs-lookup"><span data-stu-id="b5d9e-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="b5d9e-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="b5d9e-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="b5d9e-124">Patrón de identificador</span><span class="sxs-lookup"><span data-stu-id="b5d9e-124">Identifier pattern</span></span>|<span data-ttu-id="b5d9e-125">Un valor de caso de una Unión discriminada, una etiqueta de excepción o un caso de modelo activo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="b5d9e-126">Patrón de variable</span><span class="sxs-lookup"><span data-stu-id="b5d9e-126">Variable pattern</span></span>|<span data-ttu-id="b5d9e-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="b5d9e-128">`as`ajedrez</span><span class="sxs-lookup"><span data-stu-id="b5d9e-128">`as` pattern</span></span>|<span data-ttu-id="b5d9e-129">*patrón* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="b5d9e-130">Patrón OR</span><span class="sxs-lookup"><span data-stu-id="b5d9e-130">OR pattern</span></span>|<span data-ttu-id="b5d9e-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="b5d9e-132">Y patrón</span><span class="sxs-lookup"><span data-stu-id="b5d9e-132">AND pattern</span></span>|<span data-ttu-id="b5d9e-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="b5d9e-134">Patrón de cons</span><span class="sxs-lookup"><span data-stu-id="b5d9e-134">Cons pattern</span></span>|<span data-ttu-id="b5d9e-135">*Identifier* :: *List-Identifier*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="b5d9e-136">Patrón de lista</span><span class="sxs-lookup"><span data-stu-id="b5d9e-136">List pattern</span></span>|<span data-ttu-id="b5d9e-137">[ *pattern_1*;...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="b5d9e-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="b5d9e-138">Patrón de matriz</span><span class="sxs-lookup"><span data-stu-id="b5d9e-138">Array pattern</span></span>|<span data-ttu-id="b5d9e-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="b5d9e-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="b5d9e-140">Patrón entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="b5d9e-140">Parenthesized pattern</span></span>|<span data-ttu-id="b5d9e-141">( *pattern* )</span><span class="sxs-lookup"><span data-stu-id="b5d9e-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="b5d9e-142">Patrón de tupla</span><span class="sxs-lookup"><span data-stu-id="b5d9e-142">Tuple pattern</span></span>|<span data-ttu-id="b5d9e-143">( *pattern_1*,..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="b5d9e-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="b5d9e-144">Patrón de registro</span><span class="sxs-lookup"><span data-stu-id="b5d9e-144">Record pattern</span></span>|<span data-ttu-id="b5d9e-145">{ *identificador1* = *pattern_1*;...; *identifier_n*  =  *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="b5d9e-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="b5d9e-146">Patrón de carácter comodín</span><span class="sxs-lookup"><span data-stu-id="b5d9e-146">Wildcard pattern</span></span>|<span data-ttu-id="b5d9e-147">_</span><span class="sxs-lookup"><span data-stu-id="b5d9e-147">_</span></span>|`_`|
|<span data-ttu-id="b5d9e-148">Patrón junto con anotación de tipo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-148">Pattern together with type annotation</span></span>|<span data-ttu-id="b5d9e-149">*patrón* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="b5d9e-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="b5d9e-150">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-150">Type test pattern</span></span>|<span data-ttu-id="b5d9e-151">:?</span><span class="sxs-lookup"><span data-stu-id="b5d9e-151">:?</span></span> <span data-ttu-id="b5d9e-152">*tipo* de [como *identificador* ]</span><span class="sxs-lookup"><span data-stu-id="b5d9e-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="b5d9e-153">Patrón null</span><span class="sxs-lookup"><span data-stu-id="b5d9e-153">Null pattern</span></span>|<span data-ttu-id="b5d9e-154">nulo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="b5d9e-155">Patrones constantes</span><span class="sxs-lookup"><span data-stu-id="b5d9e-155">Constant Patterns</span></span>

<span data-ttu-id="b5d9e-156">Los patrones constantes son los literales numéricos, de carácter y de cadena, las constantes de enumeración (con el nombre de tipo de enumeración incluido).</span><span class="sxs-lookup"><span data-stu-id="b5d9e-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="b5d9e-157">Una `match` expresión que solo tiene patrones constantes puede compararse con una instrucción Case en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="b5d9e-158">La entrada se compara con el valor literal y el patrón coincide si los valores son iguales.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="b5d9e-159">El tipo del literal debe ser compatible con el tipo de la entrada.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="b5d9e-160">En el ejemplo siguiente se muestra el uso de patrones literales y también se usa un patrón de variable y un patrón o.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="b5d9e-161">Otro ejemplo de un patrón literal es un modelo basado en constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="b5d9e-162">Debe especificar el nombre del tipo de enumeración al usar constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="b5d9e-163">Patrones de identificador</span><span class="sxs-lookup"><span data-stu-id="b5d9e-163">Identifier Patterns</span></span>

<span data-ttu-id="b5d9e-164">Si el patrón es una cadena de caracteres que forma un identificador válido, el formato del identificador determina cómo coincide el patrón.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="b5d9e-165">Si el identificador es más largo que un carácter único y comienza con un carácter en mayúsculas, el compilador intenta establecer una coincidencia con el patrón de identificador.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="b5d9e-166">El identificador de este patrón puede ser un valor marcado con el atributo literal, un caso de Unión discriminada, un identificador de excepción o un caso de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="b5d9e-167">Si no se encuentra ningún identificador coincidente, se produce un error en la coincidencia y la siguiente regla de patrón, el patrón de variable, se compara con la entrada.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="b5d9e-168">Los patrones de Unión discriminada pueden ser casos con nombre sencillos o pueden tener un valor o una tupla que contiene varios valores.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="b5d9e-169">Si hay un valor, debe especificar un identificador para el valor.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="b5d9e-170">En el caso de una tupla, debe proporcionar un patrón de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión con nombre.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="b5d9e-171">Vea los ejemplos de código de esta sección para obtener ejemplos.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="b5d9e-172">El `option` tipo es una Unión discriminada que tiene dos casos, `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="b5d9e-173">Un caso (`Some`) tiene un valor, pero el otro (`None`) es simplemente un caso con nombre.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="b5d9e-174">Por lo `Some` tanto, debe tener una variable para el valor asociado `Some` al caso, pero `None` debe aparecer por sí sola.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="b5d9e-175">En el código siguiente, se proporciona `var1` a la variable el valor que se obtiene al buscar coincidencias con el `Some` caso.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="b5d9e-176">En el ejemplo siguiente, la `PersonName` Unión discriminada contiene una mezcla de cadenas y caracteres que representan las posibles formas de los nombres.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="b5d9e-177">Los casos de la Unión discriminada son `FirstOnly`, `LastOnly`y `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="b5d9e-178">En el caso de las uniones discriminadas que tienen campos con nombre, use el signo igual (=) para extraer el valor de un campo con nombre.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="b5d9e-179">Por ejemplo, considere una Unión discriminada con una declaración como la siguiente.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="b5d9e-180">Puede usar los campos con nombre en una expresión de coincidencia de patrones como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="b5d9e-181">El uso del campo con nombre es opcional, por lo que en el ejemplo anterior `Circle(r)` , `Circle(radius = r)` y tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="b5d9e-182">Cuando especifique varios campos, use el punto y coma (;) como separador.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="b5d9e-183">Los modelos activos permiten definir una coincidencia de patrones personalizada más compleja.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="b5d9e-184">Para obtener más información sobre los patrones activos, vea [patrones activos](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="b5d9e-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="b5d9e-185">El caso en el que el identificador es una excepción se usa en la coincidencia de patrones en el contexto de los controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="b5d9e-186">Para obtener información sobre la coincidencia de patrones en el [control de excepciones, vea excepciones: `try...with` Expresión.](/.exception-handling/the-try-with-expression.md)</span><span class="sxs-lookup"><span data-stu-id="b5d9e-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](/.exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="b5d9e-187">Patrones de variables</span><span class="sxs-lookup"><span data-stu-id="b5d9e-187">Variable Patterns</span></span>

<span data-ttu-id="b5d9e-188">El patrón variable asigna el valor que coincide con un nombre de variable, que luego está disponible para su uso en la expresión de ejecución a la derecha del `->` símbolo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="b5d9e-189">Un patrón variable solo coincide con cualquier entrada, pero los modelos variables suelen aparecer dentro de otros patrones, lo que permite que las estructuras más complejas, como las tuplas y las matrices, se descompongan en variables.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="b5d9e-190">En el ejemplo siguiente se muestra un patrón de variable dentro de un patrón de tupla.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="b5d9e-191">como patrón</span><span class="sxs-lookup"><span data-stu-id="b5d9e-191">as Pattern</span></span>

<span data-ttu-id="b5d9e-192">El `as` patrón es un patrón que tiene una `as` cláusula anexada.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="b5d9e-193">La `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de una `match` expresión, o bien, en el caso en que este patrón se utiliza en `let` un enlace, el nombre se agrega como un enlace al ámbito local.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="b5d9e-194">En el ejemplo siguiente se `as` usa un patrón.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="b5d9e-195">Patrón OR</span><span class="sxs-lookup"><span data-stu-id="b5d9e-195">OR Pattern</span></span>

<span data-ttu-id="b5d9e-196">El patrón o se utiliza cuando los datos de entrada pueden coincidir con varios patrones y desea ejecutar el mismo código como resultado.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="b5d9e-197">Los tipos de ambos lados del patrón o deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="b5d9e-198">En el siguiente ejemplo se muestra el patrón o.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="b5d9e-199">Y patrón</span><span class="sxs-lookup"><span data-stu-id="b5d9e-199">AND Pattern</span></span>

<span data-ttu-id="b5d9e-200">El patrón y requiere que la entrada coincida con dos patrones.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="b5d9e-201">Los tipos de ambos lados del patrón y deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="b5d9e-202">El ejemplo siguiente es como `detectZeroTuple` el que se muestra en la sección [modelo de tupla](https://msdn.microsoft.com/library/#tuple) más adelante en este `var1` tema `var2` , pero aquí y se obtienen como valores mediante el patrón y.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="b5d9e-203">Patrón de cons</span><span class="sxs-lookup"><span data-stu-id="b5d9e-203">Cons Pattern</span></span>

<span data-ttu-id="b5d9e-204">El patrón cons se usa para descomponer una lista en el primer elemento, el *encabezado*y una lista que contiene los elementos restantes, la *cola*.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="b5d9e-205">Patrón de lista</span><span class="sxs-lookup"><span data-stu-id="b5d9e-205">List Pattern</span></span>

<span data-ttu-id="b5d9e-206">El patrón de lista permite descomponer listas en varios elementos.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="b5d9e-207">El propio patrón de lista solo puede coincidir con las listas de un número específico de elementos.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="b5d9e-208">Patrón de matriz</span><span class="sxs-lookup"><span data-stu-id="b5d9e-208">Array Pattern</span></span>

<span data-ttu-id="b5d9e-209">El patrón de matriz se asemeja al patrón de lista y se puede usar para descomponer las matrices de una longitud específica.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="b5d9e-210">Patrón entre paréntesis</span><span class="sxs-lookup"><span data-stu-id="b5d9e-210">Parenthesized Pattern</span></span>

<span data-ttu-id="b5d9e-211">Los paréntesis se pueden agrupar en torno a patrones para lograr la asociatividad deseada.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="b5d9e-212">En el ejemplo siguiente, los paréntesis se usan para controlar la asociatividad entre un patrón AND y un patrón cons.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="b5d9e-213">Patrón de tupla</span><span class="sxs-lookup"><span data-stu-id="b5d9e-213">Tuple Pattern</span></span>

<span data-ttu-id="b5d9e-214">El patrón de tupla asocia la entrada en forma de tupla y permite descomponer la tupla en sus elementos constituyentes mediante el uso de variables de coincidencia de patrones para cada posición de la tupla.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="b5d9e-215">En el ejemplo siguiente se muestra el patrón de tupla y también se usan patrones literales, patrones de variables y el patrón de caracteres comodín.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="b5d9e-216">Patrón de registro</span><span class="sxs-lookup"><span data-stu-id="b5d9e-216">Record Pattern</span></span>

<span data-ttu-id="b5d9e-217">El patrón de registro se usa para descomponer registros para extraer los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="b5d9e-218">El patrón no tiene que hacer referencia a todos los campos del registro; los campos omitidos simplemente no participan en la coincidencia y no se extraen.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="b5d9e-219">Patrón de carácter comodín</span><span class="sxs-lookup"><span data-stu-id="b5d9e-219">Wildcard Pattern</span></span>

<span data-ttu-id="b5d9e-220">El patrón de caracteres comodín se representa mediante el carácter`_`de subrayado () y coincide con cualquier entrada, al igual que el patrón de variable, con la excepción de que la entrada se descarta en lugar de asignarla a una variable.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="b5d9e-221">El patrón de caracteres comodín se usa a menudo en otros patrones como un marcador de posición para los valores que no son necesarios en la `->` expresión a la derecha del símbolo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="b5d9e-222">El patrón de caracteres comodín también se usa con frecuencia al final de una lista de patrones para buscar coincidencias con cualquier entrada no coincidente.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="b5d9e-223">El patrón de caracteres comodín se muestra en muchos ejemplos de código de este tema.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="b5d9e-224">Vea el código anterior para ver un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="b5d9e-225">Patrones que tienen anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="b5d9e-226">Los patrones pueden tener anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-226">Patterns can have type annotations.</span></span> <span data-ttu-id="b5d9e-227">Estos se comportan como otras anotaciones de tipo e inferencia de la guía como otras anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="b5d9e-228">Se requieren paréntesis en torno a las anotaciones de tipo en los patrones.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="b5d9e-229">En el código siguiente se muestra un patrón que tiene una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="b5d9e-230">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="b5d9e-230">Type Test Pattern</span></span>

<span data-ttu-id="b5d9e-231">El modelo de prueba de tipo se usa para hacer coincidir la entrada con un tipo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="b5d9e-232">Si el tipo de entrada es una coincidencia con (o un tipo derivado de) el tipo especificado en el patrón, la coincidencia se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="b5d9e-233">En el siguiente ejemplo se muestra el modelo de prueba de tipo.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="b5d9e-234">Patrón null</span><span class="sxs-lookup"><span data-stu-id="b5d9e-234">Null Pattern</span></span>

<span data-ttu-id="b5d9e-235">El patrón null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten un valor null.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="b5d9e-236">Los patrones NULL se utilizan con frecuencia al interoperar con código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="b5d9e-237">Por ejemplo, el valor devuelto de una API de .net podría ser la entrada `match` a una expresión.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="b5d9e-238">Puede controlar el flujo del programa en función de si el valor devuelto es NULL y también de otras características del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="b5d9e-239">Puede usar el patrón null para evitar que los valores NULL se propaguen al resto del programa.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="b5d9e-240">En el ejemplo siguiente se usa el patrón NULL y el patrón variable.</span><span class="sxs-lookup"><span data-stu-id="b5d9e-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="b5d9e-241">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5d9e-241">See also</span></span>

- [<span data-ttu-id="b5d9e-242">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="b5d9e-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="b5d9e-243">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="b5d9e-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="b5d9e-244">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="b5d9e-244">F# Language Reference</span></span>](index.md)
