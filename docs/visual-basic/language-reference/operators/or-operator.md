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
ms.openlocfilehash: 0277b6f24e62ed5f0cad3dae225c86fffc4c09b9
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58835302"
---
# <a name="or-operator-visual-basic"></a>Or (Operador, Visual Basic)
Realiza una disyunción lógica en dos `Boolean` expresiones o una disyunción bit a bit de dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` o expresión numérica. Para `Boolean` comparación, `result` es la disyunción lógica inclusiva de dos `Boolean` valores. Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción inclusiva bit a bit de dos patrones de bits numéricos.  
  
 `expression1`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
 `expression2`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 Para `Boolean` comparación, `result` es `False` si y solo si ambos `expression1` y `expression2` se evalúan como `False`. La tabla siguiente se muestra cómo `result` viene determinada.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En un `Boolean` comparación, el `Or` operador siempre evalúa ambas expresiones, lo que podrían incluir la realización de llamadas de procedimiento. El [OrElse Operator](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *evaluación "cortocircuitada"*, lo que significa que si `expression1` es `True`, a continuación, `expression2` no se evalúa.  
  
 Para las operaciones bit a bit, el `Or` operador realiza una comparación bit a bit de los bits colocados de forma idéntica en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.  
  
|Si bit en `expression1` es|Y que el bit en `expression2` es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión en un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para un `Boolean` comparación, el tipo de datos del resultado es `Boolean`. Para obtener una comparación bit a bit, el tipo de datos de resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea la tabla "relacional y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `Or` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva en dos expresiones. El resultado es un `Boolean` valor que representa si alguna de las dos expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 El ejemplo anterior genera los resultados de `True`, `True`, y `False`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva de los bits individuales de dos expresiones numéricas. El bit en el modelo resultante se establece si cualquiera de los bits correspondientes de los operandos se establece en 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 El ejemplo anterior genera los resultados de 10, 14 y 14, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
