---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: a7a0952ebe13b732ce706c3dad97a6da3b5cb85d
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56966559"
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Valor `Boolean`.  
  
 `object1`  
 Obligatorio. Cualquier `Object` variable o expresión.  
  
 `object2`  
 Obligatorio. Cualquier `Object` variable o expresión.  
  
## <a name="remarks"></a>Comentarios  
 El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza las comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la instancia exacta del objeto mismo, `result` es `False`; si no, es `result` es `True`.  
  
 `IsNot` es el opuesto de la `Is` operador. La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` y `Is`, que puede ser difícil de leer.  
  
 Puede usar el `Is` y `IsNot` operadores a los objetos con enlace anticipado y en tiempo de ejecución de prueba.  
  
> [!NOTE]
>  El `IsNot` operador no puede utilizarse para comparar expresiones devueltas desde el `TypeOf` operador. En su lugar, debe usar el `Not` y `Is` operadores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se usa tanto el `Is` operador y el `IsNot` operador para realizar la comparación de la misma.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Vea también
- [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Cómo: Probar si dos objetos son iguales](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
