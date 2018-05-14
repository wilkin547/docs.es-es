---
title: Uniones discriminadas (F#)
description: 'Obtenga información acerca de cómo usar F # uniones discriminadas.'
ms.date: 05/16/2016
ms.openlocfilehash: 617c659e26df52819a98294bcbfa081ab82fed03
ms.sourcegitcommit: e5bb395ec86f536e114314184288f40a8c745e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2018
---
# <a name="discriminated-unions"></a>Uniones discriminadas

Uniones discriminadas proporcionan compatibilidad para los valores que pueden ser uno de un número de casos con nombre, posiblemente cada uno con valores y tipos diferentes. Uniones discriminadas son útiles para datos heterogéneos; datos que pueden tener casos especiales, incluidos válidos y casos de error; datos que varían en el tipo de una instancia a otra; y como una alternativa a las jerarquías de objetos pequeños. Además, discriminadas uniones se utilizan para representar estructuras de datos de árbol.

## <a name="syntax"></a>Sintaxis

```fsharp
[ attributes ]
type [accessibility-modifier] type-name =
    | case-identifier1 [of [ fieldname1 : ] type1 [ * [ fieldname2 : ] type2 ...]
    | case-identifier2 [of [fieldname3 : ]type3 [ * [ fieldname4 : ]type4 ...]
...
```

## <a name="remarks"></a>Comentarios
Uniones discriminadas son similares a los tipos de unión en otros lenguajes, pero hay diferencias. Como con un tipo de unión en C++ o un tipo variant en Visual Basic, los datos almacenados en el valor no es fijo; puede ser una de varias opciones distintas. A diferencia de uniones en estos otros idiomas, sin embargo, cada una de las opciones posibles se concede un *identificador de caso*. Los identificadores de caso son nombres para los diversos posibles tipos de valores que pudieron ser objetos de este tipo; los valores son opcionales. Si los valores no están presentes, el caso equivale a un caso de enumeración. Si los valores están presentes, cada valor puede ser un valor único de un tipo especificado o una tupla que agrega varios campos de la mismos o de tipos diferentes. Puede asignar un campo individual de un nombre, pero el nombre es opcional, aunque se denominan otros campos en las mismas mayúsculas y minúsculas.

Accesibilidad para uniones discriminadas tiene como valor predeterminado `public`.

Por ejemplo, considere la siguiente declaración de un tipo de forma.

```fsharp
type Shape =
    | Rectangle of width : float * length : float
    | Circle of radius : float
    | Prism of width : float * float * height : float
```

El código anterior declara una unión discriminada forma, que puede tener valores de cualquiera de los tres casos: rectángulo, círculo y prisma. Cada caso tiene un conjunto diferente de campos. El rectángulo caso tiene dos denominado campos, ambos de tipo `float`, que tiene el ancho de los nombres y la longitud. El caso de círculo tiene un solo campo con nombre, radius. El caso de prisma tiene tres campos, dos de qué (ancho y alto) se denominan campos. Campos sin nombre se conocen como campos anónimos.

Construir objetos proporcionando los valores para los campos con nombre y anónimos según los siguientes ejemplos.

```fsharp
let rect = Rectangle(length = 1.3, width = 10.0)
let circ = Circle (1.0)
let prism = Prism(5., 2.0, height = 3.0)
```

Este código muestra que puede usar los campos con nombre en la inicialización, o puede confiar en el orden de los campos de la declaración y basta con que proporcione los valores para cada campo a su vez. La llamada al constructor para `rect` en el código anterior usa los campos con nombre, pero la llamada al constructor para `circ` usa la ordenación. Puede combinar los campos ordenados y con el nombre de campos, como se muestra en la construcción de `prism`.

El `option` tipo es una unión discriminada simple en la biblioteca básica de F #. El `option` tipo se declara como sigue.

```fsharp
// The option type is a discriminated union.
type Option<'a> =
    | Some of 'a
    | None
```

El código anterior especifica que el tipo `Option` es una unión discriminada que tiene dos casos, `Some` y `None`. El `Some` caso tiene un valor asociado que consta de un campo anónimo, cuyo tipo es representado por el parámetro de tipo `'a`. El `None` caso no tiene ningún valor asociado. Por lo tanto la `option` tipo especifica un tipo genérico que tiene un valor de algún tipo o ningún valor. El tipo `Option` también tiene un alias de tipo en minúscula, `option`, que es más frecuente.

Los identificadores de caso pueden utilizarse como constructores para el tipo de unión discriminado. Por ejemplo, el código siguiente se utiliza para crear valores de la `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2001.fs)]

Los identificadores de caso también se utilizan en expresiones de coincidencia de patrones. En una expresión de coincidencia de modelos, los identificadores se proporcionan para los valores asociados a los casos individuales. Por ejemplo, en el código siguiente, `x` el identificador tiene el valor que está asociado el `Some` mayúsculas de la `option` tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2002.fs)]

En expresiones de coincidencia de patrones, puede utilizar campos con nombre para especificar las coincidencias de unión discriminadas. Para el tipo de forma que se declaró previamente, puede usar los campos con nombre, como se muestra en el siguiente código para extraer los valores de los campos.

```fsharp
let getShapeHeight shape =
    match shape with
    | Rectangle(height = h) -> h
    | Circle(radius = r) -> 2. * r
    | Prism(height = h) -> h
```

Normalmente, los identificadores de caso pueden utilizarse sin calificarlos con el nombre de la unión. Si desea que el nombre que siempre estén calificados con el nombre de la unión, se puede aplicar el [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15) atributo a la definición de tipo de unión.

### <a name="unwrapping-discriminated-unions"></a>Uniones discriminadas desencapsulación

En uniones discriminadas de F # suelen utilizarse en el modelado de dominio para un único tipo de ajuste. Es fácil extraer el valor subyacente a través de coincidencia de patrones también. No es necesario usar una expresión de coincidencia para un único caso:
```fsharp
let ([UnionCaseName] [values]) = [UnionValue]
```

En el siguiente ejemplo se muestra esto:

```fsharp
type ShaderProgram = | ShaderProgram of id:int

let someMethodUsingShaderProgram shaderProgram =
    let (ShaderProgram id) = shaderProgram
    // Use the unwrapped value
    ..
```

## <a name="struct-discriminated-unions"></a>Struct uniones discriminadas

A partir de F # 4.1, también puede representar uniones discriminadas como estructuras.  Esto se realiza con el `[<Struct>]` atributo.

```fsharp
[<Struct>]
type SingleCase = Case of string

[<Struct>]
type Multicase =
    | Case1 of Case1 : string
    | Case2 of Case2 : int
    | Case3 of Case3 : double
```

Dado que estos son tipos de valor y no hacen referencia a tipos, hay adicional en comparación con la referencia de consideraciones de uniones discriminadas:

1. Se copian como tipos de valor y tiene la semántica de tipos de valor.
2. No se puede usar una definición de tipo recursivo con un struct multicase discriminadas Union.
3. Debe proporcionar nombres únicos de casos para un struct multicase discriminadas Union.

## <a name="using-discriminated-unions-instead-of-object-hierarchies"></a>Usar uniones discriminadas en lugar de las jerarquías de objetos
A menudo, puede usar una unión discriminada como una alternativa más sencilla a una jerarquía de objetos pequeños. Por ejemplo, la unión discriminada siguiente podría usarse en lugar de un `Shape` clase base que tiene tipos derivados para círculo, cuadrado, y así sucesivamente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2003.fs)]

En su lugar de un método virtual para calcular un área o perímetro, que se usan en una implementación orientada a objetos, puede usar la coincidencia de patrones a diversificar las fórmulas adecuadas para calcular estas cantidades. En el ejemplo siguiente, se utilizan fórmulas diferentes para calcular el área, dependiendo de la forma.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2004.fs)]

La salida es la siguiente:

```
Area of circle that has radius 15.000000: 706.858347
Area of square that has side 10.000000: 100.000000
Area of rectangle that has height 5.000000 and width 10.000000 is 50.000000
```

## <a name="using-discriminated-unions-for-tree-data-structures"></a>Usar uniones discriminadas para las estructuras de datos de árbol
Uniones discriminadas pueden ser recursivas, lo que significa que la propia unión puede incluirse en el tipo de uno o varios casos. Recursiva uniones discriminadas pueden usarse para crear estructuras de árbol, que se utilizan para expresiones de modelo en lenguajes de programación. En el código siguiente, un discriminadas union se utiliza para crear una estructura de datos de árbol binario. La unión consta de dos casos, `Node`, que es un nodo con un valor entero y subárboles izquierdos y derecho, y `Tip`, que termina el árbol.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2005.fs)]

En el código anterior, `resultSumTree` tiene el valor 10. En la siguiente ilustración muestra la estructura de árbol de `myTree`.

![Estructura de árbol de myTree](../media/TreeStructureDiagram.png)

Uniones discriminadas funcionan bien si los nodos en el árbol son heterogéneos. En el código siguiente, el tipo `Expression` representa el árbol de sintaxis abstracta de una expresión en un lenguaje de programación simple que admite la suma y multiplicación de números y variables. Algunos de los casos de unión no son recursivos y representan cualquiera números (`Number`) o variables (`Variable`). Otros casos son recursivos y representan operaciones (`Add` y `Multiply`), donde los operandos también son expresiones. El `Evaluate` función usa una expresión de coincidencia de al proceso de forma recursiva el árbol de sintaxis.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet2006.fs)]

Cuando se ejecuta este código, el valor de `result` es 5.

## <a name="common-attributes"></a>Atributos comunes

Los siguientes atributos se observa habitualmente en uniones discriminadas:

* `[RequireQualifiedAccess]`
* `[NoEquality]`
* `[NoComparison]`
* `[Struct]` (F # 4.1 y versiones posteriores)

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)
