---
title: Solucionar problemas de tipos de datos (Visual Basic) | Documentos de Microsoft
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Char data type, converting
- Decimal data type, conversions
- data types [Visual Basic], troubleshooting
- literals, default types
- type characters, literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types
- floating-point numbers, precision
- Boolean data type, converting
- literal types
- literal type characters
- floating-point numbers, imprecision
- String data type, converting
- floating-point numbers, comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cfb8fc77d3e0d85ef795a94fc95ab61a8f68ff39
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-data-types-visual-basic"></a>Solucionar problemas de tipos de datos (Visual Basic)
Esta página muestra algunos problemas comunes que pueden aparecer al realizar operaciones en tipos de datos intrínsecos.  
  
## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Expresiones de punto flotante no se comparan como iguales  
 Al trabajar con números de punto flotante ([único tipo de datos](../../../../visual-basic/language-reference/data-types/single-data-type.md) y [tipo de datos Double](../../../../visual-basic/language-reference/data-types/double-data-type.md)), recuerde que se almacenan como fracciones binarias. Esto significa que no pueden contener una representación exacta de ninguna cantidad que no sea una fracción binaria (del formulario k / (2 ^ n) donde k y n son enteros). Por ejemplo, 0,5 (= 1/2) y 0,3125 (= 5/16) pueden mantenerse como valores precisos, mientras que 0,2 (= 1/5) y 0,3 (= 3/10) pueden ser sólo aproximaciones.  
  
 Debido a esta imprecisión, no puede confiar en resultados exactos cuando trabaje en valores de punto flotante. En concreto, los dos valores que son teóricamente iguales podrían tener representaciones ligeramente diferentes.  
  
