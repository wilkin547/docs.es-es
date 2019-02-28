---
title: AndAlso (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 5ba8be5051d0723fd2654b9733933cd434ac3ac5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965194"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso (Operador, Visual Basic)
Realiza una conjunción lógica de dos expresiones de cortocircuito.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`result`|Obligatorio. Cualquier expresión `Boolean` . El resultado es el `Boolean` resultado de comparación de las dos expresiones.|  
|`expression1`|Obligatorio. Cualquier expresión `Boolean` .|  
|`expression2`|Obligatorio. Cualquier expresión `Boolean` .|  
  
## <a name="remarks"></a>Comentarios  
 Se dice que una operación lógica sea *cortocircuitar* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, porque no se puede cambiar el resultado final. Evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja, o si se trata de las llamadas a procedimiento.  
  
 Si ambas expresiones se evalúan como `True`, `result` es `True`. La tabla siguiente se muestra cómo `result` viene determinada.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(no evaluado)|`False`|  
  
## <a name="data-types"></a>Tipos de datos  
 El `AndAlso` operador está definido solo para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario para `Boolean` y realiza la operación totalmente en `Boolean`. Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo. Esto podría producir un comportamiento inesperado. Por ejemplo, `5 AndAlso 12` da como resultado `–1` cuando se convierte en `Integer`.  
  
## <a name="overloading"></a>Sobrecarga  
 El [y operador](../../../visual-basic/language-reference/operators/and-operator.md) y [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo del que clase o estructura. Sobrecargar el `And` y `IsFalse` operadores afecta al comportamiento de la `AndAlso` operador. Si el código usa `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica de dos expresiones. El resultado es un `Boolean` valor que indica si unidas de toda la expresión es true. Si la primera expresión es `False`, no se evalúa el segundo.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 El ejemplo anterior genera los resultados de `True`, `False`, y `False`, respectivamente. En el cálculo de `secondCheck`, la segunda expresión no se evalúa porque ya se encuentra la primera `False`. Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz. Si la matriz está vacía, o si se superó la longitud de la matriz, el `While` instrucción no comprueba el elemento de matriz con el valor de búsqueda.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Vea también
- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And (operador)](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
