---
title: 'Cómo: Comprobar si dos objetos son iguales (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 005c91e6f4ec556a7e1bf255b47c8276a5d3d185
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Cómo: Comprobar si dos objetos son iguales (Visual Basic)
Si tiene dos variables que hacen referencia a objetos, puede utilizar cualquiera el `Is` o `IsNot` operador o ambos, para determinar si hacen referencia a la misma instancia.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Para probar si dos objetos son iguales  
  
-   Use la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.  
  
     [!code-vb[VbVbalrOperators#69](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-test-whether-two-objects-are-the-same_1.vb)]  
  
 Puede realizar una acción determinada, dependiendo de si los dos objetos hacen referencia a la misma instancia. En el ejemplo anterior se compara el control `c` en el control activo en el formulario `f`. Si no hay ningún control activo, o si no hay uno, pero no es la misma instancia de control como `c`, la `If` instrucción produce un error y el procedimiento devuelve un valor sin procesamiento adicional.  
  
 Si utiliza `Is` o `IsNot` es cuestión de preferencias personales. Uno podría ser más fácil de leer que el otro en una expresión determinada.  
  
## <a name="see-also"></a>Vea también  
 [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
