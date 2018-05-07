---
title: 'Cómo: Pasar procedimientos a otro procedimiento en Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c28ac7a640ec863b37bd7407d0273a1918964ac4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Cómo: Pasar procedimientos a otro procedimiento en Visual Basic
En este ejemplo se muestra cómo utilizar a los delegados para pasar un procedimiento a otro procedimiento.  
  
 Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic. El `AddressOf` operador devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento obtenido con la `AddressOf` operador.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Cree un procedimiento denominado `AddNumbers` con parámetros y el valor devuelto que coinciden con los de `MathOperator`, de modo que coincidan con las firmas.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden con la `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Cree un procedimiento denominado `Test` que llama `DelegateTest` una vez con el delegado para `AddNumbers` como un parámetro y otra con el delegado para `SubtractNumbers` como un parámetro.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Cuando `Test` es llama, primero muestra el resultado de `AddNumbers` funciona en `5` y `3`, que es 8. A continuación, el resultado de `SubtractNumbers` actúa en `9` y `3` se muestra, que es 6.  
  
## <a name="see-also"></a>Vea también  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
