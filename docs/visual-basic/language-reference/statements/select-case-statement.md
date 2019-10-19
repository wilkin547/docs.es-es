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
ms.openlocfilehash: d035118febc5ea9d1ea8e5cc0145cb030626b030
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583253"
---
# <a name="selectcase-statement-visual-basic"></a>Instrucción Select...Case (Visual Basic)
Ejecuta uno de varios grupos de instrucciones, dependiendo del valor de una expresión.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
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
|`testexpression`|Requerido. Expresiones. Debe evaluarse como uno de los tipos de datos básicos (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, 0, 1, 2 , 3, 4 y 5).|  
|`expressionlist`|Obligatorio en una instrucción `Case`. Lista de cláusulas de expresión que representan los valores de coincidencia para `testexpression`. Las cláusulas de varias expresiones se separan mediante comas. Cada cláusula puede adoptar uno de los siguientes formatos:<br /><br /> -   *expression1* `To` *expresión2*<br />-[`Is`] *expresión* comparisonoperator<br />-   *expresión* )<br /><br /> Use la palabra clave `To` para especificar los límites de un intervalo de valores coincidentes para `testexpression`. El valor de `expression1` debe ser menor o igual que el valor de `expression2`.<br /><br /> Use la palabra clave `Is` con un operador de comparación (`=`, `<>`, `<`, `<=`, `>` o `>=`) para especificar una restricción en los valores de coincidencia de `testexpression`. Si no se proporciona la palabra clave `Is`, se inserta automáticamente antes de *comparisonoperator*.<br /><br /> La forma que especifica solo `expression` se trata como un caso especial del `Is` formulario donde *comparisonoperator* es el signo igual (`=`). Este formulario se evalúa como `testexpression`  =  `expression`.<br /><br /> Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se puedan convertir implícitamente al tipo de `testexpression` y el `comparisonoperator` adecuado sea válido para los dos tipos con los que se usa.|  
|`statements`|Opcional. Una o más instrucciones que siguen `Case` que se ejecutan si `testexpression` coincide con cualquier cláusula de `expressionlist`.|  
|`elsestatements`|Opcional. Una o más instrucciones que siguen `Case Else` que se ejecutan si `testexpression` no coincide con ninguna cláusula en el `expressionlist` de cualquiera de las instrucciones de `Case`.|  
|`End Select`|Finaliza la definición de la `Select`... construcción de `Case`.|  
  
## <a name="remarks"></a>Comentarios  
 Si `testexpression` coincide con cualquier cláusula `Case` `expressionlist`, las instrucciones que siguen a esa instrucción `Case` se ejecutan hasta la siguiente instrucción `Case`, `Case Else` o `End Select`. A continuación, el control pasa a la instrucción siguiente `End Select`. Si `testexpression` coincide con una cláusula de `expressionlist` en más de una cláusula `Case`, solo se ejecutan las instrucciones que siguen a la primera coincidencia.  
  
 La instrucción `Case Else` se utiliza para introducir el `elsestatements` que se va a ejecutar si no se encuentra ninguna coincidencia entre el `testexpression` y una cláusula `expressionlist` en cualquiera de las otras instrucciones `Case`. Aunque no es necesario, es una buena idea tener una `Case Else` instrucción en la construcción de `Select Case` para administrar valores de `testexpression` imprevistos. Si ninguna cláusula de `expressionlist` de `Case` coincide con `testexpression` y no hay ninguna instrucción `Case Else`, el control pasa a la instrucción siguiente a `End Select`.  
  
 Puede usar varias expresiones o intervalos en cada cláusula de `Case`. Por ejemplo, la siguiente línea es válida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La palabra clave `Is` utilizada en las instrucciones `Case` y `Case Else` no es igual que el [operador is](../../../visual-basic/language-reference/operators/is-operator.md), que se utiliza para la comparación de referencias de objetos.  
  
 Puede especificar intervalos y varias expresiones para las cadenas de caracteres. En el ejemplo siguiente, `Case` coincide con cualquier cadena que sea exactamente igual a "manzanas", tiene un valor entre "NUTS" y "sopa" en orden alfabético, o contiene el mismo valor exacto que el valor actual de `testItem`.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 La configuración de `Option Compare` puede afectar a las comparaciones de cadenas. En `Option Compare Text`, las cadenas "manzanas" y "manzanas" se comparan como iguales, pero en `Option Compare Binary` no lo hacen.  
  
> [!NOTE]
> Una instrucción `Case` con varias cláusulas puede presentar un comportamiento conocido como *cortocircuito*. Visual Basic evalúa las cláusulas de izquierda a derecha y, si una genera una coincidencia con `testexpression`, no se evalúan las cláusulas restantes. El cortocircuito puede mejorar el rendimiento, pero puede producir resultados inesperados si espera que se evalúen todas las expresiones de `expressionlist`. Para obtener más información sobre el cortocircuito, vea [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Si el código de un bloque de instrucciones `Case` o `Case Else` no necesita ejecutar más instrucciones en el bloque, puede salir del bloque mediante la instrucción `Exit Select`. Esto transfiere el control inmediatamente a la instrucción siguiente `End Select`.  
  
 `Select Case` construcciones se pueden anidar. Cada construcción de `Select Case` anidada debe tener una instrucción `End Select` coincidente y debe estar dentro de un único bloque de instrucciones `Case` o `Case Else` de la construcción de `Select Case` externa en la que está anidada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa una construcción `Select Case` para escribir una línea que se corresponda con el valor de la variable `number`. La segunda instrucción `Case` contiene el valor que coincide con el valor actual de `number`, por lo que la instrucción que escribe "between 6 and 8, inclusive" se ejecuta.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
