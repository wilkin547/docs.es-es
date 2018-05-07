---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: babee364d350ca84a8379f675acc4b5c87f98303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Valor `Boolean`.  
  
 `object1`  
 Requerido. Cualquier `Object` variable o expresión.  
  
 `object2`  
 Requerido. Cualquier `Object` variable o expresión.  
  
## <a name="remarks"></a>Comentarios  
 El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza las comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia objeto exacta, `result` es `False`; si no lo hacen, `result` es `True`.  
  
 `IsNot` es el opuesto de la `Is` operador. La ventaja de `IsNot` es que puede evitar sintaxis extraña con `Not` y `Is`, que puede ser difícil de leer.  
  
 Puede usar el `Is` y `IsNot` operadores a los objetos de tiempo de compilación y en tiempo de ejecución de prueba.  
  
> [!NOTE]
>  El `IsNot` no se puede usar el operador para comparar expresiones devueltas desde el `TypeOf` operador. En su lugar, debe utilizar el `Not` y `Is` operadores.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se utiliza la `Is` operador y el `IsNot` operador que se va a realizar la comparación de la misma.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)  
 [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Comprobar si dos objetos son iguales](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
