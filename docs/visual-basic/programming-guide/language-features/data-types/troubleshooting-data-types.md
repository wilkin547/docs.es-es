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
ms.openlocfilehash: 9bbc7f51de9899354184d051d8f1a584651dd030
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213944"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Solucionar problemas de tipos de datos (Visual Basic)
Esta página enumera algunos problemas comunes que pueden producirse al realizar operaciones en tipos de datos intrínsecos.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Expresiones de punto flotante no se consideran iguales  
 Cuando se trabaja con números de punto flotante ([único tipo de datos](../../../../visual-basic/language-reference/data-types/single-data-type.md) y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), recuerde que se almacenan como fracciones binarias. Esto significa que no pueden contener una representación exacta de cualquier cantidad que no sea una fracción binaria (del formulario k / (2 ^ n) donde k y n son números enteros). Por ejemplo, 0,5 (= 1/2) y 0,3125 (= 5/16) pueden incluirse como valores precisos, mientras que 0,2 (= 1/5) y 0,3 (= 3/10) pueden ser solo aproximaciones.  
  
 Por este motivo imprecisión, no puede confiar en los resultados exactos cuando se opera en valores de punto flotante. En concreto, dos valores son iguales, en teoría, podrían tener representaciones ligeramente diferentes.  
  
| Para comparar las cantidades de punto flotante | 
|---| 
|1.  Calcular el valor absoluto de su diferencia mediante la <xref:System.Math.Abs%2A> método de la <xref:System.Math> clase en el <xref:System> espacio de nombres.<br />2.  Determine una diferencia máxima aceptable, de manera que puede considerar las dos cantidades para que sea igual a efectos prácticos si su diferencia no es más grande.<br />3.  Compare el valor absoluto de la diferencia con la diferencia aceptable.|  
  
 En el ejemplo siguiente se muestra una comparación correcta e incorrecta de las dos `Double` valores.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 El ejemplo anterior utiliza la <xref:System.Double.ToString%2A> método de la <xref:System.Double> estructura para que puede especificar la mayor precisión que el `CStr` usa la palabra clave. El valor predeterminado es 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operador Mod no devuelve un resultado preciso  
 Debido a la imprecisión de almacenamiento de punto flotante, el [operador Mod](../../../../visual-basic/language-reference/operators/mod-operator.md) puede devolver un resultado inesperado cuando al menos uno de los operandos es de punto flotante.  
  
 El [tipo de datos Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) no usa la representación de punto flotante. Muchos números que son la inexactos en `Single` y `Double` son exactos en `Decimal` (por ejemplo, 0.2 y 0.3). Aunque la aritmética es más lento en `Decimal` que en punto flotante, es posible que vale la pena la disminución del rendimiento para lograr una mayor precisión.  
  
