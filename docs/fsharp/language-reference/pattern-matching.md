---
title: Coincidencia de modelos [F#]
description: 'Obtenga información acerca de cómo se utilizan los patrones en F # para comparar los datos con estructuras lógicas, descomponer datos en sus partes constituyentes o extraer información de datos.'
ms.date: 05/16/2016
ms.openlocfilehash: 64f5b2534190552db71a67b30ece41bafed3d16e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566199"
---
# <a name="pattern-matching"></a>Coincidencia de modelos

Los patrones son reglas para transformar los datos de entrada. Se utilizan a lo largo del lenguaje F # para comparar los datos con una estructura lógica o estructuras, descomponer datos en sus partes constituyentes o extraer información de los datos de varias maneras.


## <a name="remarks"></a>Comentarios
Los modelos se utilizan en muchas construcciones de lenguaje, como el `match` expresión. Se utilizan cuando se procesan argumentos para las funciones de `let` enlaces, las expresiones lambda y en los controladores de excepción asociados a la `try...with` expresión. Para obtener más información, consulte [expresiones de coincidencia](match-expressions.md), [let (enlaces)](functions/let-bindings.md), [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md), y [excepciones: el `try...with` Expresión](exception-handling/the-try-with-expression.md).

Por ejemplo, en la `match` expresión, el *patrón* es lo que sigue al símbolo de canalización.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Cada modelo actúa como una regla para transformar la entrada de alguna manera. En el `match` expresión, cada modelo se examina a su vez para ver si los datos de entrada están compatibles con el patrón. Si se encuentra una coincidencia, se ejecuta la expresión de resultado. Si no se encuentra una coincidencia, se probará la siguiente regla de patrón. Opcional cuando *condición* parte se explica en [expresiones de coincidencia](match-expressions.md).

Los modelos admitidos se muestran en la tabla siguiente. En tiempo de ejecución, la entrada se prueba cada uno de los siguientes patrones en el orden mostrado en la tabla, y patrones son aplica de forma recursiva, de primero al último tal y como aparecen en el código y de izquierda a derecha para los patrones en cada línea.

|nombre|Descripción|Ejemplo|
|----|-----------|-------|
|Patrón de constante|Cualquier numérico, carácter, o literal de cadena, una constante de enumeración o un identificador literal definido|`1.0`, `"test"`, `30`, `Color.Red`|
|Identificador (modelo)|Un valor de caso de una unión discriminada, una etiqueta de excepción o un caso (modelo activo)|`Some(x)`<br /><br />`Failure(msg)`|
|Variable (modelo)|*identifier*|`a`|
|`as` Patrón|*patrón de* como *identificador*|`(a, b) as tuple1`|
|O un patrón|*pattern1* &#124; *pattern2*|<code>([h] &#124; [h; _])</code>|
|Y el patrón|*pattern1* &amp; *pattern2*|`(a, b) & (_, "test")`|
|Modelo de cons|*identificador* :: *identificador de la lista*|`h :: t`|
|Lista (modelo)|[ *modelo_1*;...; *modelo_n* ]|`[ a; b; c ]`|
|Matriz (modelo)|[&#124; *modelo_1*;...; *modelo_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Paréntesis (modelo)|( *patrón* )|`( a )`|
|Tupla (modelo)|( *modelo_1*,..., *modelo_n* )|`( a, b )`|
|Registro (modelo)|{ *identificador1* = *modelo_1*;...; *identificador_n* = *modelo_n* }|`{ Name = name; }`|
|Patrón de carácter comodín|_|`_`|
|Patrón junto con las anotaciones de tipo|*patrón de* : *tipo*|`a : int`|
|Modelo de prueba de tipo|:? *tipo de* [como *identificador* ]|`:? System.DateTime as dt`|
|Null (modelo)|nulo|`null`|

## <a name="constant-patterns"></a>Modelos de constante
Modelos de constantes son numéricos, de caracteres y literales de cadena, constantes de enumeración (con el nombre de tipo de enumeración incluidos). Un `match` expresión que tiene modelos de constante se puede comparar con una instrucción case en otros lenguajes. La entrada se compara con el valor literal y el modelo coincide si los valores son iguales. El tipo del literal debe ser compatible con el tipo de la entrada.

En el ejemplo siguiente se muestra el uso de modelos de literal y también usa un variable (modelo) y un modelo de OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Otro ejemplo de un literal (modelo) es un modelo basado en constantes de enumeración. Debe especificar el nombre de tipo de enumeración cuando se utilizan en constantes de enumeración.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Patrones de identificador
Si el patrón es una cadena de caracteres que forman un identificador válido, el formato del identificador determina cómo se compara el patrón. Si el identificador tiene más de un solo carácter y comienza con un carácter en mayúscula, el compilador intenta encontrar una coincidencia para el modelo de identificador. El identificador de este modelo podría ser un valor que se marca con el atributo Literal, un caso de unión discriminado, un identificador de excepción o un caso de modelo activo. Si no se encuentra ningún identificador coincidente, se produce un error en la coincidencia y la siguiente regla de patrón, el patrón de la variable, se compara con la entrada.

Patrones de unión discriminadas pueden ser simples denominado casos o pueden tener un valor o una tupla que contiene varios valores. Si hay un valor, debe especificar un identificador para el valor. En el caso de una tupla, debe proporcionar un patrón de tupla con un identificador para cada elemento de la tupla o un identificador con un nombre de campo para uno o más campos de unión de nombre. Vea los ejemplos de código en esta sección para obtener ejemplos.

El `option` tipo es una unión discriminada que tiene dos casos, `Some` y `None`. Un caso (`Some`) tiene un valor, pero el otro (`None`) es simplemente un caso con nombre. Por lo tanto, `Some` debe tener una variable para el valor asociado a la `Some` mayúsculas, pero `None` debe aparecer por sí sola. En el código siguiente, la variable `var1` recibe el valor que se obtiene mediante la búsqueda de coincidencias para el `Some` caso.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

En el ejemplo siguiente, la `PersonName` unión discriminada contiene una combinación de cadenas y caracteres que representan posibles formas de nombres. Los casos de la unión discriminada son `FirstOnly`, `LastOnly`, y `FirstLast`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

Para uniones discriminadas que han asignado un nombre campos, usa el signo igual (=) para extraer el valor de un campo con nombre. Por ejemplo, considere la posibilidad de una unión discriminada con una declaración similar al siguiente.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

Puede usar los campos con nombre en una expresión de búsqueda de coincidencias de patrón como se indica a continuación.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

El uso del campo con nombre es opcional, por lo que en el ejemplo anterior, ambas `Circle(r)` y `Circle(radius = r)` tienen el mismo efecto.

Al especificar varios campos, utilice el punto y coma (;) como separador.

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

Modelos activos permiten definir la búsqueda de coincidencias de patrón personalizado más complejas. Para obtener más información acerca de los patrones, vea [modelos activos](active-patterns.md).

El caso en que el identificador es una excepción se utiliza en la coincidencia de modelos en el contexto de controladores de excepciones. Para obtener información acerca de la coincidencia de modelos en el control de excepciones, vea [excepciones: la `try...with` expresión](exception-handling/the-try-with-expression.md).


## <a name="variable-patterns"></a>Patrones variables
El modelo de variable asigna el valor coincide con un nombre de variable, que, a continuación, está disponible para su uso en la expresión de ejecución a la derecha de la `->` símbolos. Un variable (modelo) por sí sola coincide con cualquier entrada, pero a menudo parecen patrones variables dentro de otros patrones, por lo tanto, lo que permite estructuras más complejas, como tuplas y matrices para que se puede descomponer en variables.

En el ejemplo siguiente se muestra un patrón variable dentro de un modelo de tupla.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>As (modelo)
El `as` patrón es un modelo con un `as` cláusula anexada al mismo. El `as` cláusula enlaza el valor coincidente con un nombre que se puede usar en la expresión de ejecución de un `match` expresión, o bien, en el caso donde este patrón se utiliza en un `let` de enlace, el nombre se agrega como un enlace para el ámbito local.

En el ejemplo siguiente se usa un `as` patrón.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>O un patrón
El modelo de OR se utiliza cuando los datos de entrada pueden coincidir con varios modelos, y desea ejecutar el mismo código como resultado. Los tipos de ambos lados del modelo de OR deben ser compatibles.

En el ejemplo siguiente se muestra el modelo de OR.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>Y el patrón
El modelo AND exige que la entrada coincida con dos modelos. Los tipos de ambos lados del modelo de AND deben ser compatibles.

El ejemplo siguiente es similar `detectZeroTuple` se muestra en el [tupla (modelo)](https://msdn.microsoft.com/library/#tuple) sección más adelante en este tema, pero aquí ambos `var1` y `var2` se obtienen como valores utilizando el modelo de AND.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Modelo de cons
El modelo de cons se utiliza para descomponer una lista en el primer elemento, el *head*y una lista que contiene los elementos restantes, el *final*.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Lista (modelo)
El patrón de lista permite descomponer en un número de elementos de las listas. El mismo patrón de lista puede coincidir con listas de un número específico de elementos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Matriz (modelo)
El patrón de matriz parece al modelo de la lista y puede usarse para descomponer matrices de una longitud concreta.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Paréntesis (modelo)
Paréntesis pueden agruparse alrededor de modelos para lograr la asociatividad deseada. En el ejemplo siguiente, se utilizan paréntesis para controlar la asociatividad entre un modelo de AND y un patrón de inconvenientes.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Tupla (modelo)
Tupla (modelo) coincide con los datos proporcionados en forma de tupla y permite la tupla puede descomponer en sus elementos constituyentes utilizando variables para cada posición de la tupla de coincidencia.

En el ejemplo siguiente se muestra el patrón de tupla y también usa patrones literales, modelos de variable y el patrón de carácter comodín.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Registro (modelo)
El modelo de registro se utiliza para descomponer los registros para extraer los valores de campos. El patrón no tiene que hacer referencia a todos los campos del registro; los campos omitidos simplemente no participan en la coincidencia y no se extraen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Patrón de carácter comodín
El patrón de carácter comodín se representa mediante el carácter de subrayado (`_`) de caracteres y coincide con cualquier entrada, al igual que la variable (modelo), salvo que la entrada se descarta en lugar de asignar a una variable. El patrón de carácter comodín se utiliza a menudo dentro de otros modelos como marcador de posición para los valores que no son necesarios en la expresión a la derecha de la `->` símbolos. El patrón de carácter comodín también con frecuencia se utiliza al final de una lista de patrones para que coincida con cualquier entrada no coincidente. Se muestra el patrón de carácter comodín en numerosos ejemplos de código de este tema. Vea el código anterior para obtener un ejemplo.


## <a name="patterns-that-have-type-annotations"></a>Modelos que tienen anotaciones de tipo
Modelos pueden tener anotaciones de tipo. Estos se comportan igual que otras anotaciones de tipo y orientan la inferencia como otras anotaciones de tipo. Se requieren paréntesis alrededor de las anotaciones de tipo en los patrones. El código siguiente muestra un modelo que tiene una anotación de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Modelo de prueba de tipo
El patrón de prueba de tipo se utiliza para que coincida con la entrada con respecto a un tipo. Si el tipo de entrada es una coincidencia (o un tipo derivado de) el tipo especificado en el patrón, la búsqueda de coincidencias se realiza correctamente.

En el ejemplo siguiente se muestra el modelo de prueba de tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a>Null (modelo)
El modelo de null coincide con el valor null que puede aparecer cuando se trabaja con tipos que permiten a un valor null. Los modelos de NULL se utilizan con frecuencia cuando se interopera con código de .NET Framework. Por ejemplo, el valor devuelto de una API de .NET puede ser la entrada a un `match` expresión. Puede controlar el flujo del programa en función de si el valor devuelto es null así como otras características del valor devuelto. Puede usar el modelo de null para evitar que los valores null se propaguen al resto del programa.

En el ejemplo siguiente se usa el modelo de null y el modelo de variable.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a>Vea también
[Expresiones de coincidencia](match-expressions.md)

[Patrones activos](active-patterns.md)

[Referencia del lenguaje F#](index.md)
