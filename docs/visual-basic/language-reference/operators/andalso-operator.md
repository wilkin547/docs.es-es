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
ms.openlocfilehash: a52f598c8a7c7a79b0f2436f1add7b3eb5d5261b
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835227"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso (Operador, Visual Basic)
Realiza una conjunción lógica de cortocircuito en dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`result`|Obligatorio. Cualquier expresión `Boolean` . El resultado es el resultado `Boolean` de la comparación de las dos expresiones.|  
|`expression1`|Obligatorio. Cualquier expresión `Boolean` .|  
|`expression2`|Obligatorio. Cualquier expresión `Boolean` .|  
  
## <a name="remarks"></a>Comentarios  
 Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final. El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.  
  
 Si ambas expresiones se evalúan como `True`, `result` es `True`. En la tabla siguiente se muestra cómo se determina `result`.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(no evaluado)|`False`|  
  
## <a name="data-types"></a>Tipos de datos  
 El operador `AndAlso` solo se define para el [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario a `Boolean` antes de evaluar la expresión. Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo, de modo que `False` se convierte en `0` y `True` se convierte en `-1`.
Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Sobrecarga  
 El [operador and](../../../visual-basic/language-reference/operators/and-operator.md) y el [operador IsFalse](../../../visual-basic/language-reference/operators/isfalse-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga de los operadores `And` y `IsFalse` afecta al comportamiento del operador `AndAlso`. Si el código usa `AndAlso` en una clase o estructura que sobrecarga `And` y `IsFalse`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `AndAlso` para realizar una conjunción lógica entre dos expresiones. El resultado es un valor `Boolean` que indica si toda la expresión conunida es true. Si la primera expresión es `False`, la segunda no se evalúa.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 En el ejemplo anterior se generan los resultados de `True`, `False` y `False`, respectivamente. En el cálculo de `secondCheck`, la segunda expresión no se evalúa porque la primera ya está `False`. Sin embargo, la segunda expresión se evalúa en el cálculo de `thirdCheck`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento `Function` que busca un valor determinado entre los elementos de una matriz. Si la matriz está vacía, o si se ha superado la longitud de la matriz, la instrucción `While` no probará el elemento de la matriz con el valor de búsqueda.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And (operador)](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse (operador)](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
