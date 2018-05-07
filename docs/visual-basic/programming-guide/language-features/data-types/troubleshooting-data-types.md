---
title: Solucionar problemas de tipos de datos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: c5ff9d097c0660956a9751a23511d8273766227c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="troubleshooting-data-types-visual-basic"></a>Solucionar problemas de tipos de datos (Visual Basic)
Esta página enumera algunos problemas comunes que pueden producirse al realizar operaciones en tipos de datos intrínsecos.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Expresiones de punto flotante no se consideran iguales  
 Al trabajar con números de punto flotante ([único tipo de datos](../../../../visual-basic/language-reference/data-types/single-data-type.md) y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), recuerde que se almacenan como fracciones binarias. Esto significa que no pueden contener una representación exacta de ninguna cantidad que no sea una fracción binaria (del formulario k / (2 ^ n) donde k y n son números enteros). Por ejemplo, 0,5 (= 1/2) y 0,3125 (= 5/16) pueden mantenerse como valores precisos, mientras que 0,2 (= 1/5) y 0,3 (= 3/10) pueden ser sólo aproximaciones.  
  
 Por este motivo imprecisión, no puede confiar en resultados exactos cuando trabaje en valores de punto flotante. En concreto, dos valores que son teóricamente iguales podrían tener representaciones ligeramente diferentes.  
  
| Para comparar cantidades de punto flotante | 
|---| 
|1.  Calcular el valor absoluto de su diferencia mediante el <xref:System.Math.Abs%2A> método de la <xref:System.Math> clase en el <xref:System> espacio de nombres.<br />2.  Determine una diferencia máxima aceptable, de manera que puede tener en cuenta las dos cantidades son iguales a efectos prácticos si su diferencia es no superior.<br />3.  Compare el valor absoluto de la diferencia con la diferencia aceptable.|  
  
 En el ejemplo siguiente se muestra una comparación correcta e incorrecta de dos `Double` valores.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 El ejemplo anterior utiliza la <xref:System.Double.ToString%2A> método de la <xref:System.Double> estructura para que puedan especificar mayor precisión que el `CStr` utiliza la palabra clave. El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operador Mod no devuelve resultados precisos  
 Debido a la imprecisión de almacenamiento de punto flotante, el [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md) puede devolver un resultado inesperado cuando al menos uno de los operandos es de punto flotante.  
  
 El [tipo de datos Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) no usa la representación de punto flotante. Muchos números que son inexactos en formato `Single` y `Double` son exactos en `Decimal` (por ejemplo 0,2 y 0,3). Aunque las operaciones aritméticas es más lento en `Decimal` que en punto flotante, es posible que vale la pena la disminución del rendimiento para lograr una mayor precisión.  
  
