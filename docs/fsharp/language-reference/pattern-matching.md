---
title: Coincidencia de modelos
description: 'Obtenga información sobre cómo se usan los patrones en F # para comparar datos con estructuras lógicas, descomponer datos en elementos constituyentes o extraer información de los datos.'
ms.date: 11/12/2020
ms.openlocfilehash: e167712b082b7f587e41a78edcaf0a0db9c7294b
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "94687810"
---
# <a name="pattern-matching"></a>Coincidencia de modelos

Los patrones son reglas para transformar los datos de entrada. Se usan en todo el lenguaje F # para comparar los datos con una estructura lógica o estructuras, descomponer los datos en partes constituyentes o extraer información de los datos de varias maneras.

## <a name="remarks"></a>Comentarios

Los patrones se usan en muchas construcciones de lenguaje, como la `match` expresión. Se utilizan cuando se procesan argumentos para funciones en `let` enlaces, expresiones lambda y en los controladores de excepciones asociados a la `try...with` expresión. Para obtener más información, [Vea expresiones de coincidencia](match-expressions.md), [enlaces Let](./functions/let-bindings.md), [expresiones lambda: la `fun` palabra clave](./functions/lambda-expressions-the-fun-keyword.md)y [excepciones: `try...with` expresión](./exception-handling/the-try-with-expression.md).

Por ejemplo, en la `match` expresión, el *patrón* es lo que sigue al símbolo de canalización.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Cada patrón actúa como una regla para transformar la entrada de alguna manera. En la `match` expresión, cada patrón se examina a su vez para ver si los datos de entrada son compatibles con el patrón. Si se encuentra una coincidencia, se ejecuta la expresión de resultado. Si no se encuentra ninguna coincidencia, se prueba la siguiente regla de patrón. La parte de *condición* opcional when se explica en [expresiones de coincidencia](match-expressions.md).

Los patrones admitidos se muestran en la tabla siguiente. En tiempo de ejecución, la entrada se prueba con cada uno de los patrones siguientes en el orden indicado en la tabla y los patrones se aplican de forma recursiva, de la primera a la última como aparecen en el código y de izquierda a derecha para los patrones de cada línea.

