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
ms.openlocfilehash: c2ce384901a9f0207e8279a5a07a88600c875e7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372212"
---
# <a name="-operator-visual-basic"></a>+= (Operador, Visual Basic)
Agrega el valor de una expresión numérica al valor de una variable o propiedad numérica y asigna el resultado a la variable o propiedad. También se puede utilizar para concatenar una `String` expresión a una `String` variable o propiedad y asignar el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>Partes  
 `variableorproperty`  
 Necesario. Cualquier valor numérico o `String` variable o propiedad.  
  
 `expression`  
 Necesario. Cualquier expresión numérica o numérica `String` .  
  
## <a name="remarks"></a>Observaciones  
 El elemento del lado izquierdo del `+=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `+=` operador agrega el valor situado a la derecha a la variable o propiedad de la izquierda, y asigna el resultado a la variable o propiedad de su izquierda. El `+=` operador también se puede usar para concatenar la `String` expresión de su derecha a la `String` variable o propiedad de su izquierda y asignar el resultado a la variable o propiedad de su izquierda.  
  
> [!NOTE]
> Al utilizar el `+=` operador, es posible que no pueda determinar si se producirá la concatenación de cadenas o la suma. Utilice el `&=` operador para la concatenación para eliminar la ambigüedad y proporcionar código autodocumentado.  
  
 Este operador de asignación realiza implícitamente conversiones de ampliación pero no de restricción si el entorno de compilación exige una semántica estricta. Para obtener más información sobre estas conversiones, vea [conversiones de restricción y ampliación](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md). Para obtener más información sobre la semántica estricta y permisiva, vea [Option Strict (instrucción](../statements/option-strict-statement.md)).  
  
 Si se permite la semántica permisiva, el `+=` operador realiza implícitamente una serie de conversiones numéricas y de cadena idénticas a las realizadas por el `+` operador. Para obtener más información sobre estas conversiones, vea [operador +](addition-operator.md).  
  
## <a name="overloading"></a>Sobrecarga  
 El `+` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `+` operador afecta al comportamiento del `+=` operador. Si el código utiliza `+=` en una clase o estructura que sobrecarga `+` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `+=` operador para combinar el valor de una variable con otra. La primera parte utiliza `+=` con variables numéricas para agregar un valor a otro. La segunda parte utiliza `+=` con `String` variables para concatenar un valor con otro. En ambos casos, el resultado se asigna a la primera variable.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 El valor de `num1` es ahora 13 y el valor de `str1` es ahora "103".  
  
## <a name="see-also"></a>Consulte también

- [+ (Operador)](addition-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Operadores de concatenación](concatenation-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
