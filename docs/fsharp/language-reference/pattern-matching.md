---
title: Coincidencia de modelos [F#]
description: "Obtenga información acerca de cómo se utilizan los patrones en F # para comparar los datos con estructuras lógicas, descomponer datos en sus partes constituyentes o extraer información de datos."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5562ee98-e2f1-4dcd-8e2f-16ae27baaade
ms.openlocfilehash: 7c7a3110a8f34c0c96c12d4584010a9ac4b485fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="pattern-matching"></a><span data-ttu-id="0c164-104">Coincidencia de modelos</span><span class="sxs-lookup"><span data-stu-id="0c164-104">Pattern Matching</span></span>

<span data-ttu-id="0c164-105">Los patrones son reglas para transformar los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="0c164-105">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="0c164-106">Se utilizan a lo largo del lenguaje F # para comparar los datos con una estructura lógica o estructuras, descomponer datos en sus partes constituyentes o extraer información de los datos de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="0c164-106">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>


## <a name="remarks"></a><span data-ttu-id="0c164-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c164-107">Remarks</span></span>
<span data-ttu-id="0c164-108">Los modelos se utilizan en muchas construcciones de lenguaje, como el `match` expresión.</span><span class="sxs-lookup"><span data-stu-id="0c164-108">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="0c164-109">Se utilizan cuando se procesan argumentos para las funciones de `let` enlaces, las expresiones lambda y en los controladores de excepción asociados a la `try...with` expresión.</span><span class="sxs-lookup"><span data-stu-id="0c164-109">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="0c164-110">Para obtener más información, consulte [expresiones de coincidencia](match-expressions.md), [let (enlaces)](functions/let-bindings.md), [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md), y [excepciones: el `try...with` Expresión](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-110">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="0c164-111">Por ejemplo, en la `match` expresión, el *patrón* es lo que sigue al símbolo de canalización.</span><span class="sxs-lookup"><span data-stu-id="0c164-111">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="0c164-112">Cada modelo actúa como una regla para transformar la entrada de alguna manera.</span><span class="sxs-lookup"><span data-stu-id="0c164-112">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="0c164-113">En el `match` expresión, cada modelo se examina a su vez para ver si los datos de entrada están compatibles con el patrón.</span><span class="sxs-lookup"><span data-stu-id="0c164-113">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="0c164-114">Si se encuentra una coincidencia, se ejecuta la expresión de resultado.</span><span class="sxs-lookup"><span data-stu-id="0c164-114">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="0c164-115">Si no se encuentra una coincidencia, se probará la siguiente regla de patrón.</span><span class="sxs-lookup"><span data-stu-id="0c164-115">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="0c164-116">Opcional cuando *condición* parte se explica en [expresiones de coincidencia](match-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-116">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="0c164-117">Los modelos admitidos se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c164-117">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="0c164-118">En tiempo de ejecución, la entrada se prueba cada uno de los siguientes patrones en el orden mostrado en la tabla, y patrones son aplica de forma recursiva, de primero al último tal y como aparecen en el código y de izquierda a derecha para los patrones en cada línea.</span><span class="sxs-lookup"><span data-stu-id="0c164-118">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="0c164-119">Nombre</span><span class="sxs-lookup"><span data-stu-id="0c164-119">Name</span></span>|<span data-ttu-id="0c164-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c164-120">Description</span></span>|<span data-ttu-id="0c164-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c164-121">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="0c164-122">Patrón de constante</span><span class="sxs-lookup"><span data-stu-id="0c164-122">Constant pattern</span></span>|<span data-ttu-id="0c164-123">Cualquier numérico, carácter, o literal de cadena, una constante de enumeración o un identificador literal definido</span><span class="sxs-lookup"><span data-stu-id="0c164-123">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="0c164-124">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="0c164-124">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="0c164-125">Identificador (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-125">Identifier pattern</span></span>|<span data-ttu-id="0c164-126">Un valor de caso de una unión discriminada, una etiqueta de excepción o un caso (modelo activo)</span><span class="sxs-lookup"><span data-stu-id="0c164-126">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="0c164-127">Variable (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-127">Variable pattern</span></span>|<span data-ttu-id="0c164-128">*identifier*</span><span class="sxs-lookup"><span data-stu-id="0c164-128">*identifier*</span></span>|`a`|
|<span data-ttu-id="0c164-129">`as`patrón</span><span class="sxs-lookup"><span data-stu-id="0c164-129">`as` pattern</span></span>|<span data-ttu-id="0c164-130">*patrón de* como *identificador*</span><span class="sxs-lookup"><span data-stu-id="0c164-130">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="0c164-131">O un patrón</span><span class="sxs-lookup"><span data-stu-id="0c164-131">OR pattern</span></span>|<span data-ttu-id="0c164-132">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="0c164-132">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="0c164-133">Y el patrón</span><span class="sxs-lookup"><span data-stu-id="0c164-133">AND pattern</span></span>|<span data-ttu-id="0c164-134">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="0c164-134">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="0c164-135">Modelo de cons</span><span class="sxs-lookup"><span data-stu-id="0c164-135">Cons pattern</span></span>|<span data-ttu-id="0c164-136">*identificador* :: *identificador de la lista*</span><span class="sxs-lookup"><span data-stu-id="0c164-136">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="0c164-137">Lista (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-137">List pattern</span></span>|<span data-ttu-id="0c164-138">[ *modelo_1*;...; *modelo_n* ]</span><span class="sxs-lookup"><span data-stu-id="0c164-138">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="0c164-139">Matriz (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-139">Array pattern</span></span>|<span data-ttu-id="0c164-140">[&#124; *modelo_1*;...; *modelo_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="0c164-140">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="0c164-141">Paréntesis (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-141">Parenthesized pattern</span></span>|<span data-ttu-id="0c164-142">( *patrón* )</span><span class="sxs-lookup"><span data-stu-id="0c164-142">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="0c164-143">Tupla (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-143">Tuple pattern</span></span>|<span data-ttu-id="0c164-144">( *modelo_1*,..., *modelo_n* )</span><span class="sxs-lookup"><span data-stu-id="0c164-144">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="0c164-145">Registro (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-145">Record pattern</span></span>|<span data-ttu-id="0c164-146">{ *identificador1* = *modelo_1*;...; *identificador_n* = *modelo_n* }</span><span class="sxs-lookup"><span data-stu-id="0c164-146">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="0c164-147">Patrón de carácter comodín</span><span class="sxs-lookup"><span data-stu-id="0c164-147">Wildcard pattern</span></span>|<span data-ttu-id="0c164-148">_</span><span class="sxs-lookup"><span data-stu-id="0c164-148">_</span></span>|`_`|
|<span data-ttu-id="0c164-149">Patrón junto con las anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="0c164-149">Pattern together with type annotation</span></span>|<span data-ttu-id="0c164-150">*patrón de* : *tipo*</span><span class="sxs-lookup"><span data-stu-id="0c164-150">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="0c164-151">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="0c164-151">Type test pattern</span></span>|<span data-ttu-id="0c164-152">:?</span><span class="sxs-lookup"><span data-stu-id="0c164-152">:?</span></span> <span data-ttu-id="0c164-153">*tipo de* [como *identificador* ]</span><span class="sxs-lookup"><span data-stu-id="0c164-153">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="0c164-154">Null (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-154">Null pattern</span></span>|<span data-ttu-id="0c164-155">nulo</span><span class="sxs-lookup"><span data-stu-id="0c164-155">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="0c164-156">Modelos de constante</span><span class="sxs-lookup"><span data-stu-id="0c164-156">Constant Patterns</span></span>
<span data-ttu-id="0c164-157">Modelos de constantes son numéricos, de caracteres y literales de cadena, constantes de enumeración (con el nombre de tipo de enumeración incluidos).</span><span class="sxs-lookup"><span data-stu-id="0c164-157">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="0c164-158">Un `match` expresión que tiene modelos de constante se puede comparar con una instrucción case en otros lenguajes.</span><span class="sxs-lookup"><span data-stu-id="0c164-158">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="0c164-159">La entrada se compara con el valor literal y el modelo coincide si los valores son iguales.</span><span class="sxs-lookup"><span data-stu-id="0c164-159">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="0c164-160">El tipo del literal debe ser compatible con el tipo de la entrada.</span><span class="sxs-lookup"><span data-stu-id="0c164-160">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="0c164-161">En el ejemplo siguiente se muestra el uso de modelos de literal y también usa un variable (modelo) y un modelo de OR.</span><span class="sxs-lookup"><span data-stu-id="0c164-161">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="0c164-162">Otro ejemplo de un literal (modelo) es un modelo basado en constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="0c164-162">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="0c164-163">Debe especificar el nombre de tipo de enumeración cuando se utilizan en constantes de enumeración.</span><span class="sxs-lookup"><span data-stu-id="0c164-163">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="0c164-164">Patrones de identificador</span><span class="sxs-lookup"><span data-stu-id="0c164-164">Identifier Patterns</span></span>
<span data-ttu-id="0c164-165">Si el patrón es una cadena de caracteres que forman un identificador válido, el formato del identificador determina cómo se compara el patrón.</span><span class="sxs-lookup"><span data-stu-id="0c164-165">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="0c164-166">Si el identificador tiene más de un solo carácter y comienza con un carácter en mayúscula, el compilador intenta encontrar una coincidencia para el modelo de identificador.</span><span class="sxs-lookup"><span data-stu-id="0c164-166">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="0c164-167">El identificador de este modelo podría ser un valor que se marca con el atributo Literal, un caso de unión discriminado, un identificador de excepción o un caso de modelo activo.</span><span class="sxs-lookup"><span data-stu-id="0c164-167">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="0c164-168">Si no se encuentra ningún identificador coincidente, se produce un error en la coincidencia y la siguiente regla de patrón, el patrón de la variable, se compara con la entrada.</span><span class="sxs-lookup"><span data-stu-id="0c164-168">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="0c164-169">Patrones de unión discriminadas pueden ser simples denominado casos o pueden tener un valor o una tupla que contiene varios valores.</span><span class="sxs-lookup"><span data-stu-id="0c164-169">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="0c164-170">Si hay un valor, debe especificar un identificador para el valor.</span><span class="sxs-lookup"><span data-stu-id="0c164-170">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="0c164-171">En el caso de una tupla, debe proporcionar un patrón de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión de nombre.</span><span class="sxs-lookup"><span data-stu-id="0c164-171">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="0c164-172">Vea los ejemplos de código en esta sección para obtener ejemplos.</span><span class="sxs-lookup"><span data-stu-id="0c164-172">See the code examples in this section for examples.</span></span>

<span data-ttu-id="0c164-173">El `option` tipo es una unión discriminada que tiene dos casos, `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="0c164-173">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="0c164-174">Un caso (`Some`) tiene un valor, pero el otro (`None`) es simplemente un caso con nombre.</span><span class="sxs-lookup"><span data-stu-id="0c164-174">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="0c164-175">Por lo tanto, `Some` debe tener una variable para el valor asociado a la `Some` mayúsculas, pero `None` debe aparecer por sí sola.</span><span class="sxs-lookup"><span data-stu-id="0c164-175">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="0c164-176">En el código siguiente, la variable `var1` recibe el valor que se obtiene mediante la búsqueda de coincidencias para el `Some` caso.</span><span class="sxs-lookup"><span data-stu-id="0c164-176">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="0c164-177">En el ejemplo siguiente, la `PersonName` unión discriminada contiene una combinación de cadenas y caracteres que representan posibles formas de nombres.</span><span class="sxs-lookup"><span data-stu-id="0c164-177">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="0c164-178">Los casos de la unión discriminada son `FirstOnly`, `LastOnly`, y `FirstLast`.</span><span class="sxs-lookup"><span data-stu-id="0c164-178">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="0c164-179">Para uniones discriminadas que han asignado un nombre campos, usa el signo igual (=) para extraer el valor de un campo con nombre.</span><span class="sxs-lookup"><span data-stu-id="0c164-179">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="0c164-180">Por ejemplo, considere la posibilidad de una unión discriminada con una declaración similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c164-180">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="0c164-181">Puede usar los campos con nombre en una expresión de búsqueda de coincidencias de patrón como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="0c164-181">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="0c164-182">El uso del campo con nombre es opcional, por lo que en el ejemplo anterior, ambas `Circle(r)` y `Circle(radius = r)` tienen el mismo efecto.</span><span class="sxs-lookup"><span data-stu-id="0c164-182">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="0c164-183">Al especificar varios campos, utilice el punto y coma (;) como separador.</span><span class="sxs-lookup"><span data-stu-id="0c164-183">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="0c164-184">Modelos activos permiten definir la búsqueda de coincidencias de patrón personalizado más complejas.</span><span class="sxs-lookup"><span data-stu-id="0c164-184">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="0c164-185">Para obtener más información acerca de los patrones, vea [modelos activos](active-patterns.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-185">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="0c164-186">El caso en que el identificador es una excepción se utiliza en la coincidencia de modelos en el contexto de controladores de excepciones.</span><span class="sxs-lookup"><span data-stu-id="0c164-186">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="0c164-187">Para obtener información acerca de la coincidencia de modelos en el control de excepciones, vea [excepciones: la `try...with` expresión](exception-handling/the-try-with-expression.md).</span><span class="sxs-lookup"><span data-stu-id="0c164-187">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>


## <a name="variable-patterns"></a><span data-ttu-id="0c164-188">Patrones variables</span><span class="sxs-lookup"><span data-stu-id="0c164-188">Variable Patterns</span></span>
<span data-ttu-id="0c164-189">El modelo de variable asigna el valor coincide con un nombre de variable, que, a continuación, está disponible para su uso en la expresión de ejecución a la derecha de la `->` símbolos.</span><span class="sxs-lookup"><span data-stu-id="0c164-189">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="0c164-190">Un variable (modelo) por sí sola coincide con cualquier entrada, pero a menudo parecen patrones variables dentro de otros patrones, por lo tanto, lo que permite estructuras más complejas, como tuplas y matrices para que se puede descomponer en variables.</span><span class="sxs-lookup"><span data-stu-id="0c164-190">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="0c164-191">En el ejemplo siguiente se muestra un patrón variable dentro de un modelo de tupla.</span><span class="sxs-lookup"><span data-stu-id="0c164-191">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="0c164-192">As (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-192">as Pattern</span></span>
<span data-ttu-id="0c164-193">El `as` patrón es un modelo con un `as` cláusula anexada al mismo.</span><span class="sxs-lookup"><span data-stu-id="0c164-193">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="0c164-194">El `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de un `match` expresión, o bien, en el caso donde este patrón se utiliza en un `let` de enlace, el nombre se agrega como un enlace para el ámbito local.</span><span class="sxs-lookup"><span data-stu-id="0c164-194">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="0c164-195">En el ejemplo siguiente se usa un `as` patrón.</span><span class="sxs-lookup"><span data-stu-id="0c164-195">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="0c164-196">O un patrón</span><span class="sxs-lookup"><span data-stu-id="0c164-196">OR Pattern</span></span>
<span data-ttu-id="0c164-197">El modelo de OR se utiliza cuando los datos de entrada pueden coincidir con varios modelos, y desea ejecutar el mismo código como resultado.</span><span class="sxs-lookup"><span data-stu-id="0c164-197">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="0c164-198">Los tipos de ambos lados del modelo de OR deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="0c164-198">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="0c164-199">En el ejemplo siguiente se muestra el modelo de OR.</span><span class="sxs-lookup"><span data-stu-id="0c164-199">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="0c164-200">Y el patrón</span><span class="sxs-lookup"><span data-stu-id="0c164-200">AND Pattern</span></span>
<span data-ttu-id="0c164-201">El modelo AND exige que la entrada coincida con dos modelos.</span><span class="sxs-lookup"><span data-stu-id="0c164-201">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="0c164-202">Los tipos de ambos lados del modelo de AND deben ser compatibles.</span><span class="sxs-lookup"><span data-stu-id="0c164-202">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="0c164-203">El ejemplo siguiente es similar `detectZeroTuple` se muestra en el [tupla (modelo)](https://msdn.microsoft.com/library/#tuple) sección más adelante en este tema, pero aquí ambos `var1` y `var2` se obtienen como valores utilizando el modelo de AND.</span><span class="sxs-lookup"><span data-stu-id="0c164-203">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="0c164-204">Modelo de cons</span><span class="sxs-lookup"><span data-stu-id="0c164-204">Cons Pattern</span></span>
<span data-ttu-id="0c164-205">El modelo de cons se utiliza para descomponer una lista en el primer elemento, el *head*y una lista que contiene los elementos restantes, el *final*.</span><span class="sxs-lookup"><span data-stu-id="0c164-205">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="0c164-206">Lista (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-206">List Pattern</span></span>
<span data-ttu-id="0c164-207">El patrón de lista permite descomponer en un número de elementos de las listas.</span><span class="sxs-lookup"><span data-stu-id="0c164-207">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="0c164-208">El mismo patrón de lista puede coincidir con listas de un número específico de elementos.</span><span class="sxs-lookup"><span data-stu-id="0c164-208">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="0c164-209">Matriz (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-209">Array Pattern</span></span>
<span data-ttu-id="0c164-210">El patrón de matriz parece al modelo de la lista y puede usarse para descomponer matrices de una longitud concreta.</span><span class="sxs-lookup"><span data-stu-id="0c164-210">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="0c164-211">Paréntesis (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-211">Parenthesized Pattern</span></span>
<span data-ttu-id="0c164-212">Paréntesis pueden agruparse alrededor de modelos para lograr la asociatividad deseada.</span><span class="sxs-lookup"><span data-stu-id="0c164-212">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="0c164-213">En el ejemplo siguiente, se utilizan paréntesis para controlar la asociatividad entre un modelo de AND y un patrón de inconvenientes.</span><span class="sxs-lookup"><span data-stu-id="0c164-213">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="0c164-214">Tupla (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-214">Tuple Pattern</span></span>
<span data-ttu-id="0c164-215">Tupla (modelo) coincide con los datos proporcionados en forma de tupla y permite la tupla puede descomponer en sus elementos constituyentes utilizando variables para cada posición de la tupla de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="0c164-215">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="0c164-216">En el ejemplo siguiente se muestra el patrón de tupla y también usa patrones literales, modelos de variable y el patrón de carácter comodín.</span><span class="sxs-lookup"><span data-stu-id="0c164-216">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="0c164-217">Registro (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-217">Record Pattern</span></span>
<span data-ttu-id="0c164-218">El modelo de registro se utiliza para descomponer los registros para extraer los valores de campos.</span><span class="sxs-lookup"><span data-stu-id="0c164-218">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="0c164-219">El patrón no tiene que hacer referencia a todos los campos del registro; los campos omitidos simplemente no participan en la coincidencia y no se extraen.</span><span class="sxs-lookup"><span data-stu-id="0c164-219">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="0c164-220">Patrón de carácter comodín</span><span class="sxs-lookup"><span data-stu-id="0c164-220">Wildcard Pattern</span></span>
<span data-ttu-id="0c164-221">El patrón de carácter comodín se representa mediante el carácter de subrayado (`_`) de caracteres y coincide con cualquier entrada, al igual que la variable (modelo), salvo que la entrada se descarta en lugar de asignar a una variable.</span><span class="sxs-lookup"><span data-stu-id="0c164-221">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="0c164-222">El patrón de carácter comodín se utiliza a menudo dentro de otros modelos como marcador de posición para los valores que no son necesarios en la expresión a la derecha de la `->` símbolos.</span><span class="sxs-lookup"><span data-stu-id="0c164-222">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="0c164-223">El patrón de carácter comodín también con frecuencia se utiliza al final de una lista de patrones para que coincida con cualquier entrada no coincidente.</span><span class="sxs-lookup"><span data-stu-id="0c164-223">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="0c164-224">Se muestra el patrón de carácter comodín en numerosos ejemplos de código de este tema.</span><span class="sxs-lookup"><span data-stu-id="0c164-224">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="0c164-225">Vea el código anterior para obtener un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0c164-225">See the preceding code for one example.</span></span>


## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="0c164-226">Modelos que tienen anotaciones de tipo</span><span class="sxs-lookup"><span data-stu-id="0c164-226">Patterns That Have Type Annotations</span></span>
<span data-ttu-id="0c164-227">Modelos pueden tener anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c164-227">Patterns can have type annotations.</span></span> <span data-ttu-id="0c164-228">Estos se comportan igual que otras anotaciones de tipo y orientan la inferencia como otras anotaciones de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c164-228">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="0c164-229">Se requieren paréntesis alrededor de las anotaciones de tipo en los patrones.</span><span class="sxs-lookup"><span data-stu-id="0c164-229">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="0c164-230">El código siguiente muestra un modelo que tiene una anotación de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c164-230">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="0c164-231">Modelo de prueba de tipo</span><span class="sxs-lookup"><span data-stu-id="0c164-231">Type Test Pattern</span></span>
<span data-ttu-id="0c164-232">El patrón de prueba de tipo se utiliza para que coincida con la entrada con respecto a un tipo.</span><span class="sxs-lookup"><span data-stu-id="0c164-232">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="0c164-233">Si el tipo de entrada es una coincidencia (o un tipo derivado de) el tipo especificado en el patrón, la búsqueda de coincidencias se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="0c164-233">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="0c164-234">En el ejemplo siguiente se muestra el modelo de prueba de tipo.</span><span class="sxs-lookup"><span data-stu-id="0c164-234">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="0c164-235">Null (modelo)</span><span class="sxs-lookup"><span data-stu-id="0c164-235">Null Pattern</span></span>
<span data-ttu-id="0c164-236">El modelo de null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten a un valor null.</span><span class="sxs-lookup"><span data-stu-id="0c164-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="0c164-237">Los modelos de NULL se utilizan con frecuencia cuando se interopera con código de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0c164-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="0c164-238">Por ejemplo, el valor devuelto de una API de .NET puede ser la entrada a un `match` expresión.</span><span class="sxs-lookup"><span data-stu-id="0c164-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="0c164-239">Puede controlar el flujo del programa en función de si el valor devuelto es null así como otras características del valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c164-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="0c164-240">Puede usar el modelo de null para evitar que los valores null se propaguen al resto del programa.</span><span class="sxs-lookup"><span data-stu-id="0c164-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="0c164-241">En el ejemplo siguiente se usa el modelo de null y el modelo de variable.</span><span class="sxs-lookup"><span data-stu-id="0c164-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="0c164-242">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c164-242">See Also</span></span>
[<span data-ttu-id="0c164-243">Expresiones de coincidencia</span><span class="sxs-lookup"><span data-stu-id="0c164-243">Match Expressions</span></span>](match-expressions.md)

[<span data-ttu-id="0c164-244">Patrones activos</span><span class="sxs-lookup"><span data-stu-id="0c164-244">Active Patterns</span></span>](active-patterns.md)

[<span data-ttu-id="0c164-245">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="0c164-245">F# Language Reference</span></span>](index.md)