|Nombre|Descripción|Ejemplo|
|----|-----------|-------|
|Patrón de constante|Cualquier literal numérico, de carácter o de cadena, una constante de enumeración o un identificador literal definido|`1.0`, `"test"`, `30`, `Color.Red`|
|Patrón de identificador|Un valor de caso de una Unión discriminada, una etiqueta de excepción o un caso de modelo activo|`Some(x)`<br /><br />`Failure(msg)`|
|Patrón de variable|*identifier*|`a`|
|`as` ajedrez|*patrón* como *identificador*|`(a, b) as tuple1`|
|Patrón OR|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|Y patrón|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Patrón de cons|*Identifier* :: *List-Identifier*|`h :: t`|
|Patrón de lista|[ *pattern_1*;...; *pattern_n* ]|`[ a; b; c ]`|
|Patrón de matriz|[&#124; *pattern_1*;... *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Patrón entre paréntesis|( *patrón* )|`( a )`|
|Patrón de tupla|( *pattern_1*,..., *pattern_n* )|`( a, b )`|
|Patrón de registro|{ *identificador1*  =  *pattern_1*; ... ; *identifier_n*  =  *pattern_n* }|`{ Name = name; }`|
|Patrón de carácter comodín|_|`_`|
|Patrón junto con anotación de tipo|*patrón* : *tipo*|`a : int`|
|Modelo de prueba de tipo|:? *tipo* [como *identificador* ]|`:? System.DateTime as dt`|
|Patrón null|null|`null`|
|Patrón Name|*Name expr*|`nameof str`|

## <a name="constant-patterns"></a>Patrones constantes

Los patrones constantes son los literales numéricos, de carácter y de cadena, las constantes de enumeración (con el nombre de tipo de enumeración incluido). Una `match` expresión que solo tiene patrones constantes puede compararse con una instrucción Case en otros lenguajes. La entrada se compara con el valor literal y el patrón coincide si los valores son iguales. El tipo del literal debe ser compatible con el tipo de la entrada.

En el ejemplo siguiente se muestra el uso de patrones literales y también se usa un patrón de variable y un patrón o.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Otro ejemplo de un patrón literal es un modelo basado en constantes de enumeración. Debe especificar el nombre del tipo de enumeración al usar constantes de enumeración.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Patrones de identificador

Si el patrón es una cadena de caracteres que forma un identificador válido, el formato del identificador determina cómo coincide el patrón. Si el identificador es más largo que un carácter único y comienza con un carácter en mayúsculas, el compilador intenta establecer una coincidencia con el patrón de identificador. El identificador de este patrón puede ser un valor marcado con el atributo literal, un caso de Unión discriminada, un identificador de excepción o un caso de modelo activo. Si no se encuentra ningún identificador coincidente, se produce un error en la coincidencia y la siguiente regla de patrón, el patrón de variable, se compara con la entrada.

Los patrones de Unión discriminada pueden ser casos con nombre sencillos o pueden tener un valor o una tupla que contiene varios valores. Si hay un valor, debe especificar un identificador para el valor. En el caso de una tupla, debe proporcionar un patrón de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión con nombre. Vea los ejemplos de código de esta sección para obtener ejemplos.

El `option` tipo es una Unión discriminada que tiene dos casos, `Some` y `None` . Un caso ( `Some` ) tiene un valor, pero el otro ( `None` ) es simplemente un caso con nombre. Por lo tanto, debe `Some` tener una variable para el valor asociado al `Some` caso, pero `None` debe aparecer por sí sola. En el código siguiente, `var1` se proporciona a la variable el valor que se obtiene al buscar coincidencias con el `Some` caso.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

En el ejemplo siguiente, la `PersonName` Unión discriminada contiene una mezcla de cadenas y caracteres que representan las posibles formas de los nombres. Los casos de la Unión discriminada son `FirstOnly` , `LastOnly` y `FirstLast` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

En el caso de las uniones discriminadas que tienen campos con nombre, use el signo igual (=) para extraer el valor de un campo con nombre. Por ejemplo, considere una Unión discriminada con una declaración como la siguiente.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

Puede usar los campos con nombre en una expresión de coincidencia de patrones como se indica a continuación.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

El uso del campo con nombre es opcional, por lo que en el ejemplo anterior, `Circle(r)` y `Circle(radius = r)` tienen el mismo efecto.

Cuando especifique varios campos, use el punto y coma (;) como separador.

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

Los modelos activos permiten definir una coincidencia de patrones personalizada más compleja. Para obtener más información sobre los patrones activos, vea [patrones activos](active-patterns.md).

El caso en el que el identificador es una excepción se usa en la coincidencia de patrones en el contexto de los controladores de excepciones. Para obtener información sobre la coincidencia de patrones en el control de excepciones, vea [excepciones: `try...with` expresión](./exception-handling/the-try-with-expression.md).

## <a name="variable-patterns"></a>Patrones de variables

El patrón variable asigna el valor que coincide con un nombre de variable, que luego está disponible para su uso en la expresión de ejecución a la derecha del `->` símbolo. Un patrón variable solo coincide con cualquier entrada, pero los modelos variables suelen aparecer dentro de otros patrones, lo que permite que las estructuras más complejas, como las tuplas y las matrices, se descompongan en variables.

En el ejemplo siguiente se muestra un patrón de variable dentro de un patrón de tupla.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>como patrón

El `as` patrón es un patrón que tiene una `as` cláusula anexada. La `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de una `match` expresión, o bien, en el caso en que este patrón se utiliza en un `let` enlace, el nombre se agrega como un enlace al ámbito local.

En el ejemplo siguiente se usa un `as` patrón.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>Patrón OR

El patrón o se utiliza cuando los datos de entrada pueden coincidir con varios patrones y desea ejecutar el mismo código como resultado. Los tipos de ambos lados del patrón o deben ser compatibles.

En el siguiente ejemplo se muestra el patrón o.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>Y patrón

El patrón y requiere que la entrada coincida con dos patrones. Los tipos de ambos lados del patrón y deben ser compatibles.

El ejemplo siguiente es como `detectZeroTuple` el que se muestra en la sección modelo de tupla más adelante en este tema, pero aquí `var1` y `var2` se obtienen como valores mediante el patrón y.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Patrón de cons

El patrón cons se usa para descomponer una lista en el primer elemento, el *encabezado* y una lista que contiene los elementos restantes, la *cola*.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Patrón de lista

El patrón de lista permite descomponer listas en varios elementos. El propio patrón de lista solo puede coincidir con las listas de un número específico de elementos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Patrón de matriz

El patrón de matriz se asemeja al patrón de lista y se puede usar para descomponer las matrices de una longitud específica.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Patrón entre paréntesis

Los paréntesis se pueden agrupar en torno a patrones para lograr la asociatividad deseada. En el ejemplo siguiente, los paréntesis se usan para controlar la asociatividad entre un patrón AND y un patrón cons.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Patrón de tupla

El patrón de tupla asocia la entrada en forma de tupla y permite descomponer la tupla en sus elementos constituyentes mediante el uso de variables de coincidencia de patrones para cada posición de la tupla.

En el ejemplo siguiente se muestra el patrón de tupla y también se usan patrones literales, patrones de variables y el patrón de caracteres comodín.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Patrón de registro

El patrón de registro se usa para descomponer registros para extraer los valores de los campos. El patrón no tiene que hacer referencia a todos los campos del registro; los campos omitidos simplemente no participan en la coincidencia y no se extraen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Patrón de carácter comodín

El patrón de caracteres comodín se representa mediante el carácter de subrayado ( `_` ) y coincide con cualquier entrada, al igual que el patrón de variable, con la excepción de que la entrada se descarta en lugar de asignarla a una variable. El patrón de caracteres comodín se usa a menudo en otros patrones como un marcador de posición para los valores que no son necesarios en la expresión a la derecha del `->` símbolo. El patrón de caracteres comodín también se usa con frecuencia al final de una lista de patrones para buscar coincidencias con cualquier entrada no coincidente. El patrón de caracteres comodín se muestra en muchos ejemplos de código de este tema. Vea el código anterior para ver un ejemplo.

## <a name="patterns-that-have-type-annotations"></a>Patrones que tienen anotaciones de tipo

Los patrones pueden tener anotaciones de tipo. Estos se comportan como otras anotaciones de tipo e inferencia de la guía como otras anotaciones de tipo. Se requieren paréntesis en torno a las anotaciones de tipo en los patrones. En el código siguiente se muestra un patrón que tiene una anotación de tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Modelo de prueba de tipo

El modelo de prueba de tipo se usa para hacer coincidir la entrada con un tipo. Si el tipo de entrada es una coincidencia con (o un tipo derivado de) el tipo especificado en el patrón, la coincidencia se realiza correctamente.

En el siguiente ejemplo se muestra el modelo de prueba de tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

Si solo está comprobando si un identificador es de un tipo derivado determinado, no necesita la `as identifier` parte del patrón, tal como se muestra en el ejemplo siguiente:

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a>Patrón null

El patrón null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten un valor null. Los patrones NULL se utilizan con frecuencia al interoperar con código de .NET Framework. Por ejemplo, el valor devuelto de una API de .NET podría ser la entrada a una `match` expresión. Puede controlar el flujo del programa en función de si el valor devuelto es NULL y también de otras características del valor devuelto. Puede usar el patrón null para evitar que los valores NULL se propaguen al resto del programa.

En el ejemplo siguiente se usa el patrón NULL y el patrón variable.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="nameof-pattern"></a>Patrón Name

El `nameof` patrón coincide con una cadena cuando su valor es igual a la expresión que sigue a la `nameof` palabra clave. Por ejemplo:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```

Vea el [`nameof`](nameof.md) operador para obtener información sobre lo que puede tomar como nombre.

## <a name="see-also"></a>Consulte también

- [Expresiones de coincidencia](match-expressions.md)
- [Patrones activos](active-patterns.md)
- [Referencia del lenguaje F#](index.md)
