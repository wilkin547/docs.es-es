---
description: 'Más información sobre: GoTo (instrucción)'
title: GoTo (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.GoTo
helpviewer_keywords:
- GoTo statement [Visual Basic]
- control flow [Visual Basic], branching
- unconditional branching [Visual Basic]
- branching [Visual Basic]
- branching [Visual Basic], unconditional
- branching [Visual Basic], conditional
- conditional statements [Visual Basic], GoTo statement
- GoTo statement [Visual Basic], syntax
ms.assetid: 313274c2-8ab3-4b9c-9ba3-0fd6798e4f6d
ms.openlocfilehash: 804baec130111562225b09cbdc7b5fb2d73adba5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769057"
---
# <a name="goto-statement"></a>GoTo (Instrucción)

Bifurca incondicionalmente a una línea especificada en un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
GoTo line  
```  
  
## <a name="part"></a>Parte  

 `line`  
 Necesario. Cualquier etiqueta de línea.  
  
## <a name="remarks"></a>Observaciones  

 La `GoTo` instrucción solo puede bifurcar a las líneas del procedimiento en el que aparece. La línea debe tener una etiqueta de línea que `GoTo` pueda hacer referencia a. Para obtener más información, vea [Cómo: etiquetar instrucciones](../../programming-guide/program-structure/how-to-label-statements.md).  
  
> [!NOTE]
> `GoTo` las instrucciones pueden hacer que el código sea difícil de leer y mantener. Siempre que sea posible, use una estructura de control en su lugar. Para más información, consulte [Control Flow](../../programming-guide/language-features/control-flow/index.md).  
  
 No se puede usar una `GoTo` instrucción para bifurcar desde fuera de `For` ... `Next` ,.. `For Each` . `Next` , `SyncLock` . `End SyncLock` . `Try` `Catch` .,... ... `Finally` , `With` ... `End With` o `Using` ... `End Using` en una etiqueta dentro de.  
  
## <a name="branching-and-try-constructions"></a>Bifurcación y construcciones try  

 Dentro de `Try` ... `Catch` ...`Finally` la construcción de, se aplican las siguientes reglas a la bifurcación con la `GoTo` instrucción.  
  
|Bloque o región|Bifurcación desde fuera|Bifurcar desde dentro|  
|---------------------|-------------------------------|-------------------------------|  
|`Try` sin|Solo desde un `Catch` bloque de la misma construcción <sup>1</sup>|Solo hacia fuera de la construcción completa|  
|`Catch` sin|Nunca permitido|Solo hacia fuera de la construcción completa o hasta el `Try` bloque de la misma construcción <sup>1</sup>|  
|`Finally` sin|Nunca permitido|Nunca permitido|  
  
 <sup>1</sup> si uno `Try` ... `Catch` ...`Finally` la construcción está anidada dentro de otra, un `Catch` bloque se puede bifurcar en el `Try` bloque en su propio nivel de anidamiento, pero no en ningún otro `Try` bloque. Una instrucción anidada `Try` ... `Catch` ...`Finally` la construcción debe estar contenida completamente en un `Try` `Catch` bloque o de la construcción en la que está anidada.  
  
 En la ilustración siguiente se muestra una `Try` construcción anidada dentro de otra. Varias ramas entre los bloques de las dos construcciones se indican como válidas o no válidas.  
  
 ![Diagrama gráfico de bifurcación en construcciones Try](./media/goto-statement/try-construction-branching.gif)  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa la `GoTo` instrucción para bifurcar a las etiquetas de línea de un procedimiento.  
  
 [!code-vb[VbVbalrStatements#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#31)]  
  
## <a name="see-also"></a>Vea también

- [Instrucción Do...Loop](do-loop-statement.md)
- [Instrucción For...Next](for-next-statement.md)
- [Instrucción For Each...Next](for-each-next-statement.md)
- [Instrucción If...Then...Else](if-then-else-statement.md)
- [Instrucción Select...Case](select-case-statement.md)
- [Try...Catch...Finally (instrucción)](try-catch-finally-statement.md)
- [Instrucción While...End While](while-end-while-statement.md)
- [Instrucción With...End With](with-end-with-statement.md)
