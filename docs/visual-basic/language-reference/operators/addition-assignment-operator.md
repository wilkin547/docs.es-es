---
title: += (Operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 7fdf5cd422cf2a4081372bc14e74ed7463393520
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979858"
---
# <a name="-operator-visual-basic"></a>+= (Operador, Visual Basic)
Agrega el valor de una expresión numérica para el valor de una propiedad o variable numérica y asigna el resultado a la variable o propiedad. También puede utilizarse para concatenar un `String` expresión a un `String` variable o propiedad y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier numérico o `String` variable o propiedad.  
  
 `expression`  
 Obligatorio. Cualquier numérico o `String` expresión.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `+=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `+=` operador agrega el valor de su derecha a la variable o propiedad a su izquierda y asigna el resultado a la variable o propiedad a su izquierda. El `+=` operador puede usarse también para concatenar la `String` expresión en su derecho de la `String` variable o propiedad a su izquierda y asigna el resultado a la variable o propiedad a su izquierda.  
  
> [!NOTE]
>  Cuando se usa el `+=` operador, es posible que no podrá determinar si se producirá la suma o la cadena de la concatenación. Use el `&=` operador de concatenación para eliminar la ambigüedad y proporcionar código autoexplicativo.  
  
 Este operador de asignación realiza implícitamente, pero no las conversiones de restricción si el entorno de compilación exige la semántica estricta de ampliación. Para obtener más información sobre estas conversiones, vea [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Si se permite la semántica permisiva, el `+=` operador implícitamente realiza una serie de conversiones numéricas y de cadena idénticas a las realizadas por el `+` operador. Para obtener más información sobre estas conversiones, vea [operador +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `+` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecargar el `+` operador afecta al comportamiento de la `+=` operador. Si el código usa `+=` en una clase o estructura que sobrecarga `+`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otro. La primera parte usa `+=` con variables numéricas para agregar un valor a otro. La segunda parte usa `+=` con `String` variables para concatenar un valor con otro. En ambos casos, el resultado se asigna a la primera variable.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 El valor de `num1` ahora es 13 y el valor de `str1` es ahora "103".  
  
## <a name="see-also"></a>Vea también
- [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
