---
title: Uniones discriminadas
description: Aprenda a usar uniones discriminadas por F.
ms.date: 05/16/2016
ms.openlocfilehash: 539e2843c0bbc8c5ac9c0597ffc5443f8cd127f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401074"
---
# <a name="discriminated-unions"></a><span data-ttu-id="37f3e-103">Uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="37f3e-103">Discriminated Unions</span></span>

<span data-ttu-id="37f3e-104">Las uniones discriminadas proporcionan compatibilidad con valores que pueden ser uno de una serie de casos con nombre, posiblemente cada uno con valores y tipos diferentes.</span><span class="sxs-lookup"><span data-stu-id="37f3e-104">Discriminated unions provide support for values that can be one of a number of named cases, possibly each with different values and types.</span></span> <span data-ttu-id="37f3e-105">Las uniones discriminadas son útiles para datos heterogéneos; datos que pueden tener casos especiales, incluidos los casos válidos y de error; datos que varían en tipo de una instancia a otra; y como alternativa para jerarquías de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="37f3e-105">Discriminated unions are useful for heterogeneous data; data that can have special cases, including valid and error cases; data that varies in type from one instance to another; and as an alternative for small object hierarchies.</span></span> <span data-ttu-id="37f3e-106">Además, las uniones discriminadas recursivas se utilizan para representar estructuras de datos de árbol.</span><span class="sxs-lookup"><span data-stu-id="37f3e-106">In addition, recursive discriminated unions are used to represent tree data structures.</span></span>

## <a name="syntax"></a><span data-ttu-id="37f3e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37f3e-107">Syntax</span></span>

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a><span data-ttu-id="37f3e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="37f3e-108">Remarks</span></span>

<span data-ttu-id="37f3e-109">Las uniones discriminadas son similares a los tipos de unión en otros idiomas, pero hay diferencias.</span><span class="sxs-lookup"><span data-stu-id="37f3e-109">Discriminated unions are similar to union types in other languages, but there are differences.</span></span> <span data-ttu-id="37f3e-110">Al igual que con un tipo de unión en C++ o un tipo de variante en Visual Basic, los datos almacenados en el valor no son fijos; puede ser una de varias opciones distintas.</span><span class="sxs-lookup"><span data-stu-id="37f3e-110">As with a union type in C++ or a variant type in Visual Basic, the data stored in the value is not fixed; it can be one of several distinct options.</span></span> <span data-ttu-id="37f3e-111">A diferencia de las uniones en estos otros idiomas, sin embargo, cada una de las opciones posibles recibe un identificador de *caso.*</span><span class="sxs-lookup"><span data-stu-id="37f3e-111">Unlike unions in these other languages, however, each of the possible options is given a *case identifier*.</span></span> <span data-ttu-id="37f3e-112">Los identificadores de caso son nombres para los distintos tipos posibles de valores que podrían ser los objetos de este tipo; los valores son opcionales.</span><span class="sxs-lookup"><span data-stu-id="37f3e-112">The case identifiers are names for the various possible types of values that objects of this type could be; the values are optional.</span></span> <span data-ttu-id="37f3e-113">Si los valores no están presentes, el caso es equivalente a un caso de enumeración.</span><span class="sxs-lookup"><span data-stu-id="37f3e-113">If values are not present, the case is equivalent to an enumeration case.</span></span> <span data-ttu-id="37f3e-114">Si hay valores presentes, cada valor puede ser un único valor de un tipo especificado o una tupla que agrega varios campos de los mismos tipos o diferentes.</span><span class="sxs-lookup"><span data-stu-id="37f3e-114">If values are present, each value can either be a single value of a specified type, or a tuple that aggregates multiple fields of the same or different types.</span></span> <span data-ttu-id="37f3e-115">Puede asignar un nombre a un campo individual, pero el nombre es opcional, incluso si se nombran otros campos en el mismo caso.</span><span class="sxs-lookup"><span data-stu-id="37f3e-115">You can give an individual field a name, but the name is optional, even if other fields in the same case are named.</span></span>

<span data-ttu-id="37f3e-116">La accesibilidad de las uniones `public`discriminadas tiene como valor predeterminado .</span><span class="sxs-lookup"><span data-stu-id="37f3e-116">Accessibility for discriminated unions defaults to `public`.</span></span>

<span data-ttu-id="37f3e-117">Por ejemplo, considere la siguiente declaración de un Shape tipo.</span><span class="sxs-lookup"><span data-stu-id="37f3e-117">For example, consider the following declaration of a Shape type.</span></span>

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

