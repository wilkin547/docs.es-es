---
title: Is (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 8beca1dc8788514224f70cacc5b8ede0974f5230
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33601955"
---
# <a name="is-operator-visual-basic"></a>Is (Operador, Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Cualquier `Boolean` valor.  
  
 `object1`  
 Requerido. Cualquier `Object` nombre.  
  
 `object2`  
 Requerido. Cualquier `Object` nombre.  
  
## <a name="remarks"></a>Comentarios  
 El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza las comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia objeto exacta, `result` es `True`; si no lo hacen, `result` es `False`.  
  
 `Is` También puede utilizarse con el `TypeOf` palabra clave que se va a realizar un `TypeOf`... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
>  El `Is` también se utiliza la palabra clave en el [seleccione... Caso instrucción](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto. El resultado se asigna a un `Boolean` valor que indica si los dos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/is-operator_1.vb)]  
  
 Como se muestra en el ejemplo anterior, puede usar el `Is` operador que se va a probar ambos enlazadas tempranamente y enlazada tempranamente objetos.  
  
## <a name="see-also"></a>Vea también  
 [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
