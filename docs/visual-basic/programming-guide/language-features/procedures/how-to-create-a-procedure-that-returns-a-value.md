---
title: Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 115c1df4bd49d5848d72c4cbd0242a49a12740c7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61863732"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Procedimiento Crear un procedimiento que devuelve un valor (Visual Basic)
Usa un `Function` procedimiento devuelva un valor al código de llamada.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor  
  
1. Fuera de cualquier otro procedimiento, utilice un `Function` instrucción, seguida de un `End Function` instrucción.  
  
2. En el `Function` (instrucción), siga el `Function` palabra clave con el nombre del procedimiento y, a continuación, en la lista de parámetros entre paréntesis.  
  
3. Siga los paréntesis con un `As` cláusula para especificar el tipo de datos del valor devuelto.  
  
4. Coloque las instrucciones de código del procedimiento entre el `Function` y `End Function` instrucciones.  
  
5. Use un `Return` instrucción para devolver el valor al código de llamada.  
  
     La siguiente `Function` procedimiento calcula el lado más largo, o la hipotenusa de un triángulo rectángulo, dado los valores para los dos lados.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     El ejemplo siguiente muestra una llamada típica al `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Cómo: Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Cómo: Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