<span data-ttu-id="37f3e-118">El código anterior declara una unión discriminada Shape, que puede tener valores de cualquiera de los tres casos: Rectangle, Circle y Prism.</span><span class="sxs-lookup"><span data-stu-id="37f3e-118">The preceding code declares a discriminated union Shape, which can have values of any of three cases: Rectangle, Circle, and Prism.</span></span> <span data-ttu-id="37f3e-119">Cada caso tiene un conjunto diferente de campos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-119">Each case has a different set of fields.</span></span> <span data-ttu-id="37f3e-120">El caso Rectangle tiene dos campos `float`con nombre, ambos de tipo , que tienen los nombres width y length.</span><span class="sxs-lookup"><span data-stu-id="37f3e-120">The Rectangle case has two named fields, both of type `float`, that have the names width and length.</span></span> <span data-ttu-id="37f3e-121">El caso Círculo tiene un solo campo con nombre, radio.</span><span class="sxs-lookup"><span data-stu-id="37f3e-121">The Circle case has just one named field, radius.</span></span> <span data-ttu-id="37f3e-122">El caso Prism tiene tres campos, dos de los cuales (ancho y alto) se denominan campos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-122">The Prism case has three fields, two of which (width and height) are named fields.</span></span> <span data-ttu-id="37f3e-123">Los campos sin nombre se conocen como campos anónimos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-123">Unnamed fields are referred to as anonymous fields.</span></span>

<span data-ttu-id="37f3e-124">Los objetos se construyen proporcionando valores para los campos con nombre y anónimos según los ejemplos siguientes.</span><span class="sxs-lookup"><span data-stu-id="37f3e-124">You construct objects by providing values for the named and anonymous fields according to the following examples.</span></span>

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

<span data-ttu-id="37f3e-125">Este código muestra que puede usar los campos con nombre en la inicialización o puede confiar en el orden de los campos de la declaración y simplemente proporcionar los valores para cada campo a su vez.</span><span class="sxs-lookup"><span data-stu-id="37f3e-125">This code shows that you can either use the named fields in the initialization, or you can rely on the ordering of the fields in the declaration and just provide the values for each field in turn.</span></span> <span data-ttu-id="37f3e-126">La llamada `rect` del constructor en el código anterior usa `circ` los campos con nombre, pero la llamada del constructor para usa el orden.</span><span class="sxs-lookup"><span data-stu-id="37f3e-126">The constructor call for `rect` in the previous code uses the named fields, but the constructor call for `circ` uses the ordering.</span></span> <span data-ttu-id="37f3e-127">Puede mezclar los campos ordenados y los `prism`campos con nombre, como en la construcción de .</span><span class="sxs-lookup"><span data-stu-id="37f3e-127">You can mix the ordered fields and named fields, as in the construction of `prism`.</span></span>

<span data-ttu-id="37f3e-128">El `option` tipo es una unión discriminada simple en la biblioteca principal de F .</span><span class="sxs-lookup"><span data-stu-id="37f3e-128">The `option` type is a simple discriminated union in the F# core library.</span></span> <span data-ttu-id="37f3e-129">El `option` tipo se declara como sigue.</span><span class="sxs-lookup"><span data-stu-id="37f3e-129">The `option` type is declared as follows.</span></span>

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

<span data-ttu-id="37f3e-130">El código anterior especifica `Option` que el tipo es una `Some` unión discriminada que tiene dos casos y `None`.</span><span class="sxs-lookup"><span data-stu-id="37f3e-130">The previous code specifies that the type `Option` is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="37f3e-131">El `Some` caso tiene un valor asociado que consta de un campo `'a`anónimo cuyo tipo está representado por el parámetro type .</span><span class="sxs-lookup"><span data-stu-id="37f3e-131">The `Some` case has an associated value that consists of one anonymous field whose type is represented by the type parameter `'a`.</span></span> <span data-ttu-id="37f3e-132">El `None` caso no tiene ningún valor asociado.</span><span class="sxs-lookup"><span data-stu-id="37f3e-132">The `None` case has no associated value.</span></span> <span data-ttu-id="37f3e-133">Por `option` lo tanto, el tipo especifica un tipo genérico que tiene un valor de algún tipo o ningún valor.</span><span class="sxs-lookup"><span data-stu-id="37f3e-133">Thus the `option` type specifies a generic type that either has a value of some type or no value.</span></span> <span data-ttu-id="37f3e-134">El `Option` tipo también tiene un `option`alias de tipo en minúsculas, , que se utiliza más comúnmente.</span><span class="sxs-lookup"><span data-stu-id="37f3e-134">The type `Option` also has a lowercase type alias, `option`, that is more commonly used.</span></span>

