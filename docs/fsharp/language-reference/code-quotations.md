---
title: Expresiones de código delimitadas
description: Obtenga información F# sobre las expresiones de código delimitadas, una característica del lenguaje que permite F# generar y trabajar con expresiones de código mediante programación.
ms.date: 05/16/2016
ms.openlocfilehash: c6ec0078c685a6452f49edd289b01491dd62e3db
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630417"
---
# <a name="code-quotations"></a>Expresiones de código delimitadas

> [!NOTE]
> El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

En este tema se describen las expresiones de *código*delimitadas, una característica del lenguaje que F# permite generar y trabajar con expresiones de código mediante programación. Esta característica permite generar un árbol de sintaxis abstracta que representa F# el código. A continuación, el árbol de sintaxis abstracta puede atravesarse y procesarse según las necesidades de la aplicación. Por ejemplo, puede usar el árbol para generar F# código o generar código en otro lenguaje.

## <a name="quoted-expressions"></a>Expresiones entre comillas

Una *expresión entre* comillas F# es una expresión del código que está delimitada de manera que no se compila como parte del programa, sino que se compila en un objeto que representa una F# expresión. Puede marcar una expresión entre comillas de una de estas dos maneras: con información de tipo o sin información de tipo. Si desea incluir información de tipo, use los símbolos `<@` y `@>` para delimitar la expresión entre comillas. Si no necesita información de tipo, use los símbolos `<@@` y. `@@>` En el código siguiente se muestran las comillas con tipo y sin tipo.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Atravesar un árbol de expresión grande es más rápido si no incluye información de tipo. El tipo resultante de una expresión entre comillas con los símbolos con `Expr<'T>`tipo es, donde el parámetro de tipo tiene el tipo de la expresión determinado F# por el algoritmo de inferencia de tipos del compilador. Cuando se usan expresiones de código delimitadas sin información de tipos, el tipo de la expresión entrecomillada es el tipo no genérico [expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Puede llamar a la propiedad [raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) en la `Expr` clase con tipo para obtener `Expr` el objeto sin tipo.

Hay una variedad de métodos estáticos que le permiten generar F# objetos de expresión mediante programación en la `Expr` clase sin usar expresiones entre comillas.

Tenga en cuenta que una expresión de código delimitada debe incluir una expresión completa. Para un `let` enlace, por ejemplo, necesitará la definición del nombre enlazado y una expresión adicional que use el enlace. En la sintaxis detallada, se trata de una expresión que sigue `in` a la palabra clave. En el nivel superior de un módulo, se trata simplemente de la siguiente expresión del módulo, pero en una expresión de código delimitada, se requiere explícitamente.

Por lo tanto, la siguiente expresión no es válida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Pero las siguientes expresiones son válidas.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Para evaluar F# las comillas, debe utilizar el [ F# evaluador](https://github.com/fsprojects/FSharp.Quotations.Evaluator)de Comillas. Proporciona compatibilidad para evaluar y ejecutar objetos de F# expresión.

## <a name="expr-type"></a>Tipo de expresión

Una instancia del `Expr` tipo representa una F# expresión. Los tipos genéricos y no genéricos `Expr` están documentados en la F# documentación de la biblioteca. Para obtener más información, vea [Microsoft. FSharp. Quotations (espacio de nombres](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) ) y Quotations [. expr (clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)).

## <a name="splicing-operators"></a>Operadores de inserción

La inserción permite combinar las expresiones de código delimitadas de literales con las expresiones que ha creado mediante programación o desde otro código de Comillas. Los `%` operadores `%%` y permiten agregar un F# objeto Expression en una expresión de código. El `%` operador se usa para insertar un objeto de expresión con tipo en una comilla con tipo; el `%%` operador se usa para insertar un objeto de expresión sin tipo en una comilla sin tipo. Ambos operadores son operadores de prefijo unario. Por lo `expr` tanto, si es una expresión sin tipo `Expr`de tipo, el código siguiente es válido.

```fsharp
<@@ 1 + %%expr @@>
```

Y si `expr` es una comilla con tipo de `Expr<int>`tipo, el código siguiente es válido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>DESCRIPCIÓN

En el ejemplo siguiente se muestra el uso de expresiones de código delimitadas para colocar F# el código en un objeto F# de expresión y, a continuación, imprimir el código que representa la expresión. Se define `println` una función que contiene una función `print` recursiva que muestra un F# objeto de expresión (de tipo `Expr`) en un formato descriptivo. Hay varios patrones activos en los módulos [Microsoft. FSharp. Quotations. Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) y [Microsoft. FSharp. Quotations. DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) que se pueden usar para analizar objetos de expresión. En este ejemplo no se incluyen todos los patrones posibles que pueden aparecer en F# una expresión. Cualquier patrón no reconocido desencadena una coincidencia con el patrón de caracteres comodín`_`() y se representa mediante el `ToString` método, que, en el `Expr` tipo, permite conocer el modelo activo que se va a agregar a la expresión de coincidencia.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Salida

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>DESCRIPCIÓN

También puede usar los tres patrones activos en el [módulo ExprShape](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) para recorrer los árboles de expresión con menos patrones activos. Estos modelos activos pueden ser útiles si desea atravesar un árbol, pero no necesita toda la información en la mayoría de los nodos. Cuando se usan estos patrones, cualquier F# expresión coincide con uno de los tres patrones siguientes `ShapeVar` : Si la expresión es una variable `ShapeLambda` , si la expresión es una expresión lambda, `ShapeCombination` o si la expresión es otra cosa. Si atraviesa un árbol de expresión usando los modelos activos como en el ejemplo de código anterior, tendrá que usar muchos más patrones para controlar todos los tipos de F# expresión posibles y el código será más complejo. Para obtener más información, consulte [ExprShape.&#124;ShapeVar&#124;ShapeLambda ShapeCombination (Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

El siguiente ejemplo de código se puede utilizar como base para los recorridos más complejos. En este código, se crea un árbol de expresión para una expresión que implica una llamada de `add`función,. El modelo activo [SpecificCall (](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) se usa para detectar cualquier llamada a `add` en el árbol de expresión. Este modelo activo asigna los argumentos de la llamada al `exprList` valor. En este caso, solo hay dos, por lo que se extraen y se llama a la función de forma recursiva en los argumentos. Los resultados se insertan en una expresión de código que representa una `mul` llamada a mediante el operador de inserción`%%`(). La `println` función del ejemplo anterior se usa para mostrar los resultados.

El código de las otras ramas del modelo activo simplemente vuelve a generar el mismo árbol de expresión, por lo que el único cambio en la expresión resultante `add` es `mul`el cambio de a.

### <a name="code"></a>Código

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Salida

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
