---
description: 'Más información sobre: Cómo: crear un procedimiento que devuelve un valor (Visual Basic)'
title: Procedimiento para crear un procedimiento que devuelve un valor
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: fa2ea50febd1cc4e7aecf1e6f5cca671789b36fd
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100467061"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)

Use un `Function` procedimiento para devolver un valor al código de llamada.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor  
  
1. Fuera de cualquier otro procedimiento, use una `Function` instrucción seguida de una `End Function` instrucción.  
  
2. En la `Function` instrucción, siga la `Function` palabra clave con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3. Siga los paréntesis con una `As` cláusula para especificar el tipo de datos del valor devuelto.  
  
4. Coloque las instrucciones de código del procedimiento entre `Function` las `End Function` instrucciones y.  
  
5. Use una `Return` instrucción para devolver el valor al código de llamada.  
  
     En el `Function` procedimiento siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse` .  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Instrucción Function](../../../language-reference/statements/function-statement.md)
- [Procedimiento para devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Procedimiento para llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
