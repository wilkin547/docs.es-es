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
ms.openlocfilehash: 5048d48cc22ebe405ef54dc207ac96b6c274078a
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202631"
---
# <a name="fornext-statement-visual-basic"></a>Instrucción For...Next (Visual Basic)
Repite un grupo de instrucciones en un número especificado de veces.  
  
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
  
|Parte|Descripción|  
|----------|-----------------|  
|`counter`|Necesario en el `For` instrucción. Variable numérica. La variable de control del bucle. Para obtener más información, consulte [contraargumento](#BKMK_Counter) más adelante en este tema.|  
|`datatype`|Opcional. Tipo de datos de `counter`. Para obtener más información, consulte [contraargumento](#BKMK_Counter) más adelante en este tema.|  
|`start`|Obligatorio. Expresión numérica. Valor inicial de `counter`.|  
|`end`|Obligatorio. Expresión numérica. El valor final de `counter`.|  
|`step`|Opcional. Expresión numérica. Cantidad por la que `counter` se incrementa cada vez a través del bucle.|  
|`statements`|Opcional. Una o varias instrucciones entre `For` y `Next` que el número especificado de veces que ejecutan.|  
|`Continue For`|Opcional. Transfiere el control a la siguiente iteración del bucle.|  
|`Exit For`|Opcional. Transfiere el control fuera de la `For` bucle.|  
|`Next`|Obligatorio. Termina la definición de la `For` bucle.|  
  
> [!NOTE]
>  El `To` palabra clave se usa en esta declaración para especificar el intervalo para el contador. También puede usar esta palabra clave en el [seleccione... Instrucción de caso](../../../visual-basic/language-reference/statements/select-case-statement.md) y en las declaraciones de matriz. Para obtener más información acerca de las declaraciones de matriz, vea [instrucción Dim](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## <a name="simple-examples"></a>Ejemplos sencillos  
 Usa un `For`... `Next` estructura cuando desea repetir un conjunto de instrucciones de un número determinado de veces.  
  
 En el ejemplo siguiente, la `index` variable empieza con un valor de 1 y se incrementa con cada iteración del bucle, finalizando después del valor de `index` llega a 5.  
  
 [!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]  
  
 En el ejemplo siguiente, la `number` variable comienza en 2 y se reduce por 0.25 en cada iteración del bucle, finalizando después del valor de `number` llega a 0. El `Step` argumento de `-.25` reduce el valor por 0.25 en cada iteración del bucle.  
  
 [!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]  
  
> [!TIP]
>  Un [mientras... End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [hacer... Instrucción del bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md) funciona bien cuando no conoce de antemano cuántas veces para ejecutar las instrucciones del bucle. Sin embargo, si tiene previsto ejecutar el bucle un número específico de veces, un `For`... `Next` bucle es una opción mejor. Determinar el número de iteraciones cuando se escribe por primera vez el bucle.  
  
## <a name="nesting-loops"></a>Bucles anidados  
 Puede anidar `For` bucles colocando un bucle dentro de otro. En el ejemplo siguiente se muestra anidada `For`... `Next` estructuras que tienen valores de paso diferente. El bucle externo crea una cadena para cada iteración del bucle. Bucle interno reduce una variable de contador de bucle para cada iteración del bucle.  
  
 [!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]  
  
 Al anidar bucles, cada bucle debe tener un único `counter` variable.  
  
 También puede anidar diferentes tipos de estructuras de control dentro de otros. Para obtener más información, consulte [estructuras de Control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Salir de y continuar para  
 El `Exit For` instrucción inmediatamente después cierra el `For`...`Next` bucle y transfiere el control a la instrucción que sigue la `Next` instrucción.  
  
 El `Continue For` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, consulte [instrucción Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 El ejemplo siguiente muestra el uso de la `Continue For` y `Exit For` instrucciones.  
  
 [!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]  
  
 Puede colocar cualquier número de `Exit For` instrucciones en un `For`...`Next` loop. Cuando se usa dentro de anidar `For`...`Next` bucles, `Exit For` sale del bucle más interno y transfiere el control al siguiente nivel más alto de anidamiento.  
  
 `Exit For` a menudo se usa después de evaluar alguna condición (por ejemplo, en un `If`... `Then`... `Else` estructura). Desea usar `Exit For` para las condiciones siguientes:  
  
-   Continuar recorrer en iteración es innecesarios o imposible. Un valor erróneo o una solicitud de finalización puede crear esta condición.  
  
-   Un `Try`... `Catch`... `Finally` instrucción detecta una excepción. Puede usar `Exit For` al final de la `Finally` bloque.  
  
-   Tiene un bucle sin fin, que es un bucle que podría ejecutar un número grande o incluso infinito de veces. Si se detecta una condición de ese tipo, puede usar `Exit For` para salir del bucle. Para obtener más información, consulte [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="technical-implementation"></a>Implementación técnica  
 Cuando un `For`... `Next` bucle se inicia, Visual Basic evalúa `start`, `end`, y `step`. Visual Basic evalúa estos valores solo en este momento y, a continuación, asigna `start` a `counter`. Antes de la instrucción de bloque se ejecuta, Visual Basic compara `counter` a `end`. Si `counter` ya es mayor que el `end` valor (o más pequeño si `step` es negativo), el `For` bucle finaliza y el control pasa a la instrucción que sigue la `Next` instrucción. En caso contrario, se ejecuta el bloque de instrucciones.  
  
 Cada vez que Visual Basic encuentra la `Next` instrucción, lo incrementa `counter` por `step` y vuelve a la `For` instrucción. Nuevo compara `counter` a `end`, y una vez ejecuta el bloque o sale del bucle, dependiendo del resultado. Este proceso continúa hasta que `counter` pasa `end` o `Exit For` se encuentra la instrucción.  
  
 No se detiene hasta que el bucle `counter` ha pasado `end`. Si `counter` es igual a `end`, el bucle continúa. La comparación que determina si se ejecuta el bloque es `counter`  <=  `end` si `step` es positivo y `counter`  >=  `end` si `step` es negativo.  
  
 Si cambia el valor de `counter` dentro de un bucle, podría ser más difícil de leer y depurar el código. Cambiar el valor de `start`, `end`, o `step` no afecta a los valores de iteración que se determinan cuando el bucle se escribió en primer lugar.  
  
 Si se anida bucles, el compilador señala un error si encuentra el `Next` instrucción de un nivel de anidamiento externo antes de la `Next` instrucción de un nivel interno. Sin embargo, el compilador puede detectar esta superposición de error únicamente si se especifica `counter` en cada `Next` instrucción.  
  
### <a name="step-argument"></a>Argumento de paso  
 El valor de `step` puede ser positivo o negativo. Este parámetro determina el procesamiento de bucles según la tabla siguiente:  
  
|**Valor de paso**|**El bucle se ejecuta si**|  
|--------------------|--------------------------|  
|Positivo o cero|`counter` <= `end`|  
|Negativo|`counter` >= `end`|  
  
 El valor predeterminado de `step` es 1.  
  
###  <a name="BKMK_Counter"></a> Argumento de contador  
 La tabla siguiente indica si `counter` define una nueva variable local que se limita a toda la `For…Next` bucle. Esta decisión depende de si `datatype` está presente y si `counter` ya está definido.  
  
|¿Es `datatype` presente?|¿Es `counter` ya definido?|Resultado (si `counter` define una nueva variable local que se limita a toda la `For...Next` bucle)|  
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|  
|No|Sí|No, porque `counter` ya está definido. Si el ámbito de `counter` no es local para el procedimiento, se produce una advertencia de tiempo de compilación.|  
|No|No|Sí. El tipo de datos se deduce de la `start`, `end`, y `step` expresiones. Para obtener información acerca de la inferencia de tipo, consulte [instrucción Option Infer](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Sí|Sí|Sí, pero solo si existente `counter` variable se define fuera del procedimiento. Esa variable sigue siendo independiente. Si el ámbito de la existente `counter` variable es local en el procedimiento, se produce un error de tiempo de compilación.|  
|Sí|No|Sí.|  
  
 Tipo de datos de `counter` determina el tipo de la iteración, que debe ser uno de los siguientes tipos:  
  
-   Un `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, o `Double`.  
  
-   Una enumeración que se declara mediante un [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Una clase `Object`.  
  
-   Un tipo `T` que tiene los siguientes operadores, donde `B` es un tipo que se puede usar en un `Boolean` expresión.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Opcionalmente, puede especificar el `counter` variable en el `Next` instrucción. Esta sintaxis mejora la legibilidad del programa, especialmente si ha anidado `For` bucles. Debe especificar la variable que aparecerá en las correspondientes `For` instrucción.  
  
 El `start`, `end`, y `step` expresiones pueden tener cualquier tipo de datos que se amplía al tipo de `counter`. Si usa un tipo definido por el usuario para `counter`, tendrá que definir la `CType` operador de conversión para convertir los tipos de `start`, `end`, o `step` al tipo de `counter`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente quita todos los elementos de una lista genérica. En lugar de un [para cada... Instrucción Next](../../../visual-basic/language-reference/statements/for-each-next-statement.md), el ejemplo se muestra un `For`... `Next` que procesa una iteración en orden descendente. El ejemplo usa esta técnica porque el `removeAt` método hace que los elementos después del elemento quitado tengan un valor de índice inferior.  
  
 [!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se recorre en iteración una enumeración que se declara mediante un [Enum (instrucción)](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, los parámetros de la instrucción usan una clase que tiene las sobrecargas del operador para el `+`, `-`, `>=`, y `<=` operadores.  
  
 [!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Collections.Generic.List%601>
- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Colecciones](../../programming-guide/concepts/collections.md)
