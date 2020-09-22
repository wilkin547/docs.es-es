---
title: /= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: d47a69e454305ce9417a46b5bbfbbb55a1ad1dc3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867072"
---
# <a name="-operator-visual-basic"></a>/= (Operador, Visual Basic)

Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Partes  

 `variableorproperty`  
 Obligatorio. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  

 El elemento del lado izquierdo del `/=` operador puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../modifiers/readonly.md).  
  
 El `/=` operador divide primero el valor de la variable o la propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador). A continuación, el operador asigna el resultado de punto flotante de esa operación a la variable o propiedad.  
  
 Esta instrucción asigna un `Double` valor a la variable o propiedad de la izquierda. Si `Option Strict` es `On` , `variableorproperty` debe ser un `Double` . Si `Option Strict` es `Off` , Visual Basic realiza una conversión implícita y asigna el valor resultante a `variableorproperty` , con un posible error en tiempo de ejecución. Para obtener más información, vea [conversiones de ampliación y restricción](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción](../statements/option-strict-statement.md)).  
  
## <a name="overloading"></a>Sobrecarga  

 El [operador/(Visual Basic)](floating-point-division-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del `/` operador afecta al comportamiento del `/=` operador. Si el código utiliza `/=` en una clase o estructura que sobrecarga `/` , asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `/=` operador para dividir una `Integer` variable por un segundo y asignar el cociente a la primera variable.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Consulte también

- [Operador/(Visual Basic)](floating-point-division-operator.md)
- [\\= (Operador)](integer-division-assignment-operator.md)
- [Operadores de asignación](assignment-operators.md)
- [Operadores aritméticos](arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Instrucciones](../../programming-guide/language-features/statements.md)