<span data-ttu-id="37f3e-135">Los identificadores de caso se pueden usar como constructores para el tipo de unión discriminada.</span><span class="sxs-lookup"><span data-stu-id="37f3e-135">The case identifiers can be used as constructors for the discriminated union type.</span></span> <span data-ttu-id="37f3e-136">Por ejemplo, el código siguiente se `option` utiliza para crear valores del tipo.</span><span class="sxs-lookup"><span data-stu-id="37f3e-136">For example, the following code is used to create values of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

<span data-ttu-id="37f3e-137">Los identificadores de mayúsculas y minúsculas también se utilizan en expresiones de coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="37f3e-137">The case identifiers are also used in pattern matching expressions.</span></span> <span data-ttu-id="37f3e-138">En una expresión de coincidencia de patrones, se proporcionan identificadores para los valores asociados con los casos individuales.</span><span class="sxs-lookup"><span data-stu-id="37f3e-138">In a pattern matching expression, identifiers are provided for the values associated with the individual cases.</span></span> <span data-ttu-id="37f3e-139">Por ejemplo, en el `x` código siguiente, es el identificador `Some` dado `option` el valor que está asociado con el caso del tipo.</span><span class="sxs-lookup"><span data-stu-id="37f3e-139">For example, in the following code, `x` is the identifier given the value that is associated with the `Some` case of the `option` type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

<span data-ttu-id="37f3e-140">En las expresiones de coincidencia de patrones, puede usar campos con nombre para especificar coincidencias de unión discriminadas.</span><span class="sxs-lookup"><span data-stu-id="37f3e-140">In pattern matching expressions, you can use named fields to specify discriminated union matches.</span></span> <span data-ttu-id="37f3e-141">Para el tipo Shape que se declaró anteriormente, puede usar los campos con nombre como se muestra en el código siguiente para extraer los valores de los campos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-141">For the Shape type that was declared previously, you can use the named fields as the following code shows to extract the values of the fields.</span></span>

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

<span data-ttu-id="37f3e-142">Normalmente, los identificadores de caso se pueden utilizar sin calificarlos con el nombre de la unión.</span><span class="sxs-lookup"><span data-stu-id="37f3e-142">Normally, the case identifiers can be used without qualifying them with the name of the union.</span></span> <span data-ttu-id="37f3e-143">Si desea que el nombre siempre se califique con el nombre de la unión, puede aplicar el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) a la definición de tipo de unión.</span><span class="sxs-lookup"><span data-stu-id="37f3e-143">If you want the name to always be qualified with the name of the union, you can apply the [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) attribute to the union type definition.</span></span>

### <a name="unwrapping-discriminated-unions"></a><span data-ttu-id="37f3e-144">Desenvolviendo uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="37f3e-144">Unwrapping Discriminated Unions</span></span>

<span data-ttu-id="37f3e-145">En las Uniones Discriminadas de F- se usan a menudo en el modelado de dominios para ajustar un solo tipo.</span><span class="sxs-lookup"><span data-stu-id="37f3e-145">In F# Discriminated Unions are often used in domain-modeling for wrapping a single type.</span></span> <span data-ttu-id="37f3e-146">También es fácil extraer el valor subyacente a través de la coincidencia de patrones.</span><span class="sxs-lookup"><span data-stu-id="37f3e-146">It's easy to extract the underlying value via pattern matching as well.</span></span> <span data-ttu-id="37f3e-147">No es necesario utilizar una expresión de coincidencia para un solo caso:</span><span class="sxs-lookup"><span data-stu-id="37f3e-147">You don't need to use a match expression for a single case:</span></span>

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

<span data-ttu-id="37f3e-148">En el siguiente ejemplo se muestra esto:</span><span class="sxs-lookup"><span data-stu-id="37f3e-148">The following example demonstrates this:</span></span>

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

<span data-ttu-id="37f3e-149">La coincidencia de patrones también se permite directamente en los parámetros de función, por lo que puede desencapsular un solo caso allí:</span><span class="sxs-lookup"><span data-stu-id="37f3e-149">Pattern matching is also allowed directly in function parameters, so you can unwrap a single case there:</span></span>

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a><span data-ttu-id="37f3e-150">Estructurar uniones discriminadas</span><span class="sxs-lookup"><span data-stu-id="37f3e-150">Struct Discriminated Unions</span></span>

<span data-ttu-id="37f3e-151">También puede representar Uniones Discriminadas como estructuras.</span><span class="sxs-lookup"><span data-stu-id="37f3e-151">You can also represent Discriminated Unions as structs.</span></span>  <span data-ttu-id="37f3e-152">Esto se hace `[<Struct>]` con el atributo.</span><span class="sxs-lookup"><span data-stu-id="37f3e-152">This is done with the `[<Struct>]` attribute.</span></span>

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

