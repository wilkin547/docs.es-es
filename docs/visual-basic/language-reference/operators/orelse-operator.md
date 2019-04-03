---
title: OrElse (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 28d1481b71979936bb16a2ecfb1140d85a674ef7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816400"
---
# <a name="orelse-operator-visual-basic"></a>OrElse (Operador) (Visual Basic)
Realiza una disyunción lógica inclusiva en dos expresiones de cortocircuito.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier expresión `Boolean` .  
  
 `expression1`  
 Obligatorio. Cualquier expresión `Boolean` .  
  
 `expression2`  
 Obligatorio. Cualquier expresión `Boolean` .  
  
## <a name="remarks"></a>Comentarios  
 Se dice que una operación lógica sea *cortocircuitar* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no hay ninguna necesidad de evaluar la segunda expresión, porque no se puede cambiar el resultado final. Evaluación cortocircuitada puede mejorar el rendimiento si la expresión omitida es compleja, o si se trata de las llamadas a procedimiento.  
  
 Si una o ambas expresiones se evalúan como `True`, `result` es `True`. La tabla siguiente se muestra cómo `result` viene determinada.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(no evaluado)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Tipos de datos  
 El `OrElse` operador está definido solo para el [tipo de datos Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario para `Boolean` y realiza la operación totalmente en `Boolean`. Si asigna el resultado a un tipo numérico, Visual Basic convierte desde `Boolean` a ese tipo. Esto podría producir un comportamiento inesperado. Por ejemplo, `5 OrElse 12` da como resultado `–1` cuando se convierte en `Integer`.  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador o](../../../visual-basic/language-reference/operators/or-operator.md) y [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md) puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de la clase o estructura. Sobrecargar el `Or` y `IsTrue` operadores afecta al comportamiento de la `OrElse` operador. Si el código usa `OrElse` en una clase o estructura que sobrecarga `Or` y `IsTrue`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `OrElse` operador para realizar una disyunción lógica entre dos expresiones. El resultado es un `Boolean` valor que representa si cualquiera de las dos expresiones es true. Si la primera expresión es `True`, no se evalúa el segundo.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 El ejemplo anterior genera los resultados de `True`, `True`, y `False` respectivamente. En el cálculo de `firstCheck`, la segunda expresión no se evalúa porque ya se encuentra la primera `True`. Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck`.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un `If`... `Then` instrucción que contiene dos llamadas a procedimiento. Si la primera llamada devuelve `True`, no se llama al procedimiento de segundo. Esto podría producir resultados inesperados si el segundo procedimiento realiza las tareas importantes que siempre se deben realizar cuando se ejecuta en esta sección del código.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OR (operador)](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
