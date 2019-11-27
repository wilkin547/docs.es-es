---
title: IsFalse (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 51b7bfb2cf5301a39818e6566b408ee0677689f2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349528"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse (Operador) (Visual Basic)
Determina si una expresión es `False`.  
  
 No se puede llamar a `IsFalse` explícitamente en el código, pero el compilador Visual Basic puede usarlo para generar código a partir de cláusulas `AndAlso`. Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una cláusula `AndAlso`, debe definir `IsFalse` en esa clase o estructura.  
  
 El compilador tiene en cuenta los operadores `IsFalse` y `IsTrue` como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
> El operador de `IsFalse` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los operadores `IsFalse` y `IsTrue`.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
