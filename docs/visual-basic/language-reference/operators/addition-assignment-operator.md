---
title: += (Operador)
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
ms.openlocfilehash: 31a6da163061b905b8ffddcfc4b44978f5cdd55e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350307"
---
# <a name="-operator-visual-basic"></a>+= (Operador, Visual Basic)
Agrega el valor de una expresión numérica al valor de una variable o propiedad numérica y asigna el resultado a la variable o propiedad. También se puede utilizar para concatenar una expresión `String` a una variable o propiedad `String` y asignar el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier variable o propiedad numérica o `String`.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica o de `String`.  
  
## <a name="remarks"></a>Comentarios  
 El elemento del lado izquierdo del operador `+=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador `+=` agrega el valor de su derecha a la variable o propiedad de su izquierda, y asigna el resultado a la variable o propiedad de su izquierda. También se puede usar el operador `+=` para concatenar la expresión de `String` de su derecha a la variable o propiedad de `String` de la izquierda, y asignar el resultado a la variable o propiedad de su izquierda.  
  
> [!NOTE]
> Al utilizar el operador `+=`, es posible que no pueda determinar si se producirá la concatenación de cadenas o de suma. Use el operador `&=` para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.  
  
 Este operador de asignación realiza implícitamente conversiones de ampliación pero no de restricción si el entorno de compilación exige una semántica estricta. Para obtener más información sobre estas conversiones, vea [conversiones de restricción y ampliación](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).  
  
 Si se permiten las semánticas permisivas, el operador `+=` realiza implícitamente una serie de conversiones numéricas y de cadena idénticas a las realizadas por el operador `+`. Para obtener más información sobre estas conversiones, vea [operador +](../../../visual-basic/language-reference/operators/addition-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El operador de `+` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del operador `+` afecta al comportamiento del operador `+=`. Si el código usa `+=` en una clase o estructura que sobrecarga `+`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `+=` para combinar el valor de una variable con otra. La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro. La segunda parte utiliza `+=` con variables de `String` para concatenar un valor con otro. En ambos casos, el resultado se asigna a la primera variable.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".  
  
## <a name="see-also"></a>Vea también

- [Operador +](../../../visual-basic/language-reference/operators/addition-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operadores de concatenación](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
