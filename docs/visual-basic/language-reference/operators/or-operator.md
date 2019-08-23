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
ms.openlocfilehash: 1d11a6d009f6ecfea9fb1a86b00c67b87d5555dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955838"
---
# <a name="or-operator-visual-basic"></a>Or (Operador, Visual Basic)
Realiza una disyunción lógica entre dos `Boolean` expresiones o una disyunción bit a bit entre dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Cualquier `Boolean` expresión numérica o. Para `Boolean` la comparación `result` , es la disyunción lógica inclusiva de `Boolean` dos valores. Para las operaciones bit `result` a bit, es un valor numérico que representa la disyunción bit a bit inclusiva de dos modelos de bits numéricos.  
  
 `expression1`  
 Necesario. Cualquier `Boolean` expresión numérica o.  
  
 `expression2`  
 Necesario. Cualquier `Boolean` expresión numérica o.  
  
## <a name="remarks"></a>Comentarios  
 Para `Boolean` la comparación `result` , `False` es si y solo si `expression1` y `expression2` se evalúan como `False`. En la tabla siguiente se muestra `result` cómo se determina.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> En una `Boolean` comparación, el `Or` operador siempre evalúa ambas expresiones, lo que podría incluir la realización de llamadas a procedimientos. El [operador OrElse](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *un cortocircuito*, lo que significa que si `expression1` es `True`, `expression2` no se evalúa.  
  
 Para las operaciones bit a `Or` bit, el operador realiza una comparación bit a bit de los bits colocados de forma idéntica en `result` dos expresiones numéricas y establece el bit correspondiente en de acuerdo con la tabla siguiente.  
  
|Si el bit `expression1` de es|Y el bit `expression2` en es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos constan de una `Boolean` expresión y una expresión numérica, Visual Basic convierte la `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean`. En una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para `expression1` los `expression2`tipos de datos de y. Vea la tabla "comparaciones relacionales y bit a bit" en [tipos de datos de resultados de operadores](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `Or` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Or` usa el operador para realizar una disyunción lógica inclusiva entre dos expresiones. El resultado es un `Boolean` valor que indica si cualquiera de las dos expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 En el ejemplo anterior se generan `True`los `True`resultados de `False`, y, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se `Or` usa el operador para realizar una disyunción lógica inclusiva en los bits individuales de dos expresiones numéricas. El bit del modelo de resultado se establece si alguno de los bits correspondientes de los operandos se establece en 1.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 En el ejemplo anterior se generan resultados de 10, 14 y 14, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
