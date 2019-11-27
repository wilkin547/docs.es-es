---
title: 'Cómo: pasar procedimientos a otro procedimiento'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: 300489935ce54d78b989d09211a7f6ba95c2f514
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345245"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Cómo: Pasar procedimientos a otro procedimiento en Visual Basic
En este ejemplo se muestra cómo usar delegados para pasar un procedimiento a otro procedimiento.  
  
 Un delegado es un tipo que puede usar como cualquier otro tipo en Visual Basic. El operador `AddressOf` devuelve un objeto delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que puede tomar una referencia a otro procedimiento, obtenido con el operador `AddressOf`.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos coincidentes  
  
1. Cree un delegado denominado `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#1)]  
  
2. Cree un procedimiento denominado `AddNumbers` con parámetros y un valor devuelto que coincida con los de `MathOperator`, para que las firmas coincidan.  
  
     [!code-vb[VbVbalrDelegates#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#2)]  
  
3. Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#3)]  
  
4. Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden con la firma `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#4)]  
  
5. Cree un procedimiento denominado `Test` que llame a `DelegateTest` una vez con el delegado para `AddNumbers` como parámetro y de nuevo con el delegado para `SubtractNumbers` como parámetro.  
  
     [!code-vb[VbVbalrDelegates#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#5)]  
  
     Cuando se llama a `Test`, en primer lugar se muestra el resultado de `AddNumbers` que actúa en `5` y `3`, que es 8. A continuación, se muestra el resultado de `SubtractNumbers` actuando en `9` y `3`, que es 6.  
  
## <a name="see-also"></a>Vea también

- [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
