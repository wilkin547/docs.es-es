---
title: Uniones discriminadas (F#)
description: "Obtenga información acerca de cómo usar F # uniones discriminadas."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 16e2a011-c785-48c8-859f-79df7f3a0e29
ms.openlocfilehash: b7a02512ce4a63885e771be56f106bc66cc2743e
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2018
---
# <a name="discriminated-unions"></a><span data-ttu-id="bbbbd-104">Uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="bbbbd-104">Discriminated Unions</span></span>

<span data-ttu-id="bbbbd-105">Uniones discriminadas proporcionan compatibilidad para los valores que pueden ser uno de un número de casos con nombre, posiblemente cada uno con valores y tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-105">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="bbbbd-106">Uniones discriminadas son útiles para datos heterogéneos; datos que pueden tener casos especiales, incluidos válidos y casos de error; datos que varían en el tipo de una instancia a otra; y como una alternativa a las jerarquías de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-106">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="bbbbd-107">Además, discriminadas uniones se utilizan para representar estructuras de datos de árbol.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-107">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="bbbbd-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbbbd-108">Syntax</span></span>

```fsharp
[ attributes ]
type type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a><span data-ttu-id="bbbbd-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbbbd-109">Remarks</span></span>
<span data-ttu-id="bbbbd-110">Uniones discriminadas son similares a los tipos de unión en otros lenguajes, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-110">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="bbbbd-111">Como con un tipo de unión en C++ o un tipo variant en Visual Basic, los datos almacenados en el valor no es fijo; puede ser una de varias opciones distintas.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-111">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="bbbbd-112">A diferencia de uniones en estos otros idiomas, sin embargo, cada una de las opciones posibles se concede un *identificador de caso*.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-112">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="bbbbd-113">Los identificadores de caso son nombres para los diversos posibles tipos de valores que pudieron ser objetos de este tipo; los valores son opcionales.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-113">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="bbbbd-114">Si los valores no están presentes, el caso equivale a un caso de enumeración.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-114">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="bbbbd-115">Si los valores están presentes, cada valor puede ser un valor único de un tipo especificado o una tupla que agrega varios campos de la mismos o de tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-115">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="bbbbd-116">A partir de F # 3.1, puede asignar un campo individual de un nombre, pero el nombre es opcional, aunque se denominan otros campos en las mismas mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-116">As of F# 3.1, you can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="bbbbd-117">Por ejemplo, considere la siguiente declaración de un tipo de forma.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="bbbbd-118">El código anterior declara una unión discriminada forma, que puede tener valores de cualquiera de los tres casos: rectángulo, círculo y prisma.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="bbbbd-119">Cada caso tiene un conjunto diferente de campos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-119">Each case has a different set of fields.</span></span> <span data-ttu-id="bbbbd-120">El rectángulo caso tiene dos denominado campos, ambos de tipo `float`, que tiene el ancho de los nombres y la longitud.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="bbbbd-121">El caso de círculo tiene un solo campo con nombre, radius.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="bbbbd-122">El caso de prisma tiene tres campos, dos de qué (ancho y alto) se denominan campos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="bbbbd-123">Campos sin nombre se conocen como campos anónimos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="bbbbd-124">Construir objetos proporcionando los valores para los campos con nombre y anónimos según los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="bbbbd-125">Este código muestra que puede usar los campos con nombre en la inicialización, o puede confiar en el orden de los campos de la declaración y basta con que proporcione los valores para cada campo a su vez.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="bbbbd-126">La llamada al constructor para `rect` en el código anterior usa los campos con nombre, pero la llamada al constructor para `circ` usa la ordenación.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="bbbbd-127">Puede combinar los campos ordenados y con el nombre de campos, como se muestra en la construcción de `prism`.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="bbbbd-128">El `option` tipo es una unión discriminada simple en la biblioteca básica de F #.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="bbbbd-129">El `option` tipo se declara como sigue.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="bbbbd-130">El código anterior especifica que el tipo `Option` es una unión discriminada que tiene dos casos, `Some` y `None`.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="bbbbd-131">El `Some` caso tiene un valor asociado que consta de un campo anónimo, cuyo tipo es representado por el parámetro de tipo `'a`.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="bbbbd-132">El `None` caso no tiene ningún valor asociado.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-132">The `None` case has no associated value.</span></span> <span data-ttu-id="bbbbd-133">Por lo tanto la `option` tipo especifica un tipo genérico que tiene un valor de algún tipo o ningún valor.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="bbbbd-134">El tipo `Option` también tiene un alias de tipo en minúscula, `option`, que es más frecuente.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="bbbbd-135">Los identificadores de caso pueden utilizarse como constructores para el tipo de unión discriminado.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="bbbbd-136">Por ejemplo, el código siguiente se utiliza para crear valores de la `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="bbbbd-137">Los identificadores de caso también se utilizan en expresiones de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="bbbbd-138">En una expresión de coincidencia de modelos, los identificadores se proporcionan para los valores asociados a los casos individuales.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="bbbbd-139">Por ejemplo, en el código siguiente, `x` el identificador tiene el valor que está asociado el `Some` mayúsculas de la `option` tipo.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="bbbbd-140">En expresiones de coincidencia de patrones, puede utilizar campos con nombre para especificar las coincidencias de unión discriminadas.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="bbbbd-141">Para el tipo de forma que se declaró previamente, puede usar los campos con nombre, como se muestra en el siguiente código para extraer los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

<span data-ttu-id="bbbbd-142">Normalmente, los identificadores de caso pueden utilizarse sin calificarlos con el nombre de la unión.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="bbbbd-143">Si desea que el nombre que siempre estén calificados con el nombre de la unión, se puede aplicar el [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo a la definición de tipo de unión.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="bbbbd-144">Uniones discriminadas desencapsulación</span><span class="sxs-lookup"><span data-stu-id="bbbbd-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="bbbbd-145">En uniones discriminadas de F # suelen utilizarse en el modelado de dominio para un único tipo de ajuste.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="bbbbd-146">Es fácil extraer el valor subyacente a través de coincidencia de patrones también.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="bbbbd-147">No es necesario usar una expresión de coincidencia para un único caso:</span><span class="sxs-lookup"><span data-stu-id="bbbbd-147">You don't need to use a match expression for a single case:</span></span>
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

<span data-ttu-id="bbbbd-148">En el siguiente ejemplo se muestra esto:</span><span class="sxs-lookup"><span data-stu-id="bbbbd-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="bbbbd-149">Struct uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="bbbbd-149">Struct Discriminated Unions</span></span>

<span data-ttu-id="bbbbd-150">A partir de F # 4.1, también puede representar uniones discriminadas como estructuras.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-150">Starting with F# 4.1, you can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="bbbbd-151">Esto se realiza con el `[<Struct>]` atributo.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-151">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="bbbbd-152">Dado que estos son tipos de valor y no hacen referencia a tipos, hay adicional en comparación con la referencia de consideraciones de uniones discriminadas:</span><span class="sxs-lookup"><span data-stu-id="bbbbd-152">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="bbbbd-153">Se copian como tipos de valor y tiene la semántica de tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-153">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="bbbbd-154">No se puede usar una definición de tipo recursivo con un struct multicase discriminadas Union.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-154">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="bbbbd-155">Debe proporcionar nombres únicos de casos para un struct multicase discriminadas Union.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-155">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="bbbbd-156">Usar uniones discriminadas en lugar de las jerarquías de objetos</span><span class="sxs-lookup"><span data-stu-id="bbbbd-156">Using Discriminated Unions Instead of Object Hierarchies</span></span>
<span data-ttu-id="bbbbd-157">A menudo, puede usar una unión discriminada como una alternativa más sencilla a una jerarquía de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-157">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="bbbbd-158">Por ejemplo, la unión discriminada siguiente podría usarse en lugar de un `Shape` clase base que tiene tipos derivados para círculo, cuadrado, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-158">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="bbbbd-159">En su lugar de un método virtual para calcular un área o perímetro, que se usan en una implementación orientada a objetos, puede usar la coincidencia de patrones a diversificar las fórmulas adecuadas para calcular estas cantidades.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-159">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="bbbbd-160">En el ejemplo siguiente, se utilizan fórmulas diferentes para calcular el área, dependiendo de la forma.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-160">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="bbbbd-161">La salida es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="bbbbd-161">The output is as follows:</span></span>

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="bbbbd-162">Usar uniones discriminadas para las estructuras de datos de árbol</span><span class="sxs-lookup"><span data-stu-id="bbbbd-162">Using Discriminated Unions for Tree Data Structures</span></span>
<span data-ttu-id="bbbbd-163">Uniones discriminadas pueden ser recursivas, lo que significa que la propia unión puede incluirse en el tipo de uno o varios casos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-163">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="bbbbd-164">Recursiva uniones discriminadas pueden usarse para crear estructuras de árbol, que se utilizan para expresiones de modelo en lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-164">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="bbbbd-165">En el código siguiente, un discriminadas union se utiliza para crear una estructura de datos de árbol binario.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-165">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="bbbbd-166">La unión consta de dos casos, `Node`, que es un nodo con un valor entero y subárboles izquierdos y derecho, y `Tip`, que termina el árbol.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-166">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="bbbbd-167">En el código anterior, `resultSumTree` tiene el valor 10.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-167">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="bbbbd-168">En la siguiente ilustración muestra la estructura de árbol de `myTree`.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-168">The following illustration shows the tree structure for `myTree`.</span></span>

![Estructura de árbol de myTree](../media/TreeStructureDiagram.png)

<span data-ttu-id="bbbbd-170">Uniones discriminadas funcionan bien si los nodos en el árbol son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-170">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="bbbbd-171">En el código siguiente, el tipo `Expression` representa el árbol de sintaxis abstracta de una expresión en un lenguaje de programación simple que admite la suma y multiplicación de números y variables.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-171">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="bbbbd-172">Algunos de los casos de unión no son recursivos y representan cualquiera números (`Number`) o variables (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="bbbbd-172">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="bbbbd-173">Otros casos son recursivos y representan operaciones (`Add` y `Multiply`), donde los operandos también son expresiones.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-173">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="bbbbd-174">El `Evaluate` función usa una expresión de coincidencia de al proceso de forma recursiva el árbol de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-174">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="bbbbd-175">Cuando se ejecuta este código, el valor de `result` es 5.</span><span class="sxs-lookup"><span data-stu-id="bbbbd-175">When this code is executed, the value of `result` is 5.</span></span>

## <a name="common-attributes"></a><span data-ttu-id="bbbbd-176">Atributos comunes</span><span class="sxs-lookup"><span data-stu-id="bbbbd-176">Common Attributes</span></span>

<span data-ttu-id="bbbbd-177">Los siguientes atributos se observa habitualmente en uniones discriminadas:</span><span class="sxs-lookup"><span data-stu-id="bbbbd-177">The following attributes are commonly seen in discriminated unions:</span></span>

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* <span data-ttu-id="bbbbd-178">`[Struct]`(F # 4.1 y versiones posteriores)</span><span class="sxs-lookup"><span data-stu-id="bbbbd-178">`[Struct]` (F# 4.1 and higher)</span></span>

## <a name="see-also"></a><span data-ttu-id="bbbbd-179">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbbbd-179">See Also</span></span>
[<span data-ttu-id="bbbbd-180">Referencia del lenguaje F#</span><span class="sxs-lookup"><span data-stu-id="bbbbd-180">F# Language Reference</span></span>](index.md)
