---
title: Procedimiento Comprobar si dos objetos son el mismo (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: d13671f284863fa7bf56964c2b9b963c25e8ea52
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977453"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Procedimiento Comprobar si dos objetos son el mismo (Visual Basic)
Si tiene dos variables que hacen referencia a objetos, puede usar el `Is` o `IsNot` operador o ambos, para determinar si hacen referencia a la misma instancia.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Para comprobar si dos objetos son iguales  
  
-   Use la [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) o [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Es posible que desee realizar una acción determinada, dependiendo de si los dos objetos hacen referencia a la misma instancia. El ejemplo anterior comparan control `c` con el control activo en el formulario `f`. Si no hay ningún control activo, o si hay uno, pero no es la misma instancia de control como `c`, el `If` instrucción produce un error y el procedimiento devuelve sin más procesamiento.  
  
 Si usa `Is` o `IsNot` es una cuestión de preferencias personales. Uno puede ser más fácil de leer que el otro en una expresión dada.  
  
## <a name="see-also"></a>Vea también
- [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
