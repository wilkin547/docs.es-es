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
ms.openlocfilehash: 627318677270ba4ffa8ee430febea7ddf83bd245
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957662"
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
  
|Término|Definición|  
|---|---|  
|`testexpression`|Necesario. Expresiones. Debe evaluarse como uno de los tipos de datos`Boolean`básicos `Byte`( `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`,,, `Single`, ,`String` ,`ULong`y). `UInteger` `UShort`|  
|`expressionlist`|Obligatorio en una `Case` instrucción. Lista de cláusulas de expresión que representan los `testexpression`valores de coincidencia para. Las cláusulas de varias expresiones se separan mediante comas. Cada cláusula puede adoptar uno de los siguientes formatos:<br /><br /> -   *expression1* `To` *expresión2*<br />-[ `Is` ] *expresión* de comparisonoperator<br />-   *Expresiones*<br /><br /> Use la `To` palabra clave para especificar los límites de un intervalo de valores de `testexpression`coincidencia para. El valor de `expression1` debe ser menor o igual que el valor de. `expression2`<br /><br /> Use la `Is` palabra clave con un operador de`=`comparación `<>`( `<`, `<=`, `>`,, `>=`o) para especificar una restricción en los valores de `testexpression`coincidencia para. Si no `Is` se proporciona la palabra clave, se inserta automáticamente antes de *comparisonoperator*.<br /><br /> La forma que especifica solo `expression` se trata como un caso especial `Is` del formulario donde *comparisonoperator* es el signo igual (`=`). Este formulario se evalúa como `testexpression`.  =  `expression`<br /><br /> Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se puedan convertir implícitamente al tipo `testexpression` de y el `comparisonoperator` adecuado sea válido para los dos tipos con los que se usa.|  
|`statements`|Opcional. Una o más instrucciones que `Case` siguen a que `testexpression` se ejecutan si `expressionlist`coincide con cualquier cláusula de.|  
|`elsestatements`|Opcional. Una o varias instrucciones que `Case Else` siguen a que `testexpression` se ejecutan si no `expressionlist` coinciden con ninguna cláusula en `Case` de cualquiera de las instrucciones.|  
|`End Select`|Finaliza la definición de `Select`... `Case` construcción.|  
  
## <a name="remarks"></a>Comentarios  
 Si `testexpression` coincide con `Case` cualquier `Case` `Case` `End Select` `Case Else`cláusula, las instrucciones que siguen a esa instrucción se ejecutan hasta la siguiente instrucción, o. `expressionlist` A continuación, el control pasa a `End Select`la instrucción que sigue a. Si `testexpression` coincide con `expressionlist` una cláusula en más de `Case` una cláusula, solo se ejecutan las instrucciones que siguen a la primera coincidencia.  
  
 La `Case Else` instrucción se utiliza para `elsestatements` introducir para que se ejecute si no se `expressionlist` encuentra ninguna coincidencia `testexpression` entre las cláusulas y en cualquiera de `Case` las demás instrucciones. Aunque no es necesario, es una buena idea tener una `Case Else` instrucción en la `Select Case` construcción `testexpression` para administrar los valores imprevistos. Si ninguna `Case` `Case Else` `End Select`cláusula coincide `testexpression` y no hay ninguna instrucción, el control pasa a la instrucción que sigue a. `expressionlist`  
  
 Puede usar varias expresiones o intervalos en cada `Case` cláusula. Por ejemplo, la siguiente línea es válida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La `Is` palabra clave usada en `Case` las `Case Else` instrucciones y no es igual que el [operador is](../../../visual-basic/language-reference/operators/is-operator.md), que se usa para la comparación de referencia de objeto.  
  
 Puede especificar intervalos y varias expresiones para las cadenas de caracteres. En el ejemplo siguiente, `Case` coincide con cualquier cadena que sea exactamente igual a "manzanas", tiene un valor entre "NUTS" y "sopa" en orden alfabético, o contiene el mismo valor exacto que el valor actual `testItem`de.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 La configuración de `Option Compare` puede afectar a las comparaciones de cadenas. En `Option Compare Text`, las cadenas "manzanas" y "manzanas" se comparan como iguales `Option Compare Binary`, pero en, no.  
  
> [!NOTE]
> Una `Case` instrucción con varias cláusulas puede presentar un comportamiento conocidocomo cortocircuito. Visual Basic evalúa las cláusulas de izquierda a derecha y, si una genera una coincidencia con `testexpression`, no se evalúan las cláusulas restantes. El cortocircuito puede mejorar el rendimiento, pero puede producir resultados inesperados si espera que se evalúen `expressionlist` todas las expresiones de. Para obtener más información sobre el cortocircuito, vea [Expresiones booleanas](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Si el código dentro de `Case` un `Case Else` bloque de instrucciones o no necesita ejecutar más instrucciones en el bloque, puede salir del bloque mediante la `Exit Select` instrucción. Esto transfiere el control inmediatamente a la instrucción `End Select`que sigue a.  
  
 `Select Case`las construcciones se pueden anidar. Cada `Select Case` construcción anidada debe tener una instrucción `End Select` coincidente y debe estar contenida completamente dentro de `Case` un `Case Else` único bloque de instrucciones o `Select Case` de la construcción externa en la que está anidada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Select Case` usa una construcción para escribir una línea que se corresponde con el `number`valor de la variable. La segunda `Case` instrucción contiene el valor que coincide con el valor actual `number`de, por lo que se ejecuta la instrucción que escribe "between 6 and 8, inclusive".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End (instrucción)](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else (instrucción)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
