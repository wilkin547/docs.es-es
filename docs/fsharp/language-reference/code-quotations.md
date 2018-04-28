---
title: Expresiones de código delimitadas (F#)
description: 'Obtenga información sobre F # expresiones de código delimitadas, una característica del lenguaje que permite generar y trabajar con expresiones de código de F # mediante programación.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cfa2e4b9a4ad1776315dfa8ea82fb8fc3f13a552
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="code-quotations"></a>Expresiones de código delimitadas

> [!NOTE]
El vínculo de la referencia de API le llevará a MSDN.  La referencia de API de docs.microsoft.com no está completa.

Este tema se describe *expresiones de código delimitadas*, una característica del lenguaje que permite generar y trabajar con expresiones de código de F # mediante programación. Esta característica le permite generar un árbol de sintaxis abstracta que representa el código de F #. Puede recorrer el árbol de sintaxis abstracta y procesan según las necesidades de su aplicación. Por ejemplo, puede usar el árbol para generar código de F # o generar código en algún otro lenguaje.


## <a name="quoted-expressions"></a>Expresiones delimitadas
A *expresión delimitada* es una expresión de F # en el código que está delimitada de tal manera que no se compila como parte del programa, pero en su lugar se compila en un objeto que representa una expresión de F #. Puede marcar una expresión entre comillas en una de dos maneras: con información de tipo o sin información de tipo. Si van a incluir información de tipo, use los símbolos `<@` y `@>` para delimitar la expresión entre comillas. Si no necesita información de tipo, se utilizan los símbolos `<@@` y `@@>`. El código siguiente muestra expresiones de código delimitadas con y sin tipo.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Recorrer un árbol de expresión grande es más rápido si no incluye la información de tipo. El tipo resultante de una expresión delimitada con los símbolos de tipo es `Expr<'T>`, donde el parámetro de tipo tiene el tipo de la expresión, según lo determinado por el algoritmo de inferencia de tipo de F # del compilador. Cuando utilice expresiones de código delimitadas sin información de tipo, el tipo de la expresión entre comillas es el tipo no genérico [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65). Puede llamar a la [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) propiedad de tipo `Expr` clase para obtener el sin tipo `Expr` objeto.

Hay una variedad de métodos estáticos que le permiten generar expresión objetos de F # mediante programación en el `Expr` clase sin usar entre comillas expresiones.

Tenga en cuenta que una expresión de código debe incluir una expresión completa. Para una `let` de enlace, por ejemplo, se necesita la definición del nombre enlazado y una expresión adicional que utilice el enlace. En la sintaxis detallada, ésta es una expresión que sigue a la `in` (palabra clave). En el nivel superior de un módulo, se trata únicamente la expresión siguiente en el módulo, pero en un presupuesto, se requiere de forma explícita.

Por lo tanto, la siguiente expresión no es válida.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Pero las expresiones siguientes son válidas.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Para usar expresiones de código delimitadas, primero debe agregar una declaración de importación (mediante el uso de la `open` palabra clave) que se abre la [Microsoft.FSharp.Quotations](https://msdn.microsoft.com/library/e9ce8a3a-e00c-4190-bad5-cce52ee089b2) espacio de nombres.

F # PowerPack proporciona compatibilidad para la evaluación y la ejecución de los objetos de expresiones de F #.


## <a name="expr-type"></a>Tipo de expresión
Una instancia de la `Expr` tipo representa una expresión de F #. La interfaz genérica y no genérica `Expr` tipos se documentan en la documentación de biblioteca de F #. Para obtener más información, consulte [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) y [Quotations.Expr clase](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).


## <a name="splicing-operators"></a>Ensamblar operadores
Insertar permite agrupar expresiones de código literal delimitadas con expresiones que ha creado mediante programación o desde otra expresión de código. El `%` y `%%` operadores permiten agregar un objeto de expresión de F # en una expresión de código. Usa el `%` operador que se va a insertar un objeto de expresión con tipo en una expresión de código delimitada con tipo; debe utilizar el `%%` operador que se va a insertar un objeto de expresión sin tipo en una expresión de código delimitada sin tipo. Ambos operadores son operadores de prefijo unario. Por lo tanto si `expr` es una expresión sin tipo del tipo `Expr`, el código siguiente es válido.

```fsharp
<@@ 1 + %%expr @@>
```

Y si `expr` es una expresión de código delimitada con tipo de tipo `Expr<int>`, el código siguiente es válido.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción
En el ejemplo siguiente se muestra el uso de expresiones de código delimitadas para colocar el código de F # en un objeto de expresión y, a continuación, imprimir el código de F # que representa la expresión. Una función `println` se define que contiene una función recursiva `print` que muestra un objeto de expresión de F # (de tipo `Expr`) en un formato descriptivo. Hay varios modelos activos en el [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) y [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) módulos que pueden usarse para analizar objetos de expresión. En este ejemplo no incluye todos los posibles modelos que pueden aparecer en una expresión de F #. Ninguno no se reconoce el patrón desencadena una coincidencia con el patrón de carácter comodín (`_`) y se representa mediante el uso de la `ToString` método, que, en el `Expr` escribe, permite saber el patrón activo para agregar a la expresión de coincidencia.


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
También puede utilizar los tres modelos activos en el [ExprShape (módulo)](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) para recorrer los árboles de expresión con menos modelos activos. Estos modelos activos pueden ser útiles cuando desea recorrer un árbol pero no es necesario toda la información en la mayoría de los nodos. Al usar estos patrones, cualquier expresión de F # coincide con uno de los siguientes tres modelos: `ShapeVar` si la expresión es una variable, `ShapeLambda` si la expresión es una expresión lambda, o `ShapeCombination` si la expresión es algo más. Si recorrer un árbol de expresión mediante el uso de los patrones activos como en el ejemplo de código anterior, tendrá que utilizar muchos más modelos para administrar todos los tipos de expresión de F # posibles, y el código será más complejo. Para obtener más información, consulte [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination (modelo activo)](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).

El ejemplo de código siguiente puede utilizarse como base para recorridos más complejos. En este código, se crea un árbol de expresión para una expresión que implica una llamada de función, `add`. El [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) (modelo activo) se utiliza para detectar cualquier llamada a `add` en el árbol de expresión. Este modelo activo asigna los argumentos de la llamada a la `exprList` valor. En este caso, hay solo dos, por lo que se extraen estos y la función se llama de forma recursiva en los argumentos. Los resultados se insertan en una expresión de código que representa una llamada a `mul` mediante el operador de intervalo (`%%`). El `println` función del ejemplo anterior se utiliza para mostrar los resultados.

El código en las otras bifurcaciones del modelo activo simplemente regenera el mismo árbol de expresión, por lo que el único cambio en la expresión resultante es el cambio de `add` a `mul`.


### <a name="code"></a>Código
[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]
    
### <a name="output"></a>Salida

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Vea también
[Referencia del lenguaje F#](index.md)

