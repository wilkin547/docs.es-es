---
title: Uniones discriminadas
description: 'Aprenda a usar uniones discriminadas de F #.'
ms.date: 08/15/2020
ms.openlocfilehash: f90ac2c2ea21182cf5fd3657d2ada00a763139fe
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740242"
---
# <a name="discriminated-unions"></a>Uniones discriminadas

Las uniones discriminadas proporcionan compatibilidad con valores que pueden ser uno de varios casos con nombre, posiblemente cada uno con valores y tipos diferentes. Las uniones discriminadas son útiles para los datos heterogéneos; datos que pueden tener casos especiales, incluidos casos de error y válidos; datos que varían según el tipo de una instancia a otra; y como alternativa para las jerarquías de objetos pequeños. Además, las uniones discriminadas recursivas se utilizan para representar estructuras de datos de árbol.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Comentarios

Las uniones discriminadas son similares a los tipos de Unión en otros lenguajes, pero hay diferencias. Como con un tipo de Unión en C++ o un tipo Variant en Visual Basic, los datos almacenados en el valor no son fijos. puede ser una de las distintas opciones. Sin embargo, a diferencia de las uniones en estos otros lenguajes, cada una de las opciones posibles tiene un *identificador de caso*. Los identificadores de mayúsculas y minúsculas son nombres para los distintos tipos de valores posibles que podrían ser los objetos de este tipo; los valores son opcionales. Si los valores no están presentes, el caso es equivalente a un caso de enumeración. Si los valores están presentes, cada valor puede ser un valor único de un tipo especificado o una tupla que agrega varios campos del mismo tipo o de tipos diferentes. Puede asignar un nombre a un campo individual, pero el nombre es opcional, incluso si otros campos del mismo caso tienen nombre.

La accesibilidad de las uniones discriminadas tiene como valor predeterminado `public` .

Por ejemplo, considere la siguiente declaración de un tipo de forma.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

El código anterior declara una forma de Unión discriminada, que puede tener valores de cualquiera de los tres casos: rectángulo, círculo y prisma. Cada caso tiene un conjunto de campos diferente. El caso del rectángulo tiene dos campos con nombre, ambos de tipo `float` , que tienen el ancho y la longitud del nombre. El caso del círculo tiene solo un campo con nombre, RADIUS. El caso de prisma tiene tres campos, dos de los cuales (ancho y alto) son campos con nombre. Los campos sin nombre se conocen como campos anónimos.

Los objetos se crean proporcionando valores para los campos con nombre y anónimos según los ejemplos siguientes.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Este código muestra que puede usar los campos con nombre en la inicialización o puede confiar en el orden de los campos en la declaración y simplemente proporcionar los valores de cada campo a su vez. La llamada al constructor de `rect` en el código anterior usa los campos con nombre, pero la llamada del constructor para `circ` usa la ordenación. Puede mezclar los campos ordenados y los campos con nombre, como en la construcción de `prism` .

El `option` tipo es una Unión discriminada simple en la biblioteca básica de F #. El `option` tipo se declara como se indica a continuación.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

El código anterior especifica que el tipo `Option` es una Unión discriminada que tiene dos casos, `Some` y `None` . El `Some` caso tiene un valor asociado que consta de un campo anónimo cuyo tipo se representa mediante el parámetro de tipo `'a` . El `None` caso no tiene ningún valor asociado. Por lo tanto, el `option` tipo especifica un tipo genérico que tiene un valor de algún tipo o ningún valor. El tipo `Option` también tiene un alias de tipo en minúsculas, `option` , que se usa con más frecuencia.

Los identificadores de caso se pueden utilizar como constructores para el tipo de Unión discriminada. Por ejemplo, el código siguiente se utiliza para crear valores del `option` tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Los identificadores de caso también se usan en expresiones de coincidencia de patrones. En una expresión de coincidencia de patrones, se proporcionan identificadores para los valores asociados a los casos individuales. Por ejemplo, en el código siguiente, `x` es el identificador dado el valor que está asociado con el `Some` caso del `option` tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

En expresiones de coincidencia de patrones, puede usar campos con nombre para especificar coincidencias de Unión discriminada. Para el tipo de forma que se declaró anteriormente, puede utilizar los campos con nombre como se muestra en el código siguiente para extraer los valores de los campos.

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

