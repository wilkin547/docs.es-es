---
title: Combinación eficaz de operadores
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 9ba6be8e1dd03c0589f712b0e9b39258953cd223
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077090"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>Combinación eficaz de operadores (Visual Basic)

Las expresiones complejas pueden contener muchos operadores diferentes. Esto se ilustra en el siguiente ejemplo:  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 La creación de expresiones complejas, como la del ejemplo anterior, requiere un conocimiento exhaustivo de las reglas de prioridad de los operadores. Para obtener más información, vea [precedencia de operadores en Visual Basic](../../../language-reference/operators/operator-precedence.md).  
  
## <a name="parenthetical-expressions"></a>Expresiones entre paréntesis  

 A menudo, desea que las operaciones continúen en un orden diferente al determinado por la prioridad de los operadores. Considere el ejemplo siguiente.  
  
 `x = z * y + 4`  
  
 En el ejemplo anterior `z` se multiplica por `y` y, a continuación, se agrega el resultado a `4` . Pero si desea agregar `y` y antes de `4` multiplicar el resultado por `z` , puede invalidar la prioridad de operador normal mediante el uso de paréntesis. Al incluir una expresión entre paréntesis, se fuerza la evaluación de esa expresión en primer lugar, independientemente de la precedencia de los operadores. Para forzar que el ejemplo anterior realice la suma en primer lugar, puede volver a escribirlo como en el ejemplo siguiente.  
  
 `x = z * (y + 4)`  
  
 En el ejemplo anterior se agrega `y` y y `4` , a continuación, se multiplica esa suma por `z` .  
  
### <a name="nested-parenthetical-expressions"></a>Expresiones entre paréntesis anidadas  

 Puede anidar Expresiones en varios niveles de paréntesis para invalidar la prioridad aún más. Primero se evalúan las expresiones que se anidan más profundamente entre paréntesis, seguidas por la siguiente más anidada y así sucesivamente hasta el menos anidado y, por último, las expresiones fuera de los paréntesis. Esto se ilustra en el siguiente ejemplo:  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 En el ejemplo anterior, `z + 2` se evalúa primero y después las demás expresiones entre paréntesis. La exponenciación, que normalmente tiene mayor precedencia que la suma o la multiplicación, se evalúa en último lugar en este ejemplo, ya que las otras expresiones se incluyen entre paréntesis.  
  
## <a name="see-also"></a>Vea también

- [Operadores aritméticos en Visual Basic](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Operadores lógicos y bit a bit en Visual Basic](logical-and-bitwise-operators.md)
- [Operadores lógicos y bit a bit (Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [Expresiones booleanas](boolean-expressions.md)
- [Comparaciones de valores](value-comparisons.md)
- [Procedimiento para calcular valores numéricos](how-to-calculate-numeric-values.md)
- [Prioridad de operador en Visual Basic](../../../language-reference/operators/operator-precedence.md)
