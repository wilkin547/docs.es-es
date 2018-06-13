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
ms.openlocfilehash: f12a0560d984f871110c02f1df2c2ec42b68809b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604021"
---
# <a name="-operator-visual-basic"></a>+= (Operador, Visual Basic)
Agrega el valor de una expresión numérica para el valor de una propiedad o variable numérica y asigna el resultado a la variable o propiedad. También puede utilizarse para concatenar un `String` expresión a un `String` variable o propiedad y asignar el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Requerido. Cualquier numérico o `String` variable o propiedad.  
  
 `expression`  
 Requerido. Cualquier numérico o `String` expresión.  
  
## <a name="remarks"></a>Comentarios  
 El elemento en el lado izquierdo de la `+=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o propiedad no puede ser [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El `+=` operador agrega el valor de su derecha a la variable o propiedad de su izquierda y asigna el resultado a la variable o propiedad de su izquierda. El `+=` operador también puede utilizarse para concatenar la `String` expresión en su derecho a la `String` variable o propiedad de su izquierda y asignar el resultado a la variable o propiedad de su izquierda.  
  
> [!NOTE]
>  Cuando se usa el `+=` (operador), es posible que no pueda determinar si se producirá la suma o la cadena de la concatenación. Use la `&=` operador de concatenación para eliminar la ambigüedad y proporcionar código autoexplicativo.  
  
 Este operador de asignación realiza implícitamente pero no las conversiones de restricción si el entorno de compilación exige la semántica estricta de ampliación. Para obtener más información sobre estas conversiones, vea [conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
 Si se permite una semántica permisiva, el `+=` operador implícitamente realiza una serie de cadenas o conversiones numéricas idénticas a las realizadas por el `+` operador. Para obtener más información sobre estas conversiones, vea [+ (operador)](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `+` puede ser *sobrecargados*, lo que significa que una clase o estructura puede definir de nuevo su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Sobrecarga de la `+` operador afecta al comportamiento de la `+=` operador. Si el código usa `+=` en una clase o estructura que sobrecarga `+`, asegúrese de conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otro. La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro. La segunda parte utiliza `+=` con `String` variables para concatenar un valor con otro. En ambos casos, el resultado se asigna a la primera variable.  
  
 [!code-vb[VbVbalrOperators#7](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_1.vb)]  
  
 [!code-vb[VbVbalrOperators#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addition-assignment-operator_2.vb)]  
  
 El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".  
  
## <a name="see-also"></a>Vea también  
 [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)  
 [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)  
 [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