|Para buscar el resto entero de cantidades de punto flotante|  
|---|  
|1.  Declarar variables como `Decimal`.<br />2.  Use el carácter de tipo literal `D` para forzar literales a `Decimal`, en caso de que sus valores sean demasiado grandes para el `Long` tipo de datos.|  
  
 En el ejemplo siguiente se muestra la posible imprecisión de operandos de punto flotante.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 El ejemplo anterior utiliza la <xref:System.Double.ToString%2A> método de la <xref:System.Double> estructura para que puedan especificar mayor precisión que el `CStr` utiliza la palabra clave. El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
 Dado que `zeroPointTwo` es `Double`, su valor para 0,2 es una fracción binaria infinitamente repetitiva con un valor almacenado de 0,20000000000000001. Al dividir 2,0 por esta cantidad, Obtiene 9,9999999999999995 con un resto de 0,19999999999999991.  
  
 En la expresión para `decimalRemainder`, el carácter de tipo literal `D` obliga a que ambos operandos para `Decimal`, y 0.2 tiene una representación precisa. Por lo tanto, la `Mod` operador produce el resto esperado de 0,0.  
  
 Tenga en cuenta que no es suficiente declarar `decimalRemainder` como `Decimal`. También debe forzar los literales a `Decimal`, o bien, usar `Double` de forma predeterminada y `decimalRemainder` recibe el mismo valor inexacto como `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo booleano no convierte con precisión al tipo numérico  
 [Tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valores no se almacenan como números y los valores almacenados no pretenden ser equivalente a números. Por compatibilidad con versiones anteriores, Visual Basic proporciona palabras clave para conversiones ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, y así sucesivamente) para realizar conversiones entre `Boolean` y los tipos numéricos. Sin embargo, otros lenguajes en ocasiones realizan diferente, como hace estas conversiones el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] métodos.  
  
 Nunca debe escribirse código que se basa en valores numéricos equivalentes para `True` y `False`. Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para los que están diseñadas. Si debe mezclar `Boolean` y valores numéricos, asegúrese de que comprende el método de conversión que seleccione.  
  
### <a name="conversion-in-visual-basic"></a>Conversión en Visual Basic  
 Cuando se usa el `CType` o `CBool` palabras clave de conversión para convertir tipos de datos numéricos a `Boolean`, 0 se convierte en `False` y todos los demás valores se convierten en `True`. Al convertir `Boolean` valores a tipos numéricos utilizando las palabras clave para conversiones, `False` se convierte en 0 y `True` se convierte en -1.  
  
### <a name="conversion-in-the-framework"></a>Conversión en el marco de trabajo  
 El <xref:System.Convert.ToInt32%2A> método de la <xref:System.Convert> clase en el <xref:System> convierte el espacio de nombres `True` a + 1.  
  
 Si debe convertir un `Boolean` valor a un tipo de datos numéricos, debe tener cuidado sobre qué método de conversión usan.  
  
## <a name="character-literal-generates-compiler-error"></a>Carácter Literal genera un Error del compilador  
 En ausencia de cualquier carácter de tipo, Visual Basic se supone de forma predeterminada tipos de datos para los valores literales. El tipo predeterminado para un literal de carácter, entre comillas (`" "`), es `String`.  
  
 El `String` tipo de datos no se amplía a la [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Esto significa que si desea asignar un literal a un `Char` variable, debe realizar una conversión de restricción o forzar que el literal el `Char` tipo.  

|Para crear a un carácter literal que se asigna a una variable o constante|
|---|  
|1.  Declarar la variable o constante como `Char`.<br />2.  Escriba el valor de carácter entre comillas (`" "`).<br />3.  Siga las comillas dobles de cierre con el carácter de tipo literal `C` para forzar el literal `Char`. Esto es necesario si el modificador de comprobación de tipo ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, y es deseable en cualquier caso.|  
  
 El ejemplo siguiente muestra las asignaciones incorrectas y correctas de un literal a un `Char` variable.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Siempre hay un riesgo para la sesión con las conversiones de restricción, porque pueden producirse errores en tiempo de ejecución. Por ejemplo, una conversión de `String` a `Char` puede fallar si el `String` valor contiene más de un carácter. Por lo tanto, es mejor programación para usar el `C` carácter de tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Se produce un error en la conversión de cadenas en tiempo de ejecución  
 El [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) participa en muy pocas conversiones de ampliación. `String` solo se amplía a sí mismo y `Object`y solo `Char` y `Char()` (un `Char` matriz) se amplían a `String`. Esto es porque `String` variables y constantes pueden contener valores que no pueden contener otros tipos de datos.  
  
 Cuando cambie la comprobación de tipos ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, el compilador no permite todas las conversiones de restricción implícitas. Esto incluye aquellas que implican `String`. El código todavía puede usar palabras clave de conversión como `CStr` y [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md), qué direct el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para intentar la conversión.  
  
> [!NOTE]
>  El error de conversión de restricción se suprime para las conversiones de los elementos en una `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección "Conversiones de restricción" en [For Each... Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protección de conversión de restricción  
 El inconveniente de las conversiones de restricción es que pueden producirse errores en tiempo de ejecución. Por ejemplo, si un `String` variable contiene algo distinto de "True" o "False", no se puede convertir a `Boolean`. Si contiene caracteres de puntuación, se produce un error en la conversión a cualquier tipo numérico. A menos que sepa que la `String` variable siempre contiene valores que puede aceptar el tipo de destino, no debería intentar la conversión.  
  
 Si debe convertir de `String` a otro tipo de datos, el procedimiento más seguro consiste en incluir el intento de conversión en el [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Esto le permite tratar con un error en tiempo de ejecución.  
  
### <a name="character-arrays"></a>Matrices de caracteres  
 Una sola `Char` y una matriz de `Char` elementos ambos amplían al `String`. Sin embargo, `String` no se amplía a `Char()`. Para convertir un `String` valor a un `Char` matriz, puede utilizar el <xref:System.String.ToCharArray%2A> método de la <xref:System.String?displayProperty=nameWithType> clase.  
  
### <a name="meaningless-values"></a>Valores sin sentido  
 En general, `String` valores no son significativos en otros tipos de datos y la conversión es muy artificial y peligrosa. Siempre que sea posible, debe restringir el uso de `String` variables en las secuencias de caracteres para los que están diseñadas. Nunca debe escribirse código que se basa en valores equivalentes en otros tipos.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
