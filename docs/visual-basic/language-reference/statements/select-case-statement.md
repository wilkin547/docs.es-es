---
title: Instrucción Select...Case (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: f99db4f1dc224e5f75ee67ba94c3745f28438724
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814619"
---
# <a name="selectcase-statement-visual-basic"></a>Instrucción Select...Case (Visual Basic)
Ejecuta uno de varios grupos de instrucciones, dependiendo del valor de una expresión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|de esquema JSON|  
|---|---|  
|`testexpression`|Obligatorio. expresión. Se debe evaluar como uno de los tipos de datos básicos (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, y `UShort`).|  
|`expressionlist`|Necesario en un `Case` instrucción. Lista de cláusulas de expresiones que representan valores que coinciden para `testexpression`. Varias cláusulas de expresión se separan mediante comas. Cada cláusula puede tomar uno de los formatos siguientes:<br /><br /> -   *expression1* `To` *expression2*<br />-   [ `Is` ] *comparisonoperator* *expression*<br />-   *expression*<br /><br /> Use la `To` palabra clave para especificar los límites de un intervalo de coincidencia de los valores de `testexpression`. El valor de `expression1` debe ser menor o igual que el valor de `expression2`.<br /><br /> Use la `Is` palabra clave con un operador de comparación (`=`, `<>`, `<`, `<=`, `>`, o `>=`) para especificar una restricción en los valores coincidentes para `testexpression`. Si el `Is` palabra clave no se proporciona, se inserta automáticamente antes de *operadordecomparación*.<br /><br /> La forma de especificar solo `expression` se trata como un caso especial de la `Is` formar where *operadordecomparación* es el signo igual (`=`). Este formulario se evalúa como `testexpression`  =  `expression`.<br /><br /> Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se pueden convertir implícitamente al tipo de `testexpression` y adecuado `comparisonoperator` es válido para usarlo con los tipos de dos.|  
|`statements`|Opcional. Uno o más instrucciones que siguen `Case` que se ejecutarán si `testexpression` coincide con cualquier cláusula en `expressionlist`.|  
|`elsestatements`|Opcional. Uno o más instrucciones que siguen `Case Else` que se ejecutarán si `testexpression` no coincide con cualquier cláusula de la `expressionlist` de cualquiera de los `Case` instrucciones.|  
|`End Select`|Termina la definición de la `Select`... `Case` construcción.|  
  
## <a name="remarks"></a>Comentarios  
 Si `testexpression` coincide con cualquiera `Case` `expressionlist` cláusula, las instrucciones siguientes que `Case` instrucción ejecutarse la próxima `Case`, `Case Else`, o `End Select` instrucción. A continuación, el control pasa a la siguiente instrucción `End Select`. Si `testexpression` coincide con un `expressionlist` cláusula en más de una `Case` cláusula, sólo ejecutan las instrucciones siguientes en la primera coincidencia.  
  
 El `Case Else` instrucción se usa para presentar el `elsestatements` ejecutar si se encuentra ninguna coincidencia entre el `testexpression` y un `expressionlist` cláusula en cualquiera de los demás `Case` instrucciones. Aunque no es necesario, es una buena idea tener una `Case Else` instrucción en su `Select Case` construcción para controlar imprevistos `testexpression` valores. Si no hay ningún `Case` `expressionlist` coincide con la cláusula `testexpression` y no hay ningún `Case Else` instrucción, el control pasa a la instrucción que sigue `End Select`.  
  
 Se pueden utilizar varias expresiones o intervalos en cada `Case` cláusula. Por ejemplo, la siguiente línea es válida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
>  El `Is` palabra clave usada en el `Case` y `Case Else` instrucciones no es el mismo que el [operador Is](../../../visual-basic/language-reference/operators/is-operator.md), que se usa para la comparación de referencias de objeto.  
  
 Puede especificar intervalos y varias expresiones para las cadenas de caracteres. En el ejemplo siguiente, `Case` coincide con cualquier cadena que es exactamente igual que "manzanas", tiene un valor entre "otros frutos" y "soup" en orden alfabético o que contiene el mismo valor exacto que el valor actual de `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 La configuración de `Option Compare` puede afectar a las comparaciones de cadenas. En `Option Compare Text`, las cadenas "Manzanas" y "manzanas" se consideran iguales, pero en `Option Compare Binary`, no lo hacen.  
  
> [!NOTE]
>  Un `Case` instrucción con varias cláusulas puede exhiben un comportamiento conocido como *cortocircuitar*. Visual Basic evalúa las cláusulas de izquierda a derecha y, si uno produce una coincidencia con `testexpression`, no se evalúan las cláusulas restantes. Evaluación cortocircuitada puede mejorar el rendimiento, pero pueden producir resultados inesperados si se espera que todas las expresiones de `expressionlist` va a evaluar. Para obtener más información sobre la evaluación "cortocircuitada", consulte [expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Si el código dentro de un `Case` o `Case Else` bloque de instrucciones no necesita ejecutar más de las instrucciones del bloque, puede salir del bloque utilizando la `Exit Select` instrucción. Esto transfiere el control inmediatamente a la siguiente instrucción `End Select`.  
  
 `Select Case` las construcciones se pueden anidar. Cada uno anidado `Select Case` construcción debe tener su correspondiente `End Select` instrucción y debe estar completamente dentro de una sola `Case` o `Case Else` bloque de instrucciones de la exterior `Select Case` construcción en el que está anidada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un `Select Case` construcción para escribir una línea que corresponde al valor de la variable `number`. El segundo `Case` instrucción contiene el valor que coincida con el valor actual de `number`, por lo que la instrucción que escribe "entre 6 y 8, inclusive" se ejecuta.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