<span data-ttu-id="37f3e-153">Dado que se trata de tipos de valor y no de tipos de referencia, hay consideraciones adicionales en comparación con las uniones discriminadas de referencia:</span><span class="sxs-lookup"><span data-stu-id="37f3e-153">Because these are value types and not reference types, there are extra considerations compared with reference discriminated unions:</span></span>

1. <span data-ttu-id="37f3e-154">Se copian como tipos de valor y tienen semántica de tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="37f3e-154">They are copied as value types and have value type semantics.</span></span>
2. <span data-ttu-id="37f3e-155">No se puede utilizar una definición de tipo recursiva con una unión discriminada de estructura multicaso.</span><span class="sxs-lookup"><span data-stu-id="37f3e-155">You cannot use a recursive type definition with a multicase struct Discriminated Union.</span></span>
3. <span data-ttu-id="37f3e-156">Debe proporcionar nombres de caso únicos para una unión discriminada de estructura multicaso.</span><span class="sxs-lookup"><span data-stu-id="37f3e-156">You must provide unique case names for a multicase struct Discriminated Union.</span></span>

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a><span data-ttu-id="37f3e-157">Uso de uniones discriminadas en lugar de jerarquías de objetos</span><span class="sxs-lookup"><span data-stu-id="37f3e-157">Using Discriminated Unions Instead of Object Hierarchies</span></span>

<span data-ttu-id="37f3e-158">A menudo puede utilizar una unión discriminada como una alternativa más sencilla a una jerarquía de objetos pequeños.</span><span class="sxs-lookup"><span data-stu-id="37f3e-158">You can often use a discriminated union as a simpler alternative to a small object hierarchy.</span></span> <span data-ttu-id="37f3e-159">Por ejemplo, la siguiente unión discriminada `Shape` podría utilizarse en lugar de una clase base que tenga tipos derivados para circle, square, etc.</span><span class="sxs-lookup"><span data-stu-id="37f3e-159">For example, the following discriminated union could be used instead of a `Shape` base class that has derived types for circle, square, and so on.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

<span data-ttu-id="37f3e-160">En lugar de un método virtual para calcular un área o perímetro, como usaría en una implementación orientada a objetos, puede usar la coincidencia de patrones para bifurcar las fórmulas adecuadas para calcular estas cantidades.</span><span class="sxs-lookup"><span data-stu-id="37f3e-160">Instead of a virtual method to compute an area or perimeter, as you would use in an object-oriented implementation, you can use pattern matching to branch to appropriate formulas to compute these quantities.</span></span> <span data-ttu-id="37f3e-161">En el ejemplo siguiente, se utilizan diferentes fórmulas para calcular el área, dependiendo de la forma.</span><span class="sxs-lookup"><span data-stu-id="37f3e-161">In the following example, different formulas are used to compute the area, depending on the shape.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

<span data-ttu-id="37f3e-162">La salida es como sigue:</span><span class="sxs-lookup"><span data-stu-id="37f3e-162">The output is as follows:</span></span>

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a><span data-ttu-id="37f3e-163">Uso de uniones discriminadas para estructuras de datos de árboles</span><span class="sxs-lookup"><span data-stu-id="37f3e-163">Using Discriminated Unions for Tree Data Structures</span></span>

<span data-ttu-id="37f3e-164">Las uniones discriminadas pueden ser recursivas, lo que significa que la propia unión puede incluirse en el tipo de uno o más casos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-164">Discriminated unions can be recursive, meaning that the union itself can be included in the type of one or more cases.</span></span> <span data-ttu-id="37f3e-165">Las uniones discriminadas recursivas se pueden utilizar para crear estructuras de árbol, que se utilizan para modelar expresiones en lenguajes de programación.</span><span class="sxs-lookup"><span data-stu-id="37f3e-165">Recursive discriminated unions can be used to create tree structures, which are used to model expressions in programming languages.</span></span> <span data-ttu-id="37f3e-166">En el código siguiente, se usa una unión discriminada recursiva para crear una estructura de datos de árbol binario.</span><span class="sxs-lookup"><span data-stu-id="37f3e-166">In the following code, a recursive discriminated union is used to create a binary tree data structure.</span></span> <span data-ttu-id="37f3e-167">La unión consta `Node`de dos casos, , que es un nodo con `Tip`un valor entero y subárboles izquierdo y derecho, y , que termina el árbol.</span><span class="sxs-lookup"><span data-stu-id="37f3e-167">The union consists of two cases, `Node`, which is a node with an integer value and left and right subtrees, and `Tip`, which terminates the tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

