---
description: 'Más información acerca de cómo: comprobar si dos objetos son iguales (Visual Basic)'
title: Procedimiento para comprobar si dos objetos son iguales
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: a0136d9db487ad0ce70b9d55ff8ee014ec30b05a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435543"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Cómo: Comprobar si dos objetos son iguales (Visual Basic)

Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` `IsNot` operador o, o ambos, para determinar si hacen referencia a la misma instancia.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Para comprobar si dos objetos son iguales  
  
- Use el [operador is](../../../language-reference/operators/is-operator.md) o el [Operador IsNot](../../../language-reference/operators/isnot-operator.md) con las dos variables como operandos.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Es posible que desee realizar una acción determinada dependiendo de si dos objetos hacen referencia a la misma instancia. En el ejemplo anterior se compara `c` el control con el control activo en el formulario `f` . Si no hay ningún control activo, o si hay alguno pero no es la misma instancia de control que `c` , la `If` instrucción genera un error y el procedimiento vuelve sin más procesamiento.  
  
 Tanto si usa `Is` como si `IsNot` es una cuestión de comodidad personal. Una puede ser más fácil de leer que la otra en una expresión dada.  
  
## <a name="see-also"></a>Consulte también

- [Comparison Operators in Visual Basic](comparison-operators.md)
