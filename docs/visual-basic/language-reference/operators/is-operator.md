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
ms.openlocfilehash: 0351d224d9bf08a8f3ca74090de7b9c51c2c61bf
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701363"
---
# <a name="is-operator-visual-basic"></a>Is (Operador, Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier valor de `Boolean`.  
  
 `object1`  
 Obligatorio. Cualquier nombre de `Object`.  
  
 `object2`  
 Obligatorio. Cualquier nombre de `Object`.  
  
## <a name="remarks"></a>Comentarios  
 El operador `Is` determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` hacen referencia a la misma instancia de objeto exacta, se `True``result`. Si no es así, `result` se `False`.  
  
 también se puede usar `Is` con la palabra clave `TypeOf` para crear una expresión `TypeOf`...`Is`, que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
> La palabra clave `Is` también se usa en [la Instrucción Case](../../../visual-basic/language-reference/statements/select-case-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `Is` para comparar pares de referencias a objetos. Los resultados se asignan a un valor `Boolean` que representa si los dos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Como se muestra en el ejemplo anterior, puede utilizar el operador `Is` para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también

- [TypeOf (operador)](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
