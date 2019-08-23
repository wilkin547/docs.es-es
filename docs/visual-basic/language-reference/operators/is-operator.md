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
ms.openlocfilehash: a5481a9bce01e84ce4f078335c8cd15a747a3c51
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69917215"
---
# <a name="is-operator-visual-basic"></a>Is (Operador, Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Cualquier `Boolean` valor.  
  
 `object1`  
 Necesario. Cualquier `Object` nombre.  
  
 `object2`  
 Necesario. Cualquier `Object` nombre.  
  
## <a name="remarks"></a>Comentarios  
 El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto `result` exacta `True`, es; si no es `result` así `False`, es.  
  
 `Is`también se puede usar con la `TypeOf` palabra clave para `TypeOf`crear... `Is` expresión, que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
> La `Is` palabra clave también se usa en la [selección... Instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Is` usa el operador para comparar pares de referencias de objeto. Los resultados se asignan a `Boolean` un valor que representa si los dos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Como se muestra en el ejemplo anterior, puede utilizar `Is` el operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
