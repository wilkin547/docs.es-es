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
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331033"
---
# <a name="-operator-visual-basic"></a>/= (Operador, Visual Basic)
Divide el valor de una variable o propiedad por el valor de una expresión y asigna el resultado de punto flotante a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento del lado izquierdo del operador `/=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador `/=` divide primero el valor de la variable o propiedad (en el lado izquierdo del operador) por el valor de la expresión (en el lado derecho del operador). A continuación, el operador asigna el resultado de punto flotante de esa operación a la variable o propiedad.  
  
 Esta instrucción asigna un valor `Double` a la variable o propiedad de la izquierda. Si `Option Strict` es `On`, `variableorproperty` debe ser `Double`. Si `Option Strict` es `Off`, Visual Basic realiza una conversión implícita y asigna el valor resultante a `variableorproperty`, con un posible error en tiempo de ejecución. Para obtener más información, vea [conversiones de ampliación y restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) y [Option Strict (instrucción](../../../visual-basic/language-reference/statements/option-strict-statement.md)).  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del operador `/` afecta al comportamiento del operador `/=`. Si el código usa `/=` en una clase o estructura que sobrecarga `/`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `/=` para dividir una variable `Integer` por un segundo y asignar el cociente a la primera variable.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vea también

- [Operador/(Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\= (operador)](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
