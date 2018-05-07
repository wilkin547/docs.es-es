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
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a>AndAlso (Operador, Visual Basic)
Realiza la evaluación "cortocircuitada" conjunción lógica en dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`result`|Requerido. Cualquier expresión `Boolean`. El resultado es el `Boolean` resultado de comparación de las dos expresiones.|  
|`expression1`|Requerido. Cualquier expresión `Boolean`.|  
|`expression2`|Requerido. Cualquier expresión `Boolean`.|  
  
## <a name="remarks"></a>Comentarios  
 Se dice que una operación lógica *evaluación "cortocircuitada"* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, ya que no puede cambiar el resultado final. Evaluación "cortocircuitada" puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas de procedimiento.  
  
 Si ambas expresiones se evalúan como `True`, `result` es `True`. La tabla siguiente se muestra cómo `result` viene determinado.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(no se evalúa)|`False`|  
  
## <a name="data-types"></a>Tipos de datos  
 El `AndAlso` operador está definido solo para la [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario para `Boolean` y realiza la operación totalmente en `Boolean`. Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo. Esto podría producir un comportamiento inesperado. Por ejemplo, `5 AndAlso 12` da como resultado `–1` cuando se convierte en `Integer`.  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador y](../../../visual-basic/language-reference/operators/and-operator.md) y [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md) puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de ese clase o estructura. Sobrecarga de la `And` y `IsFalse` operadores afecta al comportamiento de la `AndAlso` operador. Si el código usa `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AndAlso` operador para realizar una conjunción lógica en dos expresiones. El resultado es un `Boolean` valor que representa si conjunta de toda la expresión es true. Si la primera expresión es `False`, no se evalúa el segundo.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `True`, `False`, y `False`, respectivamente. En el cálculo de `secondCheck`, no se evalúa la segunda expresión porque la primera ya es `False`. Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un `Function` procedimiento que busca un valor determinado entre los elementos de una matriz. Si la matriz está vacía, o si se ha superado la longitud de la matriz, el `While` instrucción no comprueba el elemento de matriz con el valor de búsqueda.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [And (operador)](../../../visual-basic/language-reference/operators/and-operator.md)  
 [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
