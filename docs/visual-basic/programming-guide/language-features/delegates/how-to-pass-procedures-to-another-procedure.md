---
title: "Cómo: pasar procedimientos a otro procedimiento en Visual Basic | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9865e2d7d3786d289add3fa63b3db777317facdf
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>Cómo: Pasar procedimientos a otro procedimiento en Visual Basic
Este ejemplo muestra cómo utilizar a los delegados para pasar un procedimiento a otro procedimiento.  
  
 Un delegado es un tipo que puede utilizar como cualquier otro tipo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]. El `AddressOf` operador devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que se puede hacer referencia a otro procedimiento obtenido con el `AddressOf` operador.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Crear el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MathOperator`.  
  
     [!code-vb[1 VbVbalrDelegates](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Cree un procedimiento denominado `AddNumbers` con parámetros y valor devuelto que coincidan con los de `MathOperator`, de modo que coincida con las firmas.  
  
     [!code-vb[VbVbalrDelegates&#2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Cree un procedimiento denominado `DelegateTest` que toma un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia a `AddNumbers` o `SubtractNumbers`, porque sus firmas coinciden con la `MathOperator` firma.  
  
     [!code-vb[VbVbalrDelegates Nº&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Cree un procedimiento denominado `Test` que llama a `DelegateTest` una vez con el delegado para `AddNumbers` como un parámetro y, de nuevo, con el delegado para `SubtractNumbers` como un parámetro.  
  
     [!code-vb[VbVbalrDelegates&#5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Cuando `Test` es llamado, primero muestra el resultado de `AddNumbers` actúa en `5` y `3`, que es 8. A continuación, el resultado de `SubtractNumbers` a `9` y `3` se muestra, que es 6.  
  
## <a name="see-also"></a>Vea también  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [AddressOf (operador)](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate (instrucción)](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
