---
title: Instrucción While...End While
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: e3ab95f43e101a9ad8abe6fa61b94ae7542e409c
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869475"
---
# <a name="whileend-while-statement-visual-basic"></a>Instrucción While...End While (Visual Basic)

Ejecuta una serie de instrucciones siempre que una condición determinada sea `True` .  
  
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`condition`|Obligatorio. Expresión `Boolean`. Si `condition` es `Nothing` , Visual Basic lo trata como `False` .|  
|`statements`|Opcional. Una o varias instrucciones siguientes `While` , que se ejecutan cada vez `condition` `True` .|  
|`Continue While`|Opcional. Transfiere el control a la siguiente iteración del `While` bloque.|  
|`Exit While`|Opcional. Transfiere el control fuera del `While` bloque.|  
|`End While`|Obligatorio. Termina la definición del bloque `While`.|  
  
## <a name="remarks"></a>Comentarios  

 Use una `While...End While` estructura cuando desee repetir un conjunto de instrucciones un número indefinido de veces, siempre y cuando se mantenga una condición `True` . Si desea más flexibilidad con el punto de prueba de la condición o el resultado para probarlo, puede que prefiera la [acción... Instrucción Loop](do-loop-statement.md). Si desea repetir las instrucciones un número establecido de veces, la instrucción [for... La siguiente instrucción](for-next-statement.md) suele ser una mejor opción.  
  
> [!NOTE]
> La `While` palabra clave también se usa en la. [.. Instrucción Loop](do-loop-statement.md), la [cláusula SKIP while](../queries/skip-while-clause.md) y la [cláusula Take while](../queries/take-while-clause.md).  
  
 Si `condition` es `True` , todos los se `statements` ejecutan hasta que `End While` se encuentra la instrucción. A continuación, el control vuelve a la `While` instrucción y `condition` se comprueba de nuevo. Si `condition` todavía está `True` , el proceso se repite. Si es `False` , el control pasa a la instrucción que sigue a la `End While` instrucción.  
  
 La `While` instrucción siempre comprueba la condición antes de iniciar el bucle. El bucle continúa mientras se mantiene la condición `True` . Si `condition` es `False` la primera vez que se escribe el bucle, no se ejecuta ni siquiera una vez.  
  
 Normalmente es el `condition` resultado de una comparación de dos valores, pero puede ser cualquier expresión que se evalúe como un valor de [tipo de datos booleano](../data-types/boolean-data-type.md) ( `True` o `False` ). Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, que se ha convertido en `Boolean` .  
  
 Puede anidar `While` bucles colocando un bucle dentro de otro. También puede anidar distintos tipos de estructuras de control entre sí. Para obtener más información, vea [estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-while"></a>Salir  

 La instrucción [Exit while](exit-statement.md) puede proporcionar otra manera de salir de un `While` bucle. `Exit While` transfiere inmediatamente el control a la instrucción que sigue a la `End While` instrucción.  
  
 Normalmente se utiliza `Exit While` después de evaluar alguna condición (por ejemplo, en una `If...Then...Else` estructura). Es posible que desee salir de un bucle si detecta una condición que hace que sea innecesario o imposible continuar la iteración, como un valor erróneo o una solicitud de finalización. Puede usar `Exit While` al probar una condición que podría provocar un *bucle interminable*, que es un bucle que podría ejecutar un número muy grande o incluso infinito de veces. Después, puede usar `Exit While` para escapar el bucle.  
  
 Puede colocar cualquier número de `Exit While` instrucciones en cualquier parte del `While` bucle.  
  
 Cuando se usa dentro de `While` bucles anidados, `Exit While` transfiere el control fuera del bucle más interno y en el siguiente nivel superior de anidamiento.  
  
 La `Continue While` instrucción transfiere inmediatamente el control a la siguiente iteración del bucle. Para obtener más información, vea [instrucción continue](continue-statement.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la `index` variable es mayor que 10.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se muestra el uso de `Continue While` las `Exit While` instrucciones y.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se leen todas las líneas de un archivo de texto. El <xref:System.IO.File.OpenText%2A> método abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres. En la `While` condición, el <xref:System.IO.StreamReader.Peek%2A> método de `StreamReader` determina si el archivo contiene caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de bucle](../../programming-guide/language-features/control-flow/loop-structures.md)
- [Instrucción Do...Loop](do-loop-statement.md)
- [Instrucción For...Next](for-next-statement.md)
- [Tipo de datos Boolean](../data-types/boolean-data-type.md)
- [Estructuras de control anidadas](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Instrucción Exit](exit-statement.md)
- [Continue (instrucción)](continue-statement.md)
