---
title: Funciones
description: Obtenga información sobre las funciones de F# y cómo F# admite las construcciones más comunes de la programación funcional.
ms.date: 05/16/2016
ms.openlocfilehash: e49183e0634dee1750757abadbfe9e9c824f51a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596479"
---
# <a name="functions"></a>Funciones

Las funciones son la unidad fundamental de la ejecución del programa en cualquier lenguaje de programación. Al igual que en otros lenguajes, una función de F# tiene un nombre, puede tener parámetros y tomar argumentos, y tiene un cuerpo. F# también admite construcciones de programación funcional como el tratamiento de las funciones como valores, el uso de funciones sin nombre en expresiones, la composición de funciones para crear nuevas funciones, funciones currificadas y la definición implícita de funciones mediante la aplicación parcial de argumentos de función.

Las funciones se definen mediante la palabra clave `let`, o bien, si la función es recursiva, la combinación de palabras clave `let rec`.

## <a name="syntax"></a>Sintaxis

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a>Comentarios

El *nombre de la función* es un identificador que representa la función. La *lista de parámetros* consta de parámetros sucesivos separados por espacios. Se puede especificar un tipo explícito para cada parámetro, tal como se describe en la sección Parámetros. Si no se especifica un tipo de argumento concreto, el compilador intenta deducir el tipo del cuerpo de la función. El *cuerpo de la función* consta de una expresión. La expresión que forma el cuerpo de la función suele ser una expresión compuesta formada por varias expresiones que culminan en una expresión final que es el valor devuelto. El *tipo de valor devuelto* es un signo de dos puntos seguido de un tipo y es opcional. Si no se especifica explícitamente el tipo del valor devuelto, el compilador determina el tipo de valor devuelto a partir de la expresión final.

Una definición de función simple es similar a la siguiente:

```fsharp
let f x = x + 1
```

En el ejemplo anterior, el nombre de función es `f`, el argumento es `x`, que tiene el tipo `int`, el cuerpo de la función es `x + 1` y el valor devuelto es de tipo `int`.

Las funciones se pueden marcar como `inline`. Para más información sobre `inline`, vea [Inline Functions](inline-functions.md) (Funciones insertadas).

## <a name="scope"></a>Ámbito

En cualquier nivel de ámbito distinto al ámbito de módulo, no es un error volver a usar un nombre de función o valor. Si se vuelve a usar un nombre, el último nombre declarado prevalece sobre el declarado anteriormente. Pero en el ámbito de nivel superior en un módulo, los nombres deben ser únicos. Por ejemplo, el código siguiente produce un error cuando aparece en el ámbito de módulo, pero no cuando aparece dentro de una función:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

Pero el código siguiente es aceptable en cualquier nivel de ámbito:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a>Parámetros

Los nombres de los parámetros aparecen después del nombre de función. Se puede especificar un tipo para un parámetro, como se muestra en el ejemplo siguiente:

```fsharp
let f (x : int) = x + 1
```

Si se especifica un tipo, sigue al nombre del parámetro y se separa del nombre mediante dos puntos. Si se omite el tipo del parámetro, el compilador infiere el tipo de parámetro. Por ejemplo, en la siguiente definición de función, se deduce que el argumento `x` es del tipo `int` porque 1 es de tipo `int`.

```fsharp
let f x = x + 1
```

Pero el compilador intentará que la función sea lo más genérica posible. Por ejemplo, observe el código siguiente:

```fsharp
let f x = (x, x)
```

La función crea una tupla a partir de un argumento de cualquier tipo. Dado que no se especifica el tipo, la función se puede usar con cualquier tipo de argumento. Para más información, vea [Automatic Generalization](../generics/automatic-generalization.md) (Generalización automática).

## <a name="function-bodies"></a>Cuerpos de función

El cuerpo de una función puede contener definiciones de variables locales y funciones. Estas variables y funciones están en ámbito en el cuerpo de la función actual, pero no fuera de ella. Una vez habilitada la opción de sintaxis ligera, se debe usar sangría para indicar que es una definición de un cuerpo de función, como se muestra en el ejemplo siguiente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

Para más información, vea [Code Formatting Guidelines](../../style-guide/formatting.md) (Instrucciones de formato de código) y [Verbose Syntax](../verbose-syntax.md) (Sintaxis detallada).

## <a name="return-values"></a>Valores devueltos

El compilador usa la expresión final en el cuerpo de una función para determinar el tipo y el valor devuelto. Es posible que el compilador deduzca el tipo de la expresión final a partir las expresiones anteriores. En la función `cylinderVolume`, como se muestra en la sección anterior, el tipo de `pi` se determina a partir del tipo del literal `3.14159` como `float`. El compilador usa el tipo de `pi` para determinar el tipo de la expresión `h * pi * r * r` como `float`. Por tanto, el tipo de valor devuelto global de la función es `float`.

