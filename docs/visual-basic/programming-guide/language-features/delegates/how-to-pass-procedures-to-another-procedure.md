---
title: Filtrar Pasar procedimientos a otro procedimiento en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: e9e6165414db00e7d7182e204d86d23debfbf4f6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967743"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Filtrar Pasar procedimientos a otro procedimiento en Visual Basic
En este ejemplo se muestra cómo utilizar a delegados para pasar un procedimiento a otro procedimiento.  
  
 Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic. El `AddressOf` operador devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que puede hacer referencia a otro procedimiento obtenido con el `AddressOf` operador.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2.  Cree un procedimiento denominado `AddNumbers` con parámetros y el valor devuelto que coincidan con los de `MathOperator`, de modo que coincidan con las firmas.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3.  Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4.  Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden el `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5.  Cree un procedimiento denominado `Test` que llama a `DelegateTest` una vez con el delegado para `AddNumbers` como un parámetro y otra con el delegado para `SubtractNumbers` como un parámetro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Cuando `Test` es llama, primero muestra el resultado de `AddNumbers` que actúa en `5` y `3`, que es 8. A continuación, el resultado de `SubtractNumbers` que actúan en `9` y `3` se muestra, que es 6.  
  
## <a name="see-also"></a>Vea también
- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Cómo: Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
