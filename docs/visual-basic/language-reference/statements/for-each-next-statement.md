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
ms.openlocfilehash: ebfd05a39c290e379bea2b925e7ea30c40d303fe
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046313"
---
# <a name="for-eachnext-statement-visual-basic"></a>Instrucción For Each...Next (Visual Basic)

Repite un grupo de instrucciones para cada elemento de una colección.

## <a name="syntax"></a>Sintaxis

```
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
|`element`|Obligatorio en la `For Each` instrucción. Opcional en la `Next` instrucción. Variable. Se utiliza para recorrer en iteración los elementos de la colección.|
|`datatype`|Opcional si [`Option Infer`](option-infer-statement.md) está activado (valor predeterminado) o `element` ya se ha declarado; obligatorio `Option Infer` si es OFF `element` y no se ha declarado ya. Tipo de datos de `element`.|
|`group`|Necesario. Una variable con un tipo que es un tipo de colección o un objeto. Hace referencia a la colección en la `statements` que se van a repetir.|
|`statements`|Opcional. Una o más instrucciones entre `For Each` y `Next` que se ejecutan en cada `group`elemento de.|
|`Continue For`|Opcional. Transfiere el control al inicio del `For Each` bucle.|
|`Exit For`|Opcional. Transfiere el `For Each` control fuera del bucle.|
|`Next`|Necesario. Finaliza la definición del `For Each` bucle.|

## <a name="simple-example"></a>Ejemplo sencillo

`For Each`Usar... `Next` bucle cuando se desea repetir un conjunto de instrucciones para cada elemento de una colección o matriz.

> [!TIP]
> Una [para... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) funciona bien cuando se puede asociar cada iteración de un bucle a una variable de control y determinar los valores iniciales y finales de la variable. Sin embargo, cuando se trabaja con una colección, el concepto de valores iniciales y finales no es significativo y no se sabe necesariamente cuántos elementos tiene la colección. En este tipo de caso, `For Each`... `Next` el bucle suele ser una opción mejor.

En el ejemplo siguiente, `For Each`...`Next` la instrucción recorre en iteración todos los elementos de una colección de lista.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Para obtener más ejemplos, vea [colecciones](../../../standard/collections/index.md) y [matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Bucles anidados

Puede anidar `For Each` bucles colocando un bucle dentro de otro.

En el siguiente ejemplo se muestra `For Each`la instrucción anidada...`Next` obra.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Al anidar bucles, cada bucle debe tener una variable `element` única.

También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Salir de y continuar para

La instrucción [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) hace que la ejecución salga `For`de...`Next` bucle y transfiere el control a la instrucción que sigue `Next` a la instrucción.

La `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, vea [instrucción continue](../../../visual-basic/language-reference/statements/continue-statement.md).

En el ejemplo siguiente se muestra cómo usar `Continue For` las `Exit For` instrucciones y.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

Puede incluir cualquier número de `Exit For` instrucciones en un `For Each` bucle. Cuando se usa dentro de `For Each` bucles anidados, `Exit For` hace que la ejecución salga del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

`Exit For`se suele usar después de una evaluación de alguna condición, por ejemplo, en `If`... `Then`... `Else` estructura. Puede que desee usar `Exit For` para las siguientes condiciones:

- Continuar la iteración no es necesario o imposible. Esto puede deberse a un valor erróneo o a una solicitud de finalización.

- Se detecta una excepción en `Try`... `Catch`... `Finally`. Puede usar `Exit For` al final `Finally` del bloque.

