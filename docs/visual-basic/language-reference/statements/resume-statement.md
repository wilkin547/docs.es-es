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
ms.openlocfilehash: db9d47798d087d60f4318b06fe3291fb895e6618
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871873"
---
# <a name="resume-statement"></a>Resume (Instrucción)

Reanuda la ejecución después de que haya finalizado una rutina de control de errores.  
  
 Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las `On Error` `Resume` instrucciones y. Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](try-catch-finally-statement.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>Partes  

 `Resume`  
 Obligatorio. Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanuda con la instrucción que causó el error. Si el error se produjo en un procedimiento llamado, la ejecución se reanuda en la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores.  
  
 `Next`  
 Opcional. Si el error se produjo en el mismo procedimiento que el controlador de errores, la ejecución se reanudará con la instrucción inmediatamente posterior a la instrucción que causó el error. Si el error se produjo en un procedimiento llamado, la ejecución se reanuda con la instrucción inmediatamente posterior a la instrucción que se ha llamado por última vez en el procedimiento que contiene la rutina de control de errores (o `On Error Resume Next` instrucción).  
  
 `line`  
 Opcional. La ejecución se reanuda en la línea especificada en el `line` argumento requerido. El `line` argumento es una etiqueta de línea o un número de línea y debe estar en el mismo procedimiento que el controlador de errores.  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Se recomienda usar el control de excepciones estructurado en el código siempre que sea posible, en lugar de usar el control de excepciones no estructurado y las `On Error` `Resume` instrucciones y. Para obtener más información, vea [Instrucción Try...Catch...Finally (Visual Basic)](try-catch-finally-statement.md).  
  
 Si utiliza una `Resume` instrucción que no sea en una rutina de control de errores, se producirá un error.  
  
 La `Resume` instrucción no se puede usar en ningún procedimiento que contenga una `Try...Catch...Finally` instrucción.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se utiliza la `Resume` instrucción para finalizar el control de errores en un procedimiento y, a continuación, reanudar la ejecución con la instrucción que causó el error. Se genera el número de error 55 para mostrar el uso de la `Resume` instrucción.  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>Requisitos  

 **Espacio de nombres:** [Microsoft. VisualBasic](../runtime-library-members.md)  
  
 **Ensamblado:** Biblioteca en tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Try...Catch...Finally](try-catch-finally-statement.md)
- [Error (Instrucción)](error-statement.md)
- [Instrucción On Error](on-error-statement.md)
