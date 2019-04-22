---
title: And (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818623"
---
# <a name="and-operator-visual-basic"></a>And (Operador, Visual Basic)
Realiza una conjunción lógica de dos `Boolean` expresiones o una conjunción bit a bit de dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` o expresión numérica. Para la comparación booleana, `result` es la conjunción lógica de dos `Boolean` valores. Para las operaciones bit a bit, `result` es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.  
  
 `expression1`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
 `expression2`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 Para la comparación booleana, `result` es `True` si y solo si ambos `expression1` y `expression2` se evalúan como `True`. La tabla siguiente se muestra cómo `result` viene determinada.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En una comparación booleana, el `And` operador siempre evalúa ambas expresiones, lo que podrían incluir la realización de llamadas de procedimiento. El [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) realiza *cortocircuitar*, lo que significa que si `expression1` es `False`, a continuación, `expression2` no se evalúa.  
  
 Cuando se aplica a valores numéricos, el `And` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.  
  
|Si bit en `expression1` es|Y que el bit en `expression2` es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar resultados precisos.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para obtener una comparación booleana, el tipo de datos del resultado es `Boolean`. Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea la tabla "relacional y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
>  El `And` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `And` operador para realizar una conjunción lógica de dos expresiones. El resultado es un `Boolean` valor que indica si las dos expresiones son `True`.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 El ejemplo anterior genera los resultados de `True` y `False`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `And` operador para realizar la conjunción lógica de los bits individuales de dos expresiones numéricas. El bit en el modelo resultante se establece si los bits correspondientes de los operandos se establecen en 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 El ejemplo anterior genera los resultados de 8, 2 y 0, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
