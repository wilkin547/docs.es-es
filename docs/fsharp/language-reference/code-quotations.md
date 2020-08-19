---
title: Expresiones de código delimitadas
description: 'Obtenga información sobre las expresiones de código delimitadas de F #, una característica del lenguaje que permite generar y trabajar con las expresiones de código de F # mediante programación.'
ms.date: 08/13/2020
ms.openlocfilehash: 070e127397a5da7d70281d08ef7cafdb9b4f4fe5
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558340"
---
# <a name="code-quotations"></a>Expresiones de código delimitadas

En este artículo se describen las expresiones de *código delimitadas*, una característica del lenguaje que permite generar y trabajar con las expresiones de código de F # mediante programación. Esta característica permite generar un árbol de sintaxis abstracta que representa el código de F #. A continuación, el árbol de sintaxis abstracta puede atravesarse y procesarse según las necesidades de la aplicación. Por ejemplo, puede usar el árbol para generar código de F # o generar código en otro lenguaje.

## <a name="quoted-expressions"></a>Expresiones entre comillas

Una *expresión entre comillas* es una expresión de F # en el código que está delimitada de manera que no se compila como parte del programa, sino que se compila en un objeto que representa una expresión de f #. Puede marcar una expresión entre comillas de una de estas dos maneras: con información de tipo o sin información de tipo. Si desea incluir información de tipo, use los símbolos `<@` y `@>` para delimitar la expresión entre comillas. Si no necesita información de tipo, use los símbolos `<@@` y `@@>` . En el código siguiente se muestran las comillas con tipo y sin tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Atravesar un árbol de expresión grande es más rápido si no incluye información de tipo. El tipo resultante de una expresión entre comillas con los símbolos con tipo es `Expr<'T>` , donde el parámetro de tipo tiene el tipo de la expresión determinado por el algoritmo de inferencia de tipos del compilador de F #. Cuando se usan expresiones de código delimitadas sin información de tipos, el tipo de la expresión entrecomillada es el tipo no genérico [expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html). Puede llamar a la propiedad [raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) en la clase con tipo `Expr` para obtener el objeto sin tipo `Expr` .

Hay una variedad de métodos estáticos que permiten generar objetos de expresión de F # mediante programación en la `Expr` clase sin usar expresiones entre comillas.

Tenga en cuenta que una expresión de código delimitada debe incluir una expresión completa. Para un `let` enlace, por ejemplo, necesitará la definición del nombre enlazado y una expresión adicional que use el enlace. En la sintaxis detallada, se trata de una expresión que sigue a la `in` palabra clave. En el nivel superior de un módulo, se trata simplemente de la siguiente expresión del módulo, pero en una expresión de código delimitada, se requiere explícitamente.

Por lo tanto, la siguiente expresión no es válida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Pero las siguientes expresiones son válidas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Para evaluar las comillas de F #, debe utilizar el [evaluador de Comillas de f #](https://github.com/fsprojects/FSharp.Quotations.Evaluator). Proporciona compatibilidad para evaluar y ejecutar objetos de expresión de F #.

## <a name="expr-type"></a>Tipo de expresión

Una instancia del `Expr` tipo representa una expresión de F #. Los tipos genéricos y no genéricos `Expr` están documentados en la documentación de la biblioteca de F #. Para obtener más información, vea [FSharp. Quotations (espacio de nombres](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) ) y [Quotations. expr (clase](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)).

## <a name="splicing-operators"></a>Operadores de inserción

La inserción permite combinar las expresiones de código delimitadas de literales con las expresiones que ha creado mediante programación o desde otro código de Comillas. Los `%` `%%` operadores y permiten agregar un objeto Expression de F # en una expresión de código delimitada. El operador se usa `%` para insertar un objeto de expresión con tipo en una comilla con tipo; el `%%` operador se usa para insertar un objeto de expresión sin tipo en una comilla sin tipo. Ambos operadores son operadores de prefijo unario. Por lo tanto `expr` , si es una expresión sin tipo de tipo `Expr` , el código siguiente es válido.

```fsharp
<@@ 1 + %%expr @@>
```

Y si `expr` es una comilla con tipo de tipo `Expr<int>` , el código siguiente es válido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

En el ejemplo siguiente se muestra el uso de expresiones de código delimitadas para colocar código de F # en un objeto de expresión y, a continuación, imprimir el código de F # que representa la expresión. `println`Se define una función que contiene una función recursiva `print` que muestra un objeto de expresión de F # (de tipo `Expr` ) en un formato descriptivo. Hay varios patrones activos en los módulos [FSharp. Quotations. Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) y [FSharp. Quotations. DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) que se pueden usar para analizar objetos de expresión. En este ejemplo no se incluyen todos los patrones posibles que pueden aparecer en una expresión de F #. Cualquier patrón no reconocido desencadena una coincidencia con el patrón de caracteres comodín ( `_` ) y se representa mediante el `ToString` método, que, en el `Expr` tipo, permite conocer el modelo activo que se va a agregar a la expresión de coincidencia.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

También puede usar los tres patrones activos en el [módulo ExprShape](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) para recorrer los árboles de expresión con menos patrones activos. Estos modelos activos pueden ser útiles si desea atravesar un árbol, pero no necesita toda la información en la mayoría de los nodos. Cuando se usan estos patrones, cualquier expresión de F # coincide con uno de los tres patrones siguientes: `ShapeVar` si la expresión es una variable, `ShapeLambda` si la expresión es una expresión lambda, o `ShapeCombination` si la expresión es otra cosa. Si atraviesa un árbol de expresión usando los modelos activos como en el ejemplo de código anterior, tendrá que usar muchos más patrones para controlar todos los posibles tipos de expresión de F # y el código será más complejo. Para obtener más información, consulte [ExprShape. ShapeVar&#124;ShapeLambda&#124;Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).

El siguiente ejemplo de código se puede utilizar como base para los recorridos más complejos. En este código, se crea un árbol de expresión para una expresión que implica una llamada de función, `add` . El modelo activo [SpecificCall (](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) se usa para detectar cualquier llamada a `add` en el árbol de expresión. Este modelo activo asigna los argumentos de la llamada al `exprList` valor. En este caso, solo hay dos, por lo que se extraen y se llama a la función de forma recursiva en los argumentos. Los resultados se insertan en una expresión de código que representa una llamada a `mul` mediante el operador de inserción ( `%%` ). La `println` función del ejemplo anterior se usa para mostrar los resultados.

El código de las otras ramas del modelo activo simplemente vuelve a generar el mismo árbol de expresión, por lo que el único cambio en la expresión resultante es el cambio de `add` a `mul` .

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Salida

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
