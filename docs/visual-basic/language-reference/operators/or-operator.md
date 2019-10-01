---
title: Or (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 03decb4ad32e8ff2c03e3b64a272bce779282973
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701232"
---
# <a name="or-operator-visual-basic"></a>Or (Operador, Visual Basic)
Realiza una disyunción lógica entre dos expresiones `Boolean` o una disyunción bit a bit entre dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` expresión numérica o. Para la comparación de `Boolean`, `result` es la disyunción lógica inclusiva de dos valores @no__t 2. Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción bit a bit inclusiva de dos modelos de bits numéricos.  
  
 `expression1`  
 Obligatorio. Cualquier `Boolean` expresión numérica o.  
  
 `expression2`  
 Obligatorio. Cualquier `Boolean` expresión numérica o.  
  
## <a name="remarks"></a>Comentarios  
 Para la comparación de `Boolean`, `result` es `False` si y solo si ambos `expression1` y `expression2` se evalúan como `False`. En la tabla siguiente se muestra cómo se determina `result`.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> En una comparación `Boolean`, el operador `Or` siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos. El [operador OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `True`, no se evalúa `expression2`.  
  
 Para las operaciones bit a bit, el operador `Or` realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit correspondiente en `result` según la tabla siguiente.  
  
|Si el bit de `expression1` es|Y bit en `expression2` es|El bit en `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos constan de una expresión `Boolean` y una expresión numérica, Visual Basic convierte la expresión `Boolean` a un valor numérico (-1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para una comparación `Boolean`, el tipo de datos del resultado es `Boolean`. En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El operador `Or` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `Or` para realizar una disyunción lógica inclusiva entre dos expresiones. El resultado es un valor `Boolean` que indica si cualquiera de las dos expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 En el ejemplo anterior se generan los resultados de `True`, `True` y `False`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `Or` para realizar una disyunción lógica inclusiva en los bits individuales de dos expresiones numéricas. El bit del modelo de resultado se establece si alguno de los bits correspondientes de los operandos se establece en 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 En el ejemplo anterior se generan resultados de 10, 14 y 14, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
