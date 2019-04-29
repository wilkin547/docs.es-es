---
title: Expresiones de código delimitadas
description: Obtenga información sobre F# expresiones de código delimitadas, una característica del lenguaje que le permite generar y trabajar con F# expresiones de código mediante programación.
ms.date: 05/16/2016
ms.openlocfilehash: aa8a17eb8f9837ca4023abc552a6aac063117e96
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766121"
---
# <a name="code-quotations"></a>Expresiones de código delimitadas

> [!NOTE]
> El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Este tema se describe *de código delimitadas*, una característica del lenguaje que le permite generar y trabajar con F# expresiones de código mediante programación. Esta característica le permite generar un árbol de sintaxis abstracta que representa F# código. Puede recorrer el árbol de sintaxis abstracta y procesan según las necesidades de su aplicación. Por ejemplo, puede usar el árbol para generar F# código o generar código en algún otro lenguaje.

## <a name="quoted-expressions"></a>Expresiones delimitadas

Un *expresión delimitada* es un F# expresión en el código que está delimitado de tal manera que no se compilan como parte del programa, pero en su lugar se compila en un objeto que representa un F# expresión. Puede marcar una expresión entre comillas en una de dos maneras: con la información de tipo o sin información de tipo. Si desea incluir información de tipo, use los símbolos `<@` y `@>` para delimitar la expresión entre comillas. Si no necesita información de tipo, use los símbolos `<@@` y `@@>`. El código siguiente muestra los presupuestos con y sin tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Recorrer un árbol de expresión grande es más rápido si no se incluye información de tipo. El tipo resultante de una expresión delimitada con los símbolos de tipo es `Expr<'T>`, donde el parámetro de tipo tiene el tipo de la expresión, según lo determinado por la F# algoritmo de deducción de tipo del compilador. Al usar expresiones de código delimitadas sin información de tipo, el tipo de la expresión entre comillas es el tipo no genérico [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Puede llamar a la [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) propiedad en el objeto `Expr` clase para obtener el sin tipo `Expr` objeto.

Hay una gran variedad de métodos estáticos que permiten generar F# expresión objetos mediante programación en el `Expr` clase sin utilizar expresiones delimitadas.

Tenga en cuenta que una expresión de código debe incluir una expresión completa. Para un `let` de enlace, por ejemplo, se necesita la definición del nombre enlazado y una expresión adicional que usa el enlace. En la sintaxis detallada, esto es una expresión que sigue el `in` palabra clave. En el nivel superior en un módulo, esto es simplemente la siguiente expresión en el módulo, pero en una expresión, se requiere de forma explícita.

Por lo tanto, la siguiente expresión no es válida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Pero las expresiones siguientes son válidas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Para usar expresiones de código delimitadas, debe agregar una declaración de importación (mediante el uso de la `open` palabra clave) que se abre el [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) espacio de nombres.

El F# PowerPack proporciona compatibilidad para evaluar y ejecutar F# objetos de expresión.

## <a name="expr-type"></a>Tipo expr

Una instancia de la `Expr` type representa un F# expresión. El tipo genérico y no genérica `Expr` tipos se documentan en el F# documentación de la biblioteca. Para obtener más información, consulte [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) y [Quotations.Expr clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).

## <a name="splicing-operators"></a>Operadores de conjuntos

Insertar permite combinar los presupuestos de código literal con expresiones que ha creado mediante programación o desde otra expresión de código. El `%` y `%%` operadores permiten agregar un F# objeto de expresión en una expresión de código. Usa el `%` operador para insertar un objeto de expresión con tipo en una expresión con tipo; use el `%%` operador para insertar un objeto de expresión sin tipo en una expresión de código delimitada sin tipo. Ambos operadores son operadores de prefijo unario. Por lo tanto si `expr` es una expresión de tipo sin tipo `Expr`, el código siguiente es válido.

```fsharp
<@@ 1 + %%expr @@>
```

Y si `expr` es una expresión de tipo con tipo `Expr<int>`, el código siguiente es válido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

El ejemplo siguiente muestra el uso de expresiones de código delimitadas poner F# en un objeto de expresión de código y, a continuación, imprimir el F# código que representa la expresión. Una función `println` está definido que contiene una función recursiva `print` que muestra un F# objeto de expresión (de tipo `Expr`) en un formato descriptivo. Hay varios modelos activos en el [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) y [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) módulos que pueden usarse para analizar objetos de expresión. En este ejemplo no incluye todos los posibles modelos que pueden aparecer en un F# expresión. Ninguno no se reconoce el patrón desencadena una coincidencia con el carácter comodín (`_`) y se representa mediante el uso de la `ToString` método, que, en el `Expr` escriba permite saber el modelo activo para agregar a la expresión de coincidencia.

### <a name="code"></a>Código

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Salida

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

También puede usar los tres modelos activos en el [ExprShape (módulo)](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) para recorrer los árboles de expresión con menos modelos activos. Estos modelos activos pueden ser útiles cuando desea recorrer un árbol, pero no es necesario toda la información en la mayoría de los nodos. Cuando usa estos patrones, cualquier F# expresión coincide con uno de los siguientes tres modelos: `ShapeVar` si la expresión es una variable, `ShapeLambda` si la expresión es una expresión lambda, o `ShapeCombination` si la expresión no es nada más. Si se recorre un árbol de expresión mediante el uso de los patrones activos como en el ejemplo de código anterior, tendrá que usar muchos más modelos para administrar todos los posibles F# tipos de expresión y su código será más compleja. Para obtener más información, consulte [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination (modelo activo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

El siguiente ejemplo de código se puede usar como punto de partida para recorridos más complejos. En este código, se crea un árbol de expresión para una expresión que implica una llamada de función, `add`. El [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) (modelo activo) se usa para detectar cualquier llamada a `add` en el árbol de expresión. Este modelo activo asigna los argumentos de la llamada a la `exprList` valor. En este caso, hay solo dos, por lo que se extraen estos y la función se llama de forma recursiva en los argumentos. Los resultados se insertan en una expresión de código que representa una llamada a `mul` mediante el operador de inserción (`%%`). El `println` función del ejemplo anterior se usa para mostrar los resultados.

El código de las demás ramas del modelo activo simplemente regenera el mismo árbol de expresión, por lo que el único cambio en la expresión resultante es el cambio de `add` a `mul`.

### <a name="code"></a>Código

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Salida

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)