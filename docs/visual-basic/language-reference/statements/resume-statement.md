---
title: Resume (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: 1d03f631893be51529f29af824de0d684bf43804
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="resume-statement"></a>Resume (Instrucción)
Reanuda la ejecución una vez finalizada una rutina de control de errores.  
  
 Se recomienda que utilice el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control estructurado de excepciones y el `On Error` y `Resume` las instrucciones. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Elementos  
 `Resume`  
 Requerido. Si el error se produjo en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción que produjo el error. Si el error se produjo en un procedimiento llamado, la ejecución se reanuda en la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores.  
  
 `Next`  
 Opcional. Si el error se produjo en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que produjo el error. Si el error se produjo en un procedimiento llamado, la ejecución continúa con la instrucción inmediatamente posterior a la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).  
  
 `line`  
 Opcional. La ejecución se reanuda en la línea especificada en la sección necesario `line` argumento. El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Se recomienda que use el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control estructurado de excepciones y el `On Error` y `Resume` las instrucciones. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
 Si utiliza un `Resume` instrucción en cualquier lugar distinto en una rutina de control de errores, que se produce un error.  
  
 El `Resume` no se puede usar la instrucción en un procedimiento que contenga una `Try...Catch...Finally` instrucción.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `Resume` instrucción que se debe terminar en un procedimiento de control de errores y, a continuación, reanudar la ejecución con la instrucción que produjo el error. Se genera el error número 55 para ilustrar el uso de la `Resume` instrucción.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Error (instrucción)](../../../visual-basic/language-reference/statements/error-statement.md)  
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
