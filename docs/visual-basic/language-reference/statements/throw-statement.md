---
title: Throw (Instrucción, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: cfa53b3585846da25711739fb7af4bde21746b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="throw-statement-visual-basic"></a>Throw (Instrucción, Visual Basic)
Produce una excepción dentro de un procedimiento.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a>Parte  
 `expression`  
 Proporciona información sobre la excepción que se produzca. Opcional si se encuentra en un `Catch` instrucción, en caso contrario, se requiere.  
  
## <a name="remarks"></a>Comentarios  
 El `Throw` instrucción produce una excepción que se puede controlar con código de control de excepciones estructurado (`Try`... `Catch`... `Finally`) o código de control de excepciones no estructurado (`On Error GoTo`). Puede usar el `Throw` instrucción para interceptar errores dentro del código porque Visual Basic asciende por la pila de llamadas hasta que encuentra el código de control de excepciones adecuado.  
  
 A `Throw` instrucción sin expresión sólo puede utilizarse en una `Catch` (instrucción), en el que caso la instrucción, vuelve a producir la excepción se controla actualmente por el `Catch` instrucción.  
  
 El `Throw` instrucción restablece la pila de llamadas para el `expression` excepción. Si `expression` no se proporciona, la pila de llamadas es permanecen sin cambios. Puede tener acceso a la pila de llamadas para la excepción a través de la <xref:System.Exception.StackTrace%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código utiliza el `Throw` instrucción se producirá una excepción:  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a>Requisitos  
 **Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)  
  
 **Módulo:** `Interaction`  
  
 **Ensamblado:** biblioteca de tiempo de ejecución de Visual Basic (en Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>Vea también  
 [Try...Catch...Finally (instrucción)](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [On Error (instrucción)](../../../visual-basic/language-reference/statements/on-error-statement.md)
