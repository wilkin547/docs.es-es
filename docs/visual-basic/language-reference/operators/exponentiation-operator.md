---
title: ^ (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponention
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 426c3e9913dadda1091f4ba53c66c6b65e40e768
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604450"
---
# <a name="-operator-visual-basic"></a>^ (Operador, Visual Basic)
Eleva un número a la potencia de otro número.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
number ^ exponent  
```  
  
## <a name="parts"></a>Elementos  
 `number`  
 Requerido. Cualquier expresión numérica.  
  
 `exponent`  
 Requerido. Cualquier expresión numérica.  
  
## <a name="result"></a>Resultado  
 El resultado es `number` elevado a la potencia de `exponent`, siempre como un `Double` valor.  
  
## <a name="supported-types"></a>Tipos admitidos  
 `Double`. Operandos de cualquier tipo diferente se convierten en `Double`.  
  
## <a name="remarks"></a>Comentarios  
 Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md).  
  
 El valor de `exponent` puede ser fraccionario, negativo o ambos.  
  
 Cuando se realiza más de una exponenciación en una única expresión, el `^` operador se evalúa tal y como se encuentra de izquierda a derecha.  
  
> [!NOTE]
>  El `^` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `^` operador para elevar un número a la potencia de un exponente. El resultado es el primer operando elevado a la potencia del segundo.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/exponentiation-operator_1.vb)]  
  
 El ejemplo anterior produce los siguientes resultados:  
  
 `exp1` se establece en 4 (2 al cuadrado).  
  
 `exp2` se establece en 19683 (3 al cubo; a continuación, ese valor al cubo).  
  
 `exp3` se establece en -125 (-5 al cubo).  
  
 `exp4` se establece en 625 (-5 a la cuarta potencia).  
  
 `exp5` se establece en 2 (raíz cúbica de 8).  
  
 `exp6` se establece en 0,5 (1,0 dividido por la raíz cúbica de 8).  
  
 Tenga en cuenta la importancia de los paréntesis en las expresiones en el ejemplo anterior. Debido *prioridad de operador*, Visual Basic realiza normalmente la `^` operador antes de los demás, incluso el operador unario `–` operador. Si `exp4` y `exp6` se hubieran calculado sin paréntesis, habrían generado los resultados siguientes:  
  
 `exp4 = -5 ^ 4` se calcula como: (5 a la cuarta potencia), lo que podría dar lugar a-625.  
  
 `exp6 = 8 ^ -1.0 / 3.0` se calcularía como (de 8 a la potencia de – 1 o 0,125) dividido entre 3,0, cuyo resultado sería 0,041666666666666666666666666666667.  
  
## <a name="see-also"></a>Vea también  
 [Operador ^=](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores aritméticos en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
