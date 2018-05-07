---
title: 'Cómo: Devolver un valor de un procedimiento (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 62e8a52e488247d4dfcde2a560920447abe1c182
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Cómo: Devolver un valor de un procedimiento (Visual Basic)
A `Function` procedimiento devuelve un valor al código de llamada mediante la ejecución de un `Return` instrucción o encontrar una `Exit Function` o `End Function` instrucción.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Para devolver un valor mediante la instrucción Return  
  
1.  Coloque un `Return` instrucción en el punto donde se completa la tarea del procedimiento.  
  
2.  Siga el `Return` palabra clave con una expresión que da como resultado el valor que desea devolver al código de llamada.  
  
3.  Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
     El siguiente `Function` procedimiento calcula el lado o la hipotenusa de un triángulo rectángulo y lo devuelve al código de llamada.  
  
     [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_1.vb)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`, que almacena el valor devuelto.  
  
     [!code-vb[VbVbcnProcedures#6](./codesnippet/VisualBasic/how-to-return-a-value-from-a-procedure_2.vb)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Para devolver un valor mediante Exit Function o End Function  
  
1.  En lugar de al menos una de las `Function` procedimiento, asigne un valor para el nombre del procedimiento.  
  
2.  Cuando se ejecuta un `Exit Function` o `End Function` instrucción, Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.  
  
3.  Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.  
  
4.  Puede tener solo una `End Function` instrucción en un `Function` procedimiento.  
  
     Para obtener más información y un ejemplo, vea "Valor devuelto" en [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return (instrucción)](../../../../visual-basic/language-reference/statements/return-statement.md)  
 [Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)  
 [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
