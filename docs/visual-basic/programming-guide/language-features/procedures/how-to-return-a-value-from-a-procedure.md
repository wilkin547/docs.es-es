---
title: 'Cómo: Devolver un valor de un procedimiento'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346028"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Cómo: Devolver un valor de un procedimiento (Visual Basic)
Un procedimiento `Function` devuelve un valor al código de llamada mediante la ejecución de una instrucción de `Return` o una instrucción `Exit Function` o `End Function`.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Para devolver un valor mediante la instrucción return  
  
1. Coloque una instrucción `Return` en el punto en el que se complete la tarea del procedimiento.  
  
2. Siga la palabra clave `Return` con una expresión que produzca el valor que desea devolver al código de llamada.  
  
3. Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
     En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo derecho y se devuelve al código de llamada.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`, que almacena el valor devuelto.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Para devolver un valor mediante la función EXIT o end  
  
1. En al menos un lugar del procedimiento `Function`, asigne un valor al nombre del procedimiento.  
  
2. Al ejecutar una instrucción `Exit Function` o `End Function`, Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.  
  
3. Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.  
  
4. Solo puede tener una instrucción `End Function` en un procedimiento `Function`.  
  
     Para obtener más información y un ejemplo, vea el tema sobre el valor devuelto en la [instrucción function](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Return (instrucción)](../../../../visual-basic/language-reference/statements/return-statement.md)
- [Crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
