---
title: '&amp;Operador (Visual Basic)'
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
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968351"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operador (Visual Basic)
Genera una concatenación de cadenas de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Necesario. Cualquier `String` variable `Object` o.  
  
 `expression1`  
 Necesario. Cualquier expresión con un tipo de datos que se amplíe `String`a.  
  
 `expression2`  
 Necesario. Cualquier expresión con un tipo de datos que se amplíe `String`a.  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo de datos `expression1` de `expression2` o no `String` es pero se amplía `String`a, se convierte en `String`. Si uno de los tipos de datos no se amplía `String`a, el compilador genera un error.  
  
 El tipo de datos `result` de `String`es. Si una o ambas expresiones se evalúan como [Nothing](../../../visual-basic/language-reference/nothing.md) o tienen un <xref:System.DBNull.Value?displayProperty=nameWithType>valor de, se tratan como una cadena con un valor de "".  
  
> [!NOTE]
> El `&` operador se puedesobrecargar, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> El carácter de y comercial (&) también se puede usar para identificar variables `Long`como tipo. Para obtener más información, vea [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se `&` usa el operador para forzar la concatenación de cadenas. El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Operador &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores de concatenación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
