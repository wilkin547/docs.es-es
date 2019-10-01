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
ms.openlocfilehash: 5ebc5f9dbf674a9a6560bd96b3e8c9edcae08a81
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701075"
---
# <a name="not-operator-visual-basic"></a>Not (Operador, Visual Basic)
Realiza una negación lógica de una expresión @no__t 0 o una negación bit a bit en una expresión numérica.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = Not expression  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier `Boolean` expresión numérica o.  
  
 `expression`  
 Obligatorio. Cualquier `Boolean` expresión numérica o.  
  
## <a name="remarks"></a>Comentarios  
 En el caso de las expresiones `Boolean`, en la tabla siguiente se muestra cómo se determina `result`.  
  
|Si `expression` es|El valor de `result` es|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 En el caso de las expresiones numéricas, el operador `Not` invierte los valores de bit de cualquier expresión numérica y establece el bit correspondiente en `result` de acuerdo con la tabla siguiente.  
  
|Si el bit de `expression` es|El bit en `result` es|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
> Puesto que los operadores lógicos y bit a bit tienen una prioridad más baja que otros operadores aritméticos y relacionales, las operaciones bit a bit deben ir entre paréntesis para garantizar una ejecución precisa.  
  
## <a name="data-types"></a>Tipos de datos  
 En el caso de una negación booleana, el tipo de datos del resultado es `Boolean`. En el caso de una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`. Sin embargo, si Expression es `Decimal`, el resultado es `Long`.  
  
## <a name="overloading"></a>Sobrecarga  
 El operador `Not` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `Not` para realizar la negación lógica de una expresión `Boolean`. El resultado es un valor `Boolean` que representa el inverso del valor de la expresión.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 En el ejemplo anterior se generan los resultados de `False` y `True`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `Not` para realizar la negación lógica de los bits individuales de una expresión numérica. El bit en el patrón del resultado se establece en la inversa del bit correspondiente en el patrón de operando, incluido el bit de signo.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 En el ejemplo anterior se generan los resultados de – 11, – 9 y – 7, respectivamente.  
  
## <a name="see-also"></a>Vea también

- [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
