---
title: Operador IsFalse
ms.date: 07/20/2015
f1_keywords:
- vb.isfalse
helpviewer_keywords:
- AndAlso operator [Visual Basic]
- IsFalse operator [Visual Basic]
ms.assetid: 37fc9dbf-e5cc-4570-b93f-7213447974df
ms.openlocfilehash: 7c5ad5fa0b72370eeb19fbaced88807570467552
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370679"
---
# <a name="isfalse-operator-visual-basic"></a>IsFalse (Operador) (Visual Basic)
Determina si una expresión es `False` .  
  
 No se puede llamar a `IsFalse` explícitamente en el código, pero el compilador de Visual Basic puede utilizarlo para generar código a partir de `AndAlso` cláusulas. Si define una clase o estructura y, a continuación, usa una variable de ese tipo en una `AndAlso` cláusula, debe definir `IsFalse` en esa clase o estructura.  
  
 El compilador tiene en cuenta los `IsFalse` `IsTrue` operadores y como un *par coincidente*. Esto significa que si define uno de ellos, también debe definir el otro.  
  
> [!NOTE]
> El `IsFalse` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se define el contorno de una estructura que incluye definiciones para los `IsFalse` `IsTrue` operadores y.  
  
 [!code-vb[VbVbalrOperators#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Consulte también

- [Operador IsTrue](istrue-operator.md)
- [Procedimiento para definir un operador](../../programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [Operador AndAlso](andalso-operator.md)
