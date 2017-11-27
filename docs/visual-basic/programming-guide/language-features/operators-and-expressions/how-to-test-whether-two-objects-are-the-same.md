---
title: "Cómo: Comprobar si dos objetos son iguales (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 76f5c19386cce84207f80d217326d2e3babf4e44
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
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
