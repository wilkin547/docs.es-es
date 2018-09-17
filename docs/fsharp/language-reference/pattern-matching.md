---
title: Coincidencia de modelos [F#]
description: 'Obtenga información sobre cómo se usan los patrones en F # para comparar los datos con estructuras lógicas, descomponer datos en sus partes constituyentes o extraer información de los datos.'
ms.date: 05/16/2016
ms.openlocfilehash: 5ad3d3e1a78246afdfa2948fd0fb84fa04686d30
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668488"
---
# <a name="pattern-matching"></a>Coincidencia de modelos

Los modelos son reglas para transformar los datos de entrada. Se utilizan en todo el lenguaje F # para comparar los datos con una o más estructuras lógicas, descomponer datos en sus partes constituyentes o extraer información de los datos de varias maneras.

## <a name="remarks"></a>Comentarios

Los modelos se utilizan en muchas construcciones de lenguaje, como el `match` expresión. Se utilizan cuando se procesan argumentos para funciones en `let` enlaces, las expresiones lambda y en los controladores de excepción asociados del `try...with` expresión. Para obtener más información, consulte [expresiones de coincidencia](match-expressions.md), [enlaces let](functions/let-bindings.md), [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md), y [excepciones: la `try...with` Expresión](exception-handling/the-try-with-expression.md).

Por ejemplo, en el `match` expresión, el *patrón* lo que sigue el símbolo de canalización.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Cada modelo actúa como una regla para transformar la entrada de alguna manera. En el `match` cada patrón de expresión se examina a su vez, para ver si están compatibles con el patrón de los datos de entrada. Si se encuentra una coincidencia, se ejecuta la expresión de resultado. Si no se encuentra una coincidencia, se prueba la regla del modelo siguiente. Opcional cuando *condición* parte se explica en [expresiones de coincidencia](match-expressions.md).

Modelos admitidos se muestran en la tabla siguiente. En tiempo de ejecución, la entrada se prueba con cada uno de los siguientes patrones en el orden mostrado en la tabla, y patrones aplica de forma recursiva, del primero al último tal y como aparecen en el código y de izquierda a derecha para los modelos en cada línea.

|nombre|Descripción|Ejemplo|
|----|-----------|-------|
|Patrón de constante|Cualquier numérico, carácter o literal de cadena, una constante de enumeración o un identificador literal definido|`1.0`, `"test"`, `30`, `Color.Red`|
|Patrón de identificador|Un valor de caso de una unión discriminada, una etiqueta de excepción o un caso de modelo activo|`Some(x)`<br /><br />`Failure(msg)`|
|Modelo de variable|*identifier*|`a`|
|`as` Patrón|*patrón* como *identificador*|`(a, b) as tuple1`|
|O un patrón|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|Y el patrón|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Modelo de cons|*identificador* :: *identificador de la lista*|`h :: t`|
|Modelo de lista|[ *modelo_1*;...; *modelo_n* ]|`[ a; b; c ]`|
|Patrón de matriz|[&#124; *modelo_1*;.; *modelo_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Modelo entre paréntesis|( *patrón* )|`( a )`|
|Modelo de tupla|( *modelo_1*,..., *modelo_n* )|`( a, b )`|
|Modelo de registro|{ *identificador1* = *modelo_1*;...; *identificador_n* = *modelo_n* }|`{ Name = name; }`|
|Patrón de caracteres comodín|_|`_`|
|Modelo junto con anotación de tipo|*patrón* : *tipo*|`a : int`|
|Modelo de prueba de tipo|:? *tipo* [como *identificador* ]|`:? System.DateTime as dt`|
|Modelo de null|nulo|`null`|

## <a name="constant-patterns"></a>Modelos de constante

Modelos de constante son numéricos, caracteres y literales de cadena, constantes de enumeración (con el nombre de tipo de enumeración incluidos). Un `match` expresión que tiene modelos de constante solo puede compararse con una instrucción case de otros lenguajes. La entrada se compara con el valor literal y el modelo coincide si los valores son iguales. El tipo del literal debe ser compatible con el tipo de la entrada.

El ejemplo siguiente muestra el uso de modelos de literal y también usa un modelo de variable y un modelo de OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Otro ejemplo de un modelo de literal es un modelo basado en constantes de enumeración. Debe especificar el nombre del tipo de enumeración al usar las constantes de enumeración.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Patrones de identificador

Si el patrón es una cadena de caracteres que forman un identificador válido, el formato del identificador determina cómo se compara el patrón. Si el identificador tiene más de un solo carácter y comienza con una letra mayúscula, el compilador intenta hallar una coincidencia con el patrón de identificador. El identificador de este modelo podría ser un valor marcado con el atributo Literal, un caso de unión discriminado, un identificador de excepción o un caso de modelo activo. Si no se encuentra ningún identificador coincidente, la coincidencia produce un error y la regla del modelo siguiente, el modelo de variable, se compara con la entrada.

Modelos de unión discriminada pueden ser simples casos con nombre o pueden tener un valor o una tupla que contiene varios valores. Si hay un valor, debe especificar un identificador para el valor. En el caso de una tupla, debe proporcionar un modelo de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión de llamada. Vea los ejemplos de código en esta sección para obtener ejemplos.

El `option` tipo es una unión discriminada que tiene dos casos, `Some` y `None`. Un caso (`Some`) tiene un valor, pero el otro (`None`) es simplemente un caso con nombre. Por lo tanto, `Some` debe tener una variable para el valor asociado con el `Some` case, pero `None` deben aparecer por sí mismo. En el código siguiente, la variable `var1` se asigna el valor que se obtiene mediante la coincidencia para el `Some` caso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

En el ejemplo siguiente, la `PersonName` unión discriminada contiene una combinación de cadenas y caracteres que representan posibles formas de nombres. Los casos de la unión discriminada son `FirstOnly`, `LastOnly`, y `FirstLast`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

Las uniones discriminadas que tienen campos de nombre, utilice el signo igual (=) para extraer el valor de un campo con nombre. Por ejemplo, considere una unión discriminada con una declaración similar al siguiente.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

Puede usar los campos con nombre en una expresión de coincidencia de patrón como sigue.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

El uso del campo con nombre es opcional, por lo que en el ejemplo anterior, ambos `Circle(r)` y `Circle(radius = r)` tienen el mismo efecto.

Al especificar varios campos, use el punto y coma (;) como separador.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

Modelos activos permiten definir coincidencias de modelos personalizadas más complejas. Para obtener más información acerca de los patrones activos, vea [modelos activos](active-patterns.md).

El caso en que el identificador es una excepción se usa en la coincidencia de patrones en el contexto de los controladores de excepciones. Para obtener información acerca de la coincidencia de patrones en el control de excepciones, vea [excepciones: la `try...with` expresión](exception-handling/the-try-with-expression.md).

## <a name="variable-patterns"></a>Modelos de variable

El modelo de variable asigna el valor coincide con un nombre de variable, que está disponible para su uso en la expresión de ejecución a la derecha de la `->` símbolos. Un modelo de variable individual coincide con cualquier entrada, pero los modelos de variable suelen aparecen dentro de otros modelos, por lo tanto, habilitar estructuras más complejas, como las tuplas y matrices para descomposición en variables.

El ejemplo siguiente muestra un modelo de variable dentro de un modelo de tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>como el patrón

El `as` patrón es un modelo que tiene un `as` cláusula anexado a él. El `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de un `match` expresión, o bien, en el caso de que se usa este patrón en una `let` de enlace, el nombre se agrega como un enlace con el ámbito local.

En el ejemplo siguiente se usa un `as` patrón.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>O un patrón

Cuando los datos de entrada pueden coincidir con varios modelos, y desea ejecutar el mismo código como resultado, se usa el modelo de OR. Los tipos de ambos lados del modelo de OR deben ser compatibles.

El ejemplo siguiente muestra el modelo de OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>Y el patrón

El modelo de AND exige que la entrada coincida con dos modelos. Los tipos de ambos lados del modelo de AND deben ser compatibles.

El ejemplo siguiente es similar a `detectZeroTuple` se muestra en el [modelo de tupla](https://msdn.microsoft.com/library/#tuple) sección más adelante en este tema, pero aquí ambos `var1` y `var2` se obtienen como valores utilizando el modelo de AND.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Modelo de cons

El modelo de cons se utiliza para descomponer una lista en el primer elemento, el *head*y una lista que contiene los elementos restantes, el *final*.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Modelo de lista

El patrón de lista permite descomponer en un número de elementos de las listas. El mismo patrón de lista puede coincidir con sólo las listas de un número específico de elementos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Patrón de matriz

El patrón de matriz parece al modelo de lista y se puede usar para descomponer matrices de una longitud concreta.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Modelo entre paréntesis

Los paréntesis pueden agruparse en torno a los modelos para lograr la asociatividad deseada. En el ejemplo siguiente, se utilizan paréntesis para controlar la asociatividad entre un modelo de AND y un modelo de cons.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Modelo de tupla

El modelo de tupla asocia la entrada en forma de tupla y permite la tupla que se descompone en sus elementos constituyentes utilizando variables para cada posición de la tupla de coincidencia de patrones.

El ejemplo siguiente muestra el modelo de tupla y también usa modelos de literal, modelos de variable y el patrón de caracteres comodín.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Modelo de registro

El modelo de registro se utiliza para descomponer los registros para extraer los valores de campos. El patrón no tiene que hacer referencia a todos los campos del registro; solo los campos omitidos no participan en la coincidencia y no se extraen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Patrón de caracteres comodín

El modelo de carácter comodín se representa mediante el carácter de subrayado (`_`) de caracteres y coincide con cualquier entrada, al igual que el modelo de variable, salvo que la entrada se descarta en lugar de asignar a una variable. El modelo de carácter comodín se utiliza a menudo dentro de otros modelos como marcador de posición para los valores que no son necesarios en la expresión a la derecha de la `->` símbolos. El modelo de carácter comodín también con frecuencia se utiliza al final de una lista de patrones para que coincida con cualquier entrada no coincidente. En muchos ejemplos de código de este tema se muestra el patrón de caracteres comodín. Vea el código anterior para obtener un ejemplo.

## <a name="patterns-that-have-type-annotations"></a>Patrones que tienen anotaciones de tipo

Los modelos pueden tener anotaciones de tipo. Estas se comportan igual que otras anotaciones de tipo y orientan la inferencia como las demás anotaciones de tipo. Se necesitan paréntesis en torno a las anotaciones de tipos de patrones. El código siguiente muestra un modelo que tiene una anotación de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Modelo de prueba de tipo

El modelo de prueba de tipo se usa para comparar la entrada con un tipo. Si el tipo de entrada es una coincidencia (o un tipo derivado de) el tipo especificado en el modelo, la coincidencia se realiza correctamente.

El ejemplo siguiente muestra el patrón de prueba de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Modelo de null

El modelo de null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten un valor null. Los modelos de NULL se utilizan con frecuencia al interoperar con código de .NET Framework. Por ejemplo, el valor devuelto de una API de .NET puede ser la entrada a un `match` expresión. Puede controlar el flujo del programa en función de si el valor devuelto es null y también en otras características del valor devuelto. Puede usar el modelo de null para impedir que se propaguen al resto del programa valores null.

En el ejemplo siguiente se usa el modelo de null y el modelo de variable.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>Vea también

- [Expresiones de coincidencia](match-expressions.md)
- [Patrones activos](active-patterns.md)
- [Referencia del lenguaje F#](index.md)
