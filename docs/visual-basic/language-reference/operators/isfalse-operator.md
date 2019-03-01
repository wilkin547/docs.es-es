---
title: IsFalse (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 85fd6b9264fa80c3636f2cb839c8fc5ed855ddc8
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965662"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse (Operador) (Visual Basic)
Determina si una expresión es `False`.  
  
 No se puede llamar a `IsFalse` explícitamente en el código, pero el de Visual Basic compilador puede usar para generar código desde `AndAlso` cláusulas. Si se define una clase o estructura y, a continuación, utilizar una variable de ese tipo en un `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.  
  
 El compilador considera que el `IsFalse` y `IsTrue` operadores como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
>  El `IsFalse` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el esquema de una estructura que incluye las definiciones para el `IsFalse` y `IsTrue` operadores.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también
- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
