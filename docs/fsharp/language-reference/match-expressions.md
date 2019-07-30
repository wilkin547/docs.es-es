---
title: Expresiones de coincidencia
description: Obtenga información sobre F# cómo la expresión de coincidencia proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627614"
---
# <a name="match-expressions"></a>Expresiones de coincidencia

La `match` expresión proporciona control de bifurcación que se basa en la comparación de una expresión con un conjunto de patrones.

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

Las expresiones de coincidencia de patrones permiten la bifurcación compleja basada en la comparación de una expresión de prueba con un conjunto de patrones. En la `match` expresión, *Test-Expression* se compara con cada patrón a su vez y, cuando se encuentra una coincidencia, se evalúa la *expresión de resultado* correspondiente y el valor resultante se devuelve como el valor de la expresión de coincidencia.

La función de coincidencia de patrones mostrada en la sintaxis anterior es una expresión lambda en la que la coincidencia de patrones se realiza inmediatamente en el argumento. La función de coincidencia de patrones que se muestra en la sintaxis anterior es equivalente a la siguiente.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Para obtener más información sobre las expresiones lambda [, vea expresiones lambda: `fun` Palabra clave](./functions/lambda-expressions-the-fun-keyword.md).

Todo el conjunto de patrones debe cubrir todas las posibles coincidencias de la variable de entrada. Con frecuencia, se usa el patrón de`_`carácter comodín () como último patrón para buscar coincidencias con los valores de entrada no coincidentes previamente.

En el código siguiente se muestran algunas de las formas en que `match` se usa la expresión. Para obtener una referencia y ejemplos de todos los patrones posibles que se pueden usar, vea [coincidencia de patrones](pattern-matching.md).

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Protecciones en patrones

Puede usar una `when` cláusula para especificar una condición adicional que la variable debe cumplir para que coincida con un patrón. Este tipo de cláusula se conoce como *protección*. La expresión que sigue `when` a la palabra clave no se evalúa a menos que se haga una coincidencia con el patrón asociado a dicha protección.

En el ejemplo siguiente se muestra el uso de una protección para especificar un intervalo numérico para un patrón de variable. Tenga en cuenta que se combinan varias condiciones mediante el uso de operadores booleanos.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Tenga en cuenta que, dado que los valores distintos de los literales no se pueden usar en `when` el modelo, debe utilizar una cláusula si tiene que comparar alguna parte de la entrada con un valor. Esto se muestra en el código siguiente:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Tenga en cuenta que cuando un modelo de Unión está incluido en una protección, la protección se aplica a **todos** los patrones, no solo al último. Por ejemplo, según el código siguiente, la protección `when a > 12` se aplica tanto `A a` a `B a`como a:

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
