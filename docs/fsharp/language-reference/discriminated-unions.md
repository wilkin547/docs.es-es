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
# <a name="discriminated-unions"></a>Uniones discriminadas

Las uniones discriminadas proporcionan compatibilidad con valores que pueden ser uno de una serie de casos con nombre, posiblemente cada uno con valores y tipos diferentes. Las uniones discriminadas son útiles para datos heterogéneos; datos que pueden tener casos especiales, incluidos los casos válidos y de error; datos que varían en tipo de una instancia a otra; y como alternativa para jerarquías de objetos pequeños. Además, las uniones discriminadas recursivas se utilizan para representar estructuras de datos de árbol.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]

    [ member-list ]
```

## <a name="remarks"></a>Observaciones

Las uniones discriminadas son similares a los tipos de unión en otros idiomas, pero hay diferencias. Al igual que con un tipo de unión en C++ o un tipo de variante en Visual Basic, los datos almacenados en el valor no son fijos; puede ser una de varias opciones distintas. A diferencia de las uniones en estos otros idiomas, sin embargo, cada una de las opciones posibles recibe un identificador de *caso.* Los identificadores de caso son nombres para los distintos tipos posibles de valores que podrían ser los objetos de este tipo; los valores son opcionales. Si los valores no están presentes, el caso es equivalente a un caso de enumeración. Si hay valores presentes, cada valor puede ser un único valor de un tipo especificado o una tupla que agrega varios campos de los mismos tipos o diferentes. Puede asignar un nombre a un campo individual, pero el nombre es opcional, incluso si se nombran otros campos en el mismo caso.

La accesibilidad de las uniones `public`discriminadas tiene como valor predeterminado .

Por ejemplo, considere la siguiente declaración de un Shape tipo.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

El código anterior declara una unión discriminada Shape, que puede tener valores de cualquiera de los tres casos: Rectangle, Circle y Prism. Cada caso tiene un conjunto diferente de campos. El caso Rectangle tiene dos campos `float`con nombre, ambos de tipo , que tienen los nombres width y length. El caso Círculo tiene un solo campo con nombre, radio. El caso Prism tiene tres campos, dos de los cuales (ancho y alto) se denominan campos. Los campos sin nombre se conocen como campos anónimos.

Los objetos se construyen proporcionando valores para los campos con nombre y anónimos según los ejemplos siguientes.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Este código muestra que puede usar los campos con nombre en la inicialización o puede confiar en el orden de los campos de la declaración y simplemente proporcionar los valores para cada campo a su vez. La llamada `rect` del constructor en el código anterior usa `circ` los campos con nombre, pero la llamada del constructor para usa el orden. Puede mezclar los campos ordenados y los `prism`campos con nombre, como en la construcción de .

El `option` tipo es una unión discriminada simple en la biblioteca principal de F . El `option` tipo se declara como sigue.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

El código anterior especifica `Option` que el tipo es una `Some` unión discriminada que tiene dos casos y `None`. El `Some` caso tiene un valor asociado que consta de un campo `'a`anónimo cuyo tipo está representado por el parámetro type . El `None` caso no tiene ningún valor asociado. Por `option` lo tanto, el tipo especifica un tipo genérico que tiene un valor de algún tipo o ningún valor. El `Option` tipo también tiene un `option`alias de tipo en minúsculas, , que se utiliza más comúnmente.

Los identificadores de caso se pueden usar como constructores para el tipo de unión discriminada. Por ejemplo, el código siguiente se `option` utiliza para crear valores del tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Los identificadores de mayúsculas y minúsculas también se utilizan en expresiones de coincidencia de patrones. En una expresión de coincidencia de patrones, se proporcionan identificadores para los valores asociados con los casos individuales. Por ejemplo, en el `x` código siguiente, es el identificador `Some` dado `option` el valor que está asociado con el caso del tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

En las expresiones de coincidencia de patrones, puede usar campos con nombre para especificar coincidencias de unión discriminadas. Para el tipo Shape que se declaró anteriormente, puede usar los campos con nombre como se muestra en el código siguiente para extraer los valores de los campos.

```fsharp
let getShapeWidth shape =
    match shape with
    | Rectangle(width = w) -> w
    | Circle(radius = r) -> 2. * r
    | Prism(width = w) -> w
```

