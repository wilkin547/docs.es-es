---
title: Instrucción Select...Case
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
ms.openlocfilehash: 750e765390ad223976b000fe64e656fa2d62a34b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871779"
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`testexpression`|Obligatorio. Expresión. Debe evaluarse como uno de los tipos de datos básicos ( `Boolean` , `Byte` , `Char` , `Date` , `Double` , `Decimal` , `Integer` , `Long` , `Object` , `SByte` , `Short` ,,,, `Single` `String` `UInteger` `ULong` y `UShort` ).|  
|`expressionlist`|Obligatorio en una `Case` instrucción. Lista de cláusulas de expresión que representan los valores de coincidencia para `testexpression` . Las cláusulas de varias expresiones se separan mediante comas. Cada cláusula puede adoptar uno de los siguientes formatos:<br /><br /> -   *expression1* `To` *expresión2*<br />-[ `Is` ] *comparisonoperator* *expresión* de comparisonoperator<br />-   *Expresiones*<br /><br /> Use la `To` palabra clave para especificar los límites de un intervalo de valores de coincidencia para `testexpression` . El valor de `expression1` debe ser menor o igual que el valor de `expression2` .<br /><br /> Use la `Is` palabra clave con un operador de comparación ( `=` , `<>` , `<` , `<=` , `>` o `>=` ) para especificar una restricción en los valores de coincidencia para `testexpression` . Si `Is` no se proporciona la palabra clave, se inserta automáticamente antes de *comparisonoperator*.<br /><br /> La forma que especifica solo `expression` se trata como un caso especial del `Is` formulario donde *comparisonoperator* es el signo igual ( `=` ). Este formulario se evalúa como `testexpression`  =  `expression` .<br /><br /> Las expresiones de `expressionlist` pueden ser de cualquier tipo de datos, siempre que se puedan convertir implícitamente al tipo de `testexpression` y el adecuado `comparisonoperator` sea válido para los dos tipos con los que se usa.|  
|`statements`|Opcional. Una o más instrucciones que siguen a `Case` que se ejecutan si `testexpression` coincide con cualquier cláusula de `expressionlist` .|  
|`elsestatements`|Opcional. Una o varias instrucciones que siguen a `Case Else` que se ejecutan si no `testexpression` coinciden con ninguna cláusula en `expressionlist` de cualquiera de las `Case` instrucciones.|  
|`End Select`|Finaliza la definición de la `Select` construcción... `Case` .|  
  
## <a name="remarks"></a>Comentarios  

 Si `testexpression` coincide con cualquier `Case` `expressionlist` cláusula, las instrucciones que siguen `Case` a esa instrucción se ejecutan hasta la siguiente `Case` `Case Else` instrucción, o `End Select` . A continuación, el control pasa a la instrucción que sigue a `End Select` . Si `testexpression` coincide con una `expressionlist` cláusula en más de una `Case` cláusula, solo se ejecutan las instrucciones que siguen a la primera coincidencia.  
  
 La `Case Else` instrucción se utiliza para introducir `elsestatements` para que se ejecute si no se encuentra ninguna coincidencia entre las `testexpression` `expressionlist` cláusulas y en cualquiera de las demás `Case` instrucciones. Aunque no es necesario, es una buena idea tener una `Case Else` instrucción en la `Select Case` construcción para administrar los valores imprevistos `testexpression` . Si ninguna `Case` `expressionlist` cláusula coincide `testexpression` y no hay ninguna `Case Else` instrucción, el control pasa a la instrucción que sigue a `End Select` .  
  
 Puede usar varias expresiones o intervalos en cada `Case` cláusula. Por ejemplo, la siguiente línea es válida.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> La `Is` palabra clave usada en `Case` las `Case Else` instrucciones y no es igual que el [operador is](../operators/is-operator.md), que se usa para la comparación de referencia de objeto.  
  
 Puede especificar intervalos y varias expresiones para las cadenas de caracteres. En el ejemplo siguiente, `Case` coincide con cualquier cadena que sea exactamente igual a "manzanas", tiene un valor entre "NUTS" y "sopa" en orden alfabético, o contiene el mismo valor exacto que el valor actual de `testItem` .  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 La configuración de `Option Compare` puede afectar a las comparaciones de cadenas. En `Option Compare Text` , las cadenas "manzanas" y "manzanas" se comparan como iguales, pero en `Option Compare Binary` , no.  
  
> [!NOTE]
> Una `Case` instrucción con varias cláusulas puede presentar un comportamiento conocido como *cortocircuito*. Visual Basic evalúa las cláusulas de izquierda a derecha y, si una genera una coincidencia con `testexpression` , no se evalúan las cláusulas restantes. El cortocircuito puede mejorar el rendimiento, pero puede producir resultados inesperados si espera que se evalúen todas las expresiones de `expressionlist` . Para obtener más información sobre el cortocircuito, vea [Expresiones booleanas](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).  
  
 Si el código dentro de `Case` un `Case Else` bloque de instrucciones o no necesita ejecutar más instrucciones en el bloque, puede salir del bloque mediante la `Exit Select` instrucción. Esto transfiere el control inmediatamente a la instrucción que sigue a `End Select` .  
  
 `Select Case` las construcciones se pueden anidar. Cada construcción anidada `Select Case` debe tener una `End Select` instrucción coincidente y debe estar contenida completamente dentro de un único `Case` `Case Else` bloque de instrucciones o de la `Select Case` construcción externa en la que está anidada.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa una `Select Case` construcción para escribir una línea que se corresponde con el valor de la variable `number` . La segunda `Case` instrucción contiene el valor que coincide con el valor actual de `number` , por lo que se ejecuta la instrucción que escribe "between 6 and 8, inclusive".  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End (Instrucción)](end-statement.md)
- [Instrucción If...Then...Else](if-then-else-statement.md)
- [Option Compare (instrucción)](option-compare-statement.md)
- [Instrucción Exit](exit-statement.md)