Normalmente, los identificadores de caso se pueden usar sin calificarlos con el nombre de la Unión. Si desea que el nombre se califique siempre con el nombre de la Unión, puede aplicar el atributo [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) a la definición de tipo de Unión.

### <a name="unwrapping-discriminated-unions"></a>Desencapsular uniones discriminadas

En las uniones discriminadas de F #, a menudo se usan en el modelado de dominios para ajustar un tipo único. También es fácil extraer el valor subyacente a través de la coincidencia de patrones. No es necesario usar una expresión de coincidencia para un único caso:

```fsharp
let ([UnionCaseIdentifier] [values]) = [UnionValue]
```

En el siguiente ejemplo se muestra esto:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someFunctionUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ...
```

También se permite la coincidencia de patrones directamente en los parámetros de función, por lo que puede desencapsular un solo caso allí:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Uniones discriminadas de struct

También puede representar uniones discriminadas como estructuras.  Esto se hace con el `[<Struct>]` atributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Dado que se trata de tipos de valor y no de tipos de referencia, existen consideraciones adicionales en comparación con las uniones discriminadas de referencia:

1. Se copian como tipos de valor y tienen semántica de tipos de valor.
2. No se puede usar una definición de tipo recursiva con una Unión discriminada struct multicase.
3. Debe proporcionar nombres de casos únicos para una Unión discriminada struct multicase.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Usar uniones discriminadas en lugar de jerarquías de objetos

A menudo se puede usar una Unión discriminada como alternativa más sencilla a una jerarquía de objetos pequeños. Por ejemplo, se podría usar la siguiente Unión discriminada en lugar de una `Shape` clase base que tiene tipos derivados para Circle, Square, etc.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

En lugar de un método virtual para calcular un área o un perímetro, como se usaría en una implementación orientada a objetos, puede usar la coincidencia de patrones para bifurcar a las fórmulas adecuadas para calcular estas cantidades. En el ejemplo siguiente, se usan diferentes fórmulas para calcular el área, dependiendo de la forma.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

La salida es como sigue:

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Usar uniones discriminadas para estructuras de datos de árbol

Las uniones discriminadas pueden ser recursivas, lo que significa que la propia Unión puede incluirse en el tipo de uno o varios casos. Las uniones discriminadas recursivas se pueden usar para crear estructuras de árbol, que se usan para modelar expresiones en lenguajes de programación. En el código siguiente, una Unión discriminada recursiva se usa para crear una estructura de datos de árbol binario. La Unión se compone de dos casos, `Node` , que es un nodo con un valor entero y subárboles izquierdo y derecho, y `Tip` , que finaliza el árbol.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

En el código anterior, `resultSumTree` tiene el valor 10. En la ilustración siguiente se muestra la estructura de árbol de `myTree` .

![Diagrama que muestra la estructura de árbol de mi árbol.](../media/discriminated-unions/tree-structure-mytree.png)

Las uniones discriminadas funcionan bien si los nodos del árbol son heterogéneos. En el código siguiente, el tipo `Expression` representa el árbol de sintaxis abstracta de una expresión en un lenguaje de programación simple que admite la adición y la multiplicación de números y variables. Algunos de los casos de Unión no son recursivos y representan números ( `Number` ) o variables ( `Variable` ). Otros casos son recursivos y representan operaciones ( `Add` y `Multiply` ), donde los operandos también son expresiones. La `Evaluate` función utiliza una expresión de coincidencia para procesar el árbol de sintaxis de forma recursiva.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Cuando se ejecuta este código, el valor de `result` es 5.

## <a name="members"></a>Miembros

Es posible definir miembros en uniones discriminadas. En el ejemplo siguiente se muestra cómo definir una propiedad e implementar una interfaz:

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
            | Circle r -> printfn $"Circle with radius %f{r}"
            | EquilateralTriangle s -> printfn $"Equilateral Triangle of side %f{s}"
            | Square s -> printfn $"Square with side %f{s}"
            | Rectangle(l, w) -> printfn $"Rectangle with length %f{l} and width %f{w}"
```

## <a name="common-attributes"></a>Atributos comunes

Los atributos siguientes se suelen considerar en uniones discriminadas:

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
