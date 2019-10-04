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
ms.openlocfilehash: 8290e642db3ec76a931bdd2febe427309457bc86
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835245"
---
# <a name="orelse-operator-visual-basic"></a>OrElse (Operador) (Visual Basic)
Realiza una disyunción lógica inclusiva de cortocircuito en dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb
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
 Se dice que una operación lógica es *cortocircuitada* si el código compilado puede omitir la evaluación de una expresión en función del resultado de otra expresión. Si el resultado de la primera expresión evaluada determina el resultado final de la operación, no es necesario evaluar la segunda expresión, porque no puede cambiar el resultado final. El cortocircuito puede mejorar el rendimiento si la expresión omitida es compleja o si implica llamadas a procedimientos.  
  
 Si una o ambas expresiones se evalúan como `True`, `result` es `True`. En la tabla siguiente se muestra cómo se determina `result`.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(no evaluado)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Tipos de datos  
 El operador `OrElse` solo se define para el [tipo de datos booleano](../../../visual-basic/language-reference/data-types/boolean-data-type.md). Visual Basic convierte cada operando según sea necesario a `Boolean` antes de evaluar la expresión. Si asigna el resultado a un tipo numérico, Visual Basic lo convierte de `Boolean` a ese tipo, de modo que `False` se convierte en `0` y `True` se convierte en `-1`.
Para obtener más información, vea [conversiones de tipo booleano](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Sobrecarga  
 El [operador o](../../../visual-basic/language-reference/operators/or-operator.md) y el [operador IsTrue](../../../visual-basic/language-reference/operators/istrue-operator.md) se pueden *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga de los operadores `Or` y `IsTrue` afecta al comportamiento del operador `OrElse`. Si el código usa `OrElse` en una clase o estructura que sobrecarga `Or` y `IsTrue`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `OrElse` para realizar una disyunción lógica entre dos expresiones. El resultado es un valor `Boolean` que indica si cualquiera de las dos expresiones es true. Si la primera expresión es `True`, la segunda no se evalúa.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 En el ejemplo anterior se generan los resultados de `True`, `True` y `False` respectivamente. En el cálculo de `firstCheck`, la segunda expresión no se evalúa porque la primera ya está `True`. Sin embargo, la segunda expresión se evalúa en el cálculo de `secondCheck`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra una instrucción `If`... `Then` que contiene dos llamadas a procedimiento. Si la primera llamada devuelve `True`, no se llama al segundo procedimiento. Esto podría producir resultados inesperados si el segundo procedimiento realiza tareas importantes que siempre deben realizarse cuando se ejecuta esta sección del código.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OR (operador)](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue (operador)](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