<span data-ttu-id="37f3e-168">En el código `resultSumTree` anterior, tiene el valor 10.</span><span class="sxs-lookup"><span data-stu-id="37f3e-168">In the previous code, `resultSumTree` has the value 10.</span></span> <span data-ttu-id="37f3e-169">En la ilustración siguiente `myTree`se muestra la estructura de árbol para .</span><span class="sxs-lookup"><span data-stu-id="37f3e-169">The following illustration shows the tree structure for `myTree`.</span></span>

![Diagrama que muestra la estructura de árbol de myTree.](../media/discriminated-unions/tree-structure-mytree.png)

<span data-ttu-id="37f3e-171">Las uniones discriminadas funcionan bien si los nodos del árbol son heterogéneos.</span><span class="sxs-lookup"><span data-stu-id="37f3e-171">Discriminated unions work well if the nodes in the tree are heterogeneous.</span></span> <span data-ttu-id="37f3e-172">En el código siguiente, el tipo `Expression` representa el árbol de sintaxis abstracta de una expresión en un lenguaje de programación simple que admite la adición y multiplicación de números y variables.</span><span class="sxs-lookup"><span data-stu-id="37f3e-172">In the following code, the type `Expression` represents the abstract syntax tree of an expression in a simple programming language that supports addition and multiplication of numbers and variables.</span></span> <span data-ttu-id="37f3e-173">Algunos de los casos de unión no`Number`son recursivos y representan números ( ) o variables (`Variable`).</span><span class="sxs-lookup"><span data-stu-id="37f3e-173">Some of the union cases are not recursive and represent either numbers (`Number`) or variables (`Variable`).</span></span> <span data-ttu-id="37f3e-174">Otros casos son recursivos`Add` y `Multiply`representan operaciones ( y ), donde los operandos también son expresiones.</span><span class="sxs-lookup"><span data-stu-id="37f3e-174">Other cases are recursive, and represent operations (`Add` and `Multiply`), where the operands are also expressions.</span></span> <span data-ttu-id="37f3e-175">La `Evaluate` función utiliza una expresión de coincidencia para procesar recursivamente el árbol de sintaxis.</span><span class="sxs-lookup"><span data-stu-id="37f3e-175">The `Evaluate` function uses a match expression to recursively process the syntax tree.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

<span data-ttu-id="37f3e-176">Cuando se ejecuta este código, el valor de `result` es 5.</span><span class="sxs-lookup"><span data-stu-id="37f3e-176">When this code is executed, the value of `result` is 5.</span></span>

## <a name="members"></a><span data-ttu-id="37f3e-177">Members</span><span class="sxs-lookup"><span data-stu-id="37f3e-177">Members</span></span>

<span data-ttu-id="37f3e-178">Es posible definir miembros en uniones discriminadas.</span><span class="sxs-lookup"><span data-stu-id="37f3e-178">It is possible to define members on discriminated unions.</span></span> <span data-ttu-id="37f3e-179">En el ejemplo siguiente se muestra cómo definir una propiedad e implementar una interfaz:</span><span class="sxs-lookup"><span data-stu-id="37f3e-179">The following example shows how to define a property and implement an interface:</span></span>

```fsharp
open System

type IPrintable =
    abstract Print: unit -> unit

type Shape =
    | Circle of float
    | EquilateralTriangle of float
    | Square of float
    | Rectangle of float * float

    member this.Area =
        match this with
        | Circle r -> 2.0 * Math.PI * r
        | EquilateralTriangle s -> s * s * sqrt 3.0 / 4.0
        | Square s -> s * s
        | Rectangle(l, w) -> l * w

    interface IPrintable with
        member this.Print () =
            match this with
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a><span data-ttu-id="37f3e-180">Atributos comunes</span><span class="sxs-lookup"><span data-stu-id="37f3e-180">Common attributes</span></span>

<span data-ttu-id="37f3e-181">Los siguientes atributos se ven comúnmente en uniones discriminadas:</span><span class="sxs-lookup"><span data-stu-id="37f3e-181">The following attributes are commonly seen in discriminated unions:</span></span>

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a><span data-ttu-id="37f3e-182">Consulte también</span><span class="sxs-lookup"><span data-stu-id="37f3e-182">See also</span></span>

- [<span data-ttu-id="37f3e-183">Referencia del lenguaje f</span><span class="sxs-lookup"><span data-stu-id="37f3e-183">F# Language Reference</span></span>](index.md)
