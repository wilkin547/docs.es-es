---
title: Instrucción While...End While (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 9f46a6ec65faef4448bdd25e30a6cc0c605cd0f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604736"
---
# <a name="whileend-while-statement-visual-basic"></a>Instrucción While...End While (Visual Basic)
Ejecuta una serie de instrucciones mientras una condición determinada es `True`.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`condition`|Requerido. `Boolean` Expresión. Si `condition` es `Nothing`, Visual Basic lo trata como `False`.|  
|`statements`|Opcional. Uno o más instrucciones que siguen `While`, que ejecutará cada vez `condition` es `True`.|  
|`Continue While`|Opcional. Transfiere el control a la siguiente iteración de la `While` bloque.|  
|`Exit While`|Opcional. Transfiere el control fuera de la `While` bloque.|  
|`End While`|Requerido. Termina la definición del bloque `While`.|  
  
## <a name="remarks"></a>Comentarios  
 Use un `While...End While` cuando desea repetir un conjunto de instrucciones un número indefinido de veces, siempre que una condición de la estructura `True`. Si desea más flexibilidad con en el que probar la condición o resultado para el que la prueba, es preferible el [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md). Si desea repetir las instrucciones un número determinado de veces, el [para... Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una opción mejor.  
  
> [!NOTE]
>  El `While` también se utiliza la palabra clave en el [hacer... Instrucción de bucle](../../../visual-basic/language-reference/statements/do-loop-statement.md), el [omitir While (cláusula)](../../../visual-basic/language-reference/queries/skip-while-clause.md) y [Take While cláusula](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Si `condition` es `True`, todos los de la `statements` ejecución hasta que el `End While` se encuentra la instrucción. Controlar, a continuación, vuelve a la `While` (instrucción), y `condition` se comprueba de nuevo. Si `condition` sigue siendo `True`, el proceso se repite. Si tiene `False`, control pasa a la instrucción que sigue a la `End While` instrucción.  
  
 El `While` instrucción siempre comprueba la condición antes de iniciar el bucle. Ejecución en bucle continúa mientras la condición siga siendo `True`. Si `condition` es `False` cuando se escriben por primera vez el bucle, no ejecute ni siquiera una vez.  
  
 El `condition` normalmente los resultados de una comparación de dos valores, pero pueden ser cualquier expresión que se evalúa como un [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) valor (`True` o `False`). Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean`.  
  
 Puede anidar `While` bucles, colocando un bucle dentro de otra. También puede anidar diferentes tipos de estructuras de control entre sí. Para obtener más información, consulte [estructuras de Control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Salida al  
 El [salir mientras](../../../visual-basic/language-reference/statements/exit-statement.md) instrucción puede proporcionan otra forma de salir de un `While` bucle. `Exit While` transfiere el control a la instrucción que sigue inmediatamente el `End While` instrucción.  
  
 Se suele usar `Exit While` después de evaluar alguna condición (por ejemplo, en un `If...Then...Else` estructura). Puede salir de un bucle si detecta una condición que hace innecesario o imposible continuar la iteración, como puede ser un valor erróneo o una solicitud de finalización. Puede usar `Exit While` cuando se prueba una condición que podría provocar un *bucle sin fin*, que es un bucle que pueda ejecutar un número muy grande o incluso infinito de veces. A continuación, puede usar `Exit While` para salir del bucle.  
  
 Puede colocar cualquier número de `Exit While` instrucciones en cualquier lugar en el `While` bucle.  
  
 Cuando se usa en anidados `While` bucles, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel más alto de anidamiento.  
  
 El `Continue While` instrucción transfiere el control inmediatamente a la siguiente iteración del bucle. Para obtener más información, consulte [instrucción Continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones en el bucle continúen ejecutándose hasta el `index` variable es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el uso de la `Continue While` y `Exit While` las instrucciones.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se lee todas sus líneas en un archivo de texto. El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En el `While` condición, el <xref:System.IO.StreamReader.Peek%2A> método de la `StreamReader` determina si el archivo contiene caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/while-end-while-statement_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)  
 [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Continue (instrucción)](../../../visual-basic/language-reference/statements/continue-statement.md)
