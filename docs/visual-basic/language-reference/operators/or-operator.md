---
title: "Or (Operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Or"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Or (operador)"
  - "operadores [Visual Basic], bit a bit"
  - "Or inclusivo (operador)"
  - "operadores bit a bit, OR (operador)"
  - "Or (palabra clave)"
  - "operadores [Visual Basic], inclusivos o"
  - "operadores [Visual Basic], disyunción"
  - "comparación bit a bit"
  - "disyunción lógica"
  - "operador de disyunción"
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Or (Operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Realiza una disyunción lógica en dos `Boolean` expresiones o una disyunción bit a bit en dos expresiones numéricas.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Cualquier `Boolean` o expresión numérica. Para `Boolean` comparación, `result` es la disyunción lógica inclusiva de dos `Boolean` valores. Para las operaciones bit a bit, `result` es un valor numérico que representa la disyunción inclusiva bit a bit de dos modelos de bits numéricos.  
  
 `expression1`  
 Requerido. Cualquier `Boolean` o expresión numérica.  
  
 `expression2`  
 Requerido. Cualquier `Boolean` o expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 Para `Boolean` comparación, `result` es `False` si y sólo si ambos `expression1` y `expression2` se evalúan como `False`. La siguiente tabla ilustra cómo `result` viene determinado.  
  
|Si `expression1` es|Y `expression2` es|El valor de `result` es|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  En un `Boolean` comparación, la `Or` operador evalúa siempre las dos expresiones, lo que podrían incluir realizar llamadas a procedimiento. El [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md) realiza *cortocircuitar*, lo que significa que si `expression1` es `True`, a continuación, `expression2` no se evalúa.  
  
 Para las operaciones bit a bit, el `Or` operador realiza una comparación bit a bit de bits colocados idénticamente en dos expresiones numéricas y establece el bit en correspondiente `result` según la tabla siguiente.  
  
|Si bit en `expression1` es|Y que el bit de `expression2` es|El bit de `result` es|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
>  Dado que los operadores lógicos y bit a bit tienen una prioridad inferior a otros operadores aritméticos y relacionales, las operaciones bit a bit deben incluirse entre paréntesis para garantizar una correcta ejecución.  
  
## <a name="data-types"></a>Tipos de datos  
 Si los operandos se componen de uno `Boolean` expresión y una expresión numérica, Visual Basic convierte el `Boolean` expresión a un valor numérico (– 1 para `True` y 0 para `False`) y realiza una operación bit a bit.  
  
 Para una `Boolean` comparación, el tipo de datos del resultado es `Boolean`. Para obtener una comparación bit a bit, el tipo de datos del resultado es un tipo numérico adecuado para los tipos de datos de `expression1` y `expression2`. Vea la tabla "relacionales y bit a bit comparaciones" de [tipos de datos de resultados de operador](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `Or` operador puede *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Or` operador para realizar una disyunción lógica inclusiva en dos expresiones. El resultado es un `Boolean` valor que representa si alguna de las dos expresiones es `True`.  
  
 [!code-vb[VbVbalrOperators#35](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `True`, `True`, y `False`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Or` operador para realizar la disyunción lógica inclusiva de los bits individuales de dos expresiones numéricas. El bit en el modelo resultante se establece si cualquiera de los bits correspondientes de los operandos se establece en 1.  
  
 [!code-vb[VbVbalrOperators#36](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/or-operator_2.vb)]  
  
 El ejemplo anterior genera unos resultados de 10, 14 y 14, respectivamente.  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Precedencia de operadores en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [OrElse (operador)](../../../visual-basic/language-reference/operators/orelse-operator.md)   
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)