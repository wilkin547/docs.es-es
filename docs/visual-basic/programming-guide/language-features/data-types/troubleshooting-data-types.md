---
title: "Solucionar problemas de tipos de datos (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean (tipo de datos), convertir"
  - "Char (tipo de datos), convertir"
  - "tipos de datos [Visual Basic], solucionar problemas"
  - "Decimal (tipo de datos), conversiones"
  - "números de punto flotante"
  - "números de punto flotante, comparación"
  - "números de punto flotante, imprecisión"
  - "números de punto flotante, precisión"
  - "caracteres de tipo literal"
  - "tipos literales"
  - "literales, tipos predeterminados"
  - "Mod (operador) [Visual Basic], en operaciones de punto flotante"
  - "String (tipo de datos), convertir"
  - "solucionar problemas de tipos de datos"
  - "solucionar problemas de Visual Basic, tipos de datos"
  - "caracteres de tipo, literal"
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
caps.latest.revision: 29
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Solucionar problemas de tipos de datos (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Esta página muestra algunos problemas comunes que pueden aparecer al realizar operaciones en tipos de datos intrínsecos.  
  
## Las expresiones de punto flotante no se comparan como iguales  
 Cuando trabaje con números de punto flotante \([Single \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/single-data-type.md) y [Double \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/double-data-type.md)\), tenga en cuenta que se almacenan como fracciones binarias.  Esto significa que no pueden contener una representación exacta de ninguna cantidad que no sea una fracción binaria \(con el formato k \/ \(2 ^ n\) donde k y n son números enteros\).  Por ejemplo, 0,5 \(\= 1\/2\) y 0,3125 \(\= 5\/16\) se pueden almacenar como valores precisos, mientras que 0,2 \(\= 1\/5\) y 0,3 \(\= 3\/10\) sólo pueden se aproximaciones.  
  
 Debido a esta imprecisión, no puede confiar en resultados exactos cuando trabaje en valores de punto flotante.  Concretamente, dos valores que son teóricamente iguales podrían tener representaciones ligeramente distintas.  
  
||  
|-|  
|Para comparar cantidades de punto flotante|  
|1.  Calcule el valor absoluto de su diferencia, utilizando el método <xref:System.Math.Abs%2A> de la clase <xref:System.Math> contenida en el espacio de nombres <xref:System>.<br />2.  Determine una diferencia máxima aceptable, de manera que considere ambas cantidades como iguales a efectos prácticos si su diferencia es menor que la especificada.<br />3.  Compare el valor absoluto de la diferencia con la diferencia aceptable.|  
  
 En el ejemplo siguiente se muestran comparaciones incorrectas y correctas de dos valores `Double`.  
  
 [!code-vb[VbVbalrDataTypes#10](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_1.vb)]  
  
 En el ejemplo anterior se usa el método <xref:System.Double.ToString%2A> de la estructura <xref:System.Double> para que pueda especificar una mayor precisión que la utilizada por la palabra clave `CStr`.  El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
## El operador Mod no devuelve un resultado preciso  
 Debido al imprecisión de almacenamiento con punto flotante, el [Mod \(Operador\)](../../../../visual-basic/language-reference/operators/mod-operator.md) puede devolver un resultado inesperado cuando al menos uno de los operandos es de punto flotante.  
  
 El [Decimal \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/decimal-data-type.md) no utiliza la representación en punto flotante.  Muchos números que son inexactos en formato `Single` y `Double` son exactos en el formato `Decimal` \(por ejemplo 0,2 y 0,3\).  Aunque las operaciones aritméticas se realizan más lentamente en formato `Decimal` que con punto flotante, podría merecer la pena perder rendimiento para conseguir una mayor precisión.  
  
||  
|-|  
|Para buscar el resto entero de cantidades de punto flotante|  
|1.  Declare las variables como `Decimal`.<br />2.  Utilice el carácter de tipo literal `D` para forzar que los valores literales sean `Decimal`, en caso de que sus valores sean demasiado grandes para el tipo de datos `Long`.|  
  
 En el ejemplo siguiente se muestra la imprecisión potencial de los operandos de punto flotante.  
  
 [!code-vb[VbVbalrDataTypes#11](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_2.vb)]  
  
 En el ejemplo anterior se usa el método <xref:System.Double.ToString%2A> de la estructura <xref:System.Double> para que pueda especificar una mayor precisión que la utilizada por la palabra clave `CStr`.  El valor predeterminado es de 15 dígitos, pero el formato "G17" lo amplía a 17 dígitos.  
  
 Dado que `zeroPointTwo` es `Double`, su valor para 0,2 es una fracción binaria infinitamente repetitiva con un valor almacenado de 0,20000000000000001.  Al dividir 2,0 por esta cantidad, se obtiene 9,9999999999999995 con un resto de 0,19999999999999991.  
  
 En la expresión de `decimalRemainder`, el carácter de tipo literal `D` obliga a que ambos operandos sean `Decimal`, y 0,2 tenga una representación precisa.  Por consiguiente el operador `Mod` produce el resto esperado de 0,0.  
  
 Tenga en cuenta que no basta con declarar `decimalRemainder` como `Decimal`.  También debe forzar los valores literales a `Decimal` o a que su valor predeterminado sea `Double` y `decimalRemainder` reciba el mismo valor inexacto que `doubleRemainder`.  
  
## El tipo booleano no convierte con precisión al tipo numérico  
 Los valores [Boolean \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) no se almacenan como números y los valores almacenados no se consideran equivalentes a números.  Para la compatibilidad con versiones anteriores, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona las palabras clave de conversión \([CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md), `CBool`, `CInt`, etc.\) para convertir entre `Boolean` y los tipos numéricos.  Sin embargo, en ocasiones otros lenguajes realizan de manera diferente estas conversiones, como ocurre con los métodos de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 No debe escribir código que se base en los valores numéricos equivalentes de `True` y `False`.  Siempre que sea posible, debe restringir el uso de variables `Boolean` a los valores lógicos para los que se han diseñado.  Si debe mezclar valores `Boolean` y numéricos, asegúrese de que entiende el método de conversión que selecciona.  
  
### Conversión en Visual Basic  
 Cuando utilice la conversión `CType` o `CBool` para convertir tipos de datos numéricos en `Boolean`, 0 se convierte en `False` y todos los demás valores en `True`.  Al convertir valores `Boolean` en tipos numéricos usando las palabras clave de conversión, `False` se convierte en 0 y `True` en \-1.  
  
### Conversión en Framework  
 El método <xref:System.Convert.ToInt32%2A> de la clase <xref:System.Convert> del espacio de nombres <xref:System> convierte `True` en \+1.  
  
 Si necesita convertir un valor `Boolean` en un tipo de datos numérico, tenga cuidado al elegir el método de conversión usado.  
  
## El carácter literal genera un error del compilador  
 En ausencia de caracteres de tipo, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] presupone los tipos de datos predeterminados para los valores literales.  El tipo predeterminado para un literal de carácter, incluido entre comillas \(`" "`\), es `String`.  
  
 El tipo de datos `String` no amplía al [Char \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/char-data-type.md).  Esto significa que, si desea asignar un literal a una variable `Char`, debe realizar una conversión de restricción para forzar a que el valor literal sea del tipo `Char`.  
  
||  
|-|  
|Para crear un literal Char para asignarlo a una variable o constante|  
|1.  Declare la variable o constante como `Char`.<br />2.  Incluya el valor de carácter entre comillas \(`" "`\).<br />3.  A continuación de la comilla doble de cierre, coloque el carácter de tipo literal `C` para forzar que el valor literal sea de tipo `Char`.  Esto es necesario si el modificador de comprobación de tipo \([Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) es `On`, y es deseable en cualquier caso.|  
  
 El ejemplo siguiente muestra asignaciones incorrectas y correctas de un valor literal a una variable `Char`.  
  
 [!CODE [VbVbalrStatements#49](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrStatements#49)]  
  
 [!code-vb[VbVbalrDataTypes#12](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/troubleshooting-data-types_4.vb)]  
  
 Siempre existe un riesgo en la utilización de conversiones de restricción, porque se pueden producir errores en tiempo de ejecución.  Por ejemplo, se puede producir un error en una conversión de `String` a `Char` si el valor `String` contiene más de un carácter.  Por consiguiente, es mejor programar para que se utilice el carácter de tipo `C`.  
  
## La conversión de cadenas produce errores en tiempo de ejecución  
 El [String \(Tipo de datos\)](../../../../visual-basic/language-reference/data-types/string-data-type.md) toma parte en muy pocas conversiones de ampliación.  `String` solo se amplía a sí mismo y a `Object`, y solo `Char` y `Char()` \(matriz de `Char`\) amplían a `String`.  Esto es así porque las variables y constantes `String` pueden contener valores que no pueden contener otros tipos de datos.  
  
 Cuando el modificador de comprobación del tipo \([Option Strict \(Instrucción\)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)\) está `On`, el compilador deniega todas las conversiones de restricción implícitas.  Esto incluye las que implican `String`.  El código todavía puede usar palabras clave de conversión como `CStr` y la [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md), que indican a [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] que intente realizar la conversión.  
  
> [!NOTE]
>  El error de la conversión de restricción se suprime en las conversiones de los elementos de una colección `For Each…Next` a la variable de control del bucle.  Para obtener más información y ejemplos, consulte la sección "Conversiones de restricción" en [For Each...Next \(Instrucción\)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
### Protección de conversión de restricción  
 El inconveniente de las conversiones de restricción es que pueden producir errores en tiempo de ejecución.  Por ejemplo, si una variable `String` contiene un valor distinto de "True" o "False", no se puede convertir a `Boolean`.  Si contiene caracteres de puntuación, se produce un error al convertir en cualquier tipo numérico.  A menos que sepa que la variable `String` siempre contiene valores aceptados por el tipo de destino, no debería intentar la conversión.  
  
 Si necesita convertir de `String` a otro tipo de datos, el procedimiento más seguro consiste en incluir la conversión que intenta realizar en la [Try...Catch...Finally \(Instrucción\)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  Esto le permite tratar los errores en tiempo de ejecución.  
  
### Matrices de caracteres  
 Un único carácter `Char` y una matriz de elementos `Char` se amplían a `String`.  Sin embargo, `String` no amplia a `Char()`.  Para convertir un valor `String` en una matriz `Char`, puede utilizar el método <xref:System.String.ToCharArray%2A> de la clase <xref:System.String?displayProperty=fullName>.  
  
### Valores sin sentido  
 En general, los valores `String` no tienen ningún sentido en otros tipos de datos y la conversión resulta muy artificial y peligrosa.  Siempre que sea posible, debe restringir el uso de variables `String` a las secuencias de caracteres para las que están diseñadas.  Nunca debería escribir código basándose en los valores equivalentes en otros tipos.  
  
## Vea también  
 [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Caracteres de tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Tipos de datos](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Uso eficiente de tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)