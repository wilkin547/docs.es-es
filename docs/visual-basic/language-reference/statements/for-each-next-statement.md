---
title: Instrucción For Each...Next (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
ms.openlocfilehash: f56e5defa2328011d222bfca05334b610e805055
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332788"
---
# <a name="for-eachnext-statement-visual-basic"></a>Instrucción For Each...Next (Visual Basic)

Repite un grupo de instrucciones para cada elemento de una colección.

## <a name="syntax"></a>Sintaxis

```vb
For Each element [ As datatype ] In group
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ element ]
```

## <a name="parts"></a>Elementos

|Término|Definición|
|---|---|
|`element`|Obligatorio en la instrucción `For Each`. Opcional en la instrucción `Next`. Variable. Se utiliza para recorrer en iteración los elementos de la colección.|
|`datatype`|Opcional si [`Option Infer`](option-infer-statement.md) está activado (valor predeterminado) o `element` ya se ha declarado; obligatorio si `Option Infer` está desactivado y `element` no se ha declarado. Tipo de datos de `element`.|
|`group`|Obligatorio. Una variable con un tipo que es un tipo de colección o un objeto. Hace referencia a la colección en la que se van a repetir los `statements`.|
|`statements`|Opcional. Una o varias instrucciones entre `For Each` y `Next` que se ejecutan en cada elemento de `group`.|
|`Continue For`|Opcional. Transfiere el control al principio del bucle `For Each`.|
|`Exit For`|Opcional. Transfiere el control fuera del bucle `For Each`.|
|`Next`|Obligatorio. Finaliza la definición del bucle `For Each`.|

## <a name="simple-example"></a>Ejemplo sencillo

Use un bucle `For Each`...`Next` cuando desee repetir un conjunto de instrucciones para cada elemento de una colección o matriz.

> [!TIP]
> Una [para... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) funciona bien cuando se puede asociar cada iteración de un bucle a una variable de control y determinar los valores iniciales y finales de la variable. Sin embargo, cuando se trabaja con una colección, el concepto de valores iniciales y finales no es significativo y no se sabe necesariamente cuántos elementos tiene la colección. En este tipo de caso, un bucle `For Each`...`Next` suele ser una opción mejor.

En el ejemplo siguiente, el `For Each`...`Next` la instrucción recorre en iteración todos los elementos de una colección de lista.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Para obtener más ejemplos, vea [colecciones](../../../standard/collections/index.md) y [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Bucles anidados

Puede anidar `For Each` bucles colocando un bucle dentro de otro.

En el ejemplo siguiente se muestra `For Each`anidadas...`Next` Obra.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Al anidar bucles, cada bucle debe tener una variable de `element` única.

También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Salir de y continuar para

La instrucción [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) hace que la ejecución salga del `For`...`Next` bucle y transfiere el control a la instrucción que sigue a la instrucción `Next`.

La instrucción `Continue For` transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, vea [instrucción continue](../../../visual-basic/language-reference/statements/continue-statement.md).

En el ejemplo siguiente se muestra cómo usar las instrucciones `Continue For` y `Exit For`.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

Puede incluir cualquier número de instrucciones `Exit For` en un bucle de `For Each`. Cuando se usa dentro de bucles `For Each` anidados, `Exit For` hace que la ejecución salga del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

`Exit For` se suele usar después de una evaluación de alguna condición, por ejemplo, en una estructura `If`...`Then`...`Else`. Es posible que desee usar `Exit For` para las siguientes condiciones:

- Continuar la iteración no es necesario o imposible. Esto puede deberse a un valor erróneo o a una solicitud de finalización.

- Se ha detectado una excepción en una `Try`...`Catch`...`Finally`. Puede usar `Exit For` al final del bloque de `Finally`.

- Hay un bucle interminable, que es un bucle que podría ejecutar un número de veces grande o incluso infinito. Si detecta este tipo de condición, puede usar `Exit For` para escapar el bucle. Para obtener más información, vea.. [. Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iteradores

Un *iterador* se usa para realizar una iteración personalizada en una colección. Un iterador puede ser una función o un descriptor de acceso `Get`. Usa una instrucción `Yield` para devolver cada elemento de la colección de uno en uno.

Se llama a un iterador mediante una instrucción `For Each...Next`. Cada iteración del bucle `For Each` llama al iterador. Cuando se alcanza una instrucción `Yield` en el iterador, se devuelve la expresión de la instrucción `Yield` y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.

En el ejemplo siguiente se utiliza una función de iterador. La función de iterador tiene una instrucción `Yield` que se encuentra dentro de un [... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. En el método `ListEvenNumbers`, cada iteración del cuerpo de la instrucción `For Each` crea una llamada a la función de iterador, que continúa con la siguiente instrucción `Yield`.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Para obtener más información, vea [iteradores](../../programming-guide/concepts/iterators.md), [instrucción yield](../../../visual-basic/language-reference/statements/yield-statement.md)e [iterator](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Implementación técnica

Cuando una `For Each`...`Next` la instrucción se ejecuta, Visual Basic evalúa la colección solo una vez, antes de que se inicie el bucle. Si el bloque de instrucciones cambia `element` o `group`, estos cambios no afectan a la iteración del bucle.

Cuando todos los elementos de la colección se han asignado sucesivamente a `element`, el bucle `For Each` detiene y el control pasa a la instrucción que sigue a la instrucción `Next`.

Si [Option Infer](option-infer-statement.md) es on (su configuración predeterminada), el compilador Visual Basic puede deducir el tipo de datos de `element`. Si está desactivado y `element` no se ha declarado fuera del bucle, debe declararlo en la instrucción `For Each`. Para declarar el tipo de datos de `element` explícitamente, utilice una cláusula `As`. A menos que el tipo de datos del elemento esté definido fuera de la construcción `For Each`...`Next`, su ámbito es el cuerpo del bucle. Tenga en cuenta que no puede declarar `element` fuera y dentro del bucle.

Opcionalmente, puede especificar `element` en la instrucción `Next`. Esto mejora la legibilidad del programa, sobre todo si tiene bucles `For Each` anidados. Debe especificar la misma variable que la que aparece en la instrucción `For Each` correspondiente.

Puede que desee evitar cambiar el valor de `element` dentro de un bucle. Esto puede dificultar la lectura y depuración del código. Cambiar el valor de `group` no afecta a la colección ni a sus elementos, que se determinaron cuando el bucle se introdujo por primera vez.

Al anidar bucles, si se encuentra una instrucción `Next` de un nivel de anidamiento externo antes del `Next` de un nivel interno, el compilador indica un error. Sin embargo, el compilador puede detectar este error superpuesto solo si se especifica `element` en cada instrucción `Next`.

Si el código depende de atravesar una colección en un orden determinado, un bucle `For Each`...`Next` no es la mejor opción, a menos que conozca las características del objeto de enumerador que expone la colección. Visual Basic, pero con el método <xref:System.Collections.IEnumerator.MoveNext%2A> del objeto de enumerador, no determina el orden de recorrido. Por lo tanto, es posible que no pueda predecir qué elemento de la colección es el primero que se devolverá en `element`, o que es el siguiente que se devolverá después de un elemento determinado. Podría obtener resultados más confiables mediante una estructura de bucle diferente, como `For`...`Next` o `Do`...`Loop`.

El tiempo de ejecución debe ser capaz de convertir los elementos de `group` en `element`. La instrucción [`Option Strict`] controla si se permiten las conversiones de ampliación y de restricción (`Option Strict` está desactivada, su valor predeterminado) o si solo se permiten conversiones de ampliación (`Option Strict` está activada). Para obtener más información, vea [conversiones de restricción](#narrowing-conversions).

El tipo de datos de `group` debe ser un tipo de referencia que haga referencia a una colección o una matriz que sea Enumerable. Normalmente, esto significa que `group` hace referencia a un objeto que implementa la interfaz de <xref:System.Collections.IEnumerable> del espacio de nombres `System.Collections` o la interfaz <xref:System.Collections.Generic.IEnumerable%601> del espacio de nombres `System.Collections.Generic`. `System.Collections.IEnumerable` define el método de <xref:System.Collections.IEnumerable.GetEnumerator%2A>, que devuelve un objeto de enumerador para la colección. El objeto de enumerador implementa la interfaz `System.Collections.IEnumerator` del espacio de nombres `System.Collections` y expone la propiedad <xref:System.Collections.IEnumerator.Current%2A> y los métodos <xref:System.Collections.IEnumerator.Reset%2A> y <xref:System.Collections.IEnumerator.MoveNext%2A>. Visual Basic los usa para recorrer la colección.

### <a name="narrowing-conversions"></a>Conversiones de restricción

Cuando `Option Strict` se establece en `On`, las conversiones de restricción suelen producir errores del compilador. Sin embargo, en una instrucción `For Each`, las conversiones de los elementos de `group` a `element` se evalúan y se realizan en tiempo de ejecución, y se suprimen los errores del compilador causados por las conversiones de restricción.

En el ejemplo siguiente, la asignación de `m` como el valor inicial de `n` no se compila cuando `Option Strict` está activado porque la conversión de un `Long` en una `Integer` es una conversión de restricción. En la instrucción `For Each`, sin embargo, no se genera ningún error del compilador, aunque la asignación a `number` requiere la misma conversión de `Long` a `Integer`. En la instrucción `For Each` que contiene un número grande, se produce un error en tiempo de ejecución cuando se aplica <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> al número grande.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Llamadas IEnumerator

Cuando se inicia la ejecución de un bucle `For Each`...`Next`, Visual Basic comprueba que `group` hace referencia a un objeto de colección válido. Si no es así, se produce una excepción. De lo contrario, llama al método <xref:System.Collections.IEnumerator.MoveNext%2A> y a la propiedad <xref:System.Collections.IEnumerator.Current%2A> del objeto enumerador para devolver el primer elemento. Si `MoveNext` indica que no hay ningún elemento siguiente, es decir, si la colección está vacía, el bucle `For Each` detiene y el control pasa a la instrucción que sigue a la instrucción `Next`. De lo contrario, Visual Basic establece `element` en el primer elemento y ejecuta el bloque de instrucciones.

Cada vez que Visual Basic encuentra la instrucción `Next`, vuelve a la instrucción `For Each`. Una vez más, llama a `MoveNext` y `Current` para devolver el elemento siguiente y, de nuevo, ejecuta el bloque o detiene el bucle en función del resultado. Este proceso continúa hasta que `MoveNext` indica que no hay ningún elemento siguiente o se encuentra una instrucción de `Exit For`.

**Modificar la colección.** El objeto de enumerador devuelto por <xref:System.Collections.IEnumerable.GetEnumerator%2A> normalmente no permite cambiar la colección agregando, eliminando, reemplazando o reordenando los elementos. Si cambia la colección después de haber iniciado un bucle `For Each`...`Next`, el objeto de enumerador deja de ser válido y el siguiente intento de obtener acceso a un elemento produce una excepción <xref:System.InvalidOperationException>.

Sin embargo, este bloqueo de modificación no viene determinado por Visual Basic, sino por la implementación de la interfaz <xref:System.Collections.IEnumerable>. Es posible implementar `IEnumerable` de forma que permita la modificación durante la iteración. Si está pensando en realizar esta modificación dinámica, asegúrese de que comprende las características de la implementación de `IEnumerable` en la colección que está utilizando.

**Modificar elementos de la colección.** La propiedad <xref:System.Collections.IEnumerator.Current%2A> del objeto enumerador es de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md)y devuelve una copia local de cada elemento de la colección. Esto significa que no se pueden modificar los propios elementos en un bucle `For Each`...`Next`. Cualquier modificación que realice solo afectará a la copia local de `Current` y no se reflejará de nuevo en la colección subyacente. Sin embargo, si un elemento es un tipo de referencia, puede modificar los miembros de la instancia a la que señala. En el ejemplo siguiente se modifica el miembro de `BackColor` de cada elemento `thisControl`. Sin embargo, no puede modificar `thisControl` mismo.

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

En el ejemplo anterior se puede modificar el miembro de `BackColor` de cada elemento `thisControl`, aunque no se puede modificar `thisControl` mismo.

**Atravesar matrices.** Dado que la clase <xref:System.Array> implementa la interfaz <xref:System.Collections.IEnumerable>, todas las matrices exponen el método <xref:System.Array.GetEnumerator%2A>. Esto significa que puede recorrer en iteración una matriz con un bucle `For Each`...`Next`. Sin embargo, solo puede leer los elementos de la matriz. No se pueden cambiar.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se enumeran todas las carpetas de C:\ directorio mediante la clase <xref:System.IO.DirectoryInfo>.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un procedimiento para ordenar una colección. El ejemplo ordena las instancias de una clase `Car` que se almacenan en un <xref:System.Collections.Generic.List%601>. La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.

Cada llamada al método <xref:System.IComparable%601.CompareTo%2A> realiza una comparación única que se usa para la ordenación. El código escrito por el usuario en el método `CompareTo` devuelve un valor para cada comparación del objeto actual con otro objeto. El valor devuelto es menor que cero si el objeto actual es menor que el otro objeto, mayor que cero si el objeto actual es mayor que el otro objeto y cero si son iguales. Esto permite definir en el código los criterios de mayor que, menor que e igual.

En el método `ListCars`, la instrucción `cars.Sort()` ordena la lista. Esta llamada al método <xref:System.Collections.Generic.List%601.Sort%2A> de <xref:System.Collections.Generic.List%601> hace que se llame automáticamente al método `CompareTo` para los objetos `Car` de `List`.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>Vea también

- [Colecciones](../../../standard/collections/index.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Inicializadores de objeto: Tipos con nombre y anónimos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Inicializadores de colección](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)
