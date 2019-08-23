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
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913169"
---
# <a name="and-operator-visual-basic"></a>And (Operador, Visual Basic)
Realiza una conjunción lógica de `Boolean` dos expresiones o una conjunción bit a bit de dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Cualquier `Boolean` expresión numérica o. En la comparación booleana `result` , es la conjunción lógica `Boolean` de dos valores. Para las operaciones bit `result` a bit, es un valor numérico que representa la conjunción bit a bit de dos modelos de bits numéricos.  
  
 `expression1`  
 Necesario. Cualquier `Boolean` expresión numérica o.  
  
 `expression2`  
 Necesario. Cualquier `Boolean` expresión numérica o.  
  
## <a name="remarks"></a>Comentarios  
 En la comparación booleana `result` , `True` es `expression1` si y solo si y `expression2` se evalúan como `True`. En la tabla siguiente se muestra `result` cómo se determina.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> En una comparación booleana, el `And` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos. El [operador AndAlso](../../../visual-basic/language-reference/operators/andalso-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `False`, `expression2` no se evalúa.  
  
 Cuando se aplica a valores numéricos `And` , el operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos `result` expresiones numéricas y establece el bit correspondiente en de acuerdo con la tabla siguiente.  
  
|Si el bit `expression1` de es|Y el bit `expression2` en es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar resultados precisos.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 En el caso de una comparación booleana, el tipo de datos `Boolean`del resultado es. En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para `expression1` los `expression2`tipos de datos de y. Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
> [!NOTE]
> El `And` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `And` usa el operador para realizar una conjunción lógica entre dos expresiones. El resultado es un `Boolean` valor que representa si ambas expresiones son. `True`  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 En el ejemplo anterior se generan `True` los `False`resultados de y, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `And` usa el operador para realizar una conjunción lógica de los bits individuales de dos expresiones numéricas. El bit en el patrón del resultado se establece si los bits correspondientes de los operandos están establecidos en 1.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 En el ejemplo anterior se generan los resultados de 8, 2 y 0, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso (operador)](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
