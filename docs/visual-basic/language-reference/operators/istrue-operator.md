---
title: IsTrue (Operador) (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.istrue
helpviewer_keywords:
- IsTrue operator [Visual Basic]
- OrElse operator [Visual Basic]
ms.assetid: b6cec0f2-61b1-4331-a7f0-4d07ee3179d6
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c0d261186ce68f06cec95251e815248a189f6da5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="istrue-operator-visual-basic"></a>IsTrue (Operador) (Visual Basic)
Determina si una expresión es `True`.  
  
 No se puede llamar `IsTrue` explícitamente en el código, pero Visual Basic compilador puede utilizarlo para generar código a partir `OrElse` cláusulas. Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en una `OrElse` cláusula, debe definir `IsTrue` en esa clase o estructura.  
  
 El compilador considera que el `IsTrue` y `IsFalse` operadores como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
## <a name="compiler-use-of-istrue"></a>Uso de IsTrue del compilador  
 Una vez haya definido una clase o estructura, puede utilizar una variable de ese tipo en una `For`, `If`, `Else``If`, o `While` (instrucción), o en un `When` cláusula. Si lo hace, el compilador requiere un operador que convierta el tipo en un `Boolean` valor para que pueda probar una condición. Busca un operador adecuado en el orden siguiente:  
  
1.  Un operador de conversión de ampliación de la clase o estructura a `Boolean`.  
  
2.  Un operador de conversión de ampliación de la clase o estructura a `Boolean?`.  
  
3.  El `IsTrue` operador en la clase o estructura.  
  
4.  Una conversión de restricción a `Boolean?` que implican una conversión de `Boolean` a `Boolean?`.  
  
5.  Un operador de conversión de restricción de la clase o estructura a `Boolean`.  
  
 Si no ha definido ninguna conversión a `Boolean` o un `IsTrue` (operador), el compilador señala un error.  
  
> [!NOTE]
>  El `IsTrue` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para la `IsFalse` y `IsTrue` operadores.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/istrue-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
