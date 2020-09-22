---
title: Instrucción Do...Loop
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
ms.openlocfilehash: 86a702aefeea1e5e359a579a3f29e9c06f1c619c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865926"
---
# <a name="doloop-statement-visual-basic"></a>Instrucción Do...Loop (Visual Basic)

Repite un bloque de instrucciones mientras una `Boolean` condición es `True` o hasta que la condición se convierte en `True` .  
  
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`Do`|Obligatorio. Inicia la definición del `Do` bucle.|  
|`While`|Es necesario a menos que se use `Until`. Repita el bucle hasta que `condition` sea `False` .|  
|`Until`|Es necesario a menos que se use `While`. Repita el bucle hasta que `condition` sea `True` .|  
|`condition`|Opcional. Expresión `Boolean`. Si `condition` es `Nothing` , Visual Basic lo trata como `False` .|  
|`statements`|Opcional. Una o varias instrucciones que se repiten mientras, o hasta, `condition` es `True` .|  
|`Continue Do`|Opcional. Transfiere el control a la siguiente iteración del `Do` bucle.|  
|`Exit Do`|Opcional. Transfiere el control fuera del `Do` bucle.|  
|`Loop`|Obligatorio. Finaliza la definición del `Do` bucle.|  
  
## <a name="remarks"></a>Comentarios  

 Use una `Do...Loop` estructura cuando desee repetir un conjunto de instrucciones un número indefinido de veces, hasta que se satisfaga una condición. Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](for-next-statement.md) suele ser una mejor opción.  
  
 Puede usar `While` o `Until` para especificar `condition` , pero no ambos.  
  
 Solo puede probar `condition` una vez, al principio o al final del bucle. Si realiza `condition` una prueba al principio del bucle (en la `Do` instrucción), el bucle podría no ejecutarse ni siquiera una vez. Si se prueba al final del bucle (en la `Loop` instrucción), el bucle siempre se ejecuta al menos una vez.  
  
 La condición suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../data-types/boolean-data-type.md) ( `True` o `False` ). Esto incluye los valores de otros tipos de datos, como los tipos numéricos, que se han convertido en `Boolean` .  
  
 Puede anidar `Do` bucles colocando un bucle dentro de otro. También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
> La `Do...Loop` estructura proporciona más flexibilidad que el [tiempo... End while](while-end-while-statement.md) , ya que permite decidir si finalizar el bucle cuando se `condition` detiene `True` o cuando se convierte por primera vez `True` . También permite realizar pruebas `condition` en el inicio o el final del bucle.  
  
## <a name="exit-do"></a>Salir  

 La instrucción [Exit do](exit-statement.md) puede proporcionar una manera alternativa de salir de un `Do…Loop` . `Exit Do` transfiere el control inmediatamente a la instrucción que sigue a la `Loop` instrucción.  
  
 `Exit Do` se suele usar después de evaluar alguna condición, por ejemplo en una `If...Then...Else` estructura. Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización. Un uso de `Exit Do` es para probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número de veces grande o incluso infinito. Puede usar `Exit Do` para escapar el bucle.  
  
 Puede incluir cualquier número de `Exit Do` instrucciones en cualquier parte de un `Do…Loop` .  
  
 Cuando se usa dentro de `Do` bucles anidados, `Exit Do` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la `index` variable es mayor que 10. La `Until` cláusula está al final del bucle.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se utiliza una `While` cláusula en lugar de una `Until` cláusula y `condition` se prueba al principio del bucle en lugar de al final.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, `condition` detiene el bucle cuando la `index` variable es mayor que 100. La `If` instrucción del bucle, sin embargo, hace que la `Exit Do` instrucción detenga el bucle cuando la variable de índice es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se leen todas las líneas de un archivo de texto. El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En la `Do...Loop` condición, el <xref:System.IO.StreamReader.Peek%2A> método de `StreamReader` determina si hay caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de bucle](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Instrucción For...Next](for-next-statement.md)
- [Tipo de datos Boolean](../data-types/boolean-data-type.md)
- [Estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Instrucción Exit](exit-statement.md)
- [Instrucción While...End While](while-end-while-statement.md)