Normalmente, los identificadores de caso se pueden utilizar sin calificarlos con el nombre de la unión. Si desea que el nombre siempre se califique con el nombre de la unión, puede aplicar el atributo [RequireQualifiedAccess](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-[fsharp]) a la definición de tipo de unión.

### <a name="unwrapping-discriminated-unions"></a>Desenvolviendo uniones discriminadas

En las Uniones Discriminadas de F- se usan a menudo en el modelado de dominios para ajustar un solo tipo. También es fácil extraer el valor subyacente a través de la coincidencia de patrones. No es necesario utilizar una expresión de coincidencia para un solo caso:

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

La coincidencia de patrones también se permite directamente en los parámetros de función, por lo que puede desencapsular un solo caso allí:

```fsharp
let someFunctionUsingShaderProgram (ShaderProgram id) =
    // Use the unwrapped value
    ...
```

## <a name="struct-discriminated-unions"></a>Estructurar uniones discriminadas

También puede representar Uniones Discriminadas como estructuras.  Esto se hace `[<Struct>]` con el atributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Dado que se trata de tipos de valor y no de tipos de referencia, hay consideraciones adicionales en comparación con las uniones discriminadas de referencia:

1. Se copian como tipos de valor y tienen semántica de tipo de valor.
2. No se puede utilizar una definición de tipo recursiva con una unión discriminada de estructura multicaso.
3. Debe proporcionar nombres de caso únicos para una unión discriminada de estructura multicaso.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Uso de uniones discriminadas en lugar de jerarquías de objetos

A menudo puede utilizar una unión discriminada como una alternativa más sencilla a una jerarquía de objetos pequeños. Por ejemplo, la siguiente unión discriminada `Shape` podría utilizarse en lugar de una clase base que tenga tipos derivados para circle, square, etc.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

En lugar de un método virtual para calcular un área o perímetro, como usaría en una implementación orientada a objetos, puede usar la coincidencia de patrones para bifurcar las fórmulas adecuadas para calcular estas cantidades. En el ejemplo siguiente, se utilizan diferentes fórmulas para calcular el área, dependiendo de la forma.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

La salida es como sigue:

```console
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Uso de uniones discriminadas para estructuras de datos de árboles

Las uniones discriminadas pueden ser recursivas, lo que significa que la propia unión puede incluirse en el tipo de uno o más casos. Las uniones discriminadas recursivas se pueden utilizar para crear estructuras de árbol, que se utilizan para modelar expresiones en lenguajes de programación. En el código siguiente, se usa una unión discriminada recursiva para crear una estructura de datos de árbol binario. La unión consta `Node`de dos casos, , que es un nodo con `Tip`un valor entero y subárboles izquierdo y derecho, y , que termina el árbol.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

En el código `resultSumTree` anterior, tiene el valor 10. En la ilustración siguiente `myTree`se muestra la estructura de árbol para .

![Diagrama que muestra la estructura de árbol de myTree.](../media/discriminated-unions/tree-structure-mytree.png)

Las uniones discriminadas funcionan bien si los nodos del árbol son heterogéneos. En el código siguiente, el tipo `Expression` representa el árbol de sintaxis abstracta de una expresión en un lenguaje de programación simple que admite la adición y multiplicación de números y variables. Algunos de los casos de unión no`Number`son recursivos y representan números ( ) o variables (`Variable`). Otros casos son recursivos`Add` y `Multiply`representan operaciones ( y ), donde los operandos también son expresiones. La `Evaluate` función utiliza una expresión de coincidencia para procesar recursivamente el árbol de sintaxis.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Cuando se ejecuta este código, el valor de `result` es 5.

## <a name="members"></a>Members

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
            | Circle r -> printfn "Circle with radius %f" r
            | EquilateralTriangle s -> printfn "Equilateral Triangle of side %f" s
            | Square s -> printfn "Square with side %f" s
            | Rectangle(l, w) -> printfn "Rectangle with length %f and width %f" l w
```

## <a name="common-attributes"></a>Atributos comunes

Los siguientes atributos se ven comúnmente en uniones discriminadas:

- `[<RequireQualifiedAccess>]`
- `[<NoEquality>]`
- `[<NoComparison>]`
- `[<Struct>]`

## <a name="see-also"></a>Consulte también

- [Referencia del lenguaje f](index.md)