| Para comparar cantidades de punto flotante | 
|---| 
|1.  Calcular el valor absoluto de su diferencia mediante el <xref:System.Math.Abs%2A>método de la <xref:System.Math>de clase en el <xref:System>espacio de nombres.</xref:System> </xref:System.Math> </xref:System.Math.Abs%2A><br />2.  Determine una diferencia máxima aceptable, de manera que puede considerar las dos cantidades como iguales a efectos prácticos si su diferencia no es mayor.<br />3.  Compare el valor absoluto de la diferencia con la diferencia aceptable.|  
  
 En el ejemplo siguiente se muestra una comparación correcta e incorrecta de dos `Double` valores.  
  
 [!code-vb[VbVbalrDataTypes&#10;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 En el ejemplo anterior se utiliza el <xref:System.Double.ToString%2A>método de la <xref:System.Double>estructura para que pueda especificar una mayor precisión que el `CStr` utiliza la palabra clave.</xref:System.Double> </xref:System.Double.ToString%2A> El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
## <a name="mod-operator-does-not-return-accurate-result"></a>Operador Mod no devuelve resultados precisos  
 Debido a la imprecisión de almacenamiento de punto flotante, el [Mod (operador)](../../../../visual-basic/language-reference/operators/mod-operator.md) puede devolver un resultado inesperado cuando al menos uno de los operandos es de punto flotante.  
  
 El [tipo de datos Decimal](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) no utiliza la representación de punto flotante. Muchos números que son inexactos en formato `Single` y `Double` exactos en `Decimal` (por ejemplo 0,2 y 0,3). Aunque la aritmética es más lento en `Decimal` que en punto flotante, podría ser conveniente la disminución del rendimiento para conseguir una mayor precisión.  
  
|Para buscar el resto entero de cantidades de punto flotante|  
|---|  
|1.  Declarar variables como `Decimal`.<br />2.  Utilice el carácter de tipo literal `D` para forzar literales a `Decimal`, en caso de que sus valores sean demasiado grandes para el `Long` el tipo de datos.|  
  
 En el ejemplo siguiente se muestra la imprecisión de punto flotante operandos potencial.  
  
 [!code-vb[VbVbalrDataTypes&#11;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 En el ejemplo anterior se utiliza el <xref:System.Double.ToString%2A>método de la <xref:System.Double>estructura para que pueda especificar una mayor precisión que el `CStr` utiliza la palabra clave.</xref:System.Double> </xref:System.Double.ToString%2A> El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
 Porque `zeroPointTwo` es `Double`, su valor para 0,2 es una fracción binaria infinitamente repetitiva con un valor almacenado de 0,20000000000000001. Al dividir 2,0 por esta cantidad, Obtiene 9,9999999999999995 con un resto de 0,19999999999999991.  
  
 En la expresión de `decimalRemainder`, el carácter de tipo literal `D` obliga a que ambos operandos a `Decimal`, y 0.2 tiene una representación precisa. Por lo tanto, la `Mod` operador produce el resto esperado de 0,0.  
  
 Tenga en cuenta que no es suficiente declarar `decimalRemainder` como `Decimal`. También debe forzar los literales a `Decimal`, o bien usan `Double` de forma predeterminada y `decimalRemainder` recibe el mismo valor inexacto que `doubleRemainder`.  
  
## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Tipo booleano no convierte con precisión al tipo numérico  
 [Tipo de datos Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) valores no se almacenan como números y los valores almacenados no están diseñados para ser equivalentes a los números. Por compatibilidad con versiones anteriores, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona palabras clave para conversiones ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, etc.) para convertir entre `Boolean` y los tipos numéricos. Sin embargo, otros lenguajes a veces realizan diferente, como hacer estas conversiones el [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] métodos.  
  
 Nunca debería escribir código que se basa en valores numéricos equivalentes para `True` y `False`. Siempre que sea posible, debe restringir el uso de `Boolean` variables a los valores lógicos para los que se han diseñado. Si debe mezclar `Boolean` y valores numéricos, asegúrese de que comprende el método de conversión que seleccione.  
  
### <a name="conversion-in-visual-basic"></a>Conversión en Visual Basic  
 Cuando se usa el `CType` o `CBool` palabras clave de conversión para convertir tipos de datos numéricos a `Boolean`, 0 se convierte en `False` y todos los demás valores se convierten en `True`. Al convertir `Boolean` valores a tipos numéricos utilizando las palabras clave de conversión, `False` se convierte en 0 y `True` se convierte en -1.  
  
### <a name="conversion-in-the-framework"></a>Conversión en Framework  
 El <xref:System.Convert.ToInt32%2A>método de la <xref:System.Convert>de clase en el <xref:System>convierte el espacio de nombres `True` a +&1;.</xref:System> </xref:System.Convert> </xref:System.Convert.ToInt32%2A>  
  
 Si debe convertir un `Boolean` valor a un tipo de datos numérico, tenga cuidado acerca de qué método de conversión que utilizar.  
  
## <a name="character-literal-generates-compiler-error"></a>Carácter Literal genera un Error del compilador  
 En ausencia de cualquier tipo de caracteres, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] supone de forma predeterminada los tipos de datos literales. El tipo predeterminado para un literal de carácter: entre comillas (`" "`), es `String`.  
  
 El `String` tipo de datos no se amplía a la [tipo de datos Char](../../../../visual-basic/language-reference/data-types/char-data-type.md). Esto significa que si desea asignar un literal a un `Char` variable, debe realizar una conversión de restricción o forzar el literal el `Char` tipo.  

|Para crear a un carácter literal que se asigna a una variable o constante|
|---|  
|1.  Declare la variable o constante como `Char`.<br />2.  Escriba el valor de carácter entre comillas (`" "`).<br />3.  Siga las comillas de cierre con el carácter de tipo literal `C` para forzar el literal `Char`. Esto es necesario si el modificador de comprobación de tipo ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, y es deseable en cualquier caso.|  
  
 El ejemplo siguiente muestra las asignaciones incorrectas y correctas de un literal a un `Char` variable.  
  
 [!code-vb[VbVbalrDataTypes&#12;](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_3.vb)]  
  
 Siempre hay un riesgo en el uso de conversiones de restricción, ya que puede producir un error en tiempo de ejecución. Por ejemplo, una conversión de `String` a `Char` puede fallar si el `String` valor contiene más de un carácter. Por lo tanto, es mejor programación para utilizar el `C` carácter de tipo.  
  
## <a name="string-conversion-fails-at-run-time"></a>Se produce un error en la conversión de cadenas en tiempo de ejecución  
 El [tipo de datos String](../../../../visual-basic/language-reference/data-types/string-data-type.md) participa en muy pocas conversiones de ampliación. `String`sólo se amplía a sí mismo y `Object`y sólo `Char` y `Char()` (un `Char` matriz) se convierten en `String`. Esto es porque `String` variables y constantes pueden contener valores que no pueden contener otros tipos de datos.  
  
 Cuando la comprobación de tipo modificador ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `On`, el compilador deniega todas las conversiones de restricción implícitas. Esto incluye aquellas que implican `String`. El código todavía puede usar palabras clave de conversión como `CStr` y [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md), qué directa el [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] para intentar la conversión.  
  
> [!NOTE]
>  El error de conversión de restricción se suprime en las conversiones de los elementos en una `For Each…Next` colección a la variable de control de bucle. Para obtener más información y ejemplos, vea la sección "Conversiones de restricción" en [For Each... Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### <a name="narrowing-conversion-protection"></a>Protección de conversión de restricción  
 El inconveniente de las conversiones de restricción es que puede producir un error en tiempo de ejecución. Por ejemplo, si un `String` variable contiene algo distinto de "True" o "False", no se puede convertir a `Boolean`. Si contiene caracteres de puntuación, se produce un error en la conversión de cualquier tipo numérico. A menos que sepa que su `String` variable siempre contiene valores que puede aceptar el tipo de destino, no debería intentar la conversión.  
  
 Si debe convertir de `String` a otro tipo de datos, el procedimiento más seguro consiste en incluir la conversión intentada en el [intente... Catch... Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Esto le permite tratar con un error de tiempo de ejecución.  
  
### <a name="character-arrays"></a>Matrices de caracteres  
 Una sola `Char` y una matriz de `Char` elementos ambos se amplían a `String`. Sin embargo, `String` no se amplía a `Char()`. Para convertir un `String` valor a un `Char` matriz, puede utilizar el <xref:System.String.ToCharArray%2A>método de la <xref:System.String?displayProperty=fullName>clase.</xref:System.String?displayProperty=fullName> </xref:System.String.ToCharArray%2A>  
  
### <a name="meaningless-values"></a>Valores sin sentido  
 En general, `String` valores no son significativos en otros tipos de datos y la conversión resulta muy artificial y peligrosa. Siempre que sea posible, debe restringir el uso de `String` variables a las secuencias de caracteres que están diseñadas. Nunca debería escribir código que se basa en los valores equivalentes en otros tipos.  
  
## <a name="see-also"></a>Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipo](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