Para especificar explícitamente el valor devuelto, escriba el código de esta forma:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

Tal como se escribe el código anterior, el compilador aplica **float** a toda la función. Si también quiere aplicarlo a los tipos de parámetro, use el código siguiente:

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a>Llamar a una función

Las funciones se llaman especificando el nombre de la función seguido de un espacio y, después, los argumentos separados por espacios. Por ejemplo, para llamar a la función **cylinderVolume** y asignar el resultado al valor **vol**, se escribe el código siguiente:

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a>Aplicación parcial de argumentos

Si se proporcionan menos argumentos que los especificados, se crea una nueva función que espera los argumentos restantes. Este método de control de argumentos se conoce como *currificación* y es una característica de los lenguajes de programación funcionales como F#. Por ejemplo, supongamos que está trabajando con dos tamaños de canalización: una tiene un radio de **2,0** y la otra tiene un radio de **3,0**. Se podrían crear funciones que determinen el volumen de canalización de esta forma:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

Después, se proporcionaría el argumento adicional según sea necesario para las distintas longitudes de canalización de los dos tamaños diferentes:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a>Funciones recursivas

Las *funciones recursivas* son funciones que se llaman a sí mismas. Requieren que se especifique la palabra clave **rec** después de la palabra clave **let**. La función recursiva se invoca desde el interior del cuerpo de la función de la misma forma que se invocaría cualquier llamada de función. La siguiente función recursiva calcula el número *n* de Fibonacci. La secuencia de números de Fibonacci se conoce desde la antigüedad y es una secuencia en la que cada número sucesivo es la suma de los dos números anteriores en la secuencia.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

Es posible que algunas funciones recursivas desborden la pila del programa o tengan un rendimiento ineficaz si no se escriben con cuidado y con el conocimiento de determinadas técnicas especiales, como el uso de acumuladores y continuaciones.

## <a name="function-values"></a>Valores de función

En F#, todas las funciones se consideran valores, de hecho, se conocen como *valores de función*. Dado que las funciones son valores, se pueden usar como argumentos de otras funciones o en otros contextos donde se usan los valores. El siguiente ejemplo muestra una función que toma un valor de función como argumento:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

El tipo de un valor de función se especifica mediante el token `->`. En el lado izquierdo de este token está el tipo del argumento y, en el lado derecho, el valor devuelto. En el ejemplo anterior, `apply1` es una función que toma una función `transform` como argumento, donde `transform` es una función que toma un entero y devuelve otro entero. En el código siguiente se muestra cómo usar `apply1`:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

El valor de `result` será 101 después de ejecutar el código anterior.

Si hay varios argumentos, se separan por sucesivos tokens `->`, como se muestra en el ejemplo siguiente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

El resultado es 200.

## <a name="lambda-expressions"></a>Expresiones lambda

Una *expresión lambda* es una función sin nombre. En los ejemplos anteriores, en lugar de definir las funciones con nombre **increment** y **mul**, se podrían usar expresiones lambda de esta forma:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

Las expresiones lambda se definen mediante la palabra clave `fun`. Una expresión lambda es similar a una definición de función, salvo que en lugar del token `=` se usa el token `->` para separar la lista de argumentos del cuerpo de la función. Al igual que en una definición de función normal, se pueden deducir o especificar explícitamente los tipos de argumento, y el tipo de valor devuelto de la expresión lambda se deduce del tipo de la última expresión en el cuerpo. Para obtener más información, vea [Expresiones lambda: Palabra clave `fun`](lambda-expressions-the-fun-keyword.md).

## <a name="function-composition-and-pipelining"></a>Composición de funciones y canalización

En F#, las funciones se pueden componer a partir de otras funciones. La composición de dos funciones **función1** y **función2** es otra función que representa la aplicación de **función1** seguida de la aplicación de **función2**:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

El resultado es 202.

La canalización permite encadenar llamadas a funciones como operaciones sucesivas. La canalización funciona de la siguiente manera:

```fsharp
let result = 100 |> function1 |> function2
```

El resultado es 202 de nuevo.

Los operadores de composición toman dos funciones y devuelven una función. Por el contrario, los operadores de canalización toman una función y un argumento, y devuelven un valor. En el ejemplo de código siguiente se muestra la diferencia entre los operadores de canalización y composición mostrando las diferencias en las firmas de función y el uso.

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a>Sobrecargar funciones

Los métodos de un tipo se pueden sobrecargar, pero no las funciones. Para más información, vea [Métodos](../members/methods.md).

## <a name="see-also"></a>Vea también

- [Valores](../values/index.md)
- [Referencia del lenguaje F#](../index.md)
