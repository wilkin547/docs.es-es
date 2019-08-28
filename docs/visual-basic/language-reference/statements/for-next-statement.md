---
title: Instrucción For...Next (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: cafd59482036a598814dcd4815fa67a791580045
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046298"
---
# <a name="fornext-statement-visual-basic"></a>Instrucción For...Next (Visual Basic)

Repite un grupo de instrucciones un número especificado de veces.

## <a name="syntax"></a>Sintaxis

```
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>Elementos

|Parte|DESCRIPCIÓN|
|----------|-----------------|
|`counter`|Obligatorio en la `For` instrucción. Variable numérica. Variable de control del bucle. Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.|
|`datatype`|Opcional. Tipo de datos `counter`de. Para obtener más información, vea el [argumento Counter](#BKMK_Counter) más adelante en este tema.|
|`start`|Necesario. Expresión numérica. Valor inicial de `counter`.|
|`end`|Necesario. Expresión numérica. Valor final de `counter`.|
|`step`|Opcional. Expresión numérica. Cantidad que `counter` se incrementa cada vez a través del bucle.|
|`statements`|Opcional. Una o más instrucciones entre `For` y `Next` que ejecutan el número especificado de veces.|
|`Continue For`|Opcional. Transfiere el control a la siguiente iteración del bucle.|
|`Exit For`|Opcional. Transfiere el `For` control fuera del bucle.|
|`Next`|Necesario. Finaliza la definición del `For` bucle.|

> [!NOTE]
> La `To` palabra clave se usa en esta instrucción para especificar el intervalo del contador. También puede usar esta palabra clave en la [ Instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md) y en declaraciones de matriz. Para obtener más información sobre las declaraciones de matriz, vea [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md).

## <a name="simple-examples"></a>Ejemplos sencillos

Use `For`... `Next` estructura en la que se desea repetir un conjunto de instrucciones un número de veces.

En el ejemplo siguiente, la `index` variable empieza con un valor de 1 y se incrementa con cada iteración del bucle, finalizando después del valor de `index` hasta 5.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

En el ejemplo siguiente, la `number` variable empieza en 2 y se reduce por 0,25 en cada iteración del bucle, finalizando después del valor `number` de hasta 0. El `Step` argumento de `-.25` reduce el valor en 0,25 en cada iteración del bucle.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> [While... End while instrucción](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [do... La instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md) funciona bien cuando no se sabe de antemano cuántas veces ejecutar las instrucciones en el bucle. Sin embargo, cuando espera ejecutar el bucle un número determinado de veces, un `For`... `Next` el bucle es una opción mejor. El número de iteraciones se determina cuando se escribe el bucle por primera vez.

## <a name="nesting-loops"></a>Anidar bucles

Puede anidar `For` bucles colocando un bucle dentro de otro. En el siguiente ejemplo se muestra `For`la instrucción anidada... `Next` estructuras que tienen valores de pasos diferentes. El bucle exterior crea una cadena para cada iteración del bucle. El bucle interno reduce una variable de contador de bucle para cada iteración del bucle.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Al anidar bucles, cada bucle debe tener una variable `counter` única.

También puede anidar distintos tipos de estructuras de control. Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).

## <a name="exit-for-and-continue-for"></a>Salir de y continuar para

La `Exit For` instrucción sale inmediatamente de `For`...`Next` bucle y transfiere el control a la instrucción que sigue `Next` a la instrucción.

La `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, vea [instrucción continue](../../../visual-basic/language-reference/statements/continue-statement.md).

En el ejemplo siguiente se muestra el uso de `Continue For` las `Exit For` instrucciones y.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

Puede incluir cualquier número de `Exit For` instrucciones `For`en...`Next` realizar. Cuando se usa dentro de `For`la instrucción anidada...`Next` bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel superior de anidamiento.

`Exit For`se suele usar después de evaluar alguna condición (por ejemplo, en `If`... `Then`... `Else` estructura). Puede que desee usar `Exit For` para las siguientes condiciones:

- Continuar la iteración no es necesario o imposible. Un valor erróneo o una solicitud de finalización podría crear esta condición.

- `Try`... `Catch`... `Finally` la instrucción detecta una excepción. Puede usar `Exit For` al final `Finally` del bloque.

- Tiene un bucle sin fin, que es un bucle que podría ejecutar un número de veces grande o incluso infinito. Si detecta este tipo de condición, puede usar `Exit For` para escapar el bucle. Para obtener más información, vea.. [. Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>Implementación técnica

`For`Cuando... el bucle se inicia, Visual Basic `start`evalúa `end`, y `step`. `Next` Visual Basic evalúa estos valores solo en este momento y, a continuación, `start` se asigna a. `counter` Antes de que se ejecute el bloque de instrucciones `counter` , `end`Visual Basic compara con. Si `counter` ya es mayor que el `end` valor (o menor si `step` es negativo), el `For` bucle finaliza y el control pasa a la instrucción que sigue `Next` a la instrucción. De lo contrario, se ejecuta el bloque de instrucciones.

Cada vez `Next` que Visual Basic encuentra la instrucción, se `counter` incrementa `step` en y vuelve a la `For` instrucción. Una vez más, `counter` se `end`compara con y, de nuevo, ejecuta el bloque o sale del bucle, en función del resultado. Este proceso continúa hasta `counter` que `end` se encuentran `Exit For` las pasadas o una instrucción.

El bucle no se detiene `counter` hasta que `end`se ha pasado. Si `counter` es igual a `end`, el bucle continúa. La comparación que determina si se debe ejecutar el bloque `counter` es `step` `counter` `end`  <=  si es positivo y `step`  >=  `end` si es negativo.

Si cambia el valor de `counter` mientras se encuentra dentro de un bucle, el código podría ser más difícil de leer y depurar. Cambiar el valor de `start`, `end`o `step` no afecta a los valores de iteración que se determinaron cuando se escribió el bucle por primera vez.

Si anida bucles, el compilador indicará un error si encuentra la `Next` instrucción de un nivel de anidamiento externo antes de la `Next` instrucción de un nivel interno. Sin embargo, el compilador puede detectar este error superpuesto `counter` solo si `Next` especifica en cada instrucción.

### <a name="step-argument"></a>Argumento Step

El valor de `step` puede ser positivo o negativo. Este parámetro determina el procesamiento de bucles según la tabla siguiente:

|**Valor del paso**|**El bucle se ejecuta si**|
|--------------------|--------------------------|
|Positivo o cero|`counter` <= `end`|
|Negativo|`counter` >= `end`|

El valor predeterminado de `step` es 1.

### <a name="BKMK_Counter"></a>Argumento Counter

En la tabla siguiente se `counter` indica si define una nueva variable local cuyo ámbito es el bucle `For…Next` completo. Esta determinación depende de si `datatype` está presente y si `counter` ya está definido.

|¿ `datatype` Está presente?|¿ `counter` Ya está definido?|Resultado (si `counter` define una nueva variable local cuyo ámbito es el bucle completo) `For...Next`|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Sin|Sí|No, porque `counter` ya está definido. Si el ámbito de `counter` no es local para el procedimiento, se produce una advertencia en tiempo de compilación.|
|Sin|Sin|Sí. El tipo de datos se deduce de `start`las `end`expresiones, `step` y. Para obtener información sobre la inferencia de tipos, vea [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) e inferencia de [tipo local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|
|Sí|Sí|Sí, pero solo si la variable `counter` existente se define fuera del procedimiento. Esa variable sigue siendo independiente. Si el ámbito de la variable `counter` existente es local para el procedimiento, se produce un error en tiempo de compilación.|
|Sí|Sin|Sí.|

El tipo de datos `counter` de determina el tipo de iteración, que debe ser uno de los siguientes tipos:

- `Byte`, ,,`UShort` ,`Single`,,,,, O .`Double` `ULong` `Integer` `Short` `UInteger` `SByte` `Long` `Decimal`

- Una enumeración que se declara mediante una [instrucción enum](../../../visual-basic/language-reference/statements/enum-statement.md).

- Una clase `Object`.

- Tipo `T` que tiene los operadores siguientes, donde `B` es un tipo que se puede utilizar en una `Boolean` expresión.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Opcionalmente, puede especificar la `counter` variable en la `Next` instrucción. Esta sintaxis mejora la legibilidad del programa, sobre todo si tiene `For` bucles anidados. Debe especificar la variable que aparece en la instrucción correspondiente `For` .

Las `start`expresiones `end`, `counter`y `step` se pueden evaluar como cualquier tipo de datos que se amplíe al tipo de. Si usa un tipo definido por el usuario para `counter`, es posible que tenga que definir `CType` el operador de conversión para convertir los `start`tipos `end`de, `step` o al tipo de `counter`.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se quitan todos los elementos de una lista genérica. En lugar de [para cada... Instrucción siguiente](../../../visual-basic/language-reference/statements/for-each-next-statement.md), en el ejemplo se `For`muestra un... `Next` instrucción que recorre en iteración en orden descendente. En el ejemplo se utiliza esta técnica `removeAt` porque el método hace que los elementos situados después del elemento quitado tengan un valor de índice inferior.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se recorre en iteración una enumeración declarada mediante una [instrucción enum](../../../visual-basic/language-reference/statements/enum-statement.md).

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente, los parámetros de instrucción usan una clase que tiene sobrecargas de operador `+`para `-`los `>=`operadores, `<=` , y.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Vea también

- <xref:System.Collections.Generic.List%601>
- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Colecciones](../../programming-guide/concepts/collections.md)
