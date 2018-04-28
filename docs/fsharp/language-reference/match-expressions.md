---
title: 'Expresiones Match (F #)'
description: 'Obtenga información acerca de cómo la expresión de coincidencia de F # proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.'
author: cartermp
ms.author: phcart
ms.date: 04/19/2018
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f6930f782384464f0d44b205ea77cbaf43898213
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
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

Las expresiones de búsqueda de coincidencias de patrón permiten bifurcaciones complejas basadas en la comparación de una expresión de prueba con un conjunto de patrones. En el `match` expresión, el *expresión de prueba* se compara con cada modelo a su vez, y cuando se encuentra una coincidencia, la correspondiente *expresión de resultado* se evalúa y el valor resultante es se devuelve como el valor de la expresión match.

El patrón de coincidencia de función que se muestra en la sintaxis anterior es una expresión lambda en qué modelo de búsqueda de coincidencias se realiza inmediatamente en el argumento. La coincidencia de función que se muestra en la sintaxis anterior es equivalente a la siguiente.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Para obtener más información sobre las expresiones lambda, vea [expresiones Lambda: la `fun` palabra clave](functions/lambda-expressions-the-fun-keyword.md).

El conjunto de modelos debe cubrir a todas las posibles coincidencias de la variable de entrada. Con frecuencia, puede usar el patrón de carácter comodín (`_`) como el último modelo para que coincida con los valores de entrada anteriormente no coincidentes.

El código siguiente muestra algunas de las formas en que el `match` se utiliza la expresión. Para obtener una referencia y ejemplos de todos los posibles modelos que se pueden usar, vea [coincidencia de patrones](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Protecciones en los modelos

Puede usar un `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón. Una cláusula de ese tipo se conoce como un *protegerse*. La expresión que sigue el `when` palabra clave no se evalúa a menos que se encuentre una coincidencia con el modelo asociado a esa protección.

En el ejemplo siguiente se muestra el uso de una restricción para especificar un intervalo numérico para un variable (modelo). Tenga en cuenta que se combinan varias condiciones mediante operadores booleanos.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Tenga en cuenta que dado que no se puede usar valores distintos de literales en el modelo, debe utilizar un `when` cláusula si tiene alguna parte de la entrada con un valor de comparación. Esto se muestra en el código siguiente:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Tenga en cuenta que cuando un patrón de unión está cubierto por una restricción, la protección se aplica a **todos los** de los patrones, no solo la última de ellas. Por ejemplo, dado el código siguiente, la protección del `when a > 12` se aplica a los `A a` y `B a`:

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

[Referencia del lenguaje F#](index.md)  
[Patrones activos](active-patterns.md)  
[Coincidencia de patrones](pattern-matching.md)  
