---
title: Expresiones de coincidencia.
description: Obtenga información sobre cómo el F# expresión de coincidencia proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.
ms.date: 04/19/2018
ms.openlocfilehash: 8972cc012d2746cb720eeed1acee403948941425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61903960"
---
# <a name="match-expressions"></a>Expresiones de coincidencia.

El `match` expresión proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.

## <a name="syntax"></a>Sintaxis

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>Comentarios

Las expresiones de coincidencia de patrón permiten bifurcaciones complejas basadas en la comparación de una expresión de prueba con un conjunto de patrones. En el `match` expresión, el *expresión de prueba* se compara con cada modelo a su vez, y cuando se encuentra una coincidencia, la correspondiente *expresión de resultado* se evalúa y el valor resultante es se devuelve como el valor de la expresión de coincidencia.

El patrón de coincidencia de función que se muestra en la sintaxis anterior es una expresión lambda en el patrón de coincidencia se realiza inmediatamente en el argumento. El patrón de coincidencia de función que se muestra en la sintaxis anterior es equivalente a la siguiente.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Para obtener más información sobre las expresiones lambda, vea [expresiones Lambda: El `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md).

El conjunto completo de patrones debe cubrir a todas las coincidencias de la variable de entrada. Con frecuencia, puede usar el patrón de carácter comodín (`_`) como el último patrón para que coincida con los valores de entrada anteriormente no coincidentes.

El código siguiente muestra algunas de las formas en que el `match` se usa la expresión. Para obtener una referencia y ejemplos de todos los posibles modelos que se pueden usar, consulte [coincidencia de patrones](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Protecciones en los modelos

Puede usar un `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón. Una cláusula de ese tipo se conoce como un *protegerse*. La expresión que sigue el `when` palabra clave no se evalúa a menos que se realiza una coincidencia para el modelo asociado a esa restricción.

El ejemplo siguiente muestra el uso de una restricción para especificar un intervalo numérico para un modelo de variable. Tenga en cuenta que se combinan varias condiciones mediante operadores booleanos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Tenga en cuenta que dado que no se puede usar valores distintos de literales en el patrón, debe usar un `when` cláusula si tiene alguna parte de la entrada con un valor de comparación. Esto se muestra en el código siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Tenga en cuenta que cuando un patrón de unión está cubierto por una restricción, la protección se aplica a **todas** de los patrones, no solo la última de ellas. Por ejemplo, dado el código siguiente, el guardián `when a > 12` se aplica a ambos `A a` y `B a`:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Patrones activos](active-patterns.md)
- [Coincidencia de patrones](pattern-matching.md)