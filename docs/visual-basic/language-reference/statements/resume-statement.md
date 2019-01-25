---
title: Resume (instrucción) (Visual Basic)
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
ms.openlocfilehash: ef6a2e22c1394065ba6127aa3dd388b47238dea8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624800"
---
# <a name="resume-statement"></a>Resume (Instrucción)
Reanuda la ejecución una vez finalizada una rutina de control de errores.  
  
 Se recomienda que utilice control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y la `On Error` y `Resume` instrucciones. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Elementos  
 `Resume`  
 Obligatorio. Si se produjo el error en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción que produjo el error. Si se produjo el error en un procedimiento llamado, se reanuda la ejecución en la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores.  
  
 `Next`  
 Opcional. Si se produjo el error en el mismo procedimiento que el controlador de errores, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que produjo el error. Si se produjo el error en un procedimiento llamado, se reanuda la ejecución con la instrucción inmediatamente posterior a la instrucción que llame por última vez fuera del procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).  
  
 `line`  
 Opcional. Reanuda la ejecución en la línea especificada en la sección necesario `line` argumento. El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Le recomendamos que use el control de excepciones estructurado en el código siempre que sea posible, en lugar de utilizar el control no estructurado de excepciones y la `On Error` y `Resume` instrucciones. Para obtener más información, vea [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally [Instrucción, Visual Basic]).  
  
 Si usa un `Resume` instrucción en cualquier lugar distinto en una rutina de control de errores, que se produce un error.  
  
 El `Resume` instrucción no se puede usar en cualquier procedimiento que contiene un `Try...Catch...Finally` instrucción.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `Resume` instrucción a fin de control de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que produjo el error. Se genera el error número 55 para ilustrar el uso de la `Resume` instrucción.  
  
 [!code-vb[VbVbalrErrorHandling#16](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/resume-statement_1.vb)]  
  
## <a name="requirements"></a>Requisitos  
 **Espacio de nombres**: [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también
- [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Error (instrucción)](../../../visual-basic/language-reference/statements/error-statement.md)
- [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
