---
title: ^= (Operador)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331292"
---
# <a name="-operator-visual-basic"></a>^= (Operador, Visual Basic)
Eleva el valor de una variable o propiedad a la potencia de una expresión y asigna el resultado a la variable o propiedad.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a>Elementos  
 `variableorproperty`  
 Obligatorio. Cualquier variable o propiedad numérica.  
  
 `expression`  
 Obligatorio. Cualquier expresión numérica.  
  
## <a name="remarks"></a>Comentarios  
 El elemento del lado izquierdo del operador `^=` puede ser una variable escalar simple, una propiedad o un elemento de una matriz. La variable o la propiedad no pueden ser de [solo lectura](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 El operador `^=` primero genera el valor de la variable o la propiedad (en el lado izquierdo del operador) con la potencia del valor de la expresión (en el lado derecho del operador). A continuación, el operador asigna el resultado de la operación a la variable o propiedad.  
  
 Visual Basic siempre realiza la exponenciación en el [tipo de datos Double](../../../visual-basic/language-reference/data-types/double-data-type.md). Los operandos de cualquier tipo diferente se convierten en `Double`y el resultado siempre es `Double`.  
  
 El valor de `expression` puede ser fraccionario, negativo o ambos.  
  
## <a name="overloading"></a>Sobrecarga  
 El [operador ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md) se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. La sobrecarga del operador `^` afecta al comportamiento del operador `^=`. Si el código usa `^=` en una clase o estructura que sobrecarga `^`, asegúrese de que entiende su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `^=` para elevar el valor de una variable `Integer` a la potencia de una segunda variable y asignar el resultado a la primera variable.  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vea también

- [Operador ^](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [Operadores de asignación](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Operadores aritméticos](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)
