---
title: While...End While (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 87f6fbd6147b6dbfbe08c93e862d58b9868f9201
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352750"
---
# <a name="whileend-while-statement-visual-basic"></a>Instrucción While...End While (Visual Basic)
Ejecuta una serie de instrucciones siempre que se `True`una condición determinada.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
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
|`condition`|Obligatorio. `Boolean` expresión. Si `condition` es `Nothing`, Visual Basic lo trata como `False`.|  
|`statements`|Opcional. Una o más instrucciones que siguen `While`, que se ejecutan cada vez que se `True``condition`.|  
|`Continue While`|Opcional. Transfiere el control a la siguiente iteración del bloque `While`.|  
|`Exit While`|Opcional. Transfiere el control fuera del bloque `While`.|  
|`End While`|Obligatorio. Termina la definición del bloque `While`.|  
  
## <a name="remarks"></a>Comentarios  
 Use una estructura de `While...End While` cuando desee repetir un conjunto de instrucciones un número indefinido de veces, siempre que una condición permanezca `True`. Si desea más flexibilidad con el punto de prueba de la condición o el resultado para probarlo, puede que prefiera la [acción... Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md). Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser una mejor opción.  
  
> [!NOTE]
> La palabra clave `While` también se usa en la. [.. Instrucción Loop](../../../visual-basic/language-reference/statements/do-loop-statement.md), la [cláusula SKIP while](../../../visual-basic/language-reference/queries/skip-while-clause.md) y la [cláusula Take while](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Si `condition` se `True`, todos los `statements` ejecutan hasta que se encuentre la instrucción `End While`. A continuación, el control vuelve a la instrucción `While` y se comprueba de nuevo `condition`. Si `condition` todavía está `True`, se repite el proceso. Si es `False`, el control pasa a la instrucción que sigue a la instrucción `End While`.  
  
 La instrucción `While` siempre comprueba la condición antes de iniciar el bucle. El bucle continúa mientras la condición permanece `True`. Si `condition` se `False` la primera vez que se escribe el bucle, no se ejecuta ni siquiera una vez.  
  
 El `condition` suele ser el resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md) (`True` o `False`). Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean`.  
  
 Puede anidar `While` bucles colocando un bucle dentro de otro. También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Salir  
 La instrucción [Exit while](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar otra manera de salir de un bucle `While`. `Exit While` transfiere inmediatamente el control a la instrucción que sigue a la instrucción `End While`.  
  
 Normalmente se usa `Exit While` después de evaluar alguna condición (por ejemplo, en una estructura de `If...Then...Else`). Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización. Puede utilizar `Exit While` al probar una condición que podría provocar un *bucle sin fin*, que es un bucle que podría ejecutar un número muy grande o incluso infinito de veces. Después, puede usar `Exit While` para escapar el bucle.  
  
 Puede colocar cualquier número de instrucciones `Exit While` en cualquier parte del bucle `While`.  
  
 Cuando se utiliza en bucles `While` anidados, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.  
  
 La instrucción `Continue While` transfiere inmediatamente el control a la siguiente iteración del bucle. Para obtener más información, vea [instrucción continue](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la variable de `index` sea mayor que 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el uso de las instrucciones `Continue While` y `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se leen todas las líneas de un archivo de texto. El método <xref:System.IO.File.OpenText%2A> abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En la condición `While`, el método <xref:System.IO.StreamReader.Peek%2A> de la `StreamReader` determina si el archivo contiene caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de bucle](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop (instrucción)](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit (instrucción)](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue (instrucción)](../../../visual-basic/language-reference/statements/continue-statement.md)
