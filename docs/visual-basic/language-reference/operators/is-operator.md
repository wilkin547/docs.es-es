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
ms.openlocfilehash: a59ff4c956724c614342f0ee4c0622a67f1c25e7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58817076"
---
# <a name="is-operator-visual-basic"></a>Is (Operador, Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` valor.  
  
 `object1`  
 Obligatorio. Cualquier `Object` nombre.  
  
 `object2`  
 Obligatorio. Cualquier `Object` nombre.  
  
## <a name="remarks"></a>Comentarios  
 El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza las comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la instancia exacta del objeto mismo, `result` es `True`; si no, es `result` es `False`.  
  
 `Is` También puede utilizarse con el `TypeOf` palabra clave para realizar un `TypeOf`... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
>  El `Is` también se utiliza la palabra clave en el [seleccione... Instrucción de caso](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto. Los resultados se asignan a un `Boolean` valor que indica si los dos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Como se muestra en el ejemplo anterior, puede usar el `Is` operador para probar ambas enlaza de manera anticipada y los objetos enlazados en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
