---
title: Procedimiento para pasar procedimientos a otro procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 36f623068372614ae034a8a7b31bffb7496f98b1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410700"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Cómo: Pasar procedimientos a otro procedimiento en Visual Basic
En este ejemplo se muestra cómo usar delegados para pasar un procedimiento a otro procedimiento.  
  
 Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic. El `AddressOf` operador devuelve un objeto delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento, obtenido con el `AddressOf` operador.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos coincidentes  
  
1. Cree un delegado denominado `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Cree un procedimiento denominado `AddNumbers` con parámetros y un valor devuelto que coincida con `MathOperator` el de, para que las firmas coincidan.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator` .  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Cree un procedimiento denominado `DelegateTest` que tome un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers` , ya que sus firmas coinciden con la `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Cree un procedimiento denominado `Test` que llame `DelegateTest` una vez con el delegado de `AddNumbers` como parámetro y de nuevo con el delegado de `SubtractNumbers` como parámetro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Cuando `Test` se llama a, primero se muestra el resultado de `AddNumbers` actuar en `5` y `3` , que es 8. A continuación `SubtractNumbers` , se muestra el resultado de actuar en `9` y `3` , que es 6.  
  
## <a name="see-also"></a>Consulte también

- [Delegados](index.md)
- [AddressOf (operador)](../../../language-reference/operators/addressof-operator.md)
- [Delegate (Instrucción)](../../../language-reference/statements/delegate-statement.md)
- [Procedimiento para invocar un método delegado](how-to-invoke-a-delegate-method.md)
