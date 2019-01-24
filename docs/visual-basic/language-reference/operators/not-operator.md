---
title: Not (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: cd93316ada1fcf0997922f71a8efc5a3cf411d09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54614621"
---
# <a name="not-operator-visual-basic"></a>Not (Operador, Visual Basic)
Realiza una negación lógica en un `Boolean` expresión o una negación bit a bit en una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
 `expression`  
 Obligatorio. Cualquier `Boolean` o expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 Para `Boolean` expresiones, la tabla siguiente muestra cómo `result` viene determinada.  
  
|Si `expression` es|El valor de `result` es|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 Para expresiones numéricas, la `Not` operador invierte los valores de bits de cualquier expresión numérica y establece el bit en correspondiente `result` según la tabla siguiente.  
  
|Si bit en `expression` es|El bit de `result` es|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  Dado que los operadores lógicos y bit a bit tienen una prioridad menor que otros operadores relacionales y aritméticos, las operaciones bit a bit deben ir entre paréntesis para garantizar una correcta ejecución.  
  
## <a name="data-types"></a>Tipos de datos  
 En una negación booleana, el tipo de datos del resultado es `Boolean`. Para una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`. Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.  
  
## <a name="overloading"></a>Sobrecarga  
 El `Not` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica en un `Boolean` expresión. El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 El ejemplo anterior genera los resultados de `False` y `True`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Not` operador para realizar la negación lógica de los bits individuales de una expresión numérica. El bit en el modelo resultante se establece en el orden inverso del bit correspondiente en el modelo del operando, incluido el bit de signo.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 El ejemplo anterior genera los resultados de – 11, – 9 y – 7, respectivamente.  
  
## <a name="see-also"></a>Vea también
- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
