---
title: IsNot (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: 0a83b48e5e415bd6ca0c777cef6d34f7127691b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966937"
---
# <a name="isnot-operator-visual-basic"></a>IsNot (Operador) (Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Valor `Boolean`.  
  
 `object1`  
 Necesario. Cualquier `Object` variable o expresión.  
  
 `object2`  
 Necesario. Cualquier `Object` variable o expresión.  
  
## <a name="remarks"></a>Comentarios  
 El `IsNot` operador determina si dos referencias de objeto hacen referencia a objetos diferentes. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto `result` exacta `False`, es; si no es `result` así `True`, es.  
  
 `IsNot`es lo contrario del `Is` operador. La ventaja de `IsNot` es que puede evitar una sintaxis complicada con `Not` y `Is`, que puede ser difícil de leer.  
  
 Puede usar los `Is` operadores y `IsNot` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
> [!NOTE]
> No `IsNot` se puede usar el operador para comparar expresiones devueltas por el `TypeOf` operador. En su lugar, debe usar los `Not` operadores `Is` y.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se `Is` usa el operador `IsNot` y el operador para realizar la misma comparación.  
  
 [!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]  
  
## <a name="see-also"></a>Vea también

- [Is (operador)](../../../visual-basic/language-reference/operators/is-operator.md)
- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Cómo: Comprobar si dos objetos son iguales](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
