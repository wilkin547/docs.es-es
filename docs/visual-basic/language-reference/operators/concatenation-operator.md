---
title: '&amp; (Operador) (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: 28d8cdb22974d77edf055ab9b2c6c767872e6783
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604307"
---
# <a name="amp-operator-visual-basic"></a>&amp; (Operador) (Visual Basic)
Genera una concatenación de cadena de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Cualquier `String` o `Object` variable.  
  
 `expression1`  
 Requerido. Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
 `expression2`  
 Requerido. Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo de datos de `expression1` o `expression2` no `String` , pero se amplía a `String`, se convierte en `String`. Si cualquiera de los tipos de datos no se amplía a `String`, el compilador genera un error.  
  
 Tipo de datos de `result` es `String`. Si una o ambas expresiones se evalúan como [nada](../../../visual-basic/language-reference/nothing.md) o tener un valor de <xref:System.DBNull.Value?displayProperty=nameWithType>, se tratan como una cadena con un valor de "".  
  
> [!NOTE]
>  El `&` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
>  El carácter "y" comercial (&) también pueden utilizarse para identificar las variables como tipo `Long`. Para obtener más información, consulte [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `&` operador para forzar la concatenación de cadenas. El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.  
  
 [!code-vb[VbVbalrOperators#2](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/concatenation-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Operador &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)  
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Operadores de concatenación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
