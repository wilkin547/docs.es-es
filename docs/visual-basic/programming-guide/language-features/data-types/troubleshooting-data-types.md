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
ms.openlocfilehash: 5b2cb0d5270b7e14c3462aeaf54942f939511fd7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933230"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Solucionar problemas de tipos de datos (Visual Basic)
En esta página se enumeran algunos problemas comunes que pueden producirse al realizar operaciones en tipos de datos intrínsecos.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Las expresiones de punto flotante no se comparan como iguales  
 Al trabajar con números de punto flotante ([tipo de datos único](../../../../visual-basic/language-reference/data-types/single-data-type.md) y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), recuerde que se almacenan como fracciones binarias. Esto significa que no pueden contener una representación exacta de cualquier cantidad que no sea una fracción binaria (de la forma k/(2 ^ n), donde k y n son enteros). Por ejemplo, 0,5 (= 1/2) y 0,3125 (= 5/16) se pueden conservar como valores precisos, mientras que 0,2 (= 1/5) y 0,3 (= 3/10) solo pueden ser aproximaciones.  
  
 Debido a este imprecisión, no se puede confiar en los resultados exactos cuando se trabaja en valores de punto flotante. En concreto, dos valores que son teóricamente iguales pueden tener representaciones ligeramente diferentes.  
  
| Para comparar las cantidades de punto flotante | 
|---| 
|1.  Calcule el valor absoluto de su diferencia mediante el <xref:System.Math.Abs%2A> método de la <xref:System.Math> clase en el <xref:System> espacio de nombres.<br />2.  Determine una diferencia máxima aceptable, de modo que pueda considerar las dos cantidades para que sean iguales a efectos prácticos si su diferencia no es mayor.<br />3.  Compare el valor absoluto de la diferencia con la diferencia aceptable.|  
  
 En el ejemplo siguiente se muestra la comparación incorrecta y correcta `Double` de dos valores.  
  
 [!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]  
  
 En el ejemplo anterior se <xref:System.Double.ToString%2A> usa el método <xref:System.Double> de la estructura para que pueda especificar mejor precisión de `CStr` la que utiliza la palabra clave. El valor predeterminado es 15 dígitos, pero el formato "G17" lo extiende hasta 17 dígitos.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>El operador mod no devuelve un resultado preciso  
 Debido a la imprecisión del almacenamiento de punto flotante, el [operador mod](../../../../visual-basic/language-reference/operators/mod-operator.md) puede devolver un resultado inesperado cuando al menos uno de los operandos es de punto flotante.  
  
 El [tipo de datos decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) no utiliza la representación de punto flotante. Muchos números que son inexactos `Single` en `Double` y son exactos en `Decimal` (por ejemplo 0,2 y 0,3). Aunque la aritmética es más `Decimal` lenta que en punto flotante, podría merecer la pena la disminución del rendimiento para lograr una mayor precisión.  
  
