---
title: Procedimiento para devolver un valor de un procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: cbc785a07aa8a7b299508a093e08d5d0510b838a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071383"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>Cómo: Devolver un valor de un procedimiento (Visual Basic)

Un `Function` procedimiento devuelve un valor al código de llamada mediante la ejecución de una `Return` instrucción o al encontrar una `Exit Function` `End Function` instrucción o.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Para devolver un valor mediante la instrucción return  
  
1. Coloque una `Return` instrucción en el punto en el que se complete la tarea del procedimiento.  
  
2. Siga la `Return` palabra clave con una expresión que produzca el valor que desea devolver al código de llamada.  
  
3. Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
     En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo derecho y se devuelve al código de llamada.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` , que almacena el valor devuelto.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Para devolver un valor mediante la función EXIT o end  
  
1. En al menos un lugar del `Function` procedimiento, asigne un valor al nombre del procedimiento.  
  
2. Al ejecutar una `Exit Function` instrucción o `End Function` , Visual Basic devuelve el valor asignado más recientemente al nombre del procedimiento.  
  
3. Puede tener más de una instrucción `Exit Function` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit Function` en el mismo procedimiento.  
  
4. Solo puede tener una `End Function` instrucción en un `Function` procedimiento.  
  
     Para obtener más información y un ejemplo, vea el tema sobre el valor devuelto en la [instrucción function](../../../language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Function](../../../language-reference/statements/function-statement.md)
- [Instrucción Return](../../../language-reference/statements/return-statement.md)
- [Procedimiento para crear un procedimiento que devuelve un valor](./how-to-create-a-procedure-that-returns-a-value.md)
- [Procedimiento para llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
