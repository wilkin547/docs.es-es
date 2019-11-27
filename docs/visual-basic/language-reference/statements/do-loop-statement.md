---
title: Do...Loop (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 9384cbb355189be448fa4b8d274721b4a7ca6a20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351256"
---
# <a name="doloop-statement-visual-basic"></a>Instrucción Do...Loop (Visual Basic)
Repite un bloque de instrucciones mientras se `True` una condición `Boolean` o hasta que la condición se `True`.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`Do`|Obligatorio. Inicia la definición del bucle `Do`.|  
|`While`|Es necesario a menos que se use `Until`. Repita el bucle hasta que se `False``condition`.|  
|`Until`|Es necesario a menos que se use `While`. Repita el bucle hasta que se `True``condition`.|  
|`condition`|Opcional. `Boolean` expresión. Si `condition` es `Nothing`, Visual Basic lo trata como `False`.|  
|`statements`|Opcional. Una o varias instrucciones que se repiten mientras, o hasta, se `True``condition`.|  
|`Continue Do`|Opcional. Transfiere el control a la siguiente iteración del bucle `Do`.|  
|`Exit Do`|Opcional. Transfiere el control fuera del bucle `Do`.|  
|`Loop`|Obligatorio. Finaliza la definición del bucle `Do`.|  
  
## <a name="remarks"></a>Comentarios  
 Use una estructura de `Do...Loop` cuando desee repetir un conjunto de instrucciones un número indefinido de veces, hasta que se satisfaga una condición. Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una mejor opción.  
  
 Puede usar `While` o `Until` para especificar `condition`, pero no ambos.  
  
 Solo puede probar `condition` una vez, al principio o al final del bucle. Si prueba `condition` al principio del bucle (en la instrucción `Do`), es posible que el bucle no se ejecute incluso una vez. Si realiza una prueba al final del bucle (en la instrucción `Loop`), el bucle siempre se ejecuta al menos una vez.  
  
 La condición suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`). Esto incluye los valores de otros tipos de datos, como los tipos numéricos, que se han convertido en `Boolean`.  
  
 Puede anidar `Do` bucles colocando un bucle dentro de otro. También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> La estructura de `Do...Loop` proporciona más flexibilidad que el [tiempo... End while](../../../visual-basic/language-reference/statements/while-end-while-statement.md) , ya que permite decidir si finalizar el bucle cuando `condition` deja de `True` o cuando se convierte por primera vez en `True`. También le permite probar `condition` al principio o al final del bucle.  
  
## <a name="exit-do"></a>Salir  
 La instrucción [Exit do](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar una manera alternativa de salir de un `Do…Loop`. `Exit Do` transfiere el control inmediatamente a la instrucción que sigue a la instrucción `Loop`.  
  
 a menudo se usa `Exit Do` después de evaluar alguna condición, por ejemplo en una estructura de `If...Then...Else`. Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización. Un uso de `Exit Do` es probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número de veces grande o incluso infinito. Puede usar `Exit Do` para escapar el bucle.  
  
 Puede incluir cualquier número de instrucciones `Exit Do` en cualquier parte de un `Do…Loop`.  
  
 Cuando se utiliza en bucles `Do` anidados, `Exit Do` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la variable de `index` sea mayor que 10. La cláusula `Until` está al final del bucle.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza una cláusula `While` en lugar de una cláusula `Until` y `condition` se prueba al principio del bucle en lugar de al final.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `condition` detiene el bucle cuando la variable de `index` es mayor que 100. Sin embargo, la instrucción `If` del bucle hace que la instrucción `Exit Do` detenga el bucle cuando la variable de índice sea mayor que 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se leen todas las líneas de un archivo de texto. El método <xref:System.IO.File.OpenText%2A> abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En la condición `Do...Loop`, el método <xref:System.IO.StreamReader.Peek%2A> de la `StreamReader` determina si hay caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
