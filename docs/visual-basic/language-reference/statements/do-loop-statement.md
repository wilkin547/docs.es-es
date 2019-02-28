---
title: Instrucción Do...Loop (Visual Basic)
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
ms.openlocfilehash: c7c7987508260a0181904feacf3782f66066309f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968210"
---
# <a name="doloop-statement-visual-basic"></a>Instrucción Do...Loop (Visual Basic)
Repite un bloque de instrucciones mientras una `Boolean` condición es `True` o hasta que la condición se convierte en `True`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
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
|`Do`|Obligatorio. Se inicia la definición de la `Do` bucle.|  
|`While`|Es necesario a menos que se use `Until`. Repita el bucle hasta que `condition` es `False`.|  
|`Until`|Es necesario a menos que se use `While`. Repita el bucle hasta que `condition` es `True`.|  
|`condition`|Opcional. `Boolean` expresión. Si `condition` es `Nothing`, Visual Basic lo trata como `False`.|  
|`statements`|Opcional. Una o varias instrucciones que se repiten mientras o hasta, `condition` es `True`.|  
|`Continue Do`|Opcional. Transfiere el control a la siguiente iteración de la `Do` bucle.|  
|`Exit Do`|Opcional. Transfiere el control fuera de la `Do` bucle.|  
|`Loop`|Obligatorio. Termina la definición de la `Do` bucle.|  
  
## <a name="remarks"></a>Comentarios  
 Use un `Do...Loop` estructura cuando desea repetir un conjunto de instrucciones un número indefinido de veces, hasta que se cumple una condición. Si desea repetir las instrucciones de un número determinado de veces, el [para... Instrucción Next](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una opción mejor.  
  
 Puede usar `While` o `Until` especificar `condition`, pero no ambos.  
  
 Puede probar `condition` solo una vez, al principio o al final del bucle. Si prueba `condition` al principio del bucle (en el `Do` instrucción), el bucle podría no ejecutarse incluso una vez. Si prueba al final del bucle (en el `Loop` instrucción), el bucle siempre ejecuta al menos una vez.  
  
 La condición normalmente da como resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúa como un [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valor (`True` o `False`). Esto incluye los valores de otros tipos de datos, como los tipos numéricos, que se han convertido a `Boolean`.  
  
 Puede anidar `Do` bucles colocando un bucle dentro de otro. También puede anidar diferentes tipos de estructuras de control entre sí. Para obtener más información, consulte [estructuras de Control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  El `Do...Loop` estructura le ofrece más flexibilidad que la [mientras... End (instrucción) mientras](../../../visual-basic/language-reference/statements/while-end-while-statement.md) porque permite decidir si desea finalizar el bucle cuando `condition` deja de estar `True` o cuando ésta sea primero `True`. Permite probar `condition` al principio o al final del bucle.  
  
## <a name="exit-do"></a>Exit Do  
 El [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) instrucción puede proporcionar una manera alternativa de salir de un `Do…Loop`. `Exit Do` transfiere el control inmediatamente a la instrucción que sigue la `Loop` instrucción.  
  
 `Exit Do` a menudo se usa después de evaluar alguna condición, por ejemplo en un `If...Then...Else` estructura. Es posible que desee salir de un bucle si detecta una condición que hace innecesario o imposible continuar la iteración, por ejemplo, un valor erróneo o una solicitud de finalización. Un uso de `Exit Do` consiste en probar una condición que podría provocar un *bucle sin fin*, que es un bucle que podría ejecutar un número grande o incluso infinito de veces. Puede usar `Exit Do` para salir del bucle.  
  
 Puede incluir cualquier número de `Exit Do` instrucciones en cualquier lugar en un `Do…Loop`.  
  
 Cuando se usan anidados dentro `Do` bucles, `Exit Do` transfiere el control fuera del bucle más interno y en el siguiente nivel más alto de anidamiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones en el bucle continúen ejecutándose hasta el `index` variable es mayor que 10. El `Until` cláusula es el final del bucle.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un `While` cláusula en lugar de un `Until` cláusula, y `condition` se prueba al principio del bucle en lugar de al final.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, `condition` detiene el bucle cuando la `index` variable es mayor que 100. El `If` instrucción del bucle, sin embargo, hace que el `Exit Do` instrucción para detener el bucle cuando la variable de índice es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente lee todas las líneas en un archivo de texto. El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En el `Do...Loop` condición, el <xref:System.IO.StreamReader.Peek%2A> método de la `StreamReader` determina si hay caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Vea también
- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While (instrucción)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
