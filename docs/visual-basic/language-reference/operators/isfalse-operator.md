---
title: IsFalse (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: e84b2162eb0763725f05bc52d5c4223d7c430b81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600053"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse (Operador) (Visual Basic)
Determina si una expresión es `False`.  
  
 No se puede llamar `IsFalse` explícitamente en el código, pero Visual Basic compilador puede utilizarlo para generar código a partir `AndAlso` cláusulas. Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en una `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.  
  
 El compilador considera que el `IsFalse` y `IsTrue` operadores como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
>  El `IsFalse` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para la `IsFalse` y `IsTrue` operadores.  
  
 [!code-vb[VbVbalrOperators#28](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isfalse-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)  
 [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
