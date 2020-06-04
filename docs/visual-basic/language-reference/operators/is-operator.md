---
title: Operador Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370809"
---
# <a name="is-operator-visual-basic"></a>Is (Operador, Visual Basic)
Compara dos variables de referencia de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Partes  
 `result`  
 Necesario. Cualquier `Boolean` valor.  
  
 `object1`  
 Necesario. Cualquier `Object` nombre.  
  
 `object2`  
 Necesario. Cualquier `Object` nombre.  
  
## <a name="remarks"></a>Observaciones  
 El `Is` operador determina si dos referencias de objeto hacen referencia al mismo objeto. Sin embargo, no realiza comparaciones de valores. Si `object1` y `object2` ambos hacen referencia a la misma instancia de objeto exacta, `result` es `True` ; si no es así, `result` es `False` .  
  
 `Is`también se puede usar con la `TypeOf` palabra clave para crear una `TypeOf` expresión... `Is` , que comprueba si una variable de objeto es compatible con un tipo de datos.  
  
> [!NOTE]
> La `Is` palabra clave también se usa en la [selección... Instrucción Case](../statements/select-case-statement.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Is` operador para comparar pares de referencias de objeto. Los resultados se asignan a un `Boolean` valor que representa si los dos objetos son idénticos.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Como se muestra en el ejemplo anterior, puede utilizar el `Is` operador para probar los objetos enlazados en tiempo de compilación y en tiempo de ejecución.  
  
## <a name="see-also"></a>Consulte también

- [Typeof (operador)](typeof-operator.md)
- [Operador IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
