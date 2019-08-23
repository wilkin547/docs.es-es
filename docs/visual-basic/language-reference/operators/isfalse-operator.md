---
title: IsFalse (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 49b8493575685a220808df1522ce16835b3ce0ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917154"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse (Operador) (Visual Basic)
Determina si una expresión es `False`.  
  
 No se puede `IsFalse` llamar a explícitamente en el código, pero el compilador de Visual Basic puede `AndAlso` utilizarlo para generar código a partir de cláusulas. Si define una clase o estructura y, a continuación, usa una variable de ese tipo `AndAlso` en una cláusula, debe `IsFalse` definir en esa clase o estructura.  
  
 El compilador `IsFalse` tiene `IsTrue` en cuenta los operadores y como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
> El `IsFalse` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que `IsFalse` incluye `IsTrue` definiciones para los operadores y.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Vea también

- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
