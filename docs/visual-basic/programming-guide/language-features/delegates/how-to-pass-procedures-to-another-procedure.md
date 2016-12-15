---
title: "C&#243;mo: Pasar procedimientos a otro procedimiento en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf (operador)"
  - "delegados [Visual Basic], pasar procedimientos"
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Pasar procedimientos a otro procedimiento en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Este ejemplo muestra cómo se utilizan los delegados para pasar un procedimiento a otro.  
  
 Un delegado es un tipo que se puede usar como cualquier otro tipo en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  El operador `AddressOf` devuelve un objeto de delegado cuando se aplica a un nombre de procedimiento.  
  
 Este ejemplo tiene un procedimiento con un parámetro de delegado que puede llevar una referencia a otro procedimiento obtenido con el operador `AddressOf`.  
  
### Cree el delegado y los procedimientos correspondientes  
  
1.  Cree un delegado denominado `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  Cree un procedimiento denominado `AddNumbers` con los parámetros y el valor devuelto que coincidan con aquéllos de `MathOperator` para que coincidan las firmas.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  Cree un procedimiento denominado `SubtractNumbers` con una firma que coincida con `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  Cree un procedimiento denominado `DelegateTest` que tome un delegado como parámetro.  
  
     Este procedimiento puede aceptar una referencia para `AddNumbers` o `SubtractNumbers` porque sus firmas coinciden con la firma `MathOperator`.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  Cree un procedimiento denominado `Test` que llame a `DelegateTest` una vez con el delegado para `AddNumbers` como parámetro y, de nuevo, con el delegado para `SubtractNumbers` como parámetro.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     Cuando se llama a `Test`, primero muestra el resultado de `AddNumbers` sobre `5` y `3`, que es 8.  A continuación, se muestra el resultado de `SubtractNumbers` sobre `9` y `3`, que es 6.  
  
## Vea también  
 [Delegados](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [AddressOf \(Operador\)](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate \(Instrucción\)](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Cómo: Invocar un método delegado](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)