|Para buscar el resto entero de las cantidades de punto flotante|  
|---|  
|1.  Declarar variables como `Decimal`.<br />2.  Use el carácter `D` de tipo literal para forzar literales en, en caso de que `Decimal`sus valores sean `Long` demasiado grandes para el tipo de datos.|  
  
 En el ejemplo siguiente se muestran los posibles imprecisión de operandos de punto flotante.  
  
 [!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]  
  
 En el ejemplo anterior se <xref:System.Double.ToString%2A> usa el método <xref:System.Double> de la estructura para que pueda especificar mejor precisión de `CStr` la que utiliza la palabra clave. El valor predeterminado es 15 dígitos, pero el formato "G17" lo extiende hasta 17 dígitos.  
  
 Dado `zeroPointTwo` que `Double`es, su valor para 0,2 es una fracción binaria repetida infinitamente con un valor almacenado de 0.20000000000000001. La división de 2,0 por esta cantidad produce 9.9999999999999995 con un resto de 0.19999999999999991.  
  
 En la expresión para `decimalRemainder`, el carácter `D` de tipo literal fuerza ambos operandos a `Decimal`y 0,2 tiene una representación precisa. Por lo `Mod` tanto, el operador produce el resto esperado de 0,0.  
  
 Tenga en cuenta que no es suficiente declarar `decimalRemainder` como `Decimal`. También debe forzar los literales en `Decimal`, o usar `Double` de forma predeterminada y `decimalRemainder` recibir el mismo valor inexacto que `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>El tipo Boolean no se convierte en un tipo numérico con precisión  
 Los valores de [tipo de datos booleanos](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a números. Por compatibilidad con versiones anteriores, Visual Basic proporciona palabras clave de conversión ([función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, etc.) para convertir `Boolean` entre tipos numéricos y. Sin embargo, a veces otros lenguajes realizan estas conversiones de manera diferente, al igual que los métodos de .NET Framework.  
  
 Nunca debe escribir código que se base en valores numéricos equivalentes `True` para `False`y. Siempre que sea posible, debe restringir `Boolean` el uso de variables a los valores lógicos para los que están diseñadas. Si debe mezclar `Boolean` valores numéricos y, asegúrese de que comprende el método de conversión que seleccione.  
  
### <a name="conversion-in-visual-basic"></a>Conversión en Visual Basic  
 Cuando se utilizan las `CType` palabras `CBool` clave de conversión o para convertir tipos de `Boolean`datos numéricos `False` en, 0 se convierte `True`en y todos los demás valores se convierten en. Cuando se convierten `Boolean` valores en tipos numéricos mediante las palabras clave `False` de conversión, `True` se convierte en 0 y se convierte en-1.  
  
### <a name="conversion-in-the-framework"></a>Conversión en el marco de trabajo  
 El <xref:System.Convert.ToInt32%2A> método de la <xref:System.Convert> <xref:System> clase`True` en el espacio de nombres convierte en + 1.  
  
 Si debe convertir un `Boolean` valor en un tipo de datos numérico, tenga cuidado con el método de conversión que utilice.  
  
## <a name="character-literal-generates-compiler-error"></a>El literal de carácter genera un error del compilador  
 En ausencia de caracteres de tipo, Visual Basic asume los tipos de datos predeterminados para los literales. El tipo predeterminado para un literal de carácter, entre comillas (`" "`), es `String`.  
  
 El `String` tipo de datos no se amplía al [tipo de datos char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Esto significa que, si desea asignar un literal a una `Char` variable, debe realizar una conversión de restricción o forzar el literal `Char` al tipo.  

|Para crear un literal char para asignarlo a una variable o constante|
|---|  
|1.  Declare la variable o la `Char`constante como.<br />2.  Incluya el valor del carácter entre comillas`" "`().<br />3.  Siga las comillas dobles de cierre con el carácter `C` de tipo literal para forzar el literal a. `Char` Esto es necesario si el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, y es deseable en cualquier caso.|  
  
 En el ejemplo siguiente se muestran las asignaciones correctas y erróneas de un literal a una `Char` variable.  
  
 [!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]  
  
 Siempre hay un riesgo en el uso de conversiones de restricción, ya que pueden producir errores en tiempo de ejecución. Por ejemplo, una conversión de `String` a `Char` puede producir un error `String` si el valor contiene más de un carácter. Por lo tanto, es mejor programar el uso `C` del carácter de tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Error de conversión de cadena en tiempo de ejecución  
 El [tipo de datos de cadena](../../../../visual-basic/language-reference/data-types/string-data-type.md) participa en muy pocas conversiones de ampliación. `String`solo se amplía a sí mismo `Object`y, y `Char` solo `Char()` y ( `Char` una matriz) se `String`amplía a. Esto se debe `String` a que las variables y constantes pueden contener valores que otros tipos de datos no pueden contener.  
  
 Cuando el modificador de comprobación de tipo ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es, el compilador no `On`permite todas las conversiones de restricción implícitas. Esto incluye los que implican `String`. El código todavía puede usar palabras clave de conversión `CStr` como y la [función ctype](../../../../visual-basic/language-reference/functions/ctype-function.md), que dirigen el .NET Framework para intentar la conversión.  
  
> [!NOTE]
> Se suprime el error de conversión de restricción para las conversiones de los elementos de una `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección acerca de las conversiones de restricción en [for each... Instrucción siguiente](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protección de conversión de restricción  
 El inconveniente de las conversiones de restricción es que pueden producir errores en tiempo de ejecución. Por ejemplo, si una `String` variable contiene un valor distinto de "true" o "false", no se puede convertir `Boolean`en. Si contiene caracteres de puntuación, se produce un error en la conversión a cualquier tipo numérico. A menos que sepa que `String` la variable siempre contiene valores que el tipo de destino puede aceptar, no debe intentar realizar una conversión.  
  
 Si debe convertir de a `String` otro tipo de datos, el procedimiento más seguro consiste en incluir la conversión intentada en la [instrucción try... Detectar... Finally](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Esto le permite tratar con un error en tiempo de ejecución.  
  
### <a name="character-arrays"></a>Matrices de caracteres  
 Una sola `Char` y una matriz de `Char` elementos se amplían `String`a. Sin embargo `String` , no se amplía `Char()`a. Para convertir un `String` valor en una `Char` matriz, puede utilizar el <xref:System.String.ToCharArray%2A> método de la <xref:System.String?displayProperty=nameWithType> clase.  
  
### <a name="meaningless-values"></a>Valores sin sentido  
 En general, `String` los valores no son significativos en otros tipos de datos y la conversión es muy artificial y peligrosa. Siempre que sea posible, debe restringir `String` el uso de variables a las secuencias de caracteres para las que están diseñadas. Nunca debe escribir código que se base en valores equivalentes en otros tipos.  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