|Para buscar el resto entero de cantidades de punto flotante|  
|---|  
|1.  Declarar variables como `Decimal`.<br />2.  Use el carácter de tipo literal `D` para forzar que literales `Decimal`, en caso de que sus valores son demasiado grandes para el `Long` tipo de datos.|  
  
 El ejemplo siguiente muestra el potencial de imprecisión de operandos de punto flotante.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 El ejemplo anterior utiliza la <xref:System.Double.ToString%2A> método de la <xref:System.Double> estructura para que puede especificar la mayor precisión que el `CStr` usa la palabra clave. El valor predeterminado es 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
 Dado que `zeroPointTwo` es `Double`, su valor para 0,2 es una fracción binaria con un valor almacenado de 0,20000000000000001. Al dividir 2.0 por esta cantidad Obtiene 9,9999999999999995 con un resto de 0,19999999999999991.  
  
 En la expresión para `decimalRemainder`, el carácter de tipo literal `D` obliga a que ambos operandos a `Decimal`, y 0.2 tiene una representación precisa. Por lo tanto, el `Mod` operador produce el resto esperado de 0,0.  
  
 Tenga en cuenta que no es suficiente declarar `decimalRemainder` como `Decimal`. También se deben forzar que los literales `Decimal`, o bien, usar `Double` de forma predeterminada y `decimalRemainder` recibe el mismo valor inexacto como `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo booleano no convierte con precisión al tipo numérico  
 [Tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valores no se almacenan como números y los valores almacenados no pretende ser equivalente a números. Por compatibilidad con versiones anteriores, Visual Basic proporciona palabras clave para conversiones ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, y así sucesivamente) para convertir entre `Boolean` y los tipos numéricos. Sin embargo, otros lenguajes a veces realizan forma diferente, como hacer estas conversiones el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] métodos.  
  
 Nunca debería escribir código que se basa en valores numéricos equivalentes para `True` y `False`. Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para que se han diseñado. Si debe mezclar `Boolean` y valores numéricos, asegúrese de que comprende el método de conversión que seleccione.  
  
### <a name="conversion-in-visual-basic"></a>Conversión en Visual Basic  
 Cuando se usa el `CType` o `CBool` palabras clave de conversión para convertir tipos de datos numéricos a `Boolean`, se convierte en 0 `False` y todos los demás valores se convierten en `True`. Al convertir `Boolean` valores a tipos numéricos mediante las palabras clave de conversión, `False` se convierte en 0 y `True` se convierte en -1.  
  
### <a name="conversion-in-the-framework"></a>Conversión en el marco de trabajo  
 El <xref:System.Convert.ToInt32%2A> método de la <xref:System.Convert> clase en el <xref:System> convierte el espacio de nombres `True` a + 1.  
  
 Si necesita convertir una `Boolean` valor a un tipo de datos numéricos, tenga cuidado sobre qué método de conversión que usar.  
  
## <a name="character-literal-generates-compiler-error"></a>Error del compilador genera el Literal de carácter  
 En ausencia de cualquier carácter de tipo, Visual Basic se supone de forma predeterminada los tipos de datos para los literales. El tipo predeterminado para un literal de carácter, entre comillas (`" "`), es `String`.  
  
 El `String` tipo de datos no se convierten en el [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Esto significa que si desea asignar un literal para una `Char` variable, debe realizar una conversión de restricción o forzar el literal para el `Char` tipo.  

|Para crear a un carácter literal para asignar a una variable o constante|
|---|  
|1.  Declarar la variable o constante como `Char`.<br />2.  Escriba el valor de carácter entre comillas (`" "`).<br />3.  Siga las comillas dobles de cierre con el carácter de tipo literal `C` para forzar el literal `Char`. Esto es necesario si el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, y es deseable en cualquier caso.|  
  
 El ejemplo siguiente muestra las asignaciones incorrectas y correcta de un literal a una `Char` variable.  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Siempre hay un riesgo para la sesión con las conversiones de restricción, porque puede producir un error en tiempo de ejecución. Por ejemplo, una conversión de `String` a `Char` puede producir un error si el `String` valor contiene más de un carácter. Por lo tanto, es mejor programación para utilizar el `C` carácter de tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Se produce un error de conversión de cadenas en tiempo de ejecución  
 El [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) participa en muy pocas las conversiones de ampliación. `String` solo se amplía a sí mismo y `Object`y solo `Char` y `Char()` (un `Char` matriz) se convierten en `String`. Esto es porque `String` variables y constantes pueden contener valores que no pueden contener otros tipos de datos.  
  
 Cuando la comprobación de tipo modificador ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, el compilador no permite todas las conversiones de restricción implícitas. Esto incluye aquellas que implican `String`. El código todavía puede usar palabras clave de conversión, como `CStr` y [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md), qué direct el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para intentar la conversión.  
  
> [!NOTE]
>  Se suprime el error de conversión de restricción en las conversiones de los elementos de un `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección "Narrowing Conversions" en [For Each... Instrucción Next](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protección de la conversión de restricción  
 El inconveniente de las conversiones de restricción es que pueden producirse errores en tiempo de ejecución. Por ejemplo, si un `String` variable contiene algo distinto de "True" o "False", no se puede convertir a `Boolean`. Si contiene caracteres de puntuación, se produce un error de conversión para cualquier tipo numérico. A menos que sepa que su `String` variable siempre contiene valores que puede aceptar el tipo de destino, no debe intentar una conversión.  
  
 Si necesita convertir desde `String` a otro tipo de datos, el procedimiento más seguro consiste en incluir la conversión intentada en el [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Esto le permite tratar con un error en tiempo de ejecución.  
  
### <a name="character-arrays"></a>Matrices de caracteres  
 Una sola `Char` y una matriz de `Char` elementos ambos se convierten en `String`. Sin embargo, `String` no se convierten en `Char()`. Para convertir un `String` valor a un `Char` matriz, puede usar el <xref:System.String.ToCharArray%2A> método de la <xref:System.String?displayProperty=nameWithType> clase.  
  
### <a name="meaningless-values"></a>No tiene sentidos valores  
 En general, `String` valores no son significativos en otros tipos de datos y la conversión es muy artificial y peligrosa. Siempre que sea posible, debe restringir el uso de `String` variables a las secuencias de caracteres para el que se ha diseñado. Nunca debe escribirse código que se basa en valores equivalentes en otros tipos.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)  
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)  
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
