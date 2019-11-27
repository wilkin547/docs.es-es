---
title: 'Cómo: Comprobar si dos objetos son iguales'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343616"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Cómo: Comprobar si dos objetos son iguales (Visual Basic)
Si tiene dos variables que hacen referencia a objetos, puede usar el operador `Is` o `IsNot`, o ambos, para determinar si hacen referencia a la misma instancia.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Para comprobar si dos objetos son iguales  
  
- Use el [operador is](../../../../visual-basic/language-reference/operators/is-operator.md) o el [Operador IsNot](../../../../visual-basic/language-reference/operators/isnot-operator.md) con las dos variables como operandos.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Es posible que desee realizar una acción determinada dependiendo de si dos objetos hacen referencia a la misma instancia. En el ejemplo anterior se comparan los `c` de control con el control activo en el formulario `f`. Si no hay ningún control activo, o si hay alguno pero no es la misma instancia de control que `c`, se produce un error en la instrucción `If` y el procedimiento vuelve sin más procesamiento.  
  
 Tanto si usa `Is` como si `IsNot` es una cuestión de comodidad personal. Una puede ser más fácil de leer que la otra en una expresión dada.  
  
## <a name="see-also"></a>Vea también

- [Operadores de comparación en Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
