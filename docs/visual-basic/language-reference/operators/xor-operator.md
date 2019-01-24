---
title: Xor (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Xor
helpviewer_keywords:
- exclusive OR operator [Visual Basic]
- logical exclusion
- operators [Visual Basic], exclusive or
- exclusion operator [Visual Basic]
- operators [Visual Basic], bitwise
- bitwise operators [Visual Basic], XOR operator
- Xor operator [Visual Basic]
- Xor keyword [Visual Basic]
- bitwise comparison [Visual Basic]
ms.assetid: 036000a9-3934-4e7f-a9d0-a816de3d84a6
ms.openlocfilehash: af6589206232f01b572cd2b965ba1a0f36d462e1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527125"
---
# <a name="xor-operator-visual-basic"></a>Xor (Operador, Visual Basic)
Realiza una exclusión lógica en dos `Boolean` expresiones o una exclusión bit a bit en dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 Xor expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` o variable numérica. Para la comparación booleana, `result` es la exclusión lógica (disyunción lógica exclusiva) de dos `Boolean` valores. Para las operaciones bit a bit, `result` es un valor numérico que representa la exclusión bit a bit (disyunción bit a bit exclusiva) de dos modelos de bits numéricos.  
  
 `expression1`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
 `expression2`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 Para la comparación booleana, `result` es `True` si y solo si exactamente uno de `expression1` y `expression2` se evalúa como `True`. Es decir, si y solo si `expression1` y `expression2` evaluar opuesto a `Boolean` valores. La tabla siguiente se muestra cómo `result` viene determinada.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`False`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En una comparación booleana, el `Xor` operador siempre evalúa ambas expresiones, lo que podrían incluir la realización de llamadas de procedimiento. No hay ningún homólogo de cortocircuito para `Xor`, ya que el resultado depende siempre de ambos operandos. Para *cortocircuitar* operadores lógicos, vea [AndAlso Operator](../../../visual-basic/language-reference/operators/andalso-operator.md) y [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md).  
  
 Para las operaciones bit a bit, el `Xor` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.  
  
|Si bit en `expression1` es|Y que el bit en `expression2` es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|0|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.  
  
 Por ejemplo, 5 `Xor` 3 es 6. Para ver por qué esto es así, convierta 5 y 3 en sus representaciones binarias, 101 y 011. A continuación, utilice la tabla anterior para determinar que 101 Xor 011 es 110, que es la representación binaria del número decimal 6.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para un `Boolean` comparación, el tipo de datos del resultado es `Boolean`. Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea la tabla "relacional y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `Xor` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) de dos expresiones. El resultado es un `Boolean` valor que indica si exactamente uno de las expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#40](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `False`, `True`, y `False`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Xor` operador para realizar una exclusión lógica (disyunción lógica exclusiva) en los bits individuales de dos expresiones numéricas. El bit en el modelo resultante se establece si exactamente uno de los bits correspondientes de los operandos se establece en 1.  
  
 [!code-vb[VbVbalrOperators#41](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xor-operator_2.vb)]  
  
 El ejemplo anterior genera unos resultados de 2, 12 y 14, respectivamente.  
  
## <a name="see-also"></a>Vea también
- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
