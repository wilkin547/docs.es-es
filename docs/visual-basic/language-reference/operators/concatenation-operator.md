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
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592242"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operador (Visual Basic)
Genera una concatenación de cadenas de dos expresiones.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier variable `String` o `Object`.  
  
 `expression1`  
 Obligatorio. Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
 `expression2`  
 Obligatorio. Cualquier expresión con un tipo de datos que se amplíe a `String`.  
  
## <a name="remarks"></a>Comentarios  
 Si el tipo de datos de `expression1` o `expression2` no es `String` pero se amplía a `String`, se convierte en `String`. Si alguno de los tipos de datos no se amplía a `String`, el compilador genera un error.  
  
 El tipo de datos de `result` es `String`. Si una o ambas expresiones se evalúan como [Nothing](../../../visual-basic/language-reference/nothing.md) o tienen un valor de <xref:System.DBNull.Value?displayProperty=nameWithType>, se tratan como una cadena con un valor de "".  
  
> [!NOTE]
> El operador `&` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> El carácter de y comercial (&) también se puede usar para identificar variables como tipo `Long`. Para obtener más información, vea [caracteres de tipo](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el operador `&` para forzar la concatenación de cadenas. El resultado es un valor de cadena que representa la concatenación de los dos operandos de cadena.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Operador &=](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operadores de concatenación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
