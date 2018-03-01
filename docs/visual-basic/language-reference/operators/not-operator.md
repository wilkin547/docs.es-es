---
title: Not (Operador, Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ac160aef7b7dc8acb8bf0211b403599692f2373c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="not-operator-visual-basic"></a>Not (Operador, Visual Basic)
Realiza una negación lógica en una `Boolean` expresión o una negación bit a bit en una expresión numérica.  
  
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
 Para `Boolean` expresiones, la tabla siguiente muestra cómo `result` viene determinado.  
  
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
>  Dado que los operadores lógicos y bit a bit tienen una prioridad inferior a otros operadores aritméticos y relacionales, las operaciones bit a bit deben incluirse entre paréntesis para garantizar una correcta ejecución.  
  
## <a name="data-types"></a>Tipos de datos  
 En una negación booleana, el tipo de datos del resultado es `Boolean`. Para una negación bit a bit, el tipo de datos del resultado es el mismo que el de `expression`. Sin embargo, si la expresión es `Decimal`, el resultado es `Long`.  
  
## <a name="overloading"></a>Sobrecarga  
 El `Not` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando su operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Not` operador que se va a realizar la negación lógica en una `Boolean` expresión. El resultado es un `Boolean` valor que representa el inverso del valor de la expresión.  
  
 [!code-vb[VbVbalrOperators#33](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_1.vb)]  
  
 El ejemplo anterior genera unos resultados de `False` y `True`, respectivamente.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `Not` operador que se va a realizar la negación lógica de los bits individuales de una expresión numérica. El bit en el modelo resultante se establece en el orden inverso del bit correspondiente en el modelo del operando, incluido el bit de signo.  
  
 [!code-vb[VbVbalrOperators#34](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/not-operator_2.vb)]  
  
 En el ejemplo anterior se genera los resultados de – 11, – 9 y – 7, respectivamente.  
  
## <a name="see-also"></a>Vea también  
 [Operadores lógicos y bit a bit (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores lógicos y bit a bit en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