- Hay un bucle interminable, que es un bucle que podría ejecutar un número de veces grande o incluso infinito. Si detecta este tipo de condición, puede usar `Exit For` para escapar el bucle. Para obtener más información, vea.. [. Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iterators

Un *iterador* se usa para realizar una iteración personalizada en una colección. Un iterador puede ser una función o `Get` un descriptor de acceso. Usa una `Yield` instrucción para devolver cada elemento de la colección de uno en uno.

Se llama a un iterador mediante `For Each...Next` una instrucción. Cada iteración del bucle `For Each` llama al iterador. Cuando se `Yield` alcanza una instrucción en el iterador, se devuelve la `Yield` expresión de la instrucción y se conserva la ubicación actual en el código. La ejecución se reinicia desde esa ubicación la próxima vez que se llama al iterador.

En el ejemplo siguiente se utiliza una función de iterador. La función de iterador `Yield` tiene una instrucción que está dentro de un [... Siguiente](../../../visual-basic/language-reference/statements/for-next-statement.md) bucle. En el `ListEvenNumbers` método, cada iteración del `For Each` cuerpo de la instrucción crea una llamada a la función de iterador, que continúa `Yield` con la siguiente instrucción.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Para obtener más información, vea [iteradores](../../programming-guide/concepts/iterators.md), [instrucción yield](../../../visual-basic/language-reference/statements/yield-statement.md)e [iterator](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Implementación técnica

`For Each`Cuando...`Next` la instrucción se ejecuta, Visual Basic evalúa la colección solo una vez, antes de que se inicie el bucle. Si el bloque de instrucciones `element` cambia `group`o, estos cambios no afectan a la iteración del bucle.

Cuando todos los elementos de la colección se han asignado sucesivamente a `element`, el `For Each` bucle se detiene y el control pasa a la instrucción `Next` que sigue a la instrucción.

Si [Option Infer](option-infer-statement.md) es on (su configuración predeterminada), el compilador Visual Basic puede deducir el `element`tipo de datos de. Si está desactivado `element` y no se ha declarado fuera del bucle, debe declararlo `For Each` en la instrucción. Para declarar el tipo de datos `element` de explícitamente, `As` use una cláusula. A menos que el tipo de datos del elemento se `For Each`defina fuera de... `Next` , su ámbito es el cuerpo del bucle. Tenga en cuenta que no `element` puede declarar fuera y dentro del bucle.

Opcionalmente, puede especificar `element` en la `Next` instrucción. Esto mejora la legibilidad del programa, sobre todo si tiene `For Each` bucles anidados. Debe especificar la misma variable que la que aparece en la instrucción correspondiente `For Each` .

Puede que desee evitar cambiar el valor de dentro `element` de un bucle. Esto puede dificultar la lectura y depuración del código. Cambiar el valor de `group` no afecta a la colección o a sus elementos, que se determinaron cuando se escribió el bucle por primera vez.

Al anidar bucles, si se encuentra una `Next` instrucción de un nivel de anidamiento externo antes de la `Next` de un nivel interno, el compilador señala un error. Sin embargo, el compilador puede detectar este error superpuesto `element` solo si `Next` especifica en cada instrucción.

Si el código depende del recorrido de una colección en un orden determinado, `For Each`... `Next` el bucle no es la mejor opción, a menos que conozca las características del objeto de enumerador que expone la colección. Visual Basic, pero por el <xref:System.Collections.IEnumerator.MoveNext%2A> método del objeto de enumerador, no determina el orden de recorrido. Por lo tanto, es posible que no pueda predecir qué elemento de la colección es el primero que se devolverá en `element`, o cuál es el siguiente que se devolverá después de un elemento determinado. Podría obtener resultados más confiables mediante una estructura de bucle diferente, `For`como... `Next` o`Do`... `Loop`.

El tiempo de ejecución debe ser capaz de convertir los `group` elementos `element`de en. La instrucción`Option Strict`[] controla si se permiten las conversiones de ampliación y de restricción (`Option Strict` está desactivada, su valor predeterminado) o si solo se permiten conversiones de ampliación (`Option Strict` está activada). Para obtener más información, vea [conversiones de restricción](#narrowing-conversions).

El tipo de datos `group` de debe ser un tipo de referencia que haga referencia a una colección o una matriz que sea Enumerable. `group` Normalmente esto significa que hace referencia a un objeto que implementa la <xref:System.Collections.IEnumerable> interfaz del `System.Collections` espacio de nombres o la <xref:System.Collections.Generic.IEnumerable%601> interfaz del `System.Collections.Generic` espacio de nombres. `System.Collections.IEnumerable`define el <xref:System.Collections.IEnumerable.GetEnumerator%2A> método, que devuelve un objeto de enumerador para la colección. `System.Collections.IEnumerator` El objeto <xref:System.Collections.IEnumerator.Current%2A> <xref:System.Collections.IEnumerator.Reset%2A> de enumerador implementa la interfaz <xref:System.Collections.IEnumerator.MoveNext%2A> del espaciodenombresyexponelapropiedadylosmétodosy.`System.Collections` Visual Basic los usa para recorrer la colección.

### <a name="narrowing-conversions"></a>conversiones de restricción

Cuando `Option Strict` se establece en `On`, las conversiones de restricción suelen producir errores del compilador. Sin embargo `For Each` , en una instrucción, las conversiones de los elementos `group` `element` de en se evalúan y se ejecutan en tiempo de ejecución, y se suprimen los errores del compilador causados por las conversiones de restricción.

En el ejemplo siguiente, la asignación de `m` como el valor inicial de `n` no se compila `Option Strict` cuando es `Integer` on porque la conversión de `Long` un en es una conversión de restricción. En la `For Each` instrucción, sin embargo, no se muestra ningún error del compilador, `number` aunque la asignación a requiere `Long` la `Integer`misma conversión de a. En la `For Each` instrucción que contiene un número grande, se produce un error en tiempo de <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> ejecución cuando se aplica al número grande.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>Llamadas IEnumerator

Al ejecutar un `For Each`... se inicia el bucle, Visual Basic comprueba `group` que hace referencia a un objeto de colección válido. `Next` Si no es así, se produce una excepción. De lo contrario, llama <xref:System.Collections.IEnumerator.MoveNext%2A> al método y <xref:System.Collections.IEnumerator.Current%2A> a la propiedad del objeto de enumerador para devolver el primer elemento. Si `MoveNext` indica que no hay ningún elemento siguiente, es decir, si la colección está vacía, el `For Each` bucle se detiene y el control pasa a la instrucción `Next` que sigue a la instrucción. De lo contrario, `element` Visual Basic establece en el primer elemento y ejecuta el bloque de instrucciones.

Cada vez que Visual Basic encuentra la `Next` instrucción, devuelve a la `For Each` instrucción. Una vez más `MoveNext` , `Current` llama a y para devolver el siguiente elemento y, de nuevo, ejecuta el bloque o detiene el bucle en función del resultado. Este proceso continúa hasta `MoveNext` que indica que no hay ningún elemento siguiente o `Exit For` se encuentra una instrucción.

**Modificar la colección.** El objeto de enumerador <xref:System.Collections.IEnumerable.GetEnumerator%2A> devuelto por normalmente no permite cambiar la colección agregando, eliminando, reemplazando o reordenando los elementos. Si cambia la colección después de haber iniciado una `For Each`... , el objeto de enumerador deja de ser válido y el siguiente intento de obtener acceso a <xref:System.InvalidOperationException> un elemento produce una excepción. `Next`

Sin embargo, este bloqueo de modificación no viene determinado por Visual Basic, sino por la implementación de <xref:System.Collections.IEnumerable> la interfaz. Es posible implementar `IEnumerable` de forma que permita la modificación durante la iteración. Si está pensando en realizar esta modificación dinámica, asegúrese de que comprende las características de la `IEnumerable` implementación en la colección que está usando.

**Modificar elementos de la colección.** La <xref:System.Collections.IEnumerator.Current%2A> propiedad del objeto enumerador es de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md)y devuelve una copia local de cada elemento de la colección. Esto significa que no se pueden modificar los propios elementos en `For Each`una... `Next` bucle. Cualquier modificación que realice solo afectará a la copia `Current` local de y no se reflejará en la colección subyacente. Sin embargo, si un elemento es un tipo de referencia, puede modificar los miembros de la instancia a la que señala. En el ejemplo siguiente se modifica `BackColor` el miembro de `thisControl` cada elemento. Sin embargo, no puede modificarse `thisControl` a sí mismo.

```vb
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

En el ejemplo anterior se puede `BackColor` modificar el miembro `thisControl` de cada elemento, aunque no `thisControl` se puede modificar.

**Atravesar matrices.** Dado que <xref:System.Array> la clase implementa la <xref:System.Collections.IEnumerable> interfaz, todas las matrices exponen el <xref:System.Array.GetEnumerator%2A> método. Esto significa que puede recorrer en iteración una matriz con `For Each`... `Next` bucle. Sin embargo, solo puede leer los elementos de la matriz. No se pueden cambiar.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se enumeran todas las carpetas de C:\ directorio mediante la <xref:System.IO.DirectoryInfo> clase.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra un procedimiento para ordenar una colección. El ejemplo ordena las instancias de `Car` una clase que se almacenan <xref:System.Collections.Generic.List%601>en un. La clase `Car` implementa la interfaz <xref:System.IComparable%601>, que requiere implementar el método <xref:System.IComparable%601.CompareTo%2A>.

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
