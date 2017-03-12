---
title: "Instrucci&#243;n Select...Case (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Select"
  - "vb.Case"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bifurcación, conditional"
  - "Case Else (instrucción), Select...Case"
  - "Case (instrucción)"
  - "Case (instrucción), Select...Case"
  - "instrucciones condicionales, Select Case"
  - "flujo de control, bifurcación"
  - "Else (palabra clave) [Visual Basic], en instrucciones Select...Case"
  - "End (palabra clave), Select Case (instrucciones)"
  - "ejecución, conditional"
  - "Is (operador) [Visual Basic], en instrucciones Select...Case"
  - "Select Case (instrucción), Select...Case"
  - "Select (instrucción)"
  - "Select (instrucción), Select...Case"
  - "Select...Case (instrucciones)"
  - "To (palabra clave), en instrucciones Select...Case"
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Instrucci&#243;n Select...Case (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ejecuta uno de varios grupos de instrucciones, según el valor de una expresión.  
  
## Sintaxis  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`testexpression`|Obligatorio.  Expresión.  Debe evaluarse en uno de los tipos de datos elementales \(`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong` y `UShort`\).|  
|`expressionlist`|Requerido en una instrucción `Case`.  Lista de cláusulas de expresiones que representan valores que coinciden para `testexpression`.  Las cláusulas de varias expresiones se separan mediante comas.  Cada cláusula puede tomar una de las siguientes formas:<br /><br /> -   *expression1* `To` *expression2*<br />-   \[ `Is` \] *comparisonoperator* *expression*<br />-   *expresión*<br /><br /> Utilice la palabra clave `To` para especificar los límites de un intervalo de valores que coinciden para `testexpression`.  El valor de `expression1` debe ser menor o igual que el valor de `expression2`.<br /><br /> Utilice la palabra clave `Is` con un operador de comparación \(`=`, `<>`, `<`, `<=`, `>` o `>=`\) para especificar una restricción de los valores coincidentes para `testexpression`.  Si no se escribe la palabra clave `Is`, se insertará automáticamente antes de *comparisonoperator*.<br /><br /> La forma que especifica únicamente `expression` se considera un caso especial de la forma `Is`, donde *comparisonoperator* es el signo igual \(`=`\).  Esta forma se evalúa como `testexpression` \= `expression`.<br /><br /> Las expresiones contenidas en `expressionlist` pueden ser de cualquier tipo de datos, siempre que sean implícitamente convertibles al tipo de `testexpression` y el correspondiente `comparisonoperator` sea válido para los dos tipos con los que se utilice.|  
|`statements`|Opcional.  Una o más instrucciones posteriores a `Case` que se ejecutan si `testexpression` coincide con cualquier cláusula de `expressionlist`.|  
|`elsestatements`|Opcional.  Una o más instrucciones posteriores a `Case Else` que se ejecutan si `testexpression` no coincide con ninguna cláusula de `expressionlist` de cualquiera de las instrucciones `Case`.|  
|`End Select`|Termina la definición la construcción `Select`...`Case`.|  
  
## Comentarios  
 Si `testexpression` coincide con cualquier cláusula de `Case` `expressionlist`, se ejecutan las instrucciones situadas a continuación de `Case` hasta la siguiente instrucción `Case`, `Case Else` o `End Select`.  El control pasa después a la instrucción que sigue a `End Select`.  Si `testexpression` coincide con una cláusula `expressionlist` en más de una cláusula `Case`, sólo se ejecutan las instrucciones situadas después de la primera coincidencia.  
  
 La instrucción `Case Else` se utiliza para introducir las `elsestatements` que se deben ejecutar si no se encuentra ninguna coincidencia entre las cláusulas `testexpression` y `expressionlist` de cualquiera de las demás instrucciones `Case`.  Aunque no es necesario, es aconsejable tener una instrucción `Case Else` en su construcción `Select Case` para controlar los valores `testexpression` imprevistos.  Si no coincide ninguna cláusula `Case` `expressionlist` con `testexpression` y no hay ninguna instrucción `Case Else`, el control pasa a la instrucción `End Select` siguiente.  
  
 Se pueden utilizar varias expresiones o intervalos en cada cláusula `Case`.  Por ejemplo, la línea siguiente es válida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  La palabra clave `Is` utilizada en las instrucciones `Case` y `Case Else` no es igual que [Is \(Operador\)](../../../visual-basic/language-reference/operators/is-operator.md), que se utiliza para la comparación de referencias a objetos.  
  
 Puede especificar intervalos y varias expresiones para cadenas de caracteres.  En el ejemplo siguiente, `Case` coincide con cualquier cadena que sea exactamente igual a "apples", tenga un valor comprendido entre "nuts" y "soup" en orden alfabético, o contenga el mismo valor exacto que el valor actual de `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 El valor de `Option Compare` puede afectar a las comparaciones de cadenas.  Bajo `Option Compare Text`, las cadenas "Apples" y "apples" se comparan como iguales, pero no bajo `Option Compare Binary`.  
  
> [!NOTE]
>  Una instrucción `Case` con varias cláusulas puede exhibir el comportamiento conocido como *cortocircuitar*.  Visual Basic evalúa las cláusulas de izquierda a derecha y, si una de ellas coincide con `testexpression`, no se evalúan las cláusulas restantes.  El procedimiento de cortocircuitar puede mejorar el rendimiento, pero puede generar resultados inesperados si está esperando que se evalúen todas las expresiones de `expressionlist`.  Para obtener más información sobre cómo cortocircuitar, vea [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Si el código contenido en un bloque de instrucciones `Case` o `Case Else` no necesita ejecutar más instrucciones contenidas en el bloque, puede salir del bloque utilizando la instrucción `Exit Select`.  Esto transfiere inmediatamente el control a la instrucción que sigue a `End Select`.  
  
 Las construcciones `Select Case` se pueden anidar.  Cada construcción `Select Case` anidada debe tener una instrucción `End Select` coincidente y estar completamente contenida dentro de un único bloque de instrucción `Case` o `Case Else` de la construcción `Select Case` más exterior dentro de la cual está anidada.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza una construcción `Select Case` para escribir una línea correspondiente al valor de la variable `number`.  La segunda instrucción `Case` contiene el valor que coincide con el valor actual de `number`, por lo que se ejecuta la instrucción que escribe "Between 6 and 8, inclusive".  
  
 [!code-vb[VbVbalrStatements#54](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/select-case-statement_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Interaction.Choose%2A>   
 [End \(Instrucción\)](../../../visual-basic/language-reference/statements/end-statement.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